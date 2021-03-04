---
title: Experimentações do Azure Machine Learning
description: Utilize modelos baseados em Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267920"
---
# <a name="use-azure-machine-learning-based-models"></a>Utilize modelos baseados em Azure Machine Learning

Os dados unificados em Dynamics 365 Customer Insights são uma origem para a construção de modelos de aprendizagem automática que podem gerar conhecimentos empresariais adicionais. A Customer Insights integra-se com Machine Learning Studio (clássico) e a Azure Machine Learning para utilizar os seus próprios modelos personalizados. Consulte [experiências Machine Learning Studio (clássicas)](machine-learning-studio-experiments.md) como exemplos de experiências construídas sobre Machine Learning Studio (clássico). 

## <a name="prerequisites"></a>Pré-requisitos

- Aceda ao Customer Insights
- Subscrição do Azure Enterprise ativa
- [Perfis de cliente unificados](data-unification.md)
- [Exportação de entidade para Armazenamento de Blobs do Azure](export-azure-blob-storage.md) configurado

## <a name="set-up-azure-machine-learning-workspace"></a>Configurar a área de trabalho do Azure Machine Learning

1. Consulte [criar uma área de Trabalho do Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) para opções diferentes para criar a área de trabalho. Para melhor desempenho, crie a área de trabalho numa região do Azure que esteja geograficamente mais próxima do ambiente de Customer Insights.

1. Aceda à sua área de trabalho através do [Azure Machine Learning Studio](https://ml.azure.com/). Existem várias [formas de interagir](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) com a sua área de trabalho.

## <a name="work-with-azure-machine-learning-designer"></a>Trabalhar com o designer do Azure Machine Learning

O designer do Azure Machine Learning fornece uma tela visual onde pode arrastar e largar conjuntos de dados e módulos, semelhantes a Machine Learning Studio (clássico). Um pipeline de lote criado a partir do designer pode ser integrado no Customer Insights se estiverem configurados em conformidade. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Trabalhar com o SDK do Azure Machine Learning

Cientistas de dados e programadores de IA usam o [SDK do Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) para construir fluxos de trabalho de aprendizagem automática. Atualmente, os modelos treinados usando o SDK não podem ser integrados diretamente com o Customer Insights. É necessário um pipeline de inferência de lote que esse modelo consome para a integração com a Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Requisitos de pipeline de lote para integrar com a Customer Insights

### <a name="dataset-configuration"></a>Configuração do conjunto de dados

É necessário criar conjuntos de dados para utilizar os dados da entidade a partir da Customer Insights até ao seu pipeline de inferência de lote. Estes conjuntos de dados precisam de ser registados na área de trabalho. Atualmente, apenas suportamos [conjuntos de dados tabulares](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) no formato .csv. Os conjuntos de dados que correspondem aos dados da entidade devem ser parametrizados como parâmetro de pipeline.
   
* Parâmetros do conjunto de dados no Designer
   
     No designer, abra **Selecionar colunas no conjunto de dados** e selecione **Definir como parâmetro de pipeline** onde fornece um nome para o parâmetro.

     > [!div class="mx-imgBorder"]
     > ![Parametrização do conjunto de dados no designer](media/intelligence-designer-dataset-parameters.png "Parametrização do conjunto de dados no designer")
   
* Parâmetro do conjunto de dados no SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Pipeline de inferência de lote
  
* No designer, um pipeline de formação pode ser usado para criar ou atualizar um pipeline de inferência. Atualmente, apenas são suportados os pipelines de inferência de lote.

* Utilizando o SDK, pode publicar o pipeline para um ponto final. Atualmente, a Customer Insights integra-se com o pipeline padrão num ponto final do pipeline de lote na área de trabalho de aprendizagem automática.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importar dados do pipeline para Customer Insights

* O designer fornece o [módulo de Dados de Exportação](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) que permite a saída de um pipeline para exportação para o armazenamento do Azure. Atualmente, o módulo deve utilizar o tipo de datastore **Armazenamento de Blobs do Azure** e parametrizar a **Datastore** e o **Caminho** relativo. A Customer Insights substitui estes dois parâmetros durante a execução do pipeline com uma datastore e um caminho acessível ao produto.
   > [!div class="mx-imgBorder"]
   > ![Exportar configuração do módulo de dados](media/intelligence-designer-importdata.png "Exportar configuração do módulo de dados")
   
* Ao escrever a saída de inferência utilizando o código, pode enviar a saída para um caminho dentro de uma *datastore registada* na área de trabalho. Se o caminho e a datastore forem parametrizados no pipeline, a Customer insights poderá ler e importar a saída de inferência. Atualmente, só é suportada uma única saída tabular em formato CSV. O caminho deve incluir o diretório e o nome de ficheiro.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
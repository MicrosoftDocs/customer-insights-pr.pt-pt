---
title: Experimentações do Azure Machine Learning
description: Utilize modelos baseados em Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668783"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="27397-103">Utilize modelos baseados em Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="27397-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="27397-104">Os dados unificados em Dynamics 365 Customer Insights são uma origem para a construção de modelos de aprendizagem automática que podem gerar conhecimentos empresariais adicionais.</span><span class="sxs-lookup"><span data-stu-id="27397-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="27397-105">A Customer Insights integra-se com Machine Learning Studio (clássico) e a Azure Machine Learning para utilizar os seus próprios modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="27397-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="27397-106">Consulte [experiências Machine Learning Studio (clássicas)](machine-learning-studio-experiments.md) como exemplos de experiências construídas sobre Machine Learning Studio (clássico).</span><span class="sxs-lookup"><span data-stu-id="27397-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="27397-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="27397-107">Prerequisites</span></span>

- <span data-ttu-id="27397-108">Aceda ao Customer Insights</span><span class="sxs-lookup"><span data-stu-id="27397-108">Access to Customer Insights</span></span>
- <span data-ttu-id="27397-109">Subscrição do Azure Enterprise ativa</span><span class="sxs-lookup"><span data-stu-id="27397-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="27397-110">Perfis de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="27397-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="27397-111">[Exportação de entidade para Armazenamento de Blobs do Azure](export-azure-blob-storage.md) configurado</span><span class="sxs-lookup"><span data-stu-id="27397-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="27397-112">Configurar a área de trabalho do Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="27397-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="27397-113">Consulte [criar uma área de Trabalho do Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) para opções diferentes para criar a área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="27397-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="27397-114">Para melhor desempenho, crie a área de trabalho numa região do Azure que esteja geograficamente mais próxima do ambiente de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="27397-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="27397-115">Aceda à sua área de trabalho através do [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="27397-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="27397-116">Existem várias [formas de interagir](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) com a sua área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="27397-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="27397-117">Trabalhar com o designer do Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="27397-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="27397-118">O designer do Azure Machine Learning fornece uma tela visual onde pode arrastar e largar conjuntos de dados e módulos, semelhantes a Machine Learning Studio (clássico).</span><span class="sxs-lookup"><span data-stu-id="27397-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="27397-119">Um pipeline de lote criado a partir do designer pode ser integrado no Customer Insights se estiverem configurados em conformidade.</span><span class="sxs-lookup"><span data-stu-id="27397-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="27397-120">Trabalhar com o SDK do Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="27397-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="27397-121">Cientistas de dados e programadores de IA usam o [SDK do Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) para construir fluxos de trabalho de aprendizagem automática.</span><span class="sxs-lookup"><span data-stu-id="27397-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="27397-122">Atualmente, os modelos treinados usando o SDK não podem ser integrados diretamente com o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="27397-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="27397-123">É necessário um pipeline de inferência de lote que esse modelo consome para a integração com a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="27397-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="27397-124">Requisitos de pipeline de lote para integrar com a Customer Insights</span><span class="sxs-lookup"><span data-stu-id="27397-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="27397-125">Configuração do conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="27397-125">Dataset Configuration</span></span>

<span data-ttu-id="27397-126">É necessário criar conjuntos de dados para utilizar os dados da entidade a partir da Customer Insights até ao seu pipeline de inferência de lote.</span><span class="sxs-lookup"><span data-stu-id="27397-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="27397-127">Estes conjuntos de dados precisam de ser registados na área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="27397-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="27397-128">Atualmente, apenas suportamos [conjuntos de dados tabulares](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="27397-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="27397-129">Os conjuntos de dados que correspondem aos dados da entidade devem ser parametrizados como parâmetro de pipeline.</span><span class="sxs-lookup"><span data-stu-id="27397-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="27397-130">Parâmetros do conjunto de dados no Designer</span><span class="sxs-lookup"><span data-stu-id="27397-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="27397-131">No designer, abra **Selecionar colunas no conjunto de dados** e selecione **Definir como parâmetro de pipeline** onde fornece um nome para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="27397-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="27397-132">![Parametrização do conjunto de dados no designer](media/intelligence-designer-dataset-parameters.png "Parametrização do conjunto de dados no designer")</span><span class="sxs-lookup"><span data-stu-id="27397-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="27397-133">Parâmetro do conjunto de dados no SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="27397-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="27397-134">Pipeline de inferência de lote</span><span class="sxs-lookup"><span data-stu-id="27397-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="27397-135">No designer, um pipeline de formação pode ser usado para criar ou atualizar um pipeline de inferência.</span><span class="sxs-lookup"><span data-stu-id="27397-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="27397-136">Atualmente, apenas são suportados os pipelines de inferência de lote.</span><span class="sxs-lookup"><span data-stu-id="27397-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="27397-137">Utilizando o SDK, pode publicar o pipeline para um ponto final.</span><span class="sxs-lookup"><span data-stu-id="27397-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="27397-138">Atualmente, a Customer Insights integra-se com o pipeline padrão num ponto final do pipeline de lote na área de trabalho de aprendizagem automática.</span><span class="sxs-lookup"><span data-stu-id="27397-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="27397-139">Importar dados do pipeline para Customer Insights</span><span class="sxs-lookup"><span data-stu-id="27397-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="27397-140">O designer fornece o [módulo de Dados de Exportação](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) que permite a saída de um pipeline para exportação para o armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="27397-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="27397-141">Atualmente, o módulo deve utilizar o tipo de datastore **Armazenamento de Blobs do Azure** e parametrizar a **Datastore** e o **Caminho** relativo.</span><span class="sxs-lookup"><span data-stu-id="27397-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="27397-142">A Customer Insights substitui estes dois parâmetros durante a execução do pipeline com uma datastore e um caminho acessível ao produto.</span><span class="sxs-lookup"><span data-stu-id="27397-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="27397-143">![Exportar configuração do módulo de dados](media/intelligence-designer-importdata.png "Exportar configuração do módulo de dados")</span><span class="sxs-lookup"><span data-stu-id="27397-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="27397-144">Ao escrever a saída de inferência utilizando o código, pode enviar a saída para um caminho dentro de uma *datastore registada* na área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="27397-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="27397-145">Se o caminho e a datastore forem parametrizados no pipeline, a Customer insights poderá ler e importar a saída de inferência.</span><span class="sxs-lookup"><span data-stu-id="27397-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="27397-146">Atualmente, só é suportada uma única saída tabular em formato CSV.</span><span class="sxs-lookup"><span data-stu-id="27397-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="27397-147">O caminho deve incluir o diretório e o nome de ficheiro.</span><span class="sxs-lookup"><span data-stu-id="27397-147">The path must include the directory and filename.</span></span>

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

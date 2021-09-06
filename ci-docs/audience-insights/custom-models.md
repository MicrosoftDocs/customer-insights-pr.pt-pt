---
title: Modelos de aprendizagem automática personalizados | Documentos da Microsoft
description: Trabalhar com modelos personalizados do Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 187995cdf4d92a0609f8abb4c792e698ad4342cdb1f578744136add1bfcf3a53
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032956"
---
# <a name="custom-machine-learning-models"></a>Modelos de aprendizagem automática personalizados

**Informações** > **Modelos personalizados** permite-lhe gerir fluxos de trabalho baseados em modelos do Azure Machine Learning. Os fluxos de trabalho ajudam-no a escolher os dados a partir dos quais pretende gerar conhecimentos e mapear os resultados para os seus dados unificados de clientes. Para mais informações sobre a construção de modelos ML personalizados, ver [Usar modelos baseados no Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Responsável IA

As previsões oferecem capacidades para criar melhores experiências para os clientes, melhorar as capacidades empresariais, e fluxos de receitas. Recomendamos vivamente que equilibre o valor da sua previsão com o impacto que tem e os desvios que podem ser introduzidos de uma forma ética. Saiba mais sobre como a Microsoft [está a tratar a IA Responsável](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Também pode saber mais sobre [técnicas e processos para uma aprendizagem automática responsável](/azure/machine-learning/concept-responsible-ml) específica do Azure Machine Learning.

## <a name="prerequisites"></a>Pré-requisitos

- Atualmente, esta funcionalidade suporta serviços web publicados através de [Machine Learning Studio (clássico)](https://studio.azureml.net) e [pipelines por lote do Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Necessita de uma conta de armazenamento Azure Data Lake Gen2 associada à sua instância Azure Studio para utilizar esta funcionalidade. Para mais informações, consulte [Criar uma conta de armazenamento do Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Para as áreas de trabalho do Azure Machine Learning com pipelines, precisa de permissões de Proprietário ou Administrador de acesso do utilizador para a Área de Trabalho do Azure Machine Learning.

   > [!NOTE]
   > Os dados são transferidos entre as instâncias do Customer Insights e os serviços web ou pipelines selecionados do Azure no fluxo de trabalho. Quando transferir dados para um serviço Azure, certifique-se de que o serviço está configurado para processar os dados da forma e localização necessárias para cumprir quaisquer requisitos legais ou regulamentares relativos a esses dados para a sua organização.

## <a name="add-a-new-workflow"></a>Adicionar um novo fluxo de trabalho

1. Vá a **Informações** > **Modelos personalizados** e selecione **Novo fluxo de trabalho**.

1. Forneça um nome reconhecível ao modelo personalizado no campo **Nome**.

   > [!div class="mx-imgBorder"]
   > ![Captura de ecrã do painel de Novo fluxo de trabalho.](media/new-workflowv2.png "Captura de ecrã do painel de Novo fluxo de trabalho")

1. Selecione a organização que contém o serviço Web no **Inquilino que contém o seu serviço Web**.

1. Se a subscrição do Azure Machine Learning estiver num inquilino diferente do Customer Insights, selecione **Iniciar sessão** com as suas credenciais para a organização selecionada.

1. Selecione **Áreas de trabalho** associadas ao seu serviço web. Há duas secções listadas, uma para Azure Machine Learning v1 (Machine Learning Studio (clássico)) e a Azure Machine Learning v2 (Azure Machine Learning). Se não tiver a certeza qual é a área de trabalho certa para o seu serviço web de Machine Learning Studio (clássico), selecione **Qualquer uma**.

1. Escolha o serviço web Machine Learning Studio (clássico) ou pipeline Azure Machine Learning no menu pendente **Serviço Web que contém o seu modelo**. Em seguida, selecione **Seguinte**.
   - Saiba mais sobre [publicar um serviço web em Machine Learning Studio (clássico)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Saiba mais sobre [publicar um serviço web em Machine Learning Studio usando o designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou o [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). O seu pipeline deve ser publicado num [ponto final do pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Para cada **Entrada do serviço Web**, selecione a **Entidade** correspondente a partir de insights da audiência e selecione **Seguinte**.
   > [!NOTE]
   > O fluxo de trabalho do modelo personalizado aplicará heurística para mapear os campos de entrada do serviço Web para os atributos de entidade com base no nome e tipo de dados do campo. Verá um erro se um campo de serviço Web não puder ser mapeado para uma entidade.

   > [!div class="mx-imgBorder"]
   > ![Configurar um fluxo de trabalho.](media/intelligence-screen2-updated.png "Configurar um fluxo de trabalho")

1. No passo **Parâmetros de saída do modelo**, definir as seguintes propriedades:
   - Machine Learning Studio (clássico)
      1. Introduza a saída do **nome da Entidade** para onde quer que as saídas dos serviços da web fluam.
   - Azure Machine Learning
      1. Introduza a saída do **nome da Entidade** para onde quer que as saídas do pipeline fluam.
      1. Selecione o **Nome do parâmetro de armazenamento de dados de saída** do seu pipeline de lotes a partir da lista suspensa.
      1. Selecione o **Nome do parâmetro do caminho de dados de saída** do seu pipeline de lotes a partir da lista suspensa.

      > [!div class="mx-imgBorder"]
      > ![Painel de parâmetros de saída de modelo.](media/intelligence-screen3-outputparameters.png "Painel de parâmetros de saída de modelo")

1. Selecione o atributo correspondente a partir da lista pendente do **ID do cliente nos resultados** que identifica clientes e selecione **Guardar**.

   > [!div class="mx-imgBorder"]
   > ![Relacionar resultados com painel de dados do cliente.](media/intelligence-screen4-relatetocustomer.png "Relacionar resultados com painel de dados do cliente")

1. Verá o ecrã **Fluxo de Trabalho Guardado** com detalhes sobre o fluxo de trabalho.    
   Se configurou um fluxo de trabalho para um pipeline de Azure Machine Learning, os insights da audiência serão anexados à área de trabalho que contém o pipeline. Os insights da audiência terão um papel de **Contribuinte** na área de trabalho do Azure.

1. Selecione **Concluído**.

1. Pode agora executar o fluxo de trabalho a partir da página **Modelos personalizados**.

## <a name="edit-a-workflow"></a>Editar um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** junto de um fluxo de trabalho que criou anteriormente e selecione **Editar**.

1. Pode atualizar o nome reconhecível do seu fluxo de trabalho no campo **Nome a apresentar**, mas não pode alterar o serviço web configurado ou o pipeline. Selecione **Seguinte**.

1. Para cada **Entrada do serviço Web**, pode atualizar a **Entidade** correspondente a partir de insights da audiência. Em seguida, selecione **Seguinte**.

1. No passo **Parâmetros de saída do modelo**, definir as seguintes propriedades:
   - Machine Learning Studio (clássico)
      1. Introduza a saída do **nome da Entidade** para onde quer que as saídas dos serviços da web fluam.
   - Azure Machine Learning
      1. Introduza a saída do **nome da Entidade** para onde quer que as saídas do pipeline fluam.
      1. Selecione o **Nome do parâmetro de armazenamento de dados de saída** para o seu pipeline de teste.
      1. Selecione o **Nome do parâmetro do caminho de saída** para o seu pipeline de teste.

1. Selecione o atributo correspondente a partir da lista pendente do **ID do cliente nos resultados** que identifica clientes e selecione **Guardar**.
   Escolha um atributo a partir da saída de inferência com valores semelhantes à coluna de ID do Cliente da entidade Cliente. Se não tiver tal coluna no seu conjunto de dados, escolha um atributo que identifique de forma única a linha.

## <a name="run-a-workflow"></a>Executar um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** junto de um fluxo de trabalho que criou anteriormente.

1. Selecione **Executar**.

O seu fluxo de trabalho também é executado automaticamente com cada as atualização programada. Saber mais sobre a [configuração de atualizações agendadas](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Eliminar um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** junto de um fluxo de trabalho que criou anteriormente.

1. Selecione **Eliminar** e confirme a eliminação.

O fluxo de trabalho será eliminado. A [entidade](entities.md) que foi criada quando criou o fluxo de trabalho persiste e pode ser visualizada na página **Entidades**.

## <a name="results"></a>Resultados

Os resultados de um fluxo de trabalho são armazenados na entidade configurada durante a fase de Parâmetro de Saída do Modelo. Pode aceder a estes dados a partir da [página das entidades](entities.md) ou com [acesso à API](apis.md).

### <a name="api-access"></a>Acesso à API

Para que a consulta OData específica obtenha os dados de uma entidade de modelo personalizado, utilize o seguinte formato:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Substitua `<your instance id>` pelo ID do ambiente do Customer Insights, que encontra na barra de endereços do browser ao aceder ao Customer Insights.

1. Substitua `<custom model output entity>` pelo nome da entidade que forneceu durante o passo de Parâmetros de Saída do Modelo da configuração do modelo personalizado.

1. Substitua `<guid value>` pelo ID de Cliente do cliente para o qual pretende aceder ao registo. Normalmente pode encontrar este ID na [página de perfis do cliente](customer-profiles.md) no campo CustomerID.

## <a name="frequently-asked-questions"></a>Perguntas Mais Frequentes

- Por que não consigo ver o meu pipeline ao configurar um fluxo de trabalho de modelo personalizado?    
  Este problema é frequentemente causado por um problema de configuração no pipeline. Certifique-se de que o [parâmetro de entrada está configurado](azure-machine-learning-experiments.md#dataset-configuration) e que os [parâmetros de caminho e arquivo de dados de saída](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) também estão configurados.

- O que significa o erro "Não foi possível guardar o fluxo de trabalho de informações"?    
  Normalmente, os utilizadores veem esta mensagem de erro se não tiverem privilégios de Proprietário ou Administrador de acesso do utilizador na área de trabalho. O utilizador necessita de um nível mais elevado de permissões para permitir que o Customer Insights processe o fluxo de trabalho como serviço em vez de utilizar as credenciais de utilizador para execuções subsequentes do fluxo de trabalho.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Modelos de aprendizagem automática personalizados | Documentos da Microsoft
description: Trabalhar com modelos personalizados do Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609760"
---
# <a name="custom-machine-learning-models"></a>Modelos de aprendizagem automática personalizados

> [!NOTE]
> O suporte para o Machine Learning Studio (clássico) terminará a 31 de agosto de 2024. Recomendamos que faça a transição para o [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) até essa data.
>
> A partir de 1 de dezembro de 2021, não poderá criar novos recursos do Machine Learning Studio (clássico). Até 31 de agosto de 2024, poderá continuar a utilizar os recursos existentes do Machine Learning Studio (clássico). Para mais informações, consulte [Migrar para o Azure Machine Learning](/azure/machine-learning/migrate-overview).

Os modelos personalizados permitem-lhe gerir fluxos de trabalho com base em modelos do Azure Machine Learning. Os fluxos de trabalho ajudam-no a escolher os dados a partir dos quais pretende gerar conhecimentos e mapear os resultados para os seus dados unificados de clientes. Para mais informações sobre a construção de modelos ML personalizados, ver [Usar modelos baseados no Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Pré-requisitos

- Serviços Web publicados através dos [Pipelines em lote do Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).
- O pipeline tem de ser publicado num [ponto final do pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Uma [conta de armazenamento Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) associada à sua instância Azure Studio.
- Para as áreas de trabalho do Azure Machine Learning com pipelines, permissões de Proprietário ou Administrador de acesso do utilizador para a Área de Trabalho do Azure Machine Learning.

  > [!NOTE]
  > Os dados são transferidos entre as instâncias do Customer Insights e os serviços web ou pipelines selecionados do Azure no fluxo de trabalho. Quando transferir dados para um serviço Azure, certifique-se de que o serviço está configurado para processar os dados da forma e localização necessárias para cumprir quaisquer requisitos legais ou regulamentares relativos a esses dados para a sua organização.

## <a name="add-a-new-workflow"></a>Adicionar um novo fluxo de trabalho

1. Vá a **Informações** > **Modelos personalizados** e selecione **Novo fluxo de trabalho**.

1. Forneça um **Nome** reconhecível.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Captura de ecrã do painel de Novo fluxo de trabalho.":::

1. Selecione a organização que contém o serviço Web no **Inquilino que contém o seu serviço Web**.

1. Se a subscrição do Azure Machine Learning estiver num inquilino diferente do Customer Insights, selecione **Iniciar sessão** com as suas credenciais para a organização selecionada.

1. Selecione **Áreas de trabalho** associadas ao seu serviço web.

1. Escolha o pipeline do Azure Machine Learning na lista pendente **Serviço Web que contém o seu modelo**. Em seguida, selecione **Seguinte**.
   Saiba mais sobre [publicar um serviço web em Machine Learning Studio usando o designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou o [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Para cada **Entrada do serviço Web**, selecione a **Entidade** correspondente a partir do Customer Insights. Em seguida, selecione **Seguinte**.
   > [!NOTE]
   > O fluxo de trabalho do modelo personalizado aplicará heurística para mapear os campos de entrada do serviço Web para os atributos de entidade com base no nome e tipo de dados do campo. Verá um erro se um campo de serviço Web não puder ser mapeado para uma entidade.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Configurar um fluxo de trabalho.":::

1. Para **Parâmetros de Saída do Modelo**, defina as seguintes propriedades:
   - **Nome da entidade** para os resultados de saída do pipeline
   - **Nome do parâmetro de armazenamento de dados de saída** do seu pipeline de lote
   - **Nome do parâmetro do Caminho de Saída** do seu pipeline de lote

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Painel de parâmetros de saída de modelo.":::

1. Selecione o atributo correspondente a partir do **ID do cliente nos resultados** que identifica clientes e selecione **Guardar**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Relacionar resultados com painel de dados do cliente.":::

   O ecrã **Fluxo de Trabalho Guardado** apresenta detalhes sobre o fluxo de trabalho. Se tiver configurado um fluxo de trabalho para um pipeline do Azure Machine Learning, o Customer Insights é anexado à área de trabalho que contém o pipeline. O Customer Insights irá obter uma função de **Contribuidor** na área de trabalho do Azure.

1. Selecionar **Concluído**. A página **Modelos Personalizados** é apresentada.

1. Selecione as reticências verticais (&vellip;) para o fluxo de trabalho e, em seguida, selecione **Executar**. O seu fluxo de trabalho também é executado automaticamente com [cada atualização agendada](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Gerir um fluxo de trabalho existente

Aceda a **Inteligência** > **Modelos personalizados** para ver os fluxos de trabalho que criou.

Selecione um fluxo de trabalho para ver as ações disponíveis.

- **Editar** um fluxo de trabalho
- **Executar** um fluxo de trabalho
- [**Eliminar**](#delete-a-workflow) um fluxo de trabalho

### <a name="edit-a-workflow"></a>Editar um fluxo de trabalho

1. Aceda a **Inteligência** > **Modelos personalizados**.

1. Junto do fluxo de trabalho que pretende atualizar, selecione as reticências verticais (&vellip;) e selecione **Editar**.

1. Altere **Nome a apresentar**, se necessário, e selecione **Seguinte**.

1. Para cada **Entrada do serviço Web**, atualize a **Entidade** correspondente a partir do Customer Insights, se necessário. Em seguida, selecione **Seguinte**.

1. Para **Parâmetros de Saída do Modelo**, altere qualquer um dos seguintes:
   - **Nome da entidade** para os resultados de saída do pipeline
   - **Nome do parâmetro de armazenamento de dados de saída** do seu pipeline de lote
   - **Nome do parâmetro do Caminho de Saída** do seu pipeline de lote

1. Altere o atributo correspondente do **ID do cliente em resultados** para identificar clientes. Escolha um atributo a partir da saída de inferência com valores semelhantes à coluna de ID do Cliente da entidade Cliente. Se não tiver tal coluna no seu conjunto de dados, escolha um atributo que identifique de forma única a linha.

1. Selecione **Guardar**

### <a name="delete-a-workflow"></a>Eliminar um fluxo de trabalho

1. Aceda a **Inteligência** > **Modelos personalizados**.

1. Junto do fluxo de trabalho que pretende eliminar, selecione as reticências verticais (&vellip;) e selecione **Eliminar**.

1. Confirme a eliminação.

O fluxo de trabalho será eliminado. A [entidade](entities.md) que foi criada quando criou o fluxo de trabalho persiste e pode ser visualizada na página **Dados** > **Entidades**.

## <a name="view-the-results"></a>Ver os resultados

Os resultados de um fluxo de trabalho são armazenados no nome da entidade definido para **Parâmetros de Saída do Modelo**. Aceda a estes dados a partir da [página **Dados** > **Entidades**](entities.md) ou com [acesso à API](apis.md).

### <a name="api-access"></a>Acesso à API

Para que a consulta OData específica obtenha os dados de uma entidade de modelo personalizado, utilize o seguinte formato:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Substitua `<your instance id>` pelo ID do ambiente do Customer Insights, que é apresentado na barra de endereços do browser ao aceder ao Customer Insights.

1. Substitua `<custom model output entity>` pelo nome da entidade que forneceu para os **Parâmetros de Saída do Modelo**.

1. Substitua `<guid value>` pelo ID de Cliente do cliente para o qual pretende aceder. Este ID é apresentado na [página de perfis de cliente](customer-profiles.md) no campo CustomerID.

## <a name="frequently-asked-questions"></a>Perguntas Mais Frequentes

- Por que não consigo ver o meu pipeline ao configurar um fluxo de trabalho de modelo personalizado?
  Este problema é frequentemente causado por um problema de configuração no pipeline. Certifique-se de que o [parâmetro de entrada está configurado](azure-machine-learning-experiments.md#dataset-configuration) e que os [parâmetros de caminho e arquivo de dados de saída](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) também estão configurados.

- O que significa o erro "Não foi possível guardar o fluxo de trabalho de informações"? 
  Normalmente, os utilizadores veem esta mensagem de erro se não tiverem privilégios de Proprietário ou Administrador de acesso do utilizador na área de trabalho. O utilizador necessita de um nível mais elevado de permissões para permitir que o Customer Insights processe o fluxo de trabalho como serviço em vez de utilizar as credenciais de utilizador para execuções subsequentes do fluxo de trabalho.

- É suportada um ponto final privado/ligação privada para o meu fluxo de trabalho de modelo personalizado?
  Atualmente, o Customer Insights não suporta ponto final para modelos personalizados de origem, mas está disponível uma alternativa manual. Contacte o suporte para obter detalhes.

## <a name="responsible-ai"></a>Responsável IA

As previsões oferecem capacidades para criar melhores experiências para os clientes, melhorar as capacidades empresariais, e fluxos de receitas. Recomendamos vivamente que equilibre o valor da sua previsão com o impacto que tem e os desvios que podem ser introduzidos de uma forma ética. Saiba mais sobre como a Microsoft [está a tratar a IA Responsável](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Também pode saber mais sobre [técnicas e processos para uma aprendizagem automática responsável](/azure/machine-learning/concept-responsible-ml) específica do Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]

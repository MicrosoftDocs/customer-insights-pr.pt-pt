---
title: Modelos de aprendizagem automática personalizados | Documentos da Microsoft
description: Trabalhar com modelos personalizados do Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267248"
---
# <a name="custom-machine-learning-models"></a>Modelos de aprendizagem automática personalizados

**Informações** > **Modelos personalizados** permite-lhe gerir fluxos de trabalho baseados em modelos do Azure Machine Learning. Os fluxos de trabalho ajudam-no a escolher os dados a partir dos quais pretende gerar conhecimentos e mapear os resultados para os seus dados unificados de clientes. Para mais informações sobre a construção de modelos ML personalizados, ver [Usar modelos baseados no Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Responsável IA

As previsões oferecem capacidades para criar melhores experiências para os clientes, melhorar as capacidades empresariais, e fluxos de receitas. Recomendamos vivamente que equilibre o valor da sua previsão com o impacto que tem e os desvios que podem ser introduzidos de uma forma ética. Saiba mais sobre como a Microsoft [está a tratar a IA Responsável](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Também pode saber mais sobre [técnicas e processos para uma aprendizagem automática responsável](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) específica do Azure Machine Learning.

## <a name="prerequisites"></a>Pré-requisitos

- Atualmente, esta funcionalidade suporta serviços web publicados através de [Machine Learning Studio (clássico)](https://studio.azureml.net) e [pipelines por lote do Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Necessita de uma conta de armazenamento Azure Data Lake Gen2 associada à sua instância Azure Studio para utilizar esta funcionalidade. Para mais informações, consulte [Criar uma conta de armazenamento do Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Adicionar um novo fluxo de trabalho

1. Vá a **Informações** > **Modelos personalizados** e selecione **Novo fluxo de trabalho**.

1. Forneça um nome reconhecível ao modelo personalizado no campo **Nome**.

   > [!div class="mx-imgBorder"]
   > ![Captura de ecrã do painel de Novo fluxo de trabalho](media/new-workflowv2.png "Captura de ecrã do painel de Novo fluxo de trabalho")

1. Selecione a organização que contém o serviço Web no **Inquilino que contém o seu serviço Web**.

1. Se a subscrição do Azure Machine Learning estiver num inquilino diferente do Customer Insights, selecione **Iniciar sessão** com as suas credenciais para a organização selecionada.

1. Selecione **Áreas de trabalho** associadas ao seu serviço web. Há duas secções listadas, uma para Azure Machine Learning v1 (Machine Learning Studio (clássico)) e a Azure Machine Learning v2 (Azure Machine Learning). Se não tiver a certeza qual é a área de trabalho certa para o seu serviço web de Machine Learning Studio (clássico), selecione **Qualquer uma**.

1. Escolha o serviço web Machine Learning Studio (clássico) ou pipeline Azure Machine Learning no menu pendente **Serviço Web que contém o seu modelo**. Em seguida, selecione **Seguinte**.
   - Saiba mais sobre [publicar um serviço web em Machine Learning Studio (clássico)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Saiba mais sobre [publicar um serviço web em Machine Learning Studio usando o designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou o [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). O seu pipeline deve ser publicado num [ponto final do pipeline](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Para cada **Entrada do serviço Web**, selecione a **Entidade** correspondente a partir de insights da audiência e selecione **Seguinte**.
   > [!NOTE]
   > O fluxo de trabalho do modelo personalizado aplicará heurística para mapear os campos de entrada do serviço Web para os atributos de entidade com base no nome e tipo de dados do campo. Verá um erro se um campo de serviço Web não puder ser mapeado para uma entidade.

   > [!div class="mx-imgBorder"]
   > ![Configurar um fluxo de trabalho](media/intelligence-screen2-updated.png "Configurar um fluxo de trabalho")
   
1. No passo **Parâmetros de saída do modelo**, definir as seguintes propriedades:
   - Machine Learning Studio (clássico)
      1. Introduza a saída do **nome da Entidade** para onde quer que as saídas dos serviços da web fluam.
   - Azure Machine Learning
      1. Introduza a saída do **nome da Entidade** para onde quer que as saídas do pipeline fluam.
      1. Selecione o **Nome do parâmetro de armazenamento de dados de saída** do seu pipeline de lotes a partir da lista suspensa.
      1. Selecione o **Nome do parâmetro do caminho de dados de saída** do seu pipeline de lotes a partir da lista suspensa.
      
      > [!div class="mx-imgBorder"]
      > ![Painel de parâmetros de saída de modelo](media/intelligence-screen3-outputparameters.png "Painel de parâmetros de saída de modelo")

1. Selecione o atributo correspondente a partir da lista pendente do **ID do cliente nos resultados** que identifica os clientes e selecione **Guardar**.
   
   > [!div class="mx-imgBorder"]
   > ![Relacionar resultados com painel de dados do cliente](media/intelligence-screen4-relatetocustomer.png "Relacionar resultados com painel de dados do cliente")

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

1. Selecione o atributo correspondente a partir da lista pendente do **ID do cliente nos resultados** que identifica os clientes e selecione **Guardar**.
   É necessário escolher um atributo da saída de inferência com valores semelhantes aos da coluna ID do Cliente da entidade Cliente. Se não tiver tal coluna no seu conjunto de dados, escolha um atributo que identifique de forma única a linha.

## <a name="run-a-workflow"></a>Executar um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** junto de um fluxo de trabalho que criou anteriormente.

1. Selecione **Executar**.

O seu fluxo de trabalho também é executado automaticamente com cada as atualização programada. Saber mais sobre a [configuração de atualizações agendadas](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Eliminar um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** junto de um fluxo de trabalho que criou anteriormente.

1. Selecione **Eliminar** e confirme a eliminação.

O fluxo de trabalho será eliminado. A [entidade](entities.md) que foi criada quando criou o fluxo de trabalho persiste e pode ser visualizada na página **Entidades**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
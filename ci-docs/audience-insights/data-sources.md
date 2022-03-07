---
title: Utilizar origens de dados para ingerir dados
description: Saiba como importar dados de várias origens.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e7bcf82c4fe3625ef791ec2b0a7651be0356a006
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354063"
---
# <a name="data-sources-overview"></a>Descrição geral das origens de dados



A capacidade de insights da audiência em Dynamics 365 Customer Insights liga-se a dados de um vasto conjunto de origens. A ligação a um origem de dados é frequentemente referida como o processo de *ingestão de dados*. Depois de ingerir os dados, pode [unificar](data-unification.md) e tomar medidas sobre os mesmos.

## <a name="add-a-data-source"></a>Adicionar uma origem de dados

Consulte os artigos detalhados para saber como adicionar uma origem de dados, consoante a opção que escolher.

Poderá adicionar as seguintes origens de dados:

- [Através de dezenas de conectores do Power Query](connect-power-query.md)
- [A partir de uma pasta do Common Data Model](connect-common-data-model.md)
- [A partir do seu próprio Data Lake do Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [A partir de uma base de dados do Azure Synapse Analytics](connect-synapse.md)

> [!NOTE]
> Se estiver a utilizar a versão de avaliação, a secção de métodos de importação inclui uma opção **Biblioteca de dados do Customer Insights**. Escolha esta opção para selecionar um conjunto de dados de amostra disponível para vários setores. Para obter mais informações, consulte [Avaliação do Dynamics 365 Customer Insights](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Adicionar dados de origens de dados no local

Ingerir dados de origens de dados no local em informações de audiência é suportado com base em fluxos de dados do Microsoft Power Platform. Poderá ativar Fluxos de Dados no Customer Insights ao [fornecer o URL do ambiente do Microsoft Dataverse](create-environment.md) quando configurar o ambiente.

As origens de dados que são criadas após a associação de um ambiente do Dataverse ao Customer Insights utilizam [fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por predefinição. Os fluxos de dados suportam conectividade no local utilizando o gateway de dados. Poderá remover e recriar as origens de dados que existiam antes de um ambiente do Dataverse ser associado [através de gateways de dados no local](/data-integration/gateway/service-gateway-app).

Os gateways de dados de um ambiente Power BI ou Power Apps existente serão visíveis e poderá reutilizá-los no Customer Insights. A página de origens de dados mostra ligações para ir para o ambiente do Microsoft Power Platform onde pode ver e configurar gateways de dados no local.

## <a name="review-ingested-data"></a>Rever dados ingeridos

Verá o nome de cada origem de dados ingerido, o seu estado, e a última vez que os dados foram atualizados para essa origem. Pode ordenar a lista de origens de dados por cada coluna.

> [!div class="mx-imgBorder"]
> ![Origem de dados adicionada.](media/configure-data-datasource-added.png "Origem de dados adicionada")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

O carregamento de dados pode levar tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revistos na página **Entidades**. Para mais informações, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Atualizar uma origem de dados

As origens de dados podem ser atualizadas com agendamento automático ou atualizadas manualmente a pedido. 

Vá a **Admin** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações programadas de todas as suas origens de dados ingeridos.

Para atualizar uma origem de dados a pedido, siga estes passos:

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

2. Selecione as reticências verticais junto da origem de dados que pretende atualizar e selecione **Atualizar** na lista pendente.

3. A origem dos dados é agora ativada para uma atualização manual. Atualizar uma origem de dados irá atualizar tanto o esquema da entidade como os dados para todas as entidades especificadas na origem de dados.

4. Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e a origem dos dados reverterá para o seu último estado de atualização.

## <a name="delete-a-data-source"></a>Eliminar uma origem de dados

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

2. Selecione as reticências verticais junto da origem de dados que pretende remover e selecione **Eliminar** no menu pendente.

3. Confirme a eliminação.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

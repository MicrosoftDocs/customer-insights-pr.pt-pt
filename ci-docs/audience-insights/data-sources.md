---
title: Utilizar origens de dados para ingerir dados
description: Saiba como importar dados de várias origens.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304710"
---
# <a name="data-sources-overview"></a>Descrição geral das origens de dados

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

A capacidade de insights da audiência em Dynamics 365 Customer Insights liga-se a dados de um vasto conjunto de origens. A ligação a um origem de dados é frequentemente referida como o processo de *ingestão de dados*. Depois de ingerir os dados, pode [unificar](data-unification.md) e tomar medidas sobre os mesmos.

## <a name="add-a-data-source"></a>Adicionar uma origem de dados

Consulte os artigos detalhados sobre como adicionar uma origem de dados, dependendo da opção que escolher.

Pode adicionar uma origem de dados de três formas principais:

- [Através de dezenas de conectores Power Query](connect-power-query.md)
- [A partir de uma pasta do Common Data Model](connect-common-data-model.md)
- [A partir do seu próprio lake do Microsoft Dataverse](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Adicionar dados de origens de dados no local

Ingerir dados de origens de dados no local em informações de audiência é suportado com base em fluxos de dados do Microsoft Power Platform. Os fluxos de dados podem ser ativados no Customer Insights [fornecendo o URL do ambiente Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) ao configurar o ambiente.

Por predefinição, as origens de dados criadas após a associação de um ambiente Dataverse ao Customer Insights utilizarão [fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Os fluxos de dados suportam conectividade no local utilizando o gateway de dados. Remova e recrie origens de dados que existiam antes de um ambiente Dataverse ser associado a [utilizar os gateways de dados no local](/data-integration/gateway/service-gateway-app.md).

Os gateways de dados de um ambiente Power BI ou Power Apps existente serão visíveis e poderá reutilizá-los no Customer Insights. A página de origens de dados mostra ligações para ir para o ambiente do Microsoft Power Platform onde pode ver e configurar gateways de dados no local.

## <a name="review-ingested-data"></a>Rever dados ingeridos

Verá o nome de cada origem de dados ingerido, o seu estado, e a última vez que os dados foram atualizados para essa origem. Pode ordenar a lista de origens de dados por cada coluna.

> [!div class="mx-imgBorder"]
> ![Origem de dados adicionada](media/configure-data-datasource-added.png "Origem de dados adicionada")

|Estado  |Descrição  |
|---------|---------|
|Êxito   |A origem dos dados foi ingerida com sucesso se houver uma hora mencionada na coluna **Atualizada**.
|Não iniciado   |A origem dos dados ainda não tem dados ingeridos ou ainda está em modo de rascunho.         |
|A atualizar    |A ingestão de dados está em curso. Poderá cancelar esta operação ao selecionar **Parar de atualizar** na coluna **Ações**. Parar a atualização de um origem de dados irá revertê-lo para o último estado de atualização.       |
|Falha     |A ingestão de dados encontrou erros.         |

Selecione o valor na coluna **Estado** de qualquer origem de dados para rever mais detalhes. No painel **Detalhes do progresso**, expanda **Origens de dados**. Selecione **Ver detalhes** para obter mais informações sobre o estado da atualização, incluindo detalhes de erro e atualizações do processo a jusante.

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

---
title: Utilizar segmentos de informações de audiência para filtrar relatórios de informações de cativação
description: Utilize segmentos de informações de audiência em análises interativas de dados comportamentais capturados por informações de cativação no site de um cliente.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230500"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Utilizar segmentos de informações de audiência para filtrar relatórios de informações de cativação

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Com as informações de cativação, pode utilizar segmentos de informações de audiência em análises interativas de dados comportamentais capturados por informações de cativação nos seus sites.

## <a name="prerequisite"></a>Pré-requisito

- Um ambiente de informações de cativação em que tem dados de segmentos de informações de audiência ligados ao ambiente de informações de audiência onde os segmentos e perfis de clientes são criados. Mais informações: [Criar uma ligação entre as informações de audiência e as informações de cativação](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Criar segmentos de informações de audiência 

> [!IMPORTANT]
> Para que os segmentos de informações de audiência apareçam em informações de cativação, tem primeiro de [executar processos de união e a jusante](../audience-insights/merge-entities.md). Os processos a jusante são importantes porque geram uma tabela única que prepara segmentos de informações de audiência para serem partilhados com informações de cativação. (Se estiver agendada uma atualização de sistema, esta incluirá automaticamente processos a jusante.)

Pode usar segmentos de informações de audiência em relatórios de informações de cativação de origem ou relatórios personalizados que tenha criado. Para obter mais informações, aceda a [Relatórios de perfis de origem](profile-reports.md) e [Criar e editar relatórios personalizados](custom-reports.md).

**Para utilizar segmentos de informações de audiência em relatórios de informações de cativação**

1. Na sua página **Área de trabalho**, selecione **Dados** e, em seguida, selecione o separador **Segmentos**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Selecionar o separador Segmentos.":::

   >[!NOTE]
   > Selecionar um segmento de informações de audiência leva-o para as informações de audiência, onde pode descobrir como esse segmento foi criado em termos de regras e lógica. Para obter mais informações sobre segmentos de informações de audiência, vá a [Ver e criar segmentos](../audience-insights/segments.md).

2. Selecione um relatório de origem ou [crie um relatório personalizado](custom-reports.md) e, em seguida, selecione **Adicionar condição**. (Para este exemplo, escolhemos o relatório **Visualizações de página**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Adicionar uma condição.":::

3. Selecione **Filtrar por segmento**, expanda a lista **Tipo de segmento** e, em seguida, selecione **Demografia**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Selecionar o tipo de segmento Demográfico.":::

4. Expanda a lista de **Nome do segmento** e, em seguida, escolha um segmento de informações de audiência.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Escolher um segmento.":::

5. Pode aplicar um ou mais segmentos, incluindo segmentos comportamentais (informações de cativação) e demográficos (informações de audiência). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Relatório de visualizações de página restringido aos clientes dos EUA e segmentos de Página inicial.":::

Na imagem anterior, foram selecionados os segmentos **Clientes dos EUA** e **Página inicial**, o que restringe o relatório de **Visualizações de página** para mostrar apenas esses dois segmentos. 


>[!NOTE]
> Pode usar segmentos de informações de audiência para filtrar relatórios de origem, relatórios personalizados e funis em informações de cativação. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
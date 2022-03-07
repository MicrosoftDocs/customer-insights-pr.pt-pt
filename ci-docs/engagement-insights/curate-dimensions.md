---
title: Utilizar dimensões demográficas para dividir dados comportamentais (dimensões curadas)
description: Utilize dimensões unificadas com curadoria de perfis para permitir propriedades de perfil de cliente de informações de audiência.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233061"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Utilizar dimensões demográficas para dividir dados comportamentais

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ao utilizar dimensões demográficas de perfil unificado, os utilizadores podem aceder a propriedade de perfil de informações de audiência. Pode então utilizar estas propriedades em análises interativas de dados comportamentais, incluindo dados capturados por informações de cativação no seu site ou aplicação móvel.

>[!NOTE]
> As informações de cativação incluem dimensões fornecidas com o programa para propriedades de eventos. Mais informações: [Ver e criar dimensões](dimensions.md)

## <a name="prerequisite"></a>Pré-requisito

- Um ambiente de informações de cativação em que tem dados de perfil de cliente ligados ao ambiente de informações de audiência onde os perfis de clientes são criados. Mais informações: [Criar uma ligação entre as informações de audiência e as informações de cativação](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Depois de criar uma ligação entre os ambientes de informações de audiência e de informações de cativação, poderá só querer dados específicos das propriedades de perfil de cliente, o que pode ser útil como dimensões em informações de cativação. Para obter mais informações, vá a [Capacitar atributos e segmentos de perfis unificados de informações de audiência](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Criar um novo relatório personalizado

1. No painel esquerdo, selecione **Personalizado** > **Novo relatório** e, em seguida, selecione a métrica desejada. (Para este exemplo, escolhemos **Visualizações de página por Hora**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Selecionar uma métrica.":::

2. No editor Visualização, selecione **Dimensões** e, em seguida, selecione **Demografia** no menu pendente **Tipo de Dimensão**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Selecionar demografia.":::

3. Selecione uma dimensão **Signal.Customer.*xxx***. (Este exemplo mostra Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Selecionar uma dimensão.":::
  
## <a name="limitations"></a>Limitações

Atualmente, pode apenas utilizar dimensões demográficas para dividir dados comportamentais.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Ver e criar segmentos
description: Como criar, editar e eliminar segmentos e onde utilizá-los.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036162"
---
# <a name="view-and-create-segments"></a>Ver e criar segmentos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Os segmentos permitem identificar subconjuntos de visitantes com base em características ou interações do site. Os segmentos permitem aplicar filtros e analisar esses subconjuntos. A análise pode ajudar a examinar e responder às tendências no seu negócio. 

:::image type="content" source="media/segments-page.png" alt-text="Captura de ecrã da aplicação de informações de cativação a mostrar a lista de segmentos existentes numa área de trabalho.":::

## <a name="view-segments"></a>Ver segmentos

1. Aceda a **Dados** no painel de navegação esquerdo. 

1. Selecione o separador **Segmentos** para ver uma lista de todos os segmentos na área de trabalho. 

## <a name="create-a-segment"></a>Criar um segmento

Os segmentos consistem em regras e condições que estão ligadas a operadores lógicos. As condições aplicam filtros a uma dimensão selecionada. Cada segmento pode usar até cinco dimensões.

O exemplo a seguir mostra um segmento com duas condições em uma regra. Filtra todos os eventos do site onde o browser é o Chrome e os sistemas operativos são iOS ou Android.

:::image type="content" source="media/segment-sample.png" alt-text="Segmentos de exemplo com duas condições numa regra para filtrar para eventos do site.":::

Esta secção descreve como criar um *segmento em branco* a partir do zero.

1. Aceda a **Dados** > **Segmentos**.

1. Selecione **Novo segmento**.

1. Na **Biblioteca de recursos**, escolha o atributo pelo qual pretende filtrar. Atualmente, só é possível criar segmentos baseados em dimensões.

1. Escolha um operador e um valor para o atributo selecionado. As seguintes operações são suportadas.
   - **é**: requer uma correspondência exata para incluir valores. Utiliza **igual a** para um valor único ou **qualquer um de** para incluir múltiplos valores.
   - **não é**: requer uma correspondência exata para excluir valores. Utiliza **igual a** para um valor único ou **qualquer um de** para incluir múltiplos valores.
   - **começa em**: uma cadeia com que os valores correspondentes começam.
   - **termina em**: uma cadeia com que os valores correspondentes terminam.
   - **contém**: uma cadeia contida em valores correspondentes.

1. Para adicionar mais condições a um grupo, poderá utilizar dois operadores lógicos. Os atributos projetados são contabilizados quando utiliza operadores definidos.
   - Operador **AND**: ambas as condições têm de ser satisfeitas como parte do processo de segmentação. Esta opção é mais útil quando define condições em diferentes entidades.
   - Operador **OR**: qualquer uma das condições tem de ser satisfeita como parte do processo de segmentação. Esta opção é mais útil quando define múltiplas condições para a mesma entidade.

1. Selecione **Guardar** e dê nome ao segmento. 

O segmento será listado na página Segmentos e pode aplicá-lo a todos os relatórios e funis na área de trabalho.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Use um segmento num relatório ou funil

Pode aplicar segmentos a um relatório ou a um funil para os filtrar com base nas condições do segmento. No entanto, não é possível aplicar segmentos ao relatório de utilização em tempo real.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Uma relatórios de visualizações de página com uma lista pendente expandida para escolher que segmentos aplicar.":::

Para aplicar um segmento, abra o relatório ou funil. Selecione **Adicionar condição** e escolha **Filtrar por segmento**. Escolha o segmento da lista que pretende aplicar. O segmento é aplicado ao relatório. Se um gráfico não suporta o segmento, mostra um erro.
 
Pode aplicar *até três segmentos* a um relatório ou funil.

## <a name="edit-a-segment"></a>Editar um segmento

1. Aceda a **Dados** > **Segmentos**.
1. Selecione o segmento na lista para o abrir. 
1. Altere ou adicione valores conforme necessário.
1. Selecione **Guardar** para aplicar as alterações.

## <a name="change-the-name-of-a-segment"></a>Altere o nome de um segmento

1. Aceda a **Dados** > **Segmentos**.
1. Na lista de segmentos, selecione **Mais [...]**. 
1. Na lista pendente, escolha **Editar nome**.
1. Introduza o nome novo e selecione **Mudar o nome**.

## <a name="delete-a-segment"></a>Eliminar um segmento

1. Aceda a **Dados** > **Segmentos**.
1. Na lista de segmentos, selecione **Mais [...]**. 
1. Na lista pendente, escolha **Eliminar**.
1. Selecione **Eliminar** para confirmar.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

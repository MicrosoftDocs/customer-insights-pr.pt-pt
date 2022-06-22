---
title: Rever a unificação de dados
description: Rever os passos de unificação de dados, criar unified customer profiles e rever os resultados
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844100"
---
# <a name="review-data-unification"></a>Rever a unificação de dados

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Este último passo no processo de unificação mostra um resumo dos passos no processo e oferece uma oportunidade de efetuar alterações antes de criar o perfil unificado.

:::image type="content" source="media/m3_review.png" alt-text="Captura de ecrã de Rever e criar perfis de cliente.":::

## <a name="review-the-data-unification-steps"></a>Rever os passos de unificação de dados

1. Selecione **Editar** em qualquer um dos passos de unificação de dados para rever efetuar quaisquer alterações.

1. Se estiver satisfeito com as suas seleções, selecione **Criar perfis de cliente**. A página **Unificar** é apresentada durante a criação do unified customer profile. Todos os mosaicos, exceto **Campos de origem**, mostram o estado **Em fila** ou **A atualizar**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de ecrã da página Unificar com mosaicos a mostrar Em fila ou A atualizar.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificação demora algum tempo a ser concluído e não pode alterar a configuração enquanto não for concluído. Quando o processo de unificação for concluído, a entidade unified customer profile denominada *Cliente* é listada na página **Entidades** na secção **Perfis**. A primeira execução de unificação realizada com êxito cria a entidade *Cliente* unificada. Todas as execuções subsequentes expandem essa entidade.

## <a name="review-the-results-of-data-unification"></a>Rever os resultados da unificação de dados

Após a unificação, a página **Dados** > **Unificar** mostra o número de unified customer profiles. Os resultados de cada passo no processo de unificação são apresentados em cada mosaico. Por exemplo, **Campos de origem** mostra o número de atributos mapeados (campos) e **Registos duplicados** mostram o número de registos duplicados encontrados.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de ecrã da página Unificação de dados após a unificação dos dados.":::

> [!TIP]
> O mosaico **Condições de correspondência** só é apresentado se várias entidades tiverem sido selecionadas.

Recomendamos que reveja os resultados, particularmente a qualidade das [regras de correspondência](data-unification-update.md#manage-match-rules) refina-as se necessário.

Sempre que for necessário, [efetue alterações às definições de unificação](data-unification-update.md) e execute novamente o perfil unificado.

## <a name="next-step"></a>Passo Seguinte

Configure [atividades](activities.md), [melhoramento](enrichment-hub.md), [relações](relationships.md) ou [medidas](measures.md) para obter mais informações sobre os seus clientes.

[!INCLUDE[footer-include](includes/footer-banner.md)]

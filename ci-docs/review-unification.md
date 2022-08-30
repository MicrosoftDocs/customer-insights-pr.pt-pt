---
title: Rever a unificação de dados
description: Rever os passos de unificação de dados, criar perfis de cliente unificados e rever os resultados
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303981"
---
# <a name="review-data-unification"></a>Rever a unificação de dados

Reveja o resumo das alterações, crie o perfil unificado e reveja os resultados.

## <a name="review-and-create-customer-profiles"></a>Rever e criar perfis de cliente

Este último passo no processo de unificação mostra um resumo dos passos no processo e oferece uma oportunidade de efetuar alterações antes de criar o perfil unificado.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Captura de ecrã de Rever e criar perfis de cliente.":::

1. Selecione **Editar** em qualquer um dos passos de unificação de dados para rever efetuar quaisquer alterações.

1. Se estiver satisfeito com as suas seleções, selecione **Criar perfis de cliente** (ou **Criar perfis de conta** para B2B). A página **Unificar** é apresentada durante a criação do unified customer profile.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de ecrã da página Unificar com mosaicos a mostrar Em fila ou A atualizar.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificação demora algum tempo a ser concluído e não pode alterar a configuração enquanto não for concluído.

## <a name="view-the-results-of-data-unification"></a>Ver os resultados da unificação de dados

Após a unificação, a página **Dados** > **Unificar** mostra o número de perfis de cliente unificados (ou perfis de conta para B2B). Os resultados de cada passo no processo de unificação são apresentados em cada mosaico. Por exemplo, **Campos de origem** mostra o número de atributos mapeados (campos) e **Registos duplicados** mostram o número de registos duplicados encontrados.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de ecrã da página Unificação de dados após a unificação dos dados.":::

> [!TIP]
> O mosaico **Condições de correspondência** só é apresentado se várias entidades tiverem sido selecionadas.

Recomendamos que reveja os resultados, particularmente a qualidade das [regras de correspondência](data-unification-update.md#manage-match-rules) refina-as se necessário.

Sempre que for necessário, [efetue alterações às definições de unificação](data-unification-update.md) e execute novamente o perfil unificado.

### <a name="verify-output-entities-from-data-unification"></a>Verificar entidades de saída a partir da unificação de dados

Aceda a **Dados** > **Entidades** para verificar as entidades de saída.

A entidade de perfil cliente unificada, denominada *Cliente*, surge na secção **Perfis**. A primeira execução de unificação realizada com êxito cria a entidade *Cliente* unificada. Todas as execuções subsequentes expandem essa entidade.

As entidades de deduplicação e conflação são criadas e apresentadas na secção **Sistema**. Uma entidade deduplicada para cada entidade de origem é criada com o nome **Deduplication_DataSource_Entity**. A entidade **ConflationMatchPairs** contém informações sobre correspondências cruzadas de entidades.

Uma entidade de saída de eliminação de duplicados contém as seguintes informações:
- IDs / Chaves
  - Campos Chave primária e ID Alternativo. O campo de ID alternativo é composto por todos os IDs alternativos identificados num registo.
  - O campo Deduplication_GroupId mostra o grupo ou o cluster identificado dentro de uma entidade que agrupa todos os registos semelhantes com base nos campos de eliminação de duplicados especificados. É utilizado para fins de processamento do sistema. Se não existirem regras de eliminação de duplicados manuais especificadas e se aplicarem regras de eliminação de duplicados definidas pelo sistema, poderá não encontrar este campo na entidade de saída de eliminação de duplicados.
  - Deduplication_WinnerId: este campo contém o ID de vencedor dos grupos ou clusters identificados. Se Deduplication_WinnerId é o mesmo que o valor da Chave primária para um registo, significa que o registo é o registo vencedor.
- Campos usados para definir as regras de eliminação de duplicados.
- Campos Regra e Pontuação para denotar quais as regras de eliminação de duplicados foram aplicadas e a pontuação devolvida pelo algoritmo correspondente.

## <a name="next-step"></a>Passo Seguinte

- Opcionalmente, para B2B, realize a [unificação do contacto](data-unification-contacts.md).

- Para B2C, configure [atividades](activities.md), [melhoramentos](enrichment-hub.md), [relações](relationships.md) ou [medidas](measures.md) para obter mais informações sobre os seus clientes.

[!INCLUDE[footer-include](includes/footer-banner.md)]

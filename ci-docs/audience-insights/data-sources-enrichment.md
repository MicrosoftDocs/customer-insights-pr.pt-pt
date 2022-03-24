---
title: Melhoramento de origens de dados
description: Melhore as origens de dados antes de passar pelo processo de unificação de dados.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376593"
---
# <a name="enrichment-for-data-sources-preview"></a>Melhoramento de origens de dados (pré-visualização)

Utilize dados de origens como a Microsoft e outros parceiros para melhorar os dados dos seus clientes antes da unificação de dados. Os melhoramentos de origens de dados ajudam a produzir uma maior qualidade e integralidade de dados que podem ajudar a obter melhores resultados quando unificar os seus dados. Por exemplo, a utilização de um formato normalizado e padronizado para os endereços aumenta a qualidade dos resultados de correspondência. Para obter uma lista dos melhoramentos suportados, consulte [opções de melhoramento de origens de dados suportadas](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Melhorar uma origem de dados

Tem de ter as permissões Contribuidor ou Administrador para criar ou editar melhoramentos. Para mais informações, consulte [Permissões](permissions.md).  

1. Vá para **Dados** > **Unificar**. Selecione a entidade que pretende melhorar e selecione um atributo como chave primária para a entidade. Para obter mais informações, consulte [Selecionar chave primária](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Aceda a **Dados** > **Origens de dados**.
 
1. Selecione as reticências verticais junto à origem de dados que pretende melhorar e selecione **Melhorar**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Página de melhoramentos de origens de dados.":::

   O separador **Detetar** apresenta as [opções de melhoramento de origens de dados suportadas](#supported-data-source-enrichments).

1. Selecione **Melhorar os meus dados** para configurar um melhoramento de origens de dados. O nome da entidade de saída é preenchido automaticamente.

## <a name="supported-data-source-enrichments"></a>Melhoramentos de origens de dados suportados

Atualmente, os seguintes melhoramentos estão disponíveis para origens de dados. Reveja os passos detalhados para o melhoramento para saber como configurá-lo.

- [Endereços melhorados](enrichment-enhanced-addresses.md)
- [Dados de empresas melhorados](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Gerir os melhoramentos de origens de dados existentes

Aceda ao separador **Os meus melhoramentos** para ver todos os melhoramentos configurados.

Selecione o enriquecimento para ver as opções disponíveis. Também pode selecionar as reticências (...) num item de lista para ver as opções. Se configurou vários enriquecimentos, pode usar a caixa de pesquisa para encontrá-lo rapidamente.

Pode ver, editar, executar ou eliminar um melhoramento de origens de dados. Para mais informações, consulte [Gerir melhoramentos existentes](enrichment-hub.md).

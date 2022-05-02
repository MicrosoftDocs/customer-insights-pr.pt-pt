---
title: Compreender e gerir medidas
description: Saiba como as medidas ajudam a analisar e a refletir o desempenho da sua empresa.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646825"
---
# <a name="measures-overview"></a>Descrição geral das medidas

As medidas ajudam-no a compreender melhor os comportamentos dos clientes e o desempenho do negócio. Olham para os valores relevantes dos [perfis unificados](data-unification.md). Por exemplo, uma empresa quer ver o *gasto total por cliente* para entender o histórico de compras de um cliente individual ou medir as *vendas totais da empresa* para entender a receita ao nível agregado de todo o negócio.  

As medidas são criadas [utilizando o criador de medidas](measure-builder.md), uma plataforma de consulta de dados com vários operadores e opções simples de mapeamento. Permite filtrar os dados, agrupar os resultados, detetar [caminhos de relações entres entidades](relationships.md) e pré-visualizar a saída. Pode [utilizar modelos predefinidos](measure-templates.md) para configurar eficazmente as medidas habitualmente utilizadas.

Utilize o criador de medidas para planear as atividades empresariais consultando os dados dos clientes e extraindo informações. Por exemplo, criar uma medida de *gasto total por cliente* e *devoluções totais por cliente* ajuda a identificar um grupo de clientes com elevado gasto mas com elevadas devoluções também. Pode [criar um segmento](segments.md) baseado nestas medidas para impulsionar as melhores ações seguintes.

## <a name="manage-your-measures"></a>Gerir as medidas

Pode encontrar a lista de medidas na página **Medidas**.

Encontrará informações sobre o tipo de medida, o criador, data de criação e estado. Quando selecionar uma medida da lista, pode pré-visualizar a saída e transferir um ficheiro CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Ações para gerir medidas únicas."lightbox="media/measures-actions.png":::

As seguintes ações estão disponíveis quando seleciona uma medida:

- **Edite** a configuração da medida.
- **Duplique** uma medida. Pode optar por editar as suas propriedades imediatamente ou simplesmente guardar o duplicado.
- **Atualize** a medida com base nos dados mais recentes. Para atualizar todas as suas medidas ao mesmo tempo, selecione todas as medidas e, em seguida, **Atualize**.
- **Mude o nome** da medida.
- **Ativar** ou **Desativar**. As medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).
- **Etiqueta** para [gerir etiquetas](work-with-tags-columns.md#manage-tags) para o segmento.
- **Elimine** a medição.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Próximo passo

Pode utilizar as medidas existentes para criar [um segmento de cliente](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

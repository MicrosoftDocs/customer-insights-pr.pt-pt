---
title: Compreender e gerir medidas
description: Saiba como as medidas ajudam a analisar e a refletir o desempenho da sua empresa.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359801"
---
# <a name="measures-overview"></a>Descrição geral das medidas

As medidas ajudam-no a compreender melhor os comportamentos dos clientes e o desempenho do negócio. Olham para os valores relevantes dos [perfis unificados](data-unification.md). Por exemplo, uma empresa quer ver o *gasto total por cliente* para entender o histórico de compras de um cliente individual ou medir as *vendas totais da empresa* para entender a receita ao nível agregado de todo o negócio.  

As medidas são criadas [utilizando o criador de medidas](measure-builder.md), uma plataforma de consulta de dados com vários operadores e opções simples de mapeamento. Permite filtrar os dados, agrupar os resultados, detetar [caminhos de relações entres entidades](relationships.md) e pré-visualizar a saída. Pode [utilizar modelos predefinidos](measure-templates.md) para configurar eficazmente as medidas habitualmente utilizadas.

Utilize o criador de medidas para planear as atividades empresariais consultando os dados dos clientes e extraindo informações. Por exemplo, criar uma medida de *gasto total por cliente* e *devoluções totais por cliente* ajuda a identificar um grupo de clientes com elevado gasto mas com elevadas devoluções também. Pode [criar um segmento](segments.md) baseado nestas medidas para impulsionar as melhores ações seguintes. 

## <a name="manage-your-measures"></a>Gerir as medidas

Pode encontrar a lista de medidas na página **Medidas**.

Encontrará informações sobre o tipo de medida, o criador, data de criação e estado. Quando selecionar uma medida da lista, pode pré-visualizar a saída e transferir um ficheiro CSV.

Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.

:::image type="content" source="media/measure-actions.png" alt-text="Ações para gerir medidas únicas.":::

Selecione uma medida da lista para as seguintes opções:

- Selecione o nome da medida para ver os respetivos detalhes.
- **Edite** a configuração da medida.
- **Atualize** a medida com base nos dados mais recentes.
- **Mude o nome** da medida.
- **Elimine** a medição.
- **Ativar** ou **Desativar**. As medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Próximo passo

Pode utilizar as medidas existentes para criar [um segmento de cliente](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]

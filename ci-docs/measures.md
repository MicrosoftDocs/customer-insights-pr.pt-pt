---
title: Descrição geral das medidas
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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170859"
---
# <a name="measures-overview"></a>Descrição geral das medidas

As medidas ajudam-no a compreender melhor os comportamentos dos clientes e o desempenho do negócio. Olham para os valores relevantes dos [perfis unificados](data-unification.md). Por exemplo, uma empresa quer ver o *gasto total por cliente* para entender o histórico de compras de um cliente individual ou medir as *vendas totais da empresa* para entender a receita ao nível agregado de todo o negócio.

Criar medidas para planear as atividades empresariais consultando os dados dos clientes e extraindo informações. Por exemplo, crie uma medida de *gasto total por cliente* e *devoluções totais por cliente* para ajudar a identificar um grupo de clientes com elevado gasto mas com elevadas devoluções também. Em seguida, [crie um segmento](segments.md) baseado nestas medidas para impulsionar as melhores ações seguintes.

## <a name="create-a-measure"></a>Criar uma medida

Escolha como criar uma medida com base na audiência de destino.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- De raiz com o construtor de medidas: [Crie o seu próprio](measure-builder.md).
- A partir de medidas de uso comum: [Utilizar modelos predefinidos](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

De raiz com o construtor de medidas: [Crie o seu próprio](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Gerir medidas existentes

Vá para a página **Medidas** para ver as medidas que criou, o seu estado, tipo de medida e a última vez que os dados foram atualizados. Pode ordenar a lista de medidas por qualquer coluna ou utilizar a caixa de pesquisa para encontrar a medida que pretende gerir.

Selecione junto a uma medida para ver as ações disponíveis. Selecione o nome de medida para pré-visualizar a saída e transferir um ficheiro CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Ações para gerir medidas únicas."lightbox="media/measures-actions.png":::

- **Editar** a medida para alterar as respetivas propriedades.
- **Atualizar** a medida a incluir os dados mais recentes.
- **Mude o nome** da medida.
- **Ativar** ou **desativar** a medida. As medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab) e têm o **Estado** listado como **Ignorado** indicando que uma atualização nem sequer foi tentada.
- **Etiqueta** para [gerir etiquetas](work-with-tags-columns.md#manage-tags) para a medida.
- **Elimine** a medição.
- **Colunas** para [personalizar as colunas](work-with-tags-columns.md#customize-columns) que são apresentadas.
- **Filtrar** para [filtrar em etiquetas](work-with-tags-columns.md#filter-on-tags).
- **Pesquisar nome** para pesquisar por nome de medida.

## <a name="refresh-measures"></a>Atualizar medidas

As medidas podem ser atualizadas com agendamento automático ou atualizadas manualmente a pedido. Para atualizar manualmente uma ou mais medidas, selecione-as e escolha **Atualizar**. Para [agendar uma atualização automática](system.md#schedule-tab), aceda a **Admin** > **Sistema** > **Agendar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Gerir o Índice de pesquisas e filtros para perfis de cliente
description: Encontre rapidamente informações sobre perfis de cliente unificados e filtre por atributos especificados.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187923"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Gerir o Índice de pesquisas e filtros para perfis de cliente

O resultado da unificação dos dados dos clientes é uma entidade *Cliente* que fornece uma vista unificada sobre a base de clientes total. Para os utilizadores rapidamente [localizarem informações num grupo de clientes ou num cliente específico](customer-profiles.md), um administrador tem de configurar as funcionalidades **Procurar** e **Filtrar** para a página **Clientes**.

   :::image type="content" source="media/search-filter.png" alt-text="Filtro de pesquisa":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definir atributos pesquisáveis e campos indexados

Se for a primeira vez que define atributos pesquisáveis enquanto administrador, defina primeiro os campos indexados. Sugerimos que escolha todos os atributos pelos quais os utilizadores podem procurar e filtrar clientes na página **Clientes**. Só é possível especificar os atributos existentes na entidade *Cliente* criada durante o processo de unificação de dados.

1. Vá para **Clientes** e selecione **Índice de pesquisa e filtro**.

1. Selecione **+ Adicionar**.

1. Selecione os atributos na lista que pretende adicionar como campos indexados e clique em **Aplicar**.

1. Para adicionar mais atributos, selecione **Adicionar**. Para remover um atributo selecionado, selecione o atributo e, em seguida, **Eliminar**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Página Índice de pesquisas e filtros":::

1. Selecione **Executar** quando estiver pronto para aplicar as suas definições de pesquisas e filtros. Depois de processadas as alterações, veja-as nos [cartões de cliente na página do Cliente](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definir opções de filtragem para um determinado atributo

Configure os campos que podem ser utilizados para filtrar clientes na página **Clientes**.

1. Vá para **Clientes** e selecione **Índice de pesquisa e filtro**.

1. Selecione um atributo e **Adicionar Filtro**. Defina o número de resultados e a ordem pela qual serão organizados. Consoante o tipo de dados do atributo, aparece um dos seguintes painéis.

   - Atributos de tipo de cadeia: Especifique o número de resultados pretendidos no painel **Filtro de cadeia** e a política de ordenação pela qual serão organizados.

   - Atributos de tipo numérico: Especifique os intervalos incluídos no painel **Filtro de número** e a política de ordenação pela qual serão organizados.

   - Atributos de tipo de data: Especifique os intervalos incluídos no painel **Filtro de data** e a política de ordenação pela qual serão organizados.

1. Selecione **OK**. Repita para todos os atributos pelos quais pretende filtrar.

1. Selecione **Executar** quando estiver pronto para aplicar as suas definições de pesquisas e filtros. Depois de processadas as alterações, veja-as nos [cartões de cliente na página do Cliente](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Ver campos de cliente indexados

A página **Índice de pesquisas e filtros** apresenta as seguintes informações:

- **Nome**: representa o nome do atributo tal como aparece na entidade *Cliente*.
- **Tipo de dados**: especifica se o tipo de dados é uma cadeia de caracteres, um número ou uma data.
- **Incluído na pesquisa**: especifica se este atributo pode ser utilizado para procurar clientes na página **Clientes** através do campo **Clientes**.
- **Adicionar Filtro**: controlo para definir como este atributo pode ser utilizado para filtragens na página **Clientes**.

## <a name="next-steps"></a>Próximos passos

Reveja a [página de perfis unificados](customer-profiles.md) para procurar perfis ou use os campos indexados para ver um subconjunto de todos os perfis unificados.

[!INCLUDE [footer-include](includes/footer-banner.md)]

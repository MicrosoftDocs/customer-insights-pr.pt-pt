---
title: Pesquisar e filtrar perfis de clientes
description: Encontre rapidamente informações sobre perfis de cliente unificados e filtre por atributos especificados.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647084"
---
# <a name="customer-profiles-search--filter-index"></a>Perfis de clientes: índice de pesquisa e de filtro

O resultado da unificação dos dados dos clientes é uma entidade Perfil do Cliente que fornece uma vista unificada sobre a base de clientes total. Para [localizar informações num grupo de clientes ou num cliente específico](customer-profiles.md) rapidamente, poderá configurar as funcionalidades **Procurar** e **Filtrar** na página **Clientes**. Continue a ler para saber como os administradores podem editar a página **Índice de pesquisas e filtros**, disponível para os utilizadores fazerem pesquisas e aplicarem filtros.

   :::image type="content" source="media/search-filter.png" alt-text="Filtro de pesquisa":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Adicionar campos e especificar atributos

Se for a primeira vez que define atributos pesquisáveis enquanto administrador, primeiro tem de definir campos indexados. Sugerimos que escolha todos os atributos pelos quais os utilizadores podem procurar e filtrar clientes na página **Clientes**. Só pode especificar os atributos existentes na entidade Perfil de Cliente que criou durante o processo de unificação de dados.

1. Abra a página **Clientes** e selecione **Índice de pesquisa e filtro**.

2. Selecione **+ Adicionar** para especificar os campos indexados.

3. Selecione os atributos na lista que pretende adicionar como campos indexados. Pode sempre adicionar mais atributos ao selecionar **Adicionar**. Também pode remover quaisquer atributos selecionados selecionando o símbolo **Remover**.

## <a name="explore-the-indexed-customer-fields-table"></a>Explorar a tabela campos de cliente indexados

São apresentadas na tabela as seguintes informações.

- **Nome**: representa o nome do atributo tal como aparece na entidade Perfil de Cliente.
- **Tipo de dados**: especifica se o tipo de dados é uma cadeia de caracteres, um número ou uma data.
- **Incluído na pesquisa**: especifica se este atributo pode ser utilizado para procurar clientes na página **Clientes** através do campo **Clientes**.
- **Adicionar Filtro**: controlo para definir como este atributo pode ser utilizado para filtragens na página **Clientes**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Editar opções de filtragem para um determinado atributo

O menu **Filtro** na página **Clientes** pode incluir um número variável de níveis de atributos (por exemplo, diferentes grupos etários pelos quais filtrar os clientes).

1. Selecione **Adicionar Filtro** para um determinado atributo na página **Índice de pesquisas e filtros**. Pode definir o número de resultados e a ordem pela qual serão organizados. Consoante o tipo de dados do atributo, aparece um dos seguintes painéis.

- Atributos de tipo de cadeia: Especifique o número de resultados pretendidos no painel **Opções de filtro de cadeia** e a política de ordenação pela qual serão organizados.

- Atributos de tipo numérico: Especifique os intervalos incluídos no painel **Opções de filtro de número** e a política de ordenação pela qual serão organizados.

- Atributos de tipo de data: Especifique os intervalos incluídos no painel **Opções de filtro de data** e a política de ordenação pela qual serão organizados.

2. Selecione **Guardar** para aplicar as alterações.

3. Selecione **Executar** quando estiver pronto para aplicar as suas definições. Depois de processadas as alterações, encontra-as nos [cartões de cliente na página do Cliente](customer-profiles.md). 

## <a name="next-steps"></a>Passos seguintes

Reveja a [página de perfis unificados](customer-profiles.md) para procurar perfis ou use os campos indexados para ver um subconjunto de todos os perfis unificados.


[!INCLUDE [footer-include](includes/footer-banner.md)]
---
title: Pesquisar e filtrar perfis de clientes
description: Encontre rapidamente informações sobre perfis de cliente unificados e filtre por atributos especificados.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406652"
---
# <a name="customer-profiles-search--filter-index"></a>Perfis de clientes: índice de pesquisa e de filtro

O resultado da unificação dos dados dos clientes é uma entidade Perfil do Cliente que fornece uma vista unificada sobre a base de clientes total. Para [localizar informações num grupo de clientes ou num cliente específico](customer-profiles.md) rapidamente, poderá configurar as funcionalidades **Procurar** e **Filtrar** na página **Clientes**. Continue a ler para saber como os administradores podem editar a página **Índice de pesquisas e filtros**, disponível para os utilizadores fazerem pesquisas e aplicarem filtros.

> [!div class="mx-imgBorder"]
> ![Filtro de pesquisa](media/search-filter.png "Filtro de pesquisa")

## <a name="add-fields-and-specify-attributes"></a>Adicionar campos e especificar atributos

Se for a primeira vez que define atributos pesquisáveis enquanto administrador, primeiro tem de definir campos indexados. Sugerimos que escolha todos os atributos pelos quais os utilizadores podem procurar e filtrar clientes na página **Clientes**. Só pode especificar os atributos existentes na entidade Perfil de Cliente que criou durante o processo de unificação de dados.

1. Abra a página **Clientes** e selecione **Índice de pesquisa e filtro**.

> [!NOTE]
> Criamos uma configuração de índice de pesquisa predefinida nos atributos disponíveis na entidade Cliente a partir dos seguintes tipos semânticos, tal como definidos na página do Mapa.
> - Nome próprio, Apelido, Segundo nome, Nome Completo da pessoa
> - Nome da Organização
> - Endereço de Correio Eletrónico
> - Número de telefone
> - Informações de localização

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

3. Selecione **Executar** quando estiver pronto para aplicar as suas definições.

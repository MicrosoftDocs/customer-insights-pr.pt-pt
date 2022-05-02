---
title: Ver perfis de cliente
description: Obtenha uma visão combinada dos seus dados unificados de clientes.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 45ef6abcd612178a097569825e32ff9ac779de01
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646590"
---
# <a name="customer-profiles"></a>Perfis de cliente

A página **Clientes** mostra uma visão combinada dos seus perfis de clientes unificados. Os perfis de clientes estão disponíveis assim que [tiver criado a entidade Cliente unificada](data-unification.md). A página permite-lhe procurar clientes e definir o índice para essa pesquisa.

Os clientes podem ser indivíduos ou organizações. Cada perfil do cliente é representado por um mosaico. Utilize os controlos de paginação para obter mais registos. O cartão apresenta campos da entidade *Cliente*, tal como definido no **Índice de pesquisas e filtros**. A ordem dos campos dentro de cada cartão é selecionada pelo sistema.

Selecione um mosaico para ver os dados do cliente selecionado numa página dedicada chamada [página de detalhes do Cliente](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Página Clientes a mostrar mosaicos de resultados](media/customers-page-result-tiles-B2C.png "Página Clientes a mostrar mosaicos de resultados")

> [!NOTE]
> Se não conseguir ver os mosaicos quando seleciona **Clientes** na navegação, o seu administrador precisa de [definir, pelo menos, um atributo pesquisável](search-filter-index.md) no **Índice de pesquisas e filtros**.

## <a name="search-for-customers"></a>Procurar clientes

Procure clientes ao inserir um nome ou algum outro atributo na caixa de pesquisa. A pesquisa apenas funciona dentro da entidade _Cliente_ criada durante o processo de unificação de dados.

Como administrador, pode configurar os atributos pesquisáveis através da página **Índice de pesquisas e filtros**. Para obter mais informações, aceda a [Gerir índice de pesquisas e filtros](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar clientes

Pode filtrar os clientes pelos campos da entidade _Cliente_. Semelhante à pesquisa, primeiro o seu administrador terá de definir os campos como filtráveis através da página **Índice de pesquisas e filtros**.

1. Selecione **Mostrar filtros** na página **Clientes**.

1. Marque as caixas junto aos atributos pelos quais pretende filtrar os clientes.

1. Retire os seus filtros, selecionando **Limpar filtros** na página **Clientes**.

## <a name="customer-details-page"></a>Página detalhes do cliente

Selecione qualquer um dos mosaicos do cliente para abrir a **Página de detalhes do cliente**. Esta vista contém informação unificada para o cliente selecionado. Os detalhes do cliente incluem o seguinte conteúdo:

**Mosaico do perfil do cliente**: este mosaico mostra os diferentes valores da entidade _Cliente_ unificada. Se um campo não tiver valor para o perfil do cliente selecionado, não aparecerá. O mosaico é estruturado em secções:  
  - A primeira secção mostra um conjunto de campos predefinidos seguidos por todos os campos que fazem parte do índice de pesquisas e filtros. Todos os campos relacionados com endereços são combinados numa única linha se o perfil contiver esses campos. 
  - **Contactos para este cliente**: em ambientes para contas empresariais, verá todos os contactos relacionados para este cliente como a segunda secção. Cada contacto é mostrado com os respetivos campos. Os campos vazios estão ocultos.
  - **Campos adicionais**: mostra os campos restantes do cliente selecionado, exceto IDs. 
  - **IDs**: lista todos os IDs com o nome da entidade correspondente. Os campos são identificados como IDs pela sua semântica, que os classificam como tal.

**Linha cronológica da atividade**: mostra dados se tiver atividades configuradas. A vista da linha cronológica contém atividades cronologicamente ordenadas do cliente selecionado, começando pela atividade mais recente. Para mais informações, aceda a [Atividades do cliente](activities.md).

**Informações**:  
  - **Medidas**: mostra se configurou uma ou mais medidas de atributos do cliente. Incluem os KPIs calculados em torno dos seus clientes a nível do cliente individual. Para mais informações, aceda a [Definir e gerir medidas](measures.md).

  - **Interesses potenciais, marcas potenciais**: mostra se configurou um melhoramento de afinidade de marca e interesses. Representa interesses e afinidades potenciais para marcas baseadas em outros clientes cujo perfil é semelhante ao perfil do cliente selecionado. Para mais informações, aceda ao [Melhorar perfis dos clientes com afinidades de marca e interesses](enrichment-microsoft.md).

Para voltar à página de pesquisa do cliente, selecione **Voltar a Clientes**.

## <a name="next-steps"></a>Passos seguintes

[Adicione mais origens de dados](data-sources.md), [melhore perfis unificados](enrichment-hub.md) ou [crie segmentos](segments.md) para trabalhar com perfis de clientes unificados noutras aplicações.


[!INCLUDE [footer-include](includes/footer-banner.md)]

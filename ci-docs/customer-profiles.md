---
title: Ver perfis de cliente
description: Ver os dados unificados do cliente, incluindo a utilização de pesquisa e filtro
ms.date: 06/08/2022
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188107"
---
# <a name="view-customer-profiles"></a>Ver perfis de cliente

Os perfis de cliente estão disponíveis depois de [criar a entidade *Cliente* unificada](data-unification.md). A vista combinada dos seus perfis de cliente unificados é apresentada na página **Clientes**. Os clientes podem ser indivíduos ou organizações.

Vá para a página **Clientes** para ver os seus clientes e os respectivos perfis. Cada perfil do cliente é representado por um mosaico. Utilize os controlos de paginação para obter mais registos. O cartão apresenta campos da entidade *Cliente*, tal como definido no **Índice de pesquisas e filtros**. A ordem dos campos dentro de cada cartão é selecionada pelo sistema.

> [!NOTE]
> Se não conseguir ver os mosaicos quando seleciona **Clientes**, o seu administrador precisa de [definir, pelo menos, um atributo pesquisável](search-filter-index.md) no **Índice de pesquisas e filtros**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Página Clientes a mostrar mosaicos de resultados.":::

Selecione qualquer uma das seguintes ações:
- [Ver detalhes do cliente](#view-customer-details)
- [Gerir o índice de Procurar e Filtrar](search-filter-index.md) (apenas administradores)
- [Filtrar clientes](#filter-customers)
- **Expandir cartões** ou **Fechar cartões** para expandir ou fechar as informações apresentadas no mosaico do cliente
- **Ordenar por** um atributo específico
- [Procurar clientes](#search-for-customers)

  > [!NOTE]
  > Para utilizar Procurar e Filtrar, um administrador tem de configurar os atributos pesquisáveis e definir os campos filtrados utilizando o índice Procurar e Filtrar.

## <a name="search-for-customers"></a>Procurar clientes

Procure clientes ao inserir um nome ou algum outro atributo em **Procurar clientes**. Os atributos pesquisáveis são definidos pelo administrador e têm origem da entidade *Cliente* unificada.

> [!NOTE]
> **Cadeia** é o único tipo de dados incluído na pesquisa. Utilize-o no campo **Procurar clientes** na página Clientes para procurar clientes.

## <a name="filter-customers"></a>Filtrar clientes

Filtre os clientes pelos campos da entidade *Cliente*. Os campos filtrados são definidos pelo administrador.

1. Na página **Clientes**, selecione **Mostrar filtros**. É apresentado o painel Filtro.

1. Marque as caixas junto aos atributos pelos quais pretende filtrar os clientes.

1. Remova todos os filtros ao selecionar **Limpar filtros** ou ao desmarcar uma caixa de verificação junto a um atributo selecionado.

1. Selecione **Ocultar filtros** para fechar o painel de filtro.

1. Para guardar os resultados de filtro como um [segmento](segments.md), selecione **Guardar filtros como segmento**.
   1. Introduza um nome para o segmento
   1. Selecione **Guardar** para guardar o segmento.
   1. Escolha se pretende executar agora ao selecionar **Ativar** ou ao executá-lo **Mais Tarde**.

## <a name="view-customer-details"></a>Ver detalhes do cliente

Na página **Clientes**, selecione um mosaico de cliente para ver os detalhes para o cliente selecionado.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Página de detalhes do cliente.":::

Detalhes do cliente incluem:

**Mosaico do perfil do cliente**: mostra os diferentes valores da entidade *Cliente* unificada. Se um campo não tiver valor para o perfil do cliente selecionado, não aparecerá, exceto para o campo de endereço. O mosaico é estruturado em secções:

- A primeira secção mostra um conjunto de campos predefinidos seguidos por todos os campos que fazem parte do índice de pesquisas e filtros. Todos os campos relacionados com endereços são combinados numa única linha, o que é mostrado mesmo se o perfil não contiver informações de endereço.
- **Contactos para este cliente** aparece em ambientes para contas empresariais. Cada contacto é mostrado com os respetivos campos. Os campos vazios estão ocultos.
- **Campos adicionais**: mostra os campos restantes do cliente selecionado, exceto IDs.
- **IDs**: lista todos os IDs com o nome da entidade correspondente. Os campos são identificados como IDs pela respetiva semântica.

**Linha cronológica da atividade** mostra dados se tiver [atividades](activities.md) configuradas. A vista da linha cronológica contém atividades cronologicamente ordenadas do cliente selecionado, começando pela atividade mais recente.

**Informações**:

- **Medidas** mostra se configurou [medidas de atributo de cliente](measures.md) configuradas. Incluem os KPIs calculados em torno dos seus clientes a nível do cliente individual.

- **Interesses potenciais, marcas potenciais** mostra se configurou um [melhoramento de afinidade de marca e interesses](enrichment-microsoft.md). Representa interesses e afinidades potenciais para marcas baseadas em outros clientes cujo perfil é semelhante ao perfil do cliente selecionado.

Para regressar à página **Clientes**, selecione **Voltar a Clientes**.

## <a name="next-steps"></a>Próximos passos

[Adicione mais origens de dados](data-sources.md), [melhore perfis unificados](enrichment-hub.md) ou [crie segmentos](segments.md) para trabalhar com perfis de clientes unificados noutras aplicações.

[!INCLUDE [footer-include](includes/footer-banner.md)]

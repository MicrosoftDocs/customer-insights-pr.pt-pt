---
title: Ver perfis de cliente
description: Obtenha uma visão combinada dos seus dados unificados de clientes.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8ab55d101f98169b8f794ce580ddd0a71ede6642
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554632"
---
# <a name="customer-profiles"></a>Perfis de cliente

A página **Clientes** mostra uma visão combinada dos seus clientes, com base em dados de perfil recolhidos a partir [todas as origens de dados](data-sources.md). Os perfis de cliente estão disponíveis depois de [criar a entidade Cliente unificado](data-unification.md). Certifique-se de que conclui o processo de unificação de dados para obter visões mais avançadas dos seus clientes. A página também permite procurar clientes.

Os clientes podem ser indivíduos ou organizações (Pré-visualização). Cada perfil de cliente ou organização é representado por um mosaico. Selecione um mosaico para ver informações adicionais sobre esse cliente ou organização específica. Utilize os controlos de paginação na parte inferior da página para ver registos adicionais.

> [!div class="mx-imgBorder"] 
> ![Perfis de cliente B2C.](media/profiles-customers.png "Perfis de cliente B2C")

Organizações (Pré-visualização)
> [!div class="mx-imgBorder"] 
> ![Perfis de cliente B2B](media/profile-customers-b2b.png "Perfis de cliente B2B")

> [!NOTE]
> Se não conseguir ver os mosaicos quando seleciona **Clientes** na navegação, o seu administrador terá de [definir, pelo menos, um atributo pesquisável](search-filter-index.md) no **Índice de pesquisas e filtros**.

## <a name="search-for-customers"></a>Procurar clientes

Procure clientes ao inserir um nome ou algum outro atributo na caixa de pesquisa. A pesquisa só funciona dentro da entidade Perfil de Cliente criada durante o processo de unificação de dados.

Como administrador, pode configurar os atributos pesquisáveis através da página **Índice de pesquisas e filtros**. Para mais informações, consulte [Gerir Índice de pesquisas e filtros](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar clientes

Poderá filtrar os clientes pelos campos da entidade Perfil de Cliente. Semelhante à pesquisa, primeiro o seu administrador terá de definir os campos como filtráveis através da página **Índice de pesquisas e filtros**.

1. Selecione **Filtrar** na página **Clientes**.

2. Marque as caixas junto aos atributos pelos quais pretende filtrar os clientes.

   > [!div class="mx-imgBorder"] 
   > ![Perfis de cliente.](media/profiles-customers3.png "Perfis de cliente")

3. Retire os seus filtros, selecionando **Limpar filtros** na página **Clientes**.

##  <a name="customer-details-page"></a>Página detalhes do cliente

Selecione qualquer um dos mosaicos do cliente para abrir a **Página de detalhes do cliente**. Esta vista contém informação unificada para o cliente selecionado.

Detalhes do cliente incluem:

-   **Mosaico de perfil de cliente**: este mosaico mostra os diferentes valores da entidade unificada de perfil de cliente. Estes detalhes podem incluir endereço de e-mail, nome, cidade, e assim por diante. 

-   **Potenciais interesses, potenciais marcas**: mostra se foi configurado um melhoramento de primeira parte. Representa interesses e afinidades potenciais para marcas que um cliente com um perfil semelhante a este cliente possa ter. Para mais informações, consulte [Enriquecer perfis de clientes com afinidades de marca e interesse](enrichment-microsoft.md).

-   **Medidas**: mostra se configurou uma ou mais medidas de um tipo específico: medidas de atributos do cliente. Incluem os KPIs calculados em torno dos seus clientes a nível do cliente individual. Para mais informações, consulte [Definir e gerir medidas](measures.md).

-   **Cronologia da atividade**: mostra se tem atividades configuradas. A vista da cronologia contém as atividades deste cliente ordenadas cronologicamente, começando pela atividade mais recente. Para mais informações, veja [Atividades de cliente](activities.md).

Selecione **Voltar aos clientes** para voltar à página de pesquisa de clientes.

## <a name="next-steps"></a>Passos seguintes

[Adicionar mais origens de dados](data-sources.md) ou [criar segmentos de clientes](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

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
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896341"
---
# <a name="customer-profiles"></a><span data-ttu-id="a9404-103">Perfis de cliente</span><span class="sxs-lookup"><span data-stu-id="a9404-103">Customer profiles</span></span>

<span data-ttu-id="a9404-104">A página **Clientes** mostra uma visão combinada dos seus clientes, com base em dados de perfil recolhidos a partir [todas as origens de dados](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="a9404-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="a9404-105">Os perfis de cliente estão disponíveis depois de [criar a entidade Cliente unificado](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a9404-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="a9404-106">Certifique-se de que conclui o processo de unificação de dados para obter visões mais avançadas dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="a9404-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="a9404-107">A página também permite procurar clientes.</span><span class="sxs-lookup"><span data-stu-id="a9404-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="a9404-108">Os clientes podem ser indivíduos ou organizações (Pré-visualização).</span><span class="sxs-lookup"><span data-stu-id="a9404-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="a9404-109">Cada perfil de cliente ou organização é representado por um mosaico.</span><span class="sxs-lookup"><span data-stu-id="a9404-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="a9404-110">Selecione um mosaico para ver informações adicionais sobre esse cliente ou organização específica.</span><span class="sxs-lookup"><span data-stu-id="a9404-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="a9404-111">Utilize os controlos de paginação na parte inferior da página para ver registos adicionais.</span><span class="sxs-lookup"><span data-stu-id="a9404-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="a9404-112">![Perfis de cliente B2C](media/profiles-customers.png "Perfis de cliente B2C")</span><span class="sxs-lookup"><span data-stu-id="a9404-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="a9404-113">Organizações (Pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="a9404-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="a9404-114">![Perfis de cliente B2B](media/profile-customers-b2b.png "Perfis de cliente B2B")</span><span class="sxs-lookup"><span data-stu-id="a9404-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="a9404-115">Se não conseguir ver os mosaicos quando seleciona **Clientes** na navegação, o seu administrador terá de [definir, pelo menos, um atributo pesquisável](search-filter-index.md) no **Índice de pesquisas e filtros**.</span><span class="sxs-lookup"><span data-stu-id="a9404-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="a9404-116">Procurar clientes</span><span class="sxs-lookup"><span data-stu-id="a9404-116">Search for customers</span></span>

<span data-ttu-id="a9404-117">Procure clientes ao inserir um nome ou algum outro atributo na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a9404-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="a9404-118">A pesquisa só funciona dentro da entidade Perfil de Cliente criada durante o processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="a9404-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="a9404-119">Como administrador, pode configurar os atributos pesquisáveis através da página **Índice de pesquisas e filtros**.</span><span class="sxs-lookup"><span data-stu-id="a9404-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="a9404-120">Para mais informações, consulte [Gerir Índice de pesquisas e filtros](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="a9404-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="a9404-121">Filtrar clientes</span><span class="sxs-lookup"><span data-stu-id="a9404-121">Filter customers</span></span>

<span data-ttu-id="a9404-122">Poderá filtrar os clientes pelos campos da entidade Perfil de Cliente.</span><span class="sxs-lookup"><span data-stu-id="a9404-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="a9404-123">Semelhante à pesquisa, primeiro o seu administrador terá de definir os campos como filtráveis através da página **Índice de pesquisas e filtros**.</span><span class="sxs-lookup"><span data-stu-id="a9404-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="a9404-124">Selecione **Filtrar** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="a9404-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="a9404-125">Marque as caixas junto aos atributos pelos quais pretende filtrar os clientes.</span><span class="sxs-lookup"><span data-stu-id="a9404-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="a9404-126">![Perfis de cliente](media/profiles-customers3.png "Perfis de cliente")</span><span class="sxs-lookup"><span data-stu-id="a9404-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="a9404-127">Retire os seus filtros, selecionando **Limpar filtros** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="a9404-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="a9404-128">Página detalhes do cliente</span><span class="sxs-lookup"><span data-stu-id="a9404-128">Customer details page</span></span>

<span data-ttu-id="a9404-129">Selecione qualquer um dos mosaicos do cliente para abrir a **Página de detalhes do cliente**.</span><span class="sxs-lookup"><span data-stu-id="a9404-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="a9404-130">Esta vista contém informação unificada para o cliente selecionado.</span><span class="sxs-lookup"><span data-stu-id="a9404-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="a9404-131">Detalhes do cliente incluem:</span><span class="sxs-lookup"><span data-stu-id="a9404-131">Customer details include:</span></span>

-   <span data-ttu-id="a9404-132">**Mosaico de perfil de cliente:** Este mosaico mostra os diferentes valores da entidade unificada de perfil de cliente.</span><span class="sxs-lookup"><span data-stu-id="a9404-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="a9404-133">Estes detalhes podem incluir endereço de e-mail, nome, cidade, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a9404-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="a9404-134">**Potenciais interesses, potenciais marcas:** Mostra se foi configurado um enriquecimento de primera parte.</span><span class="sxs-lookup"><span data-stu-id="a9404-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="a9404-135">Representa interesses e afinidades potenciais para marcas que um cliente com um perfil semelhante a este cliente possa ter.</span><span class="sxs-lookup"><span data-stu-id="a9404-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="a9404-136">Para mais informações, consulte [Enriquecer perfis de clientes com afinidades de marca e interesse](enrichment-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="a9404-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="a9404-137">**Medidas:** Mostra se configurou uma ou mais medidas de um tipo específico: medidas de atributos do cliente.</span><span class="sxs-lookup"><span data-stu-id="a9404-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="a9404-138">Incluem os KPIs calculados em torno dos seus clientes a nível do cliente individual.</span><span class="sxs-lookup"><span data-stu-id="a9404-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="a9404-139">Para mais informações, consulte [Definir e gerir medidas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="a9404-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="a9404-140">**Cronologia da actividade:** Mostra se tem atividades configuradas.</span><span class="sxs-lookup"><span data-stu-id="a9404-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="a9404-141">A vista da cronologia contém as atividades deste cliente ordenadas cronologicamente, começando pela atividade mais recente.</span><span class="sxs-lookup"><span data-stu-id="a9404-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="a9404-142">Para mais informações, veja [Atividades de cliente](activities.md).</span><span class="sxs-lookup"><span data-stu-id="a9404-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="a9404-143">Selecione **Voltar aos clientes** para voltar à página de pesquisa de clientes.</span><span class="sxs-lookup"><span data-stu-id="a9404-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9404-144">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="a9404-144">Next steps</span></span>

<span data-ttu-id="a9404-145">[Adicionar mais origens de dados](data-sources.md) ou [criar segmentos de clientes](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a9404-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
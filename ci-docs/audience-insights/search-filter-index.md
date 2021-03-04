---
title: Pesquisar e filtrar perfis de clientes
description: Encontre rapidamente informações sobre perfis de cliente unificados e filtre por atributos especificados.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270080"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="77bea-103">Perfis de clientes: índice de pesquisa e de filtro</span><span class="sxs-lookup"><span data-stu-id="77bea-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="77bea-104">O resultado da unificação dos dados dos clientes é uma entidade Perfil do Cliente que fornece uma vista unificada sobre a base de clientes total.</span><span class="sxs-lookup"><span data-stu-id="77bea-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="77bea-105">Para [localizar informações num grupo de clientes ou num cliente específico](customer-profiles.md) rapidamente, poderá configurar as funcionalidades **Procurar** e **Filtrar** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="77bea-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="77bea-106">Continue a ler para saber como os administradores podem editar a página **Índice de pesquisas e filtros**, disponível para os utilizadores fazerem pesquisas e aplicarem filtros.</span><span class="sxs-lookup"><span data-stu-id="77bea-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77bea-107">![Filtro de pesquisa](media/search-filter.png "Filtro de pesquisa")</span><span class="sxs-lookup"><span data-stu-id="77bea-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="77bea-108">Adicionar campos e especificar atributos</span><span class="sxs-lookup"><span data-stu-id="77bea-108">Add fields and specify attributes</span></span>

<span data-ttu-id="77bea-109">Se for a primeira vez que define atributos pesquisáveis enquanto administrador, primeiro tem de definir campos indexados.</span><span class="sxs-lookup"><span data-stu-id="77bea-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="77bea-110">Sugerimos que escolha todos os atributos pelos quais os utilizadores podem procurar e filtrar clientes na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="77bea-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="77bea-111">Só pode especificar os atributos existentes na entidade Perfil de Cliente que criou durante o processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="77bea-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="77bea-112">Abra a página **Clientes** e selecione **Índice de pesquisa e filtro**.</span><span class="sxs-lookup"><span data-stu-id="77bea-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="77bea-113">Selecione **+ Adicionar** para especificar os campos indexados.</span><span class="sxs-lookup"><span data-stu-id="77bea-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="77bea-114">Selecione os atributos na lista que pretende adicionar como campos indexados.</span><span class="sxs-lookup"><span data-stu-id="77bea-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="77bea-115">Pode sempre adicionar mais atributos ao selecionar **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="77bea-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="77bea-116">Também pode remover quaisquer atributos selecionados selecionando o símbolo **Remover**.</span><span class="sxs-lookup"><span data-stu-id="77bea-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="77bea-117">Explorar a tabela campos de cliente indexados</span><span class="sxs-lookup"><span data-stu-id="77bea-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="77bea-118">São apresentadas na tabela as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="77bea-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="77bea-119">**Nome**: representa o nome do atributo tal como aparece na entidade Perfil de Cliente.</span><span class="sxs-lookup"><span data-stu-id="77bea-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="77bea-120">**Tipo de dados**: especifica se o tipo de dados é uma cadeia de caracteres, um número ou uma data.</span><span class="sxs-lookup"><span data-stu-id="77bea-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="77bea-121">**Incluído na pesquisa**: especifica se este atributo pode ser utilizado para procurar clientes na página **Clientes** através do campo **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="77bea-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="77bea-122">**Adicionar Filtro**: controlo para definir como este atributo pode ser utilizado para filtragens na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="77bea-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="77bea-123">Editar opções de filtragem para um determinado atributo</span><span class="sxs-lookup"><span data-stu-id="77bea-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="77bea-124">O menu **Filtro** na página **Clientes** pode incluir um número variável de níveis de atributos (por exemplo, diferentes grupos etários pelos quais filtrar os clientes).</span><span class="sxs-lookup"><span data-stu-id="77bea-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="77bea-125">Selecione **Adicionar Filtro** para um determinado atributo na página **Índice de pesquisas e filtros**.</span><span class="sxs-lookup"><span data-stu-id="77bea-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="77bea-126">Pode definir o número de resultados e a ordem pela qual serão organizados.</span><span class="sxs-lookup"><span data-stu-id="77bea-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="77bea-127">Consoante o tipo de dados do atributo, aparece um dos seguintes painéis.</span><span class="sxs-lookup"><span data-stu-id="77bea-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="77bea-128">Atributos de tipo de cadeia: Especifique o número de resultados pretendidos no painel **Opções de filtro de cadeia** e a política de ordenação pela qual serão organizados.</span><span class="sxs-lookup"><span data-stu-id="77bea-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="77bea-129">Atributos de tipo numérico: Especifique os intervalos incluídos no painel **Opções de filtro de número** e a política de ordenação pela qual serão organizados.</span><span class="sxs-lookup"><span data-stu-id="77bea-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="77bea-130">Atributos de tipo de data: Especifique os intervalos incluídos no painel **Opções de filtro de data** e a política de ordenação pela qual serão organizados.</span><span class="sxs-lookup"><span data-stu-id="77bea-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="77bea-131">Selecione **Guardar** para aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="77bea-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="77bea-132">Selecione **Executar** quando estiver pronto para aplicar as suas definições.</span><span class="sxs-lookup"><span data-stu-id="77bea-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="77bea-133">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="77bea-133">Next steps</span></span>

<span data-ttu-id="77bea-134">Vá à página **Clientes** para procurar perfis de clientes ou utilize os campos indexados para ver um subconjunto de todos os perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="77bea-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
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
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="8cf16-103">Perfis de clientes: índice de pesquisa e de filtro</span><span class="sxs-lookup"><span data-stu-id="8cf16-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="8cf16-104">O resultado da unificação dos dados dos clientes é uma entidade Perfil do Cliente que fornece uma vista unificada sobre a base de clientes total.</span><span class="sxs-lookup"><span data-stu-id="8cf16-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="8cf16-105">Para [localizar informações num grupo de clientes ou num cliente específico](customer-profiles.md) rapidamente, poderá configurar as funcionalidades **Procurar** e **Filtrar** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="8cf16-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="8cf16-106">Continue a ler para saber como os administradores podem editar a página **Índice de pesquisas e filtros**, disponível para os utilizadores fazerem pesquisas e aplicarem filtros.</span><span class="sxs-lookup"><span data-stu-id="8cf16-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8cf16-107">![Filtro de pesquisa](media/search-filter.png "Filtro de pesquisa")</span><span class="sxs-lookup"><span data-stu-id="8cf16-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="8cf16-108">Adicionar campos e especificar atributos</span><span class="sxs-lookup"><span data-stu-id="8cf16-108">Add fields and specify attributes</span></span>

<span data-ttu-id="8cf16-109">Se for a primeira vez que define atributos pesquisáveis enquanto administrador, primeiro tem de definir campos indexados.</span><span class="sxs-lookup"><span data-stu-id="8cf16-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="8cf16-110">Sugerimos que escolha todos os atributos pelos quais os utilizadores podem procurar e filtrar clientes na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="8cf16-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="8cf16-111">Só pode especificar os atributos existentes na entidade Perfil de Cliente que criou durante o processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="8cf16-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="8cf16-112">Abra a página **Clientes** e selecione **Índice de pesquisa e filtro**.</span><span class="sxs-lookup"><span data-stu-id="8cf16-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf16-113">Criamos uma configuração de índice de pesquisa predefinida nos atributos disponíveis na entidade Cliente a partir dos seguintes tipos semânticos, tal como definidos na página do Mapa.</span><span class="sxs-lookup"><span data-stu-id="8cf16-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="8cf16-114">Nome próprio, Apelido, Segundo nome, Nome Completo da pessoa</span><span class="sxs-lookup"><span data-stu-id="8cf16-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="8cf16-115">Nome da Organização</span><span class="sxs-lookup"><span data-stu-id="8cf16-115">Organization Name</span></span>
> - <span data-ttu-id="8cf16-116">Endereço de Correio Eletrónico</span><span class="sxs-lookup"><span data-stu-id="8cf16-116">Email address</span></span>
> - <span data-ttu-id="8cf16-117">Número de telefone</span><span class="sxs-lookup"><span data-stu-id="8cf16-117">Phone number</span></span>
> - <span data-ttu-id="8cf16-118">Informações de localização</span><span class="sxs-lookup"><span data-stu-id="8cf16-118">Location information</span></span>

2. <span data-ttu-id="8cf16-119">Selecione **+ Adicionar** para especificar os campos indexados.</span><span class="sxs-lookup"><span data-stu-id="8cf16-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="8cf16-120">Selecione os atributos na lista que pretende adicionar como campos indexados.</span><span class="sxs-lookup"><span data-stu-id="8cf16-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="8cf16-121">Pode sempre adicionar mais atributos ao selecionar **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8cf16-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="8cf16-122">Também pode remover quaisquer atributos selecionados selecionando o símbolo **Remover**.</span><span class="sxs-lookup"><span data-stu-id="8cf16-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="8cf16-123">Explorar a tabela campos de cliente indexados</span><span class="sxs-lookup"><span data-stu-id="8cf16-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="8cf16-124">São apresentadas na tabela as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="8cf16-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="8cf16-125">**Nome**: representa o nome do atributo tal como aparece na entidade Perfil de Cliente.</span><span class="sxs-lookup"><span data-stu-id="8cf16-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="8cf16-126">**Tipo de dados**: especifica se o tipo de dados é uma cadeia de caracteres, um número ou uma data.</span><span class="sxs-lookup"><span data-stu-id="8cf16-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="8cf16-127">**Incluído na pesquisa**: especifica se este atributo pode ser utilizado para procurar clientes na página **Clientes** através do campo **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="8cf16-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="8cf16-128">**Adicionar Filtro**: controlo para definir como este atributo pode ser utilizado para filtragens na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="8cf16-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="8cf16-129">Editar opções de filtragem para um determinado atributo</span><span class="sxs-lookup"><span data-stu-id="8cf16-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="8cf16-130">O menu **Filtro** na página **Clientes** pode incluir um número variável de níveis de atributos (por exemplo, diferentes grupos etários pelos quais filtrar os clientes).</span><span class="sxs-lookup"><span data-stu-id="8cf16-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="8cf16-131">Selecione **Adicionar Filtro** para um determinado atributo na página **Índice de pesquisas e filtros**.</span><span class="sxs-lookup"><span data-stu-id="8cf16-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="8cf16-132">Pode definir o número de resultados e a ordem pela qual serão organizados.</span><span class="sxs-lookup"><span data-stu-id="8cf16-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="8cf16-133">Consoante o tipo de dados do atributo, aparece um dos seguintes painéis.</span><span class="sxs-lookup"><span data-stu-id="8cf16-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="8cf16-134">Atributos de tipo de cadeia: Especifique o número de resultados pretendidos no painel **Opções de filtro de cadeia** e a política de ordenação pela qual serão organizados.</span><span class="sxs-lookup"><span data-stu-id="8cf16-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="8cf16-135">Atributos de tipo numérico: Especifique os intervalos incluídos no painel **Opções de filtro de número** e a política de ordenação pela qual serão organizados.</span><span class="sxs-lookup"><span data-stu-id="8cf16-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="8cf16-136">Atributos de tipo de data: Especifique os intervalos incluídos no painel **Opções de filtro de data** e a política de ordenação pela qual serão organizados.</span><span class="sxs-lookup"><span data-stu-id="8cf16-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="8cf16-137">Selecione **Guardar** para aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="8cf16-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="8cf16-138">Selecione **Executar** quando estiver pronto para aplicar as suas definições.</span><span class="sxs-lookup"><span data-stu-id="8cf16-138">Select **Run** once you're ready to apply your settings.</span></span>

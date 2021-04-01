---
title: Conector do Power Apps
description: Ligar com o Power Apps e Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598169"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="bb460-103">Conector do Microsoft Power Apps (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="bb460-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="bb460-104">Integre os perfis de clientes unificados nas suas aplicações personalizadas com o Power Apps.</span><span class="sxs-lookup"><span data-stu-id="bb460-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="bb460-105">Ligar ao Power Apps e a Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="bb460-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="bb460-106">O Customer Insights é uma das muitas [origens disponíveis para os dados no Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="bb460-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="bb460-107">Consulte a documentação do Power Apps para saber como [adicionar uma ligação de dados a uma aplicação](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="bb460-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="bb460-108">Recomendamos que também reveja [como o Power Apps usa a delegação usa para lidar com grandes conjuntos de dados em Aplicações de tela](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="bb460-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="bb460-109">Entidades disponíveis</span><span class="sxs-lookup"><span data-stu-id="bb460-109">Available entities</span></span>

<span data-ttu-id="bb460-110">Depois de adicionar o Customer Insights como uma ligação de dados, poderá escolher as seguintes entidades no Power Apps:</span><span class="sxs-lookup"><span data-stu-id="bb460-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="bb460-111">Cliente: para utilizar os dados do [perfil de cliente unificado](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bb460-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="bb460-112">UnifiedActivity: para apresentar a [linha cronológica de atividade](activities.md) na aplicação.</span><span class="sxs-lookup"><span data-stu-id="bb460-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="bb460-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="bb460-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="bb460-114">Entidades que pode obter</span><span class="sxs-lookup"><span data-stu-id="bb460-114">Retrievable entities</span></span>

<span data-ttu-id="bb460-115">Só é possível obter as entidades **Cliente**, **UnifiedActivity** e **Segmentos** através do conector Power Apps.</span><span class="sxs-lookup"><span data-stu-id="bb460-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="bb460-116">Outras entidades são mostradas porque o conector subjacente as suporta através de acionadores no Power Automate.</span><span class="sxs-lookup"><span data-stu-id="bb460-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="bb460-117">Delegação</span><span class="sxs-lookup"><span data-stu-id="bb460-117">Delegation</span></span>

<span data-ttu-id="bb460-118">A delegação trabalha para a entidade Cliente e entidade UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="bb460-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="bb460-119">Delegação para a entidade **Cliente**: Para utilizar a delegação para esta entidade, os campos precisam de ser indexados em [Índice procurar e filtrar](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="bb460-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="bb460-120">Delegação para **UnifiedActivity**: a delegação para esta entidade só funciona para os campos **ActivityId** e **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="bb460-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="bb460-121">Para obter mais informações sobre a delegação, consulte [Funções e operações delegatáveis do Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="bb460-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="bb460-122">Exemplo de controlo de galeria</span><span class="sxs-lookup"><span data-stu-id="bb460-122">Example gallery control</span></span>

<span data-ttu-id="bb460-123">Por exemplo, adiciona perfis de clientes a um [controlo da galeria](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="bb460-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="bb460-124">Adicione um controlo **Galeria** a uma aplicação que esteja a criar.</span><span class="sxs-lookup"><span data-stu-id="bb460-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bb460-125">![Adicionar um elemento de galeria](media/connector-powerapps9.png "Adicionar um elemento de galeria")</span><span class="sxs-lookup"><span data-stu-id="bb460-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="bb460-126">Selecione **Cliente** como origem de dados para os itens.</span><span class="sxs-lookup"><span data-stu-id="bb460-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bb460-127">![Selecionar uma origem de dados](media/choose-datasource-powerapps.png "Selecionar uma origem de dados")</span><span class="sxs-lookup"><span data-stu-id="bb460-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="bb460-128">Pode alterar o painel de dados à direita para selecionar o campo que a entidade Cliente vai mostrar na galeria.</span><span class="sxs-lookup"><span data-stu-id="bb460-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="bb460-129">Se pretende mostrar qualquer campo do cliente selecionado na galeria, preencha a propriedade Texto de uma etiqueta:  **{Name_of_the_gallery}.Selecionado.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="bb460-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="bb460-130">Exemplo: Galeria1.Selecionada.address1_city</span><span class="sxs-lookup"><span data-stu-id="bb460-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="bb460-131">Para apresentar a linha cronológica unificada para um cliente, adicione um elemento Galeria e adicione a propriedade Itens: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="bb460-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="bb460-132">Exemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="bb460-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
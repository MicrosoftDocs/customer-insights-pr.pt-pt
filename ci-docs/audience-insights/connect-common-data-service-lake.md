---
title: Conecte-se a entidades no lake gerido do Common Data Service
description: Importar dados de um data lake gerido do Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596973"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="ab429-103">Conecte-se aos dados num data lake gerido do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ab429-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ab429-104">Este artigo fornece informações sobre como os clientes existentes do Dynamics 365 podem rapidamente ligar-se às suas entidades analíticas no lake gerido do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ab429-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="ab429-105">Deve ser um administrador na organização do Common Data Service para prosseguir e ver a lista de entidades disponíveis no lake gerido.</span><span class="sxs-lookup"><span data-stu-id="ab429-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="ab429-106">Considerações importantes</span><span class="sxs-lookup"><span data-stu-id="ab429-106">Important considerations</span></span>

<span data-ttu-id="ab429-107">Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados numa localização diferente do local em que os dados são processados ou armazenados no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab429-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="ab429-108"> Ao importar, ou ligar a, os dados armazenados em serviços online, como o , concorda que os dados podem ser transferidos para, e armazenados com o Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="ab429-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="ab429-109">Ligar a um lake gerido do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ab429-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="ab429-110">Em informações de audiência, aceda a **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="ab429-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ab429-111">Selecione **Adicionar origem de dados**.</span><span class="sxs-lookup"><span data-stu-id="ab429-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="ab429-112">Selecione **Ligar ao Common Data Service** e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="ab429-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="ab429-113">Introduza um **Nome** para a oridem de dados e, em seguida, selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="ab429-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="ab429-114">Nomear diretrizes:</span><span class="sxs-lookup"><span data-stu-id="ab429-114">Name guidelines:</span></span> 
   - <span data-ttu-id="ab429-115">Comece com uma letra.</span><span class="sxs-lookup"><span data-stu-id="ab429-115">Start with a letter.</span></span>
   - <span data-ttu-id="ab429-116">Utilize apenas letras e números.</span><span class="sxs-lookup"><span data-stu-id="ab429-116">Use letters and numbers only.</span></span> <span data-ttu-id="ab429-117">Não são permitidos carateres especiais e espaços.</span><span class="sxs-lookup"><span data-stu-id="ab429-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="ab429-118">Utilize entre 3 e 64 carateres.</span><span class="sxs-lookup"><span data-stu-id="ab429-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="ab429-119">Forneça o **Endereço de servidor** para a sua organização do Common Data Service e selecione **Iniciar sessão**.</span><span class="sxs-lookup"><span data-stu-id="ab429-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab429-120">![Caixa de diálogo para introduzir o endereço do servidor do Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="ab429-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="ab429-121">Selecione as entidades que pretende ingerir a partir da lista disponível.</span><span class="sxs-lookup"><span data-stu-id="ab429-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="ab429-122">Se algumas entidades já estiverem selecionadas, poderão ser utilizadas por outras aplicações do Dynamics 365 (como o Dynamics 365 Sales Insights ou o Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="ab429-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="ab429-123">Não pode alterar a seleção.</span><span class="sxs-lookup"><span data-stu-id="ab429-123">You can't change the selection.</span></span> <span data-ttu-id="ab429-124">Estas entidades estarão disponíveis assim que a origem de dados for criada.</span><span class="sxs-lookup"><span data-stu-id="ab429-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab429-125">![Caixa de diálogo que mostra uma lista de entidades na organização do Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="ab429-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="ab429-126">Guarde a seleção para iniciar a sincronização das entidades selecionadas para o lake gerido do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ab429-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="ab429-127">Encontrará a ligação recentemente adicionada na página **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="ab429-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="ab429-128">A mesma será colocada em fila para atualização e mostrará as entidades como 0 até que todas as entidades sejam sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="ab429-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="ab429-129">Apenas uma origem de dados de um ambiente pode simultaneamente usar o mesmo lake gerido Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ab429-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="ab429-130">Editar uma origem de dados de lake gerido do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ab429-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="ab429-131">Só edita a seleção de entidade depois de criar a origem de dados.</span><span class="sxs-lookup"><span data-stu-id="ab429-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="ab429-132">Por exemplo, se entidades adicionais forem adicionadas ao Common Data Service e quiser importá-las também.</span><span class="sxs-lookup"><span data-stu-id="ab429-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="ab429-133">Para ligar a outro Common Data Service, [crie uma nova origem de dados](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="ab429-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="ab429-134">Em informações de audiência, aceda a **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="ab429-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ab429-135">Junto da origem de dados que pretende atualizar, selecione as reticências.</span><span class="sxs-lookup"><span data-stu-id="ab429-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="ab429-136">Selecione a opção **Editar** da lista.</span><span class="sxs-lookup"><span data-stu-id="ab429-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="ab429-137">Selecione entidades adicionais a partir da lista de entidades disponíveis e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ab429-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
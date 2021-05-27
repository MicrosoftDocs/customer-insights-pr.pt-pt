---
title: Exportar dados Customer Insights para o Dynamics 365 Sales
description: Aprenda a configurar a ligação e exportar para o Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976240"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="e3d45-103">Utilizar segmentos no Dynamics 365 Sales (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="e3d45-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e3d45-104">Utilize os dados dos seus clientes para criar listas de marketing, dar seguimento a fluxos de trabalho e enviar promoções com o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e3d45-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="e3d45-105">Pré-requisito para a ligação</span><span class="sxs-lookup"><span data-stu-id="e3d45-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="e3d45-106">Os registos de contacto têm de estar presentes no Dynamics 365 Sales antes de poder exportar um segmento do Customer Insights para o Sales.</span><span class="sxs-lookup"><span data-stu-id="e3d45-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="e3d45-107">Leia mais sobre como ingerir contactos no [Dynamics 365 Sales utilizando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e3d45-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e3d45-108">A exportação de segmentos a partir de informações da audiência para o Sales não criarão novos registos de contacto nas instâncias do Sales.</span><span class="sxs-lookup"><span data-stu-id="e3d45-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="e3d45-109">Os registos de contacto do Sales têm de ser ingeridos nas informações da audiência e utilizados como origem de dados.</span><span class="sxs-lookup"><span data-stu-id="e3d45-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e3d45-110">Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="e3d45-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="e3d45-111">Configure a ligação para o Sales</span><span class="sxs-lookup"><span data-stu-id="e3d45-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="e3d45-112">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e3d45-113">Selecione **Adicionar ligação** e escolha **Dynamics 365 Sales** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d45-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="e3d45-114">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e3d45-115">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d45-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e3d45-116">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d45-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e3d45-117">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d45-117">Choose who can use this connection.</span></span> <span data-ttu-id="e3d45-118">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="e3d45-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e3d45-119">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e3d45-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e3d45-120">Introduza o URL do Sales da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e3d45-121">Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e3d45-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="e3d45-122">Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e3d45-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e3d45-123">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d45-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e3d45-124">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="e3d45-124">Configure an export</span></span>

<span data-ttu-id="e3d45-125">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="e3d45-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e3d45-126">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e3d45-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e3d45-127">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e3d45-128">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e3d45-129">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e3d45-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="e3d45-130">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="e3d45-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e3d45-131">Escolher um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="e3d45-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="e3d45-132">Selecione **Guardar**</span><span class="sxs-lookup"><span data-stu-id="e3d45-132">Select **Save**</span></span>

<span data-ttu-id="e3d45-133">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e3d45-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e3d45-134">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e3d45-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3d45-135">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e3d45-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]

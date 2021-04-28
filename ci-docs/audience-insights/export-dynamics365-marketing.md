---
title: Exportar dados Customer Insights para o Dynamics 365 Marketing
description: Aprenda a configurar a ligação e exportar para o Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759651"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="3d658-103">Utilizar segmentos no Dynamics 365 Marketing (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="3d658-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3d658-104">Utilize os [segmentos](segments.md) para gerar campanhas e contactar grupos específicos de clientes com Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="3d658-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="3d658-105">Para mais informações, consulte [Usar segmentos do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="3d658-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="3d658-106">Pré-requisito para uma ligação</span><span class="sxs-lookup"><span data-stu-id="3d658-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="3d658-107">Os registos de contacto têm de estar presentes no Dynamics 365 Marketing antes de poder exportar um segmento do Customer Insights para o Marketing.</span><span class="sxs-lookup"><span data-stu-id="3d658-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="3d658-108">Leia mais sobre como ingerir contactos no [Dynamics 365 Marketing utilizando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3d658-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="3d658-109">A exportação de segmentos a partir de informações da audiência para o Marketing não criarão novos registos de contacto nas instâncias do Marketing.</span><span class="sxs-lookup"><span data-stu-id="3d658-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="3d658-110">Os registos de contacto do Marketing têm de ser ingeridos nas informações da audiência e utilizados como origem de dados.</span><span class="sxs-lookup"><span data-stu-id="3d658-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="3d658-111">Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="3d658-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="3d658-112">Configure a ligação para o Marketing</span><span class="sxs-lookup"><span data-stu-id="3d658-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="3d658-113">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="3d658-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3d658-114">Selecione **Adicionar ligação** e escolha **Dynamics 365 Marketing** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="3d658-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="3d658-115">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="3d658-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3d658-116">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="3d658-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3d658-117">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="3d658-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3d658-118">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="3d658-118">Choose who can use this connection.</span></span> <span data-ttu-id="3d658-119">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="3d658-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3d658-120">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3d658-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3d658-121">Introduza o URL do Marketing da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="3d658-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="3d658-122">Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="3d658-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="3d658-123">Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3d658-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="3d658-124">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="3d658-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="3d658-125">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="3d658-125">Configure an export</span></span>

<span data-ttu-id="3d658-126">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="3d658-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3d658-127">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3d658-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3d658-128">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="3d658-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3d658-129">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="3d658-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3d658-130">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="3d658-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="3d658-131">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="3d658-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3d658-132">Escolher um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="3d658-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="3d658-133">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3d658-133">Select **Save**.</span></span>

<span data-ttu-id="3d658-134">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="3d658-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3d658-135">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3d658-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3d658-136">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3d658-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Exportar dados do Customer Insights para um Armazenamento de Blobs do Azure
description: Aprenda a configurar a ligação e exportar para o Armazenamento de Blobs.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760249"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="22463-103">Exportar lista de segmentos e outros dados para o Armazenamento de Blobs do Azure (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="22463-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="22463-104">Armazene os seus dados do Customer Insights num Armazenamento de Blobs ou utilize-os para transferir os seus dados para outras aplicações.</span><span class="sxs-lookup"><span data-stu-id="22463-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="22463-105">Configure a ligação para o Armazenamento de Blobs</span><span class="sxs-lookup"><span data-stu-id="22463-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="22463-106">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="22463-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="22463-107">Selecione **Adicionar ligação** e escolha **Armazenamento de Blobs do Azure** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="22463-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="22463-108">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="22463-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="22463-109">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="22463-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="22463-110">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="22463-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="22463-111">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="22463-111">Choose who can use this connection.</span></span> <span data-ttu-id="22463-112">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="22463-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="22463-113">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="22463-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="22463-114">Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da sua conta de Armazenamento de Blobs.</span><span class="sxs-lookup"><span data-stu-id="22463-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="22463-115">Para saber mais sobre como encontrar o nome da conta de Armazenamento de Blobs e a chave da conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="22463-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="22463-116">Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="22463-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="22463-117">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="22463-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="22463-118">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="22463-118">Configure an export</span></span>

<span data-ttu-id="22463-119">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="22463-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="22463-120">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="22463-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="22463-121">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="22463-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="22463-122">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="22463-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="22463-123">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="22463-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="22463-124">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="22463-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="22463-125">Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.</span><span class="sxs-lookup"><span data-stu-id="22463-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="22463-126">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="22463-126">Select **Save**.</span></span>

<span data-ttu-id="22463-127">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="22463-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="22463-128">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="22463-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="22463-129">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="22463-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="22463-130">Os dados exportados são armazenados no contentor de Armazenamento de Blobs que configurou.</span><span class="sxs-lookup"><span data-stu-id="22463-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="22463-131">Os seguintes caminhos de pastas são criados automaticamente no seu contentor:</span><span class="sxs-lookup"><span data-stu-id="22463-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="22463-132">Para entidades de origem e entidades geradas pelo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="22463-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="22463-133">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="22463-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="22463-134">O model.json para as entidades exportadas estará ao nível de %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="22463-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="22463-135">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="22463-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

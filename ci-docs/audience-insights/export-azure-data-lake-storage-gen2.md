---
title: Exportar dados do Customer Insights para o Azure Data Lake Storage Gen2
description: Aprenda a configurar a ligação ao Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760065"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="53048-103">Configure a ligação ao Azure Data Lake Storage Gen2 (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="53048-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="53048-104">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="53048-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="53048-105">Selecione **Adicionar ligação** e escolha **Azure Data Lake Gen 2** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="53048-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="53048-106">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="53048-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="53048-107">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="53048-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="53048-108">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="53048-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="53048-109">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="53048-109">Choose who can use this connection.</span></span> <span data-ttu-id="53048-110">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="53048-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="53048-111">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="53048-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="53048-112">Introduza o **Nome da conta**, a **Chave da conta** e o **Recipiente** para o seu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="53048-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="53048-113">Para aprender a criar uma conta de armazenamento a utilizar com o Azure Data Lake Storage Gen2, consulte [Criar conta de armazenamento](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="53048-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="53048-114">Para saber mais sobre o nome da conta de armazenamento do Azure Data Lake Gen2 e a chave da conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="53048-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="53048-115">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="53048-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="53048-116">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="53048-116">Configure an export</span></span>

<span data-ttu-id="53048-117">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="53048-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="53048-118">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="53048-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="53048-119">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="53048-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="53048-120">Para criar um nova exportação, selecione **Adicionar exportação**.</span><span class="sxs-lookup"><span data-stu-id="53048-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="53048-121">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="53048-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="53048-122">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="53048-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="53048-123">Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.</span><span class="sxs-lookup"><span data-stu-id="53048-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="53048-124">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53048-124">Select **Save**.</span></span>

<span data-ttu-id="53048-125">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="53048-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="53048-126">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="53048-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="53048-127">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="53048-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="53048-128">Os dados exportados são armazenados no contentor do Azure Data Lake Gen 2 que configurou.</span><span class="sxs-lookup"><span data-stu-id="53048-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Exportar dados do Customer Insights para o Azure Data Lake Storage Gen2
description: Aprenda a configurar a ligação ao Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477193"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="dcab2-103">Conector para o Azure Data Lake Storage Gen2 (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="dcab2-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="dcab2-104">Armazene os seus dados do Customer Insights no Azure Data Lake Storage Gen2 ou utilize-os para transferir os seus dados para outras aplicações.</span><span class="sxs-lookup"><span data-stu-id="dcab2-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="dcab2-105">Configure o conector para o Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="dcab2-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="dcab2-106">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="dcab2-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dcab2-107">Sob **Azure Data Lake Storage Gen2**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="dcab2-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="dcab2-108">Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="dcab2-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dcab2-109">Introduza o **Nome da conta**, a **Chave da conta** e o **Recipiente** para o seu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="dcab2-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="dcab2-110">Para aprender a criar uma conta de armazenamento a utilizar com o Azure Data Lake Storage Gen2, consulte [Criar conta de armazenamento](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="dcab2-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="dcab2-111">Para saber mais sobre como encontrar o nome da conta de armazenamento e a chave da conta do Azure Data Lake Gen2, consulte [Gerir definições da conta de armazenamento no portal do Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="dcab2-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="dcab2-112">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="dcab2-112">Select **Next**.</span></span>

1. <span data-ttu-id="dcab2-113">Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.</span><span class="sxs-lookup"><span data-stu-id="dcab2-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="dcab2-114">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dcab2-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dcab2-115">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="dcab2-115">Export the data</span></span>

<span data-ttu-id="dcab2-116">Pode [exportar dados a pedido](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dcab2-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="dcab2-117">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dcab2-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

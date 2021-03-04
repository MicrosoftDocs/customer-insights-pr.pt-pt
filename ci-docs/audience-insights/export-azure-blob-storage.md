---
title: Exportar dados do Customer Insights para um Armazenamento de Blobs do Azure
description: Aprenda a configurar a ligação ao armazenamento de Blobs do Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269206"
---
# <a name="connector-for-azure-blob-storage-preview"></a><span data-ttu-id="021c8-103">Conector para armazenamento de Blobs do Azure (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="021c8-103">Connector for Azure Blob storage (preview)</span></span>

<span data-ttu-id="021c8-104">Armazene os seus dados de Customer Insights num Armazenamento de Blobs do Azure ou utilize-os para transferir os seus dados para outras aplicações.</span><span class="sxs-lookup"><span data-stu-id="021c8-104">Store your Customer Insights data in an Azure Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-blob-storage"></a><span data-ttu-id="021c8-105">Configure o conector para armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="021c8-105">Configure the connector for Azure Blob storage</span></span>

1. <span data-ttu-id="021c8-106">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="021c8-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="021c8-107">Em **Armazenamento de Blobs do Azure**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="021c8-107">Under **Azure Blob Storage**, select **Set up**.</span></span>

1. <span data-ttu-id="021c8-108">Introduza o **Nome da conta**, a **Chave da conta** e o **Recipiente** para a sua conta de armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="021c8-108">Enter **Account name**, **Account key**, and **Container** for your Azure Blob storage account.</span></span>
    - <span data-ttu-id="021c8-109">Para saber mais sobre como localizar o nome da conta de armazenamento do Azure Blob e a chave de conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="021c8-109">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="021c8-110">Para saber mais sobre como criar um contentor, consulte [Criar um contentor](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="021c8-110">To learn how to create a container, see [Create a container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="021c8-111">Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="021c8-111">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="021c8-112">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="021c8-112">Select **Next**.</span></span>

1. <span data-ttu-id="021c8-113">Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.</span><span class="sxs-lookup"><span data-stu-id="021c8-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="021c8-114">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="021c8-114">Select **Save**.</span></span>

<span data-ttu-id="021c8-115">Os dados exportados são armazenados no recipiente de armazenamento de Blobs do Azure que configurou.</span><span class="sxs-lookup"><span data-stu-id="021c8-115">Exported data is stored in the Azure Blob storage container you configured.</span></span> <span data-ttu-id="021c8-116">Os seguintes caminhos de pastas são criados automaticamente no seu contentor:</span><span class="sxs-lookup"><span data-stu-id="021c8-116">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="021c8-117">Para entidades de origem e entidades geradas pelo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="021c8-117">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="021c8-118">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="021c8-118">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="021c8-119">O model.json para as entidades exportadas residirá ao nível %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="021c8-119">The model.json for the exported entities will reside at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="021c8-120">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="021c8-120">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

## <a name="export-the-data"></a><span data-ttu-id="021c8-121">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="021c8-121">Export the data</span></span>

<span data-ttu-id="021c8-122">Pode [exportar dados a pedido](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="021c8-122">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="021c8-123">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="021c8-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
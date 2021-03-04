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
# <a name="connector-for-azure-blob-storage-preview"></a>Conector para armazenamento de Blobs do Azure (pré-visualização)

Armazene os seus dados de Customer Insights num Armazenamento de Blobs do Azure ou utilize-os para transferir os seus dados para outras aplicações.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Configure o conector para armazenamento de Blobs do Azure

1. Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.

1. Em **Armazenamento de Blobs do Azure**, selecione **Configurar**.

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Recipiente** para a sua conta de armazenamento de Blobs do Azure.
    - Para saber mais sobre como localizar o nome da conta de armazenamento do Azure Blob e a chave de conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Para saber mais sobre como criar um contentor, consulte [Criar um contentor](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.

1. Selecione **Seguinte**.

1. Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.

1. Selecione **Guardar**.

Os dados exportados são armazenados no recipiente de armazenamento de Blobs do Azure que configurou. Os seguintes caminhos de pastas são criados automaticamente no seu contentor:

- Para entidades de origem e entidades geradas pelo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- O model.json para as entidades exportadas residirá ao nível %ExportDestinationName%
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md#export-data-on-demand). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
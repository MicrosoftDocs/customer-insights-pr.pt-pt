---
title: Exportar dados para um Armazenamento de Blobs do Azure (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o Armazenamento de Blobs.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195718"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportar dados para um Armazenamento de Blobs do Azure (pré-visualização)

Armazene os seus dados do Customer Insights num Armazenamento de Blobs ou utilize-os para transferir os seus dados para outras aplicações.

## <a name="prerequisites"></a>Pré-requisitos

- Uma chave de conta e nome de [conta de Armazenamento de Blobs do Azure](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar o nome e a chave, consulte [Gerir definições de conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
- Um [contentor do Armazenamento de Blobs do Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitações conhecidas

- Para o Armazenamento de Blobs do Azure, escolha entre o [escalão de desempenho Standard e o escalão de desempenho Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se escolher o escalão de desempenho Premium, selecione os [blobs de blocos premium como o tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Configurar ligação ao Armazenamento de Blobs

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Armazenamento de Blobs do Azure**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da sua conta de Armazenamento de Blobs.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Para configurar esta exportação, tem de ter [permissão](export-destinations.md#set-up-a-new-export) para este tipo de ligação.

> [!IMPORTANT]
> Se tiver ativado a [definição de eliminação recuperável](/azure/storage/blobs/soft-delete-blob-enable) para a conta de Armazenamento de Blobs do Azure, as exportações falharão. Desative a eliminação de forma recuperável para exportar dados para blobs.

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Armazenamento de Blobs do Azure. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Introduza o nome de pasta para o Armazenamento de blobs.

1. Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Os dados exportados são armazenados no contentor de Armazenamento de Blobs que configurou. Os seguintes caminhos de pastas são criados automaticamente no seu contentor:

- Para entidades de origem e entidades geradas pelo sistema:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > A exportação de entidades que contenham uma grande quantidade de dados pode levar a vários ficheiros CSV na mesma pasta para cada exportação. A divisão de exportações ocorre por razões de desempenho que minimizam o tempo que demora a conclusão de uma exportação.

- O model.json para as entidades exportadas reside ao nível de *%ExportDestinationName%*.  
  
  Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]

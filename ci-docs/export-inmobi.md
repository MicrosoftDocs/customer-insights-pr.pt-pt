---
title: Exportar dados do Customer Insights para o InMobi
description: Saiba como configurar a ligação e exportar para o InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056549"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Exportar a lista de segmentos e outros dados para o InMobi (pré-visualização)

Exportar listas de segmentos ou outros dados da instância Customer Insights para o [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Pré-requisitos

1. Tem uma [conta InMobi](https://www.inmobi.com/) e credenciais de admin.
1. Tem um nome de conta de armazenamento de Blobs do Azure e a chave de conta correspondente. Para mais informações, consulte [Gerir definições de conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage). Existe um contentor na conta de armazenamento para onde exportar os dados inMobi. Para obter mais informações, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. O InMobi irá criar uma ligação direta ao Armazenamento de Blobs e configurar uma importação automática dos seus dados para o InMobi. Contacte o representante InMobi para iniciar o processo.

## <a name="known-limitations"></a>Limitações conhecidas

1. Para o Armazenamento de Blobs do Azure, pode escolher entre [o escalão de desempenho Standard e o escalão de desempenho Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se escolher o escalão de desempenho Premium, selecione os [blobs de blocos premium como o tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Configurar a ligação ao Armazenamento de Blobs do Azure e configurar uma exportação

1. Seguir as instruções para [configurar uma ligação ao Armazenamento de Blobs do Azure](export-azure-blob-storage.md).
2. Seguir as instruções para [configurar uma exportação](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]

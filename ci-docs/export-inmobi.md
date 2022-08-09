---
title: Exportar dados do Customer Insights para o InMobi
description: Saiba como configurar a ligação e exportar para o InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195902"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Exportar dados do Customer Insights para o InMobi (pré-visualização)

Exportar listas de segmentos ou outros dados da instância Customer Insights para o [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta InMobi](https://www.inmobi.com/) e credenciais de administrador.
- Uma chave de conta e nome de [conta de Armazenamento de Blobs do Azure](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar o nome e a chave, consulte [Gerir definições de conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
- Um [contentor do Armazenamento de Blobs do Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) para o qual exportar os dados do InMobi.
- O InMobi irá criar uma ligação direta ao Armazenamento de Blobs e configurar uma importação automática dos seus dados para o InMobi. Contacte o representante InMobi para iniciar o processo.

## <a name="known-limitations"></a>Limitações conhecidas

- Para o Armazenamento de Blobs do Azure, escolha entre o [escalão de desempenho Standard e o escalão de desempenho Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se escolher o escalão de desempenho Premium, selecione os [blobs de blocos premium como o tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Configurar ligação ao Armazenamento de Blobs do Azure

[Configurar uma ligação ao seu Armazenamento de Blobs do Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Configurar uma exportação

[Configurar uma exportação](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]

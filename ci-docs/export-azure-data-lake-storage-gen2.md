---
title: Exportar dados para o Azure Data Lake Storage Gen2 (pré-visualização)
description: Aprenda a configurar a ligação ao Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196454"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar dados para o Azure Data Lake Storage Gen2 (pré-visualização)

Armazene os seus dados do Customer Insights numa conta Data Lake Storage Gen2 ou utilize-os para transferir os seus dados para outras aplicações.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta de armazenamento para usar com o Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar o nome da conta de armazenamento e a chave, consulte [Gerir definições de conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
- Um [contentor do Armazenamento de Blobs do Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitações conhecidas

- Para o Azure Data Lake Storage Gen2, escolha entre [desempenho Standard e escalão de desempenho Premium](/azure/storage/blobs/create-data-lake-storage-account). Se escolher o escalão de desempenho Premium, selecione os [blobs de blocos premium como o tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Configurar ligação ao Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Azure Data Lake Gen 2**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Recipiente** para o seu Azure Data Lake Storage Gen2.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Azure Data Lake. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Introduza o nome de pasta para o armazenamento do Azure Data Lake Storage Gen2.

1. Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Os dados exportados são armazenados no contentor do Azure Data Lake Gen 2 que configurou.

> [!TIP]
> A exportação de entidades que contenham uma grande quantidade de dados pode levar a vários ficheiros CSV na mesma pasta para cada exportação. A divisão de exportações ocorre por razões de desempenho que minimizam o tempo que demora a conclusão de uma exportação.

[!INCLUDE [footer-include](includes/footer-banner.md)]

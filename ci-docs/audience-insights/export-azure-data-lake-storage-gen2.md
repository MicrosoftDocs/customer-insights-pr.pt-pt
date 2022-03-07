---
title: Exportar dados do Customer Insights para o Azure Data Lake Storage Gen2
description: Aprenda a configurar a ligação ao Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: cc0b3aac11a33facc366e9c57071d1fb8be4ecc4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231688"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar a lista de segmentos e outros dados para o Azure Data Lake Storage Gen2 (pré-visualização)

Armazene os seus dados do Customer Insights numa conta Data Lake Storage Gen2 ou utilize-os para transferir os seus dados para outras aplicações.

## <a name="known-limitations"></a>Limitações conhecidas

1. Para o Azure Data Lake Storage Gen2 pode escolher entre [o escalão de desempenho Standard e o escalão de desempenho Premium](/azure/storage/blobs/create-data-lake-storage-account) quando estiver a criar uma conta de armazenamento para o seu data lake. Se escolher o escalão de desempenho Premium, selecione os blobs de blocos premium como o tipo de conta. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Configurar a ligação para o Azure Data Lake Storage Gen2 


1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Azure Data Lake Gen 2** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Recipiente** para o seu Azure Data Lake Storage Gen2.
    - Para aprender a criar uma conta de armazenamento a utilizar com o Azure Data Lake Storage Gen2, consulte [Criar conta de armazenamento](/azure/storage/blobs/create-data-lake-storage-account). 
    - Para saber mais sobre o nome da conta de armazenamento do Azure Data Lake Gen2 e a chave da conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

1. Selecione **Guardar** para concluir a ligação. 

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar um nova exportação, selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção **Azure Data Lake**. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

Os dados exportados são armazenados no contentor do Azure Data Lake Gen 2 que configurou. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]

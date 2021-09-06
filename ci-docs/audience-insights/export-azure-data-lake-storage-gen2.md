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
ms.openlocfilehash: c4408e52550b6648e2a001041dc0acdb5063d6a6ef1b8e4bba3321bf25fefcfc
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031993"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Configure a ligação ao Azure Data Lake Storage Gen2 (pré-visualização)

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

---
title: Exportar dados para um Armazenamento de Blobs do Azure (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o Armazenamento de Blobs.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 059c8364ca0f3740bc0e4ffeeeba94246c9e5696
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055504"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportar dados para um Armazenamento de Blobs do Azure (pré-visualização)

Armazene os seus dados do Customer Insights num Armazenamento de Blobs ou utilize-os para transferir os seus dados para outras aplicações.

## <a name="known-limitations"></a>Limitações conhecidas

1. Para o Armazenamento de Blobs do Azure pode escolher entre [o escalão de desempenho Standard e o escalão de desempenho Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se escolher o escalão de desempenho Premium, selecione os [blobs de blocos premium como o tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Configurar a ligação ao Armazenamento de Blobs

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Armazenamento de Blobs do Azure** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da sua conta de Armazenamento de Blobs.
    - Para saber mais sobre como encontrar o nome da conta de Armazenamento de Blobs e a chave da conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
    - Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Guardar** para concluir a ligação. 

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Se tiver ativar a definição de eliminação de forma recuperável para a conta de Armazenamento de Blobs do Azure, as exportações falharão. Desative a eliminação de forma recuperável para exportar dados para blobs. Para obter mais informações, consulte [Ativar eliminação de forma recuperável de blobs](/azure/storage/blobs/soft-delete-blob-enable)

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Armazenamento de Blobs do Azure. Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.

1. Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab).

Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).

Os dados exportados são armazenados no contentor de Armazenamento de Blobs que configurou. Os seguintes caminhos de pastas são criados automaticamente no seu contentor:

- Para entidades de origem e entidades geradas pelo sistema:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > A exportação de entidades que contenham uma grande quantidade de dados pode levar a vários ficheiros CSV na mesma pasta para cada exportação. A divisão de exportações ocorre por razões de desempenho que minimizam o tempo que demora a conclusão de uma exportação.

- O model.json para as entidades exportadas estará ao nível de %ExportDestinationName%.  
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]

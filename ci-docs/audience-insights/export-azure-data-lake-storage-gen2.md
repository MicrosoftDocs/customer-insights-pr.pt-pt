---
title: Exportar dados do Customer Insights para o Azure Data Lake Storage Gen2
description: Aprenda a configurar a ligação ao Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596652"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Conector para o Azure Data Lake Storage Gen2 (pré-visualização)

Armazene os seus dados do Customer Insights no Azure Data Lake Storage Gen2 ou utilize-os para transferir os seus dados para outras aplicações.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configure o conector para o Azure Data Lake Storage Gen2

1. Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.

1. Sob **Azure Data Lake Storage Gen2**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Recipiente** para o seu Azure Data Lake Storage Gen2.
    - Para aprender a criar uma conta de armazenamento a utilizar com o Azure Data Lake Storage Gen2, consulte [Criar conta de armazenamento](/azure/storage/blobs/create-data-lake-storage-account). 
    - Para saber mais sobre como encontrar o nome da conta de armazenamento e a chave da conta do Azure Data Lake Gen2, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

1. Selecione **Seguinte**.

1. Selecione a caixa junto de cada uma das entidades que pretende exportar para este destino.

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md#export-data-on-demand). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).
---
title: Exportar dados Customer Insights para o Dynamics 365 Sales
description: Saiba como configurar a ligação ao Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598123"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Conector para Dynamics 365 Sales (pré-visualização)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilize os dados dos seus clientes para criar listas de marketing, dar seguimento a fluxos de trabalho e enviar promoções com o Dynamics 365 Sales.

## <a name="prerequisite"></a>Pré-requisito

1. Os registos de contacto têm de estar presentes no Dynamics 365 Sales antes de poder exportar um segmento do Customer Insights para o Sales. Leia mais sobre como ingerir contactos no [Dynamics 365 Sales utilizando o Common Data Services](connect-power-query.md).

   > [!NOTE]
   > A exportação de segmentos a partir de informações da audiência para o Sales não criarão novos registos de contacto nas instâncias do Sales. Os registos de contacto do Sales têm de ser ingeridos nas informações da audiência e utilizados como origem de dados. Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.

## <a name="configure-the-connector-for-sales"></a>Configurar o conector para o Sales

1. Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.

1. Em **Dynamics 365 Sales**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.

1. Introduza o URL do Sales da sua organização no campo **Endereço do servidor**.

1. Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Sales.

1. Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.

1. Selecione **Seguinte**.

1. Escolher um ou mais segmentos.

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
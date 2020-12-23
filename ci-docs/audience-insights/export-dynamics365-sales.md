---
title: Exportar dados Customer Insights para o Dynamics 365 Sales
description: Saiba como configurar a ligação ao Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643832"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Conector para Dynamics 365 Sales (pré-visualização)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilize os dados dos seus clientes para criar listas de marketing, dar seguimento a fluxos de trabalho e enviar promoções com o Dynamics 365 Sales.

## <a name="prerequisite"></a>Pré-requisito

Registos de contacto [do Dynamics 365 Sales ingeridos usando o Common Data Service](connect-power-query.md).

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

---
title: Exportar dados Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a ligação ao Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643787"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="bb606-103">Conector para Dynamics 365 Marketing (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="bb606-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bb606-104">Utilize os [segmentos](segments.md) para gerar campanhas e contactar grupos específicos de clientes com Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="bb606-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="bb606-105">Para mais informações, consulte [Usar segmentos do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="bb606-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="bb606-106">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="bb606-106">Prerequisite</span></span>

<span data-ttu-id="bb606-107">Registos de contacto [do Dynamics 365 Marketing ingeriram o Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="bb606-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="bb606-108">Configurar o conector para o Marketing</span><span class="sxs-lookup"><span data-stu-id="bb606-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="bb606-109">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="bb606-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bb606-110">Em **Dynamics 365 Marketing**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="bb606-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="bb606-111">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="bb606-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bb606-112">Introduza o URL do Marketing da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="bb606-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="bb606-113">Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="bb606-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="bb606-114">Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bb606-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="bb606-115">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="bb606-115">Select **Next**.</span></span>

1. <span data-ttu-id="bb606-116">Escolher um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="bb606-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="bb606-117">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb606-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bb606-118">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="bb606-118">Export the data</span></span>

<span data-ttu-id="bb606-119">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bb606-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bb606-120">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb606-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

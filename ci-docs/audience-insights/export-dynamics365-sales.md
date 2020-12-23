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
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="ea30b-103">Conector para Dynamics 365 Sales (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="ea30b-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ea30b-104">Utilize os dados dos seus clientes para criar listas de marketing, dar seguimento a fluxos de trabalho e enviar promoções com o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ea30b-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ea30b-105">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="ea30b-105">Prerequisite</span></span>

<span data-ttu-id="ea30b-106">Registos de contacto [do Dynamics 365 Sales ingeridos usando o Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ea30b-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="ea30b-107">Configurar o conector para o Sales</span><span class="sxs-lookup"><span data-stu-id="ea30b-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="ea30b-108">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="ea30b-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ea30b-109">Em **Dynamics 365 Sales**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="ea30b-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="ea30b-110">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="ea30b-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ea30b-111">Introduza o URL do Sales da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="ea30b-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ea30b-112">Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ea30b-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="ea30b-113">Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ea30b-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ea30b-114">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="ea30b-114">Select **Next**.</span></span>

1. <span data-ttu-id="ea30b-115">Escolher um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="ea30b-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="ea30b-116">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ea30b-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ea30b-117">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="ea30b-117">Export the data</span></span>

<span data-ttu-id="ea30b-118">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ea30b-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ea30b-119">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ea30b-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

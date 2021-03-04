---
title: Exportar dados Customer Insights para o Dynamics 365 Sales
description: Saiba como configurar a ligação ao Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269022"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="bb975-103">Conector para Dynamics 365 Sales (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="bb975-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bb975-104">Utilize os dados dos seus clientes para criar listas de marketing, dar seguimento a fluxos de trabalho e enviar promoções com o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bb975-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="bb975-105">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="bb975-105">Prerequisite</span></span>

1. <span data-ttu-id="bb975-106">Os registos de contacto têm de estar presentes no Dynamics 365 Sales antes de poder exportar um segmento do Customer Insights para o Sales.</span><span class="sxs-lookup"><span data-stu-id="bb975-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="bb975-107">Leia mais sobre como ingerir contactos no [Dynamics 365 Sales utilizando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="bb975-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="bb975-108">A exportação de segmentos a partir de informações da audiência para o Sales não criarão novos registos de contacto nas instâncias do Sales.</span><span class="sxs-lookup"><span data-stu-id="bb975-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="bb975-109">Os registos de contacto do Sales têm de ser ingeridos nas informações da audiência e utilizados como origem de dados.</span><span class="sxs-lookup"><span data-stu-id="bb975-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="bb975-110">Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="bb975-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="bb975-111">Configurar o conector para o Sales</span><span class="sxs-lookup"><span data-stu-id="bb975-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="bb975-112">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="bb975-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bb975-113">Em **Dynamics 365 Sales**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="bb975-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="bb975-114">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="bb975-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bb975-115">Introduza o URL do Sales da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="bb975-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="bb975-116">Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bb975-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="bb975-117">Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bb975-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="bb975-118">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="bb975-118">Select **Next**.</span></span>

1. <span data-ttu-id="bb975-119">Escolher um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="bb975-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="bb975-120">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb975-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bb975-121">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="bb975-121">Export the data</span></span>

<span data-ttu-id="bb975-122">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bb975-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bb975-123">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb975-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
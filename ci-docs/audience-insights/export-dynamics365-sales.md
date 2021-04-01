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
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="0c799-103">Conector para Dynamics 365 Sales (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="0c799-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0c799-104">Utilize os dados dos seus clientes para criar listas de marketing, dar seguimento a fluxos de trabalho e enviar promoções com o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0c799-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="0c799-105">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="0c799-105">Prerequisite</span></span>

1. <span data-ttu-id="0c799-106">Os registos de contacto têm de estar presentes no Dynamics 365 Sales antes de poder exportar um segmento do Customer Insights para o Sales.</span><span class="sxs-lookup"><span data-stu-id="0c799-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="0c799-107">Leia mais sobre como ingerir contactos no [Dynamics 365 Sales utilizando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0c799-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="0c799-108">A exportação de segmentos a partir de informações da audiência para o Sales não criarão novos registos de contacto nas instâncias do Sales.</span><span class="sxs-lookup"><span data-stu-id="0c799-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="0c799-109">Os registos de contacto do Sales têm de ser ingeridos nas informações da audiência e utilizados como origem de dados.</span><span class="sxs-lookup"><span data-stu-id="0c799-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="0c799-110">Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="0c799-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="0c799-111">Configurar o conector para o Sales</span><span class="sxs-lookup"><span data-stu-id="0c799-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="0c799-112">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="0c799-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0c799-113">Em **Dynamics 365 Sales**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="0c799-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="0c799-114">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="0c799-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0c799-115">Introduza o URL do Sales da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="0c799-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0c799-116">Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0c799-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="0c799-117">Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0c799-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0c799-118">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="0c799-118">Select **Next**.</span></span>

1. <span data-ttu-id="0c799-119">Escolher um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="0c799-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="0c799-120">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c799-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0c799-121">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="0c799-121">Export the data</span></span>

<span data-ttu-id="0c799-122">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0c799-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0c799-123">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0c799-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
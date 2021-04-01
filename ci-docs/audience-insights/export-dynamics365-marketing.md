---
title: Exportar dados Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a ligação ao Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597617"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="f880e-103">Conector para Dynamics 365 Marketing (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="f880e-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f880e-104">Utilize os [segmentos](segments.md) para gerar campanhas e contactar grupos específicos de clientes com Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f880e-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="f880e-105">Para mais informações, consulte [Usar segmentos do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="f880e-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="f880e-106">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="f880e-106">Prerequisite</span></span>

- <span data-ttu-id="f880e-107">Os registos de contacto têm de estar presentes no Dynamics 365 Marketing antes de poder exportar um segmento do Customer Insights para o Marketing.</span><span class="sxs-lookup"><span data-stu-id="f880e-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="f880e-108">Leia mais sobre como ingerir contactos no [Dynamics 365 Marketing utilizando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f880e-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="f880e-109">A exportação de segmentos a partir de informações da audiência para o Marketing não criarão novos registos de contacto nas instâncias do Marketing.</span><span class="sxs-lookup"><span data-stu-id="f880e-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="f880e-110">Os registos de contacto do Marketing têm de ser ingeridos nas informações da audiência e utilizados como origem de dados.</span><span class="sxs-lookup"><span data-stu-id="f880e-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="f880e-111">Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="f880e-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="f880e-112">Configurar o conector para o Marketing</span><span class="sxs-lookup"><span data-stu-id="f880e-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="f880e-113">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="f880e-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f880e-114">Em **Dynamics 365 Marketing**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="f880e-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="f880e-115">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="f880e-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f880e-116">Introduza o URL do Marketing da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="f880e-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="f880e-117">Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f880e-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="f880e-118">Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f880e-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="f880e-119">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="f880e-119">Select **Next**.</span></span>

1. <span data-ttu-id="f880e-120">Escolher um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="f880e-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="f880e-121">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f880e-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f880e-122">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="f880e-122">Export the data</span></span>

<span data-ttu-id="f880e-123">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f880e-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f880e-124">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f880e-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
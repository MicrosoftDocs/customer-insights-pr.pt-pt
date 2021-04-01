---
title: Conector do Power Automate| Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597939"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="6828a-103">Conector do Power Automate (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="6828a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="6828a-104">Acione eventos específicos para ocorrerem automaticamente quando os seus dados forem alterados e faça a gestão de fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6828a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="6828a-105">Acionadores do Power Automate</span><span class="sxs-lookup"><span data-stu-id="6828a-105">Power Automate triggers</span></span>

<span data-ttu-id="6828a-106">Utilize acionadores para criar fluxos de cloud e automatizar tarefas repetitivas, tais como notificações ou ações mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="6828a-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="6828a-107">É acionado quando uma atualização de origem de dados falha.</span><span class="sxs-lookup"><span data-stu-id="6828a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="6828a-108">É acionado quando uma atualização de origem de dados é bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="6828a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="6828a-109">É acionado quando um limiar é ultrapassado num segmento.</span><span class="sxs-lookup"><span data-stu-id="6828a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="6828a-110">O acionador limita-se a passar acima do limiar.</span><span class="sxs-lookup"><span data-stu-id="6828a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="6828a-111">É acionado quando um limiar é ultrapassado numa medida empresarial.</span><span class="sxs-lookup"><span data-stu-id="6828a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="6828a-112">O acionador limita-se a passar acima do limiar.</span><span class="sxs-lookup"><span data-stu-id="6828a-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="6828a-113">Acionar quando uma atualização completa de ( origens de dados, segmentos, medidas,...) é completada.</span><span class="sxs-lookup"><span data-stu-id="6828a-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="6828a-114">Acionar quando uma atualização do processo de unificação (mapa, correspondência, união) estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="6828a-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="6828a-115">[Configure os seus acionadores no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="6828a-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="6828a-116">Ações do Power Automate</span><span class="sxs-lookup"><span data-stu-id="6828a-116">Power Automate actions</span></span>
<span data-ttu-id="6828a-117">O conector do Power Automate fornece outras ações que não os acionadores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6828a-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="6828a-118">Para mais informações, consulte o [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="6828a-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="6828a-119">Criar um fluxo do Power Automate</span><span class="sxs-lookup"><span data-stu-id="6828a-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="6828a-120">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="6828a-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6828a-121">No mosaico **Power Automate**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6828a-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="6828a-122">O Conector Customer Insights (pré-visualização) no Power Automate abre-se.</span><span class="sxs-lookup"><span data-stu-id="6828a-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="6828a-123">**Inicie sessão** no Power Automate.</span><span class="sxs-lookup"><span data-stu-id="6828a-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="6828a-124">Escolha um dos acionadores disponíveis e adicione mais passos ao seu novo fluxo.</span><span class="sxs-lookup"><span data-stu-id="6828a-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="6828a-125">Para obter mais informações, consulte [Criar um fluxo de cloud no Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="6828a-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="6828a-126">Exemplos de como utilizar fluxos:</span><span class="sxs-lookup"><span data-stu-id="6828a-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="6828a-127">Publique uma mensagem num canal do Microsoft Teams se uma atualização de origem de dados falhar.</span><span class="sxs-lookup"><span data-stu-id="6828a-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="6828a-128">Envie um e-mail aos proprietários de dados quando um limiar de um segmento é ultrapassado.</span><span class="sxs-lookup"><span data-stu-id="6828a-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Conector do Power Automate| Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976102"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="bca84-103">Conector do Power Automate (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="bca84-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="bca84-104">Acione eventos específicos para ocorrerem automaticamente quando os seus dados forem alterados e faça a gestão de fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bca84-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="bca84-105">Acionadores do Power Automate</span><span class="sxs-lookup"><span data-stu-id="bca84-105">Power Automate triggers</span></span>

<span data-ttu-id="bca84-106">Utilize acionadores para criar fluxos de cloud e automatizar tarefas repetitivas, tais como notificações ou ações mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="bca84-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="bca84-107">É acionado quando uma atualização de origem de dados falha.</span><span class="sxs-lookup"><span data-stu-id="bca84-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="bca84-108">É acionado quando uma atualização de origem de dados é bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="bca84-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="bca84-109">É acionado quando um limiar é ultrapassado num segmento.</span><span class="sxs-lookup"><span data-stu-id="bca84-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="bca84-110">O acionador limita-se a passar acima do limiar.</span><span class="sxs-lookup"><span data-stu-id="bca84-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="bca84-111">É acionado quando um limiar é ultrapassado numa medida empresarial.</span><span class="sxs-lookup"><span data-stu-id="bca84-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="bca84-112">Apenas as medidas de negócio sem uma dimensão são suportadas.</span><span class="sxs-lookup"><span data-stu-id="bca84-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="bca84-113">O acionador limita-se a passar acima do limiar.</span><span class="sxs-lookup"><span data-stu-id="bca84-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="bca84-114">Acionar quando uma atualização completa de ( origens de dados, segmentos, medidas,...) é completada.</span><span class="sxs-lookup"><span data-stu-id="bca84-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="bca84-115">Acionar quando uma atualização do processo de unificação (mapa, correspondência, união) estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="bca84-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="bca84-116">[Configure os seus acionadores no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="bca84-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="bca84-117">Ações do Power Automate</span><span class="sxs-lookup"><span data-stu-id="bca84-117">Power Automate actions</span></span>
<span data-ttu-id="bca84-118">O conector do Power Automate fornece outras ações que não os acionadores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bca84-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="bca84-119">Para mais informações, consulte o [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="bca84-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="bca84-120">Criar um fluxo do Power Automate</span><span class="sxs-lookup"><span data-stu-id="bca84-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="bca84-121">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="bca84-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bca84-122">No mosaico **Power Automate**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="bca84-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="bca84-123">O Conector Customer Insights (pré-visualização) no Power Automate abre-se.</span><span class="sxs-lookup"><span data-stu-id="bca84-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="bca84-124">**Inicie sessão** no Power Automate.</span><span class="sxs-lookup"><span data-stu-id="bca84-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="bca84-125">Escolha um dos acionadores disponíveis e adicione mais passos ao seu novo fluxo.</span><span class="sxs-lookup"><span data-stu-id="bca84-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="bca84-126">Para obter mais informações, consulte [Criar um fluxo de cloud no Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="bca84-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="bca84-127">Exemplos de como utilizar fluxos:</span><span class="sxs-lookup"><span data-stu-id="bca84-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="bca84-128">Publique uma mensagem num canal do Microsoft Teams se uma atualização de origem de dados falhar.</span><span class="sxs-lookup"><span data-stu-id="bca84-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="bca84-129">Envie um e-mail aos proprietários de dados quando um limiar de um segmento é ultrapassado.</span><span class="sxs-lookup"><span data-stu-id="bca84-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Conector do Power Automate| Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406605"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="89460-103">Conector do Power Automate (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="89460-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="89460-104">Acione eventos específicos para ocorrerem automaticamente quando os seus dados forem alterados e faça a gestão de fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="89460-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="89460-105">Acionadores do Power Automate</span><span class="sxs-lookup"><span data-stu-id="89460-105">Power Automate triggers</span></span>

<span data-ttu-id="89460-106">Pode utilizar uma variedade de acionadores que lhe permitem criar fluxos para automatizar tarefas repetitivas, tais como notificações ou ações mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="89460-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="89460-107">É acionado quando uma atualização de origem de dados falha.</span><span class="sxs-lookup"><span data-stu-id="89460-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="89460-108">É acionado quando uma atualização de origem de dados é bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="89460-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="89460-109">É acionado quando um limiar é ultrapassado num segmento.</span><span class="sxs-lookup"><span data-stu-id="89460-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="89460-110">O acionador limita-se a passar acima do limiar.</span><span class="sxs-lookup"><span data-stu-id="89460-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="89460-111">É acionado quando um limiar é ultrapassado numa medida empresarial.</span><span class="sxs-lookup"><span data-stu-id="89460-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="89460-112">O acionador limita-se a passar acima do limiar.</span><span class="sxs-lookup"><span data-stu-id="89460-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="89460-113">Acionar quando uma atualização completa de ( origens de dados, segmentos, medidas,...) é completada.</span><span class="sxs-lookup"><span data-stu-id="89460-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="89460-114">Acionar quando uma atualização do processo de unificação (mapa, correspondência, união) estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="89460-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="89460-115">[Configure os seus acionadores no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="89460-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="89460-116">Ações do Power Automate</span><span class="sxs-lookup"><span data-stu-id="89460-116">Power Automate actions</span></span>
<span data-ttu-id="89460-117">O conector do Power Automate fornece outras ações que não os acionadores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="89460-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="89460-118">Para mais informações, consulte o [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="89460-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="89460-119">Criar um fluxo Power Automate nos insights de audiência</span><span class="sxs-lookup"><span data-stu-id="89460-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="89460-120">Nos insights de audiência, vá a **Admin** > **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="89460-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="89460-121">Na página **Sistema**, selecione o separador **Estado**.</span><span class="sxs-lookup"><span data-stu-id="89460-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="89460-122">Na secção **Origens de Dados**, selecione **Fluxos** e selecione **Criar um fluxo** a partir da lista pendente.</span><span class="sxs-lookup"><span data-stu-id="89460-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89460-123">![Conector do Power Automate a mostrar a ação Criar um Fluxo](media/power-automate-connector-create-flow.png "Conector do Power Automate a mostrar a ação Criar um Fluxo")</span><span class="sxs-lookup"><span data-stu-id="89460-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="89460-124">No Power Automate, selecione um dos acionadores disponíveis para criar o seu fluxo preferencial.</span><span class="sxs-lookup"><span data-stu-id="89460-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="89460-125">Se estiver a criar o seu primeiro fluxo, terá de efetuar inicialmente a autenticação do conector do Power Automate.</span><span class="sxs-lookup"><span data-stu-id="89460-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>

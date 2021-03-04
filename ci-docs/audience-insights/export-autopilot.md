---
title: Exportar dados do Customer Insights para o Autopilot
description: Aprenda a configurar a ligação ao Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269252"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="2b478-103">Conector para o Autopilot (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="2b478-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="2b478-104">Exportar segmentos de perfis unificados de clientes para o Autopilot e utilizá-los para marketing de e-mail no Autopilot.</span><span class="sxs-lookup"><span data-stu-id="2b478-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2b478-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2b478-105">Prerequisites</span></span>

-   <span data-ttu-id="2b478-106">Tem uma [conta do Autopilot](https://www.autopilothq.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="2b478-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2b478-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="2b478-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2b478-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="2b478-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="2b478-109">Ligar ao Autopilot</span><span class="sxs-lookup"><span data-stu-id="2b478-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="2b478-110">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="2b478-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2b478-111">Sob **Autopilot**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2b478-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="2b478-112">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="2b478-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Painel de configuração para a ligação ao Autopilot.":::

1. <span data-ttu-id="2b478-114">Introduza a sua **Chave de API do Autopilot** [Chave de API do Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="2b478-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="2b478-115">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="2b478-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2b478-116">Selecione **Ligar** para inicializar a ligação ao Autopilot.</span><span class="sxs-lookup"><span data-stu-id="2b478-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="2b478-117">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2b478-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2b478-118">Selecione **Seguinte** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="2b478-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2b478-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="2b478-119">Configure the connector</span></span>

1. <span data-ttu-id="2b478-120">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="2b478-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2b478-121">Repita os mesmos passos para outros campos opcionais, tais como **Nome próprio**, **Apelido**.</span><span class="sxs-lookup"><span data-stu-id="2b478-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="2b478-122">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="2b478-122">Select the segments you want to export.</span></span> <span data-ttu-id="2b478-123">**Recomendamos que não exporte mais de 100.000 perfis de clientes no total** para o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="2b478-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="2b478-124">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b478-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2b478-125">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="2b478-125">Export the data</span></span>

<span data-ttu-id="2b478-126">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2b478-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2b478-127">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2b478-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2b478-128">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="2b478-128">Known limitations</span></span>

- <span data-ttu-id="2b478-129">Pode exportar até 100.000 perfis no total para o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="2b478-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="2b478-130">A exportação para o Autopilot está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="2b478-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="2b478-131">Exportar até 100.000 perfis para o Autopilot pode demorar até algumas horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="2b478-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="2b478-132">O número de perfis que pode exportar para o Autopilot é dependente e limitado no seu contrato com o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="2b478-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2b478-133">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="2b478-133">Data privacy and compliance</span></span>

<span data-ttu-id="2b478-134">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Autopilot, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="2b478-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2b478-135">A Microsoft transferirá esses dados a seu pedido, mas você é responsável por garantir que o Autopilot cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="2b478-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2b478-136">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2b478-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2b478-137">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2b478-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
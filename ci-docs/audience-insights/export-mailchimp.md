---
title: Exportar dados Customer Insights para a Mailchimp
description: Saiba como configurar a ligação a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267187"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="9cc46-103">Ligação para Mailchimp (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="9cc46-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="9cc46-104">Exportar segmentos de perfis unificados de clientes para Mailchimp para criar boletins informativos e campanhas de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="9cc46-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9cc46-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9cc46-105">Prerequisites</span></span>

-   <span data-ttu-id="9cc46-106">Tem uma [conta Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="9cc46-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9cc46-107">Existem audiências na Mailchimp e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9cc46-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="9cc46-108">Para mais informações, consulte [audiências da Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="9cc46-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="9cc46-109">Tem [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="9cc46-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="9cc46-110">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="9cc46-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="9cc46-111">Ligar ao Mailchimp</span><span class="sxs-lookup"><span data-stu-id="9cc46-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="9cc46-112">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="9cc46-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9cc46-113">Em **Mailchimp**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9cc46-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="9cc46-114">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="9cc46-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9cc46-115">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="9cc46-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9cc46-116">Introduza a sua **[ID de audiência da Mailchimp](https://mailchimp.com/help/find-audience-id/)** e selecione **Ligar** para iniciar a ligação à Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9cc46-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="9cc46-117">Selecione **Autenticar com a Mailchimp** e forneça as suas credenciais da Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9cc46-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="9cc46-118">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9cc46-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Exportar captura de ecrã para ligação a Mailchimp":::

1. <span data-ttu-id="9cc46-120">Selecione **Seguinte** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="9cc46-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9cc46-121">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="9cc46-121">Configure the connector</span></span>

1. <span data-ttu-id="9cc46-122">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="9cc46-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9cc46-123">Opcionalmente, pode exportar o **nome próprio** e o **apelido** como campos adicionais para criar e-mails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="9cc46-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="9cc46-124">Selecione **Adicionar atributo** para mapear estes campos.</span><span class="sxs-lookup"><span data-stu-id="9cc46-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9cc46-125">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="9cc46-125">Select the segments you want to export.</span></span> <span data-ttu-id="9cc46-126">Pode exportar até 1 milhão de perfis de clientes no total para a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9cc46-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selecionar campos e segmentos a exportar para Mailchimp":::

1. <span data-ttu-id="9cc46-128">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9cc46-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9cc46-129">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="9cc46-129">Export the data</span></span>

<span data-ttu-id="9cc46-130">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9cc46-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9cc46-131">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9cc46-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9cc46-132">Na Mailchimp, pode agora encontrar os seus segmentos nas [audiências da Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="9cc46-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9cc46-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="9cc46-133">Known limitations</span></span>

- <span data-ttu-id="9cc46-134">Até 1 milhão de perfis por exportar para a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9cc46-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="9cc46-135">A exportação para a Mailchimp é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="9cc46-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="9cc46-136">A exportação de segmentos com um total de 1 milhão de perfis pode demorar até três horas devido a limitações do lado do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="9cc46-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="9cc46-137">O número de perfis que pode exportar para a Mailchimp está dependente e limitado ao seu contrato com a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9cc46-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9cc46-138">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="9cc46-138">Data privacy and compliance</span></span>

<span data-ttu-id="9cc46-139">Quando ativa Dynamics 365 Customer Insights para transmitir dados à Mailchimp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="9cc46-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9cc46-140">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Mailchimp cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="9cc46-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9cc46-141">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9cc46-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9cc46-142">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="9cc46-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
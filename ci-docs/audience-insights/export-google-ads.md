---
title: Exportar dados Customer Insights para o Google Ads
description: Saiba como configurar a ligação a Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598261"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="a76ca-103">Ligação para Google Ads (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="a76ca-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="a76ca-104">Exportar segmentos de perfis unificados de clientes para a lista de audiências do Google Ads e utilizá-los para fazer publicidade na Pesquisa Google, Gmail, YouTube, e Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="a76ca-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a76ca-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a76ca-105">Prerequisites</span></span>

-   <span data-ttu-id="a76ca-106">Tem uma [conta Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="a76ca-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a76ca-107">Existem audiências no Google Ads e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a76ca-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="a76ca-108">Para mais informações, consulte [audiências do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="a76ca-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="a76ca-109">Tem [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="a76ca-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="a76ca-110">Os perfis unificados dos clientes nos segmentos exportados contêm campos que representam um endereço de correio eletrónico, nome e apelido</span><span class="sxs-lookup"><span data-stu-id="a76ca-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="a76ca-111">Ligar ao Google Ads</span><span class="sxs-lookup"><span data-stu-id="a76ca-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="a76ca-112">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="a76ca-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a76ca-113">Em **Google Ads**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="a76ca-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="a76ca-114">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="a76ca-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a76ca-115">Introduza a sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="a76ca-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="a76ca-116">Introduza a sua **[token de programador aprovado do Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="a76ca-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="a76ca-117">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="a76ca-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a76ca-118">Introduza a sua **[ID de audiência do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e selecione **Ligar** para iniciar a ligação ao Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a76ca-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="a76ca-119">Selecione **Autenticar com o Google Ads** e forneça as suas credenciais do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a76ca-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="a76ca-120">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a76ca-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Exportar captura de ecrã para ligação ao Google Ads":::

1. <span data-ttu-id="a76ca-122">Selecione **Seguinte** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="a76ca-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a76ca-123">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="a76ca-123">Configure the connector</span></span>

1. <span data-ttu-id="a76ca-124">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="a76ca-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a76ca-125">Repita os mesmos passos para os campos **nome próprio** e **apelido**.</span><span class="sxs-lookup"><span data-stu-id="a76ca-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="a76ca-126">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="a76ca-126">Select the segments you want to export.</span></span> <span data-ttu-id="a76ca-127">Pode exportar até 1 milhão de perfis de clientes no total para o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a76ca-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="a76ca-128">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a76ca-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a76ca-129">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="a76ca-129">Export the data</span></span>

<span data-ttu-id="a76ca-130">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a76ca-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a76ca-131">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a76ca-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a76ca-132">No Google Ads, pode agora encontrar os seus segmentos nas [audiências do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="a76ca-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a76ca-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="a76ca-133">Known limitations</span></span>

- <span data-ttu-id="a76ca-134">Até 1 milhão de perfis por exportar para o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a76ca-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="a76ca-135">A exportação para o Google Ads é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="a76ca-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="a76ca-136">A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 5 minutos devido a limitações do lado do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a76ca-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="a76ca-137">A correspondência no Google Ads pode demorar até 48 horas.</span><span class="sxs-lookup"><span data-stu-id="a76ca-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a76ca-138">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="a76ca-138">Data privacy and compliance</span></span>

<span data-ttu-id="a76ca-139">Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Google Ads, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="a76ca-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a76ca-140">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Google Ads cumprem quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="a76ca-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a76ca-141">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a76ca-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a76ca-142">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="a76ca-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
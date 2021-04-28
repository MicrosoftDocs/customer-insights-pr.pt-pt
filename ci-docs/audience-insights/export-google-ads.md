---
title: Exportar dados Customer Insights para o Google Ads
description: Aprenda a configurar a ligação e exportar para o Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759707"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="83464-103">Exportar segmentos para o Google Ads (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="83464-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="83464-104">Exportar segmentos de perfis unificados de clientes para a lista de audiências do Google Ads e utilizá-los para fazer publicidade na Pesquisa Google, Gmail, YouTube, e Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="83464-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="83464-105">Pré-requisitos para a ligação</span><span class="sxs-lookup"><span data-stu-id="83464-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="83464-106">Tem uma [conta Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="83464-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="83464-107">Tem um [token de programador do Google Ads aprovado](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="83464-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="83464-108">Cumpre os requisitos da [Política de Correspondência de Clientes](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="83464-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="83464-109">Cumpre os requisitos dos [tamanhos da lista de remarketing](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="83464-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="83464-110">Existem audiências no Google Ads e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="83464-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="83464-111">Para mais informações, consulte [audiências do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="83464-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="83464-112">Tem [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="83464-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="83464-113">Os perfis unificados dos clientes nos segmentos exportados contêm campos que representam um endereço de correio eletrónico, nome e apelido</span><span class="sxs-lookup"><span data-stu-id="83464-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="83464-114">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="83464-114">Known limitations</span></span>

- <span data-ttu-id="83464-115">Até 1 milhão de perfis por exportar para o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="83464-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="83464-116">A exportação para o Google Ads é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="83464-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="83464-117">A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 5 minutos devido a limitações do lado do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="83464-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="83464-118">A correspondência no Google Ads pode demorar até 48 horas.</span><span class="sxs-lookup"><span data-stu-id="83464-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="83464-119">Configurar ligação ao Google Ads</span><span class="sxs-lookup"><span data-stu-id="83464-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="83464-120">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="83464-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="83464-121">Selecione **Adicionar ligação** e escolha **Google Ads** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="83464-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="83464-122">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="83464-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="83464-123">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="83464-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="83464-124">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="83464-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="83464-125">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="83464-125">Choose who can use this connection.</span></span> <span data-ttu-id="83464-126">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="83464-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="83464-127">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="83464-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="83464-128">Introduza a sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="83464-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="83464-129">Introduza a sua **[token de programador aprovado do Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="83464-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="83464-130">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="83464-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="83464-131">Selecione **Autenticar com o Google Ads** e forneça as suas credenciais do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="83464-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="83464-132">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="83464-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="83464-133">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="83464-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="83464-134">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="83464-134">Configure an export</span></span>

<span data-ttu-id="83464-135">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="83464-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="83464-136">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="83464-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="83464-137">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="83464-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="83464-138">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="83464-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="83464-139">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Google Ads.</span><span class="sxs-lookup"><span data-stu-id="83464-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="83464-140">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="83464-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="83464-141">Introduza a sua **[ID de audiência do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e selecione **Ligar** para iniciar a ligação ao Google Ads.</span><span class="sxs-lookup"><span data-stu-id="83464-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="83464-142">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="83464-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="83464-143">Repita os mesmos passos para os campos **nome próprio** e **apelido**.</span><span class="sxs-lookup"><span data-stu-id="83464-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="83464-144">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="83464-144">Select the segments you want to export.</span></span> <span data-ttu-id="83464-145">Pode exportar até 1 milhão de perfis de clientes no total para o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="83464-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="83464-146">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="83464-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="83464-147">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="83464-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="83464-148">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="83464-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="83464-149">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="83464-149">Data privacy and compliance</span></span>

<span data-ttu-id="83464-150">Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Google Ads, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="83464-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="83464-151">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Google Ads cumprem quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="83464-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="83464-152">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="83464-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="83464-153">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="83464-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

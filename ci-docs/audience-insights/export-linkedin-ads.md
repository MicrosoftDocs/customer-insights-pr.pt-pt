---
title: Exportar dados do Customer Insights para o LinkedIn Ads
description: Aprenda a configurar a ligação e exportar para o LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124536"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="094d4-103">Exportar segmentos para o LinkedIn Ads (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="094d4-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="094d4-104">Segmentos de exportação de perfis de clientes unificados para o LinkedIn Ads para criar Matched Audiences.</span><span class="sxs-lookup"><span data-stu-id="094d4-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="094d4-105">Utilize as Matched Audiences para direcionamento de empresa e direcionamento de contactos.</span><span class="sxs-lookup"><span data-stu-id="094d4-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="094d4-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="094d4-106">Prerequisites</span></span>

-   <span data-ttu-id="094d4-107">Tem uma [conta do LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e credenciais correspondentes de administrador.</span><span class="sxs-lookup"><span data-stu-id="094d4-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="094d4-108">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="094d4-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="094d4-109">Os perfis de clientes nos segmentos exportados contêm um campo com um endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="094d4-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="094d4-110">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="094d4-110">Known limitations</span></span>

- <span data-ttu-id="094d4-111">Pode exportar até 100 mil perfis por exportação para o LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="094d4-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="094d4-112">A exportação para o LinkedIn Ads limita-se a segmentos.</span><span class="sxs-lookup"><span data-stu-id="094d4-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="094d4-113">Exportar até 100 mil perfis para o LinkedIn Ads pode levar até 10 minutos a ser concluído.</span><span class="sxs-lookup"><span data-stu-id="094d4-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="094d4-114">Configure a ligação para o LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="094d4-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="094d4-115">No Audience Insights, vá a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="094d4-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="094d4-116">Selecione **Adicionar ligação** e escolha **LinkedIn Ads** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="094d4-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="094d4-117">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="094d4-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="094d4-118">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="094d4-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="094d4-119">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="094d4-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="094d4-120">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="094d4-120">Choose who can use this connection.</span></span> <span data-ttu-id="094d4-121">Se não tomar nenhuma ação, a predefinição é administradores.</span><span class="sxs-lookup"><span data-stu-id="094d4-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="094d4-122">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="094d4-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="094d4-123">Forneça o seu [ID da Conta do LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="094d4-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="094d4-124">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="094d4-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="094d4-125">Selecione **Ligar** para inicializar a ligação à Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="094d4-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="094d4-126">Selecione **Autenticar com o LinkedIn** e forneça as suas credenciais de admin para o LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="094d4-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="094d4-127">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="094d4-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="094d4-128">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="094d4-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="094d4-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="094d4-129">Configure an export</span></span>

<span data-ttu-id="094d4-130">Pode configurar uma exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="094d4-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="094d4-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="094d4-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="094d4-132">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="094d4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="094d4-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="094d4-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="094d4-134">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="094d4-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="094d4-135">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="094d4-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="094d4-136">Escolha se pretende exportar dados para [direcionamento de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou [direcionamento de empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) no LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="094d4-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="094d4-137">Na secção **Correspondência de dados**, selecione o campo no seu perfil de cliente unificado que representa o endereço de e-mail de um cliente.</span><span class="sxs-lookup"><span data-stu-id="094d4-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="094d4-138">É obrigatório exportar segmentos para o LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="094d4-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="094d4-139">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="094d4-139">Select the segments you want to export.</span></span> <span data-ttu-id="094d4-140">As Matched Audiences no LinkedIn Campaign Manager serão automaticamente criadas com o nome dos segmentos que selecionou para exportar.</span><span class="sxs-lookup"><span data-stu-id="094d4-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="094d4-141">Cada segmento resultará num Matched Audience separada.</span><span class="sxs-lookup"><span data-stu-id="094d4-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="094d4-142">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="094d4-142">Select **Save**.</span></span>

<span data-ttu-id="094d4-143">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="094d4-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="094d4-144">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="094d4-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="094d4-145">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="094d4-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="094d4-146">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="094d4-146">Data privacy and compliance</span></span>

<span data-ttu-id="094d4-147">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o LinkedIn Ads, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="094d4-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="094d4-148">A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que o LinkedIn Ads cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="094d4-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="094d4-149">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="094d4-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="094d4-150">O seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para parar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="094d4-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>

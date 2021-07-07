---
title: Exportar dados do Customer Insights para a ActiveCampaign
description: Aprenda a configurar a ligação e a exportar para a ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314659"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="43abf-103">Exportar segmentos para a ActiveCampaign (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="43abf-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="43abf-104">Exporte segmentos de perfis de clientes unificados para a ActiveCampaign e utilize-os para atividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="43abf-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43abf-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="43abf-105">Prerequisites</span></span>

-   <span data-ttu-id="43abf-106">Tem uma [conta ActiveCampaign](https://www.activecampaign.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="43abf-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="43abf-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="43abf-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="43abf-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo com um endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="43abf-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="43abf-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="43abf-109">Known limitations</span></span>

- <span data-ttu-id="43abf-110">Pode exportar até 1 milhão de perfis por exportação para a ActiveCampaign e pode levar até 90 minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="43abf-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="43abf-111">A exportação para ActiveCampaign está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="43abf-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="43abf-112">O número de perfis que pode exportar para a ActiveCampaign depende do seu contrato com a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="43abf-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="43abf-113">Configure a ligação para a ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="43abf-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="43abf-114">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="43abf-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="43abf-115">Selecione **Adicionar ligação** e escolha **ActiveCampaign** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="43abf-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="43abf-116">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="43abf-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="43abf-117">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="43abf-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="43abf-118">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="43abf-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="43abf-119">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="43abf-119">Choose who can use this connection.</span></span> <span data-ttu-id="43abf-120">Por predefinição, são apenas administradores.</span><span class="sxs-lookup"><span data-stu-id="43abf-120">By default, it's only administrators.</span></span> <span data-ttu-id="43abf-121">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="43abf-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="43abf-122">Introduza a [chave de API ActiveCampaign e o Nome do Anfitrião de Ponto Final REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="43abf-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="43abf-123">O Nome do Anfitrião do Ponto Final REST é apenas o nome de anfitrião, sem https://.</span><span class="sxs-lookup"><span data-stu-id="43abf-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="43abf-124">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="43abf-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="43abf-125">Selecione **Ligar** para inicializar a ligação para a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="43abf-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="43abf-126">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="43abf-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="43abf-127">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="43abf-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="43abf-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="43abf-128">Configure an export</span></span>

<span data-ttu-id="43abf-129">Pode configurar uma exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="43abf-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="43abf-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="43abf-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="43abf-131">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="43abf-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="43abf-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="43abf-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="43abf-133">No campo **Ligação à exportação**, escolha uma ligação a partir da secção ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="43abf-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="43abf-134">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="43abf-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="43abf-135">Introduza o [**ID de Lista ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="43abf-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="43abf-136">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="43abf-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="43abf-137">É obrigatório para exportar segmentos para ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="43abf-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="43abf-138">Opcionalmente, pode exportar Nome próprio, Apelido e Telefone para criar e-mails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="43abf-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="43abf-139">Selecione Adicionar atributo para mapear estes campos.</span><span class="sxs-lookup"><span data-stu-id="43abf-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="43abf-140">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="43abf-140">Select **Save**.</span></span>

<span data-ttu-id="43abf-141">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="43abf-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="43abf-142">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="43abf-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="43abf-143">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="43abf-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="43abf-144">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="43abf-144">Data privacy and compliance</span></span>

<span data-ttu-id="43abf-145">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a ActiveCampaign, permite a transferência de dados para fora do limite de conformidade para o Dynamics 365 Customer Insights , incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="43abf-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="43abf-146">A Microsoft transferirá esses dados conforme as suas instruções, mas você é responsável por garantir que a ActiveCampaign cumpre quaisquer obrigações de privacidade ou de segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="43abf-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="43abf-147">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="43abf-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="43abf-148">O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="43abf-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

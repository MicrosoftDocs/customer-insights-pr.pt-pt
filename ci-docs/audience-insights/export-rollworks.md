---
title: Exportar dados do Customer Insights para a RollWorks
description: Aprenda a configurar a ligação e exportar para a RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760608"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="f455d-103">Exportar listas de segmentos para a RollWorks (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="f455d-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="f455d-104">Exporte segmentos de perfis de clientes unificados para a RollWorks e utilize-os para publicidade.</span><span class="sxs-lookup"><span data-stu-id="f455d-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f455d-105">Pré-requisitos para uma ligação</span><span class="sxs-lookup"><span data-stu-id="f455d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f455d-106">Tem uma [conta da RollWorks](https://www.rollworks.com/) e credenciais correspondentes de administrador.</span><span class="sxs-lookup"><span data-stu-id="f455d-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f455d-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="f455d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f455d-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="f455d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f455d-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="f455d-109">Known limitations</span></span>

- <span data-ttu-id="f455d-110">Pode exportar até 250.000 perfis por exportação para a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="f455d-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="f455d-111">Não é possível exportar segmentos com menos de 100 perfis para a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="f455d-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="f455d-112">A exportação para a RollWorks limita-se a segmentos.</span><span class="sxs-lookup"><span data-stu-id="f455d-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="f455d-113">Exportar até 250.000 perfis para a RollWorks pode levar até 10 minutos a ser concluído.</span><span class="sxs-lookup"><span data-stu-id="f455d-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="f455d-114">O número de perfis que pode exportar para a RollWorks dependente e está limitado no seu contrato com a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="f455d-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="f455d-115">Configurar ligação à RollWorks</span><span class="sxs-lookup"><span data-stu-id="f455d-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="f455d-116">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="f455d-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f455d-117">Selecione **Adicionar ligação** e escolha **RollWorks** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="f455d-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="f455d-118">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="f455d-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f455d-119">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="f455d-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f455d-120">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="f455d-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f455d-121">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="f455d-121">Choose who can use this connection.</span></span> <span data-ttu-id="f455d-122">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="f455d-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f455d-123">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f455d-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f455d-124">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="f455d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f455d-125">Selecione **Ligar** para inicializar a ligação à RollWorks.</span><span class="sxs-lookup"><span data-stu-id="f455d-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="f455d-126">Selecione **Autenticar com a RollWorks** e forneça as suas credenciais de admin para a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="f455d-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="f455d-127">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f455d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f455d-128">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="f455d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f455d-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="f455d-129">Configure an export</span></span>

<span data-ttu-id="f455d-130">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="f455d-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f455d-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f455d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f455d-132">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="f455d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f455d-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="f455d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f455d-134">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção RollWorks.</span><span class="sxs-lookup"><span data-stu-id="f455d-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="f455d-135">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="f455d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f455d-136">Introduza o seu **ID de Anunciante da RollWorks** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="f455d-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="f455d-137">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="f455d-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f455d-138">É obrigatório exportar segmentos para a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="f455d-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="f455d-139">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="f455d-139">Select the segments you want to export.</span></span> <span data-ttu-id="f455d-140">Selecione um segmento com, pelo menos, 100 membros.</span><span class="sxs-lookup"><span data-stu-id="f455d-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="f455d-141">Não pode exportar segmentos menores.</span><span class="sxs-lookup"><span data-stu-id="f455d-141">You can't export smaller segments.</span></span> <span data-ttu-id="f455d-142">Além disso, o tamanho máximo de um segmento para exportar é de 250.000 membros por exportação.</span><span class="sxs-lookup"><span data-stu-id="f455d-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="f455d-143">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f455d-143">Select **Save**.</span></span>

<span data-ttu-id="f455d-144">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f455d-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f455d-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f455d-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f455d-146">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f455d-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f455d-147">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="f455d-147">Data privacy and compliance</span></span>

<span data-ttu-id="f455d-148">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a RollWorks, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="f455d-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f455d-149">A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que a RollWorks cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="f455d-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f455d-150">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f455d-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f455d-151">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f455d-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

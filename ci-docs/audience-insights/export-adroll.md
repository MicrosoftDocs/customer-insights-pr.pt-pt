---
title: Exportar dados do Customer Insights para o AdRoll
description: Aprenda a configurar a ligação e exportar para o AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895973"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="b838b-103">Exportar listas de segmentos para o AdRoll (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="b838b-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="b838b-104">Exportar segmentos de perfis de clientes unificados para o AdRoll e usá-los para publicidade.</span><span class="sxs-lookup"><span data-stu-id="b838b-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b838b-105">Pré-requisitos para uma ligação</span><span class="sxs-lookup"><span data-stu-id="b838b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="b838b-106">Tem uma [conta do AdRoll](https://www.adroll.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="b838b-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b838b-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="b838b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b838b-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="b838b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b838b-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="b838b-109">Known limitations</span></span>

- <span data-ttu-id="b838b-110">Pode exportar até 250.000 perfis por exportação para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b838b-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="b838b-111">Não pode exportar segmentos com menos de 100 perfis para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b838b-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="b838b-112">A exportação para o AdRoll está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="b838b-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="b838b-113">Exportar até 250.000 perfis para o AdRoll pode demorar até 10 minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="b838b-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="b838b-114">O número de perfis que pode exportar para o AdRoll é dependente e limitado no seu contrato com o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b838b-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="b838b-115">Configure a ligação para o AdRoll</span><span class="sxs-lookup"><span data-stu-id="b838b-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="b838b-116">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="b838b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b838b-117">Selecione **Adicionar ligação** e escolha **AdRoll** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="b838b-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="b838b-118">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="b838b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b838b-119">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="b838b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b838b-120">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="b838b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b838b-121">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="b838b-121">Choose who can use this connection.</span></span> <span data-ttu-id="b838b-122">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="b838b-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b838b-123">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b838b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b838b-124">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="b838b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b838b-125">Selecione **Ligar** para inicializar a ligação ao AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b838b-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="b838b-126">Selecione **Autenticar com o AdRoll** e forneça as suas credenciais de administrador para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b838b-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="b838b-127">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b838b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b838b-128">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="b838b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b838b-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="b838b-129">Configure an export</span></span>

<span data-ttu-id="b838b-130">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="b838b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b838b-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b838b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b838b-132">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="b838b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b838b-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="b838b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b838b-134">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b838b-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="b838b-135">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="b838b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b838b-136">Introduza o seu **ID do Anunciante do AdRoll**. Para mais informações, consulte [Perfis do Anunciante do AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="b838b-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="b838b-137">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="b838b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b838b-138">É necessário exportar segmentos para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b838b-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="b838b-139">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="b838b-139">Select the segments you want to export.</span></span> <span data-ttu-id="b838b-140">Selecione um segmento com, pelo menos, 100 membros.</span><span class="sxs-lookup"><span data-stu-id="b838b-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="b838b-141">Não pode exportar segmentos menores.</span><span class="sxs-lookup"><span data-stu-id="b838b-141">You can't export smaller segments.</span></span> <span data-ttu-id="b838b-142">Além disso, o tamanho máximo de um segmento para exportar é de 250.000 membros por exportação.</span><span class="sxs-lookup"><span data-stu-id="b838b-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="b838b-143">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b838b-143">Select **Save**.</span></span>

<span data-ttu-id="b838b-144">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b838b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b838b-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b838b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b838b-146">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b838b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b838b-147">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="b838b-147">Data privacy and compliance</span></span>

<span data-ttu-id="b838b-148">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o AdRoll, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="b838b-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b838b-149">A Microsoft transferirá esses dados a seu pedido, mas o utilizador responsável por garantir que o AdRoll cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="b838b-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b838b-150">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b838b-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b838b-151">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="b838b-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

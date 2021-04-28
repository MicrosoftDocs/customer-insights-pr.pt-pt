---
title: Exportar dados do Customer Insights para o Autopilot
description: Aprenda a configurar a ligação e exportar para o Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760157"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="4636b-103">Exportar segmentos para o Autopilot (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="4636b-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="4636b-104">Exportar segmentos de perfis unificados de clientes para o Autopilot e utilizá-los para marketing de e-mail no Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4636b-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4636b-105">Pré-requisitos para uma ligação</span><span class="sxs-lookup"><span data-stu-id="4636b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="4636b-106">Tem uma [conta do Autopilot](https://www.autopilothq.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="4636b-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4636b-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="4636b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4636b-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="4636b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4636b-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="4636b-109">Known limitations</span></span>

- <span data-ttu-id="4636b-110">Pode exportar até 100.000 perfis no total para o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4636b-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="4636b-111">A exportação para o Autopilot está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="4636b-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="4636b-112">Exportar até 100.000 perfis para o Autopilot pode demorar até algumas horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4636b-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="4636b-113">O número de perfis que pode exportar para o Autopilot é dependente e limitado no seu contrato com o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4636b-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="4636b-114">Configure a ligação para o Autopilot</span><span class="sxs-lookup"><span data-stu-id="4636b-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="4636b-115">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="4636b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4636b-116">Selecione **Adicionar ligação** e escolha **Autopilot** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="4636b-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="4636b-117">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="4636b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4636b-118">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="4636b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4636b-119">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="4636b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4636b-120">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="4636b-120">Choose who can use this connection.</span></span> <span data-ttu-id="4636b-121">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="4636b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4636b-122">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4636b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="4636b-123">Introduza a sua [chave de API do Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="4636b-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="4636b-124">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="4636b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4636b-125">Selecione **Ligar** para inicializar a ligação ao Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4636b-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="4636b-126">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4636b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4636b-127">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="4636b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4636b-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="4636b-128">Configure an export</span></span>

<span data-ttu-id="4636b-129">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="4636b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4636b-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4636b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4636b-131">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="4636b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4636b-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="4636b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4636b-133">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4636b-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="4636b-134">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="4636b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="4636b-135">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="4636b-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4636b-136">Repita os mesmos passos para outros campos opcionais, tais como **Nome próprio**, **Apelido**.</span><span class="sxs-lookup"><span data-stu-id="4636b-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="4636b-137">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="4636b-137">Select the segments you want to export.</span></span> <span data-ttu-id="4636b-138">**Recomendamos que não exporte mais de 100.000 perfis de clientes no total** para o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4636b-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="4636b-139">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4636b-139">Select **Save**.</span></span>

<span data-ttu-id="4636b-140">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4636b-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4636b-141">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4636b-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4636b-142">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4636b-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4636b-143">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="4636b-143">Data privacy and compliance</span></span>

<span data-ttu-id="4636b-144">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Autopilot, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="4636b-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4636b-145">A Microsoft transferirá esses dados a seu pedido, mas você é responsável por garantir que o Autopilot cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="4636b-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="4636b-146">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4636b-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4636b-147">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="4636b-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

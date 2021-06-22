---
title: Exportar dados do Customer Insights para o Microsoft Advertising
description: Aprenda a configurar a ligação e exportar para para o Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124534"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="354d4-103">Exportar segmentos para o Microsoft Advertising (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="354d4-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="354d4-104">Exporte segmentos do Customer Insights para o Microsoft Advertising para criar audiências de Correspondência de Clientes.</span><span class="sxs-lookup"><span data-stu-id="354d4-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="354d4-105">Utilize estas audiências para as suas campanhas publicitárias.</span><span class="sxs-lookup"><span data-stu-id="354d4-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="354d4-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="354d4-106">Prerequisites</span></span>

-   <span data-ttu-id="354d4-107">Uma [conta do Microsoft Advertising](https://ads.microsoft.com/) e credenciais correspondentes de administrador.</span><span class="sxs-lookup"><span data-stu-id="354d4-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="354d4-108">Aceitou os termos de utilização de Correspondência de Clientes.</span><span class="sxs-lookup"><span data-stu-id="354d4-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="354d4-109">[Segmentos configurados](segments.md) nas informações de audiência.</span><span class="sxs-lookup"><span data-stu-id="354d4-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="354d4-110">Os perfis de clientes unificados nos segmentos exportados contêm um campo com um endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="354d4-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="354d4-111">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="354d4-111">Known limitations</span></span>

- <span data-ttu-id="354d4-112">Pode exportar até 500 mil perfis por exportação para o Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="354d4-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="354d4-113">A exportação para o Microsoft Advertising limita-se a segmentos.</span><span class="sxs-lookup"><span data-stu-id="354d4-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="354d4-114">Exportar até 500 mil perfis para o Microsoft Advertising pode levar até 10 minutos a ser concluído.</span><span class="sxs-lookup"><span data-stu-id="354d4-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="354d4-115">Configure a ligação ao Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="354d4-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="354d4-116">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="354d4-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="354d4-117">Selecione **Adicionar ligação** e escolha **Microsoft Advertising** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="354d4-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="354d4-118">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="354d4-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="354d4-119">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="354d4-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="354d4-120">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="354d4-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="354d4-121">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="354d4-121">Choose who can use this connection.</span></span> <span data-ttu-id="354d4-122">A predefinição é administradores.</span><span class="sxs-lookup"><span data-stu-id="354d4-122">The default is administrators.</span></span> <span data-ttu-id="354d4-123">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="354d4-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="354d4-124">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="354d4-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="354d4-125">Selecione **Ligar** para inicializar a ligação ao Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="354d4-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="354d4-126">Selecione **Autenticar com o Microsoft Advertising** e forneça as suas credenciais de admin para o Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="354d4-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="354d4-127">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="354d4-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="354d4-128">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="354d4-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="354d4-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="354d4-129">Configure an export</span></span>

<span data-ttu-id="354d4-130">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="354d4-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="354d4-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="354d4-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="354d4-132">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="354d4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="354d4-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="354d4-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="354d4-134">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="354d4-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="354d4-135">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="354d4-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="354d4-136">Selecione os segmentos a exportar.</span><span class="sxs-lookup"><span data-stu-id="354d4-136">Select the segments to export.</span></span> <span data-ttu-id="354d4-137">As audiências de Correspondência de Clientes no Microsoft Advertising são automaticamente criadas com o nome dos segmentos selecionados para exportação.</span><span class="sxs-lookup"><span data-stu-id="354d4-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="354d4-138">Cada segmento resultará num audiência de Correspondência de Clientes separada.</span><span class="sxs-lookup"><span data-stu-id="354d4-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="354d4-139">Introduza o seu **ID de Cliente e ID da Conta do Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="354d4-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="354d4-140">Pode encontrar o ID de Cliente (`cid`) e o ID da Conta (`aid`) nos parâmetros do URL quando estiver registado no Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="354d4-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="354d4-141">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil de cliente unificado com o endereço de e-mail de um cliente.</span><span class="sxs-lookup"><span data-stu-id="354d4-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="354d4-142">É obrigatório exportar segmentos para o Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="354d4-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="354d4-143">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="354d4-143">Select **Save**.</span></span>

<span data-ttu-id="354d4-144">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="354d4-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="354d4-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="354d4-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="354d4-146">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="354d4-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="354d4-147">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="354d4-147">Data privacy and compliance</span></span>

<span data-ttu-id="354d4-148">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Microsoft Advertising, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="354d4-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="354d4-149">A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que o Microsoft Advertising cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="354d4-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="354d4-150">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="354d4-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="354d4-151">O seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para parar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="354d4-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>

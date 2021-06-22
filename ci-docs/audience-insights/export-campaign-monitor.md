---
title: Exportar dados do Customer Insights para a Campaign Monitor
description: Aprenda a configurar a ligação e exportar para a Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124195"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="a800f-103">Exportar segmentos para o Monitor de Campanha (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="a800f-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="a800f-104">Exporte segmentos de perfis de clientes unificados para a Campaign Monitor e utilize-os para atividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="a800f-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a800f-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a800f-105">Prerequisites</span></span>

-   <span data-ttu-id="a800f-106">Tem uma [conta da Campaign Monitor](https://www.campaignmonitor.com/) e credenciais correspondentes de administrador.</span><span class="sxs-lookup"><span data-stu-id="a800f-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a800f-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="a800f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a800f-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="a800f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a800f-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="a800f-109">Known limitations</span></span>

- <span data-ttu-id="a800f-110">Pode exportar até 1 milhão de perfis por exportação para a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a800f-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="a800f-111">A exportação para a Campaign Monitor limita-se a segmentos.</span><span class="sxs-lookup"><span data-stu-id="a800f-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="a800f-112">Exportar até 1 milhão de perfis para a Campaign Monitor pode levar até 20 minutos a ser concluído.</span><span class="sxs-lookup"><span data-stu-id="a800f-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="a800f-113">O número de perfis que pode exportar para a Campaign Monitor dependente e está limitado no seu contrato com a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a800f-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="a800f-114">Configurar ligação aa Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="a800f-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="a800f-115">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="a800f-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a800f-116">Selecione **Adicionar ligação** e escolha **Campaign Monitor** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="a800f-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="a800f-117">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="a800f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a800f-118">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="a800f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a800f-119">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="a800f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a800f-120">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="a800f-120">Choose who can use this connection.</span></span> <span data-ttu-id="a800f-121">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="a800f-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a800f-122">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a800f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a800f-123">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="a800f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a800f-124">Selecione **Ligar** para inicializar a ligação à Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a800f-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="a800f-125">Selecione **Autenticar com a Campaign Monitor** e forneça as suas credenciais de admin para a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a800f-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="a800f-126">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a800f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a800f-127">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="a800f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a800f-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="a800f-128">Configure an export</span></span>

<span data-ttu-id="a800f-129">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="a800f-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a800f-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a800f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a800f-131">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="a800f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a800f-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="a800f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a800f-133">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a800f-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="a800f-134">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="a800f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a800f-135">Introduza o seu [**ID da Lista da Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="a800f-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="a800f-136">[Gerar a chave de API](https://www.campaignmonitor.com/api/getting-started/) a partir de **Definições de Conta** na Campaign Monitor primeiro para ver o ID da lista de API.</span><span class="sxs-lookup"><span data-stu-id="a800f-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="a800f-137">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="a800f-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a800f-138">É obrigatório exportar segmentos para a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a800f-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="a800f-139">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a800f-139">Select **Save**.</span></span>

<span data-ttu-id="a800f-140">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="a800f-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a800f-141">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a800f-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a800f-142">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a800f-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a800f-143">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="a800f-143">Data privacy and compliance</span></span>

<span data-ttu-id="a800f-144">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a Campaign Monitor, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="a800f-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a800f-145">A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que a Campaign Monitor cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="a800f-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a800f-146">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a800f-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a800f-147">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="a800f-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

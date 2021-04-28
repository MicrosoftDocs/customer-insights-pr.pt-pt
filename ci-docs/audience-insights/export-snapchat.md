---
title: Exportar dados do Customer Insights para o Snapchat
description: Aprenda a configurar a ligação e exportar para o Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760605"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="7aceb-103">Exportar listas de segmentos para o Snapchat (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="7aceb-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="7aceb-104">Exporte segmentos de perfis de clientes unificados para o Snapchat e utilize-os para publicidade.</span><span class="sxs-lookup"><span data-stu-id="7aceb-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="7aceb-105">Pré-requisitos para uma ligação</span><span class="sxs-lookup"><span data-stu-id="7aceb-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="7aceb-106">Tem uma [conta Snapchat Business](https://business.snapchat.com/), uma [conta Snapchat Ads](https://ads.snapchat.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7aceb-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7aceb-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="7aceb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7aceb-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="7aceb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7aceb-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="7aceb-109">Known limitations</span></span>

- <span data-ttu-id="7aceb-110">A exportação para o Snapchat limita-se a segmentos.</span><span class="sxs-lookup"><span data-stu-id="7aceb-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="7aceb-111">Exportar até 1 milhão de perfis para o Snapchat pode levar até 15 minutos a ser concluído.</span><span class="sxs-lookup"><span data-stu-id="7aceb-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="7aceb-112">Configurar ligação ao Snapchat</span><span class="sxs-lookup"><span data-stu-id="7aceb-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="7aceb-113">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="7aceb-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7aceb-114">Selecione **Adicionar ligação** e escolha **Snapchat** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="7aceb-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="7aceb-115">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="7aceb-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7aceb-116">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="7aceb-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7aceb-117">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="7aceb-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7aceb-118">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="7aceb-118">Choose who can use this connection.</span></span> <span data-ttu-id="7aceb-119">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="7aceb-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7aceb-120">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7aceb-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7aceb-121">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="7aceb-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7aceb-122">Selecione **Ligar** para inicializar a ligação ao Snapchat.</span><span class="sxs-lookup"><span data-stu-id="7aceb-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="7aceb-123">Selecione **Autenticar com o Snapchat** e forneça as suas credenciais de admin para o Snapchat.</span><span class="sxs-lookup"><span data-stu-id="7aceb-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="7aceb-124">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7aceb-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7aceb-125">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="7aceb-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7aceb-126">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="7aceb-126">Configure an export</span></span>

<span data-ttu-id="7aceb-127">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="7aceb-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7aceb-128">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7aceb-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7aceb-129">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="7aceb-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7aceb-130">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="7aceb-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7aceb-131">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Snapchat.</span><span class="sxs-lookup"><span data-stu-id="7aceb-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="7aceb-132">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="7aceb-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7aceb-133">Introduza o [**ID de Audiência do Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="7aceb-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="7aceb-134">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="7aceb-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7aceb-135">É obrigatório exportar segmentos para o Snapchat.</span><span class="sxs-lookup"><span data-stu-id="7aceb-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="7aceb-136">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="7aceb-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="7aceb-137">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7aceb-137">Select **Save**.</span></span>

<span data-ttu-id="7aceb-138">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="7aceb-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7aceb-139">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7aceb-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7aceb-140">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7aceb-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7aceb-141">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="7aceb-141">Data privacy and compliance</span></span>

<span data-ttu-id="7aceb-142">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Snapchat, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="7aceb-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7aceb-143">A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que o Snapchat cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="7aceb-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7aceb-144">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7aceb-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="7aceb-145">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="7aceb-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

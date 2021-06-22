---
title: Exportar dados do Customer Insights para a Constant Contact
description: Aprenda a configurar a ligação e exportar para a Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124287"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="8f515-103">Exportar segmentos para o Constant Contact (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="8f515-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="8f515-104">Exporte segmentos de perfis de clientes unificados para a Constant Contact e utilize-os para atividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="8f515-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="8f515-105">Pré-requisitos para uma ligação</span><span class="sxs-lookup"><span data-stu-id="8f515-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="8f515-106">Tem uma [conta da Constant Contact](https://www.constantcontact.com/account-home) e credenciais correspondentes de administrador.</span><span class="sxs-lookup"><span data-stu-id="8f515-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8f515-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="8f515-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8f515-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="8f515-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8f515-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="8f515-109">Known limitations</span></span>

- <span data-ttu-id="8f515-110">Pode exportar até 1 milhão de perfis por exportação para a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="8f515-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="8f515-111">A exportação para a Constant Contact limita-se a segmentos.</span><span class="sxs-lookup"><span data-stu-id="8f515-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="8f515-112">Exportar até 1 milhão de perfis para a Constant Contact pode levar até 1 hora a ser concluído.</span><span class="sxs-lookup"><span data-stu-id="8f515-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="8f515-113">O número de perfis que pode exportar para a Constant Contact dependente e está limitado no seu contrato com a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="8f515-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="8f515-114">Configurar uma ligação à Constant Contact</span><span class="sxs-lookup"><span data-stu-id="8f515-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="8f515-115">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="8f515-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8f515-116">Selecione **Adicionar ligação** e escolha **Constant Contact** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="8f515-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="8f515-117">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="8f515-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8f515-118">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="8f515-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8f515-119">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="8f515-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8f515-120">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="8f515-120">Choose who can use this connection.</span></span> <span data-ttu-id="8f515-121">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="8f515-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8f515-122">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8f515-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8f515-123">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="8f515-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8f515-124">Selecione **Ligar** para inicializar a ligação à Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="8f515-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="8f515-125">Selecione **Autenticar com o AdRoll** e forneça as suas credenciais de admin para a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="8f515-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="8f515-126">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8f515-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8f515-127">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="8f515-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8f515-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="8f515-128">Configure an export</span></span>

<span data-ttu-id="8f515-129">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="8f515-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8f515-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8f515-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8f515-131">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="8f515-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8f515-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="8f515-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8f515-133">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="8f515-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="8f515-134">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="8f515-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8f515-135">Introduza o seu [**ID da Lista da Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="8f515-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="8f515-136">Abra uma lista na Constant Contact para encontrar o ID da lista no URL.</span><span class="sxs-lookup"><span data-stu-id="8f515-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="8f515-137">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="8f515-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8f515-138">É obrigatório exportar segmentos para a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="8f515-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="8f515-139">Opcionalmente, pode exportar o nome próprio e o apelido como campos adicionais para criar e-mails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="8f515-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="8f515-140">Selecione **Adicionar atributo** para mapear estes campos.</span><span class="sxs-lookup"><span data-stu-id="8f515-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8f515-141">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="8f515-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="8f515-142">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8f515-142">Select **Save**.</span></span>

<span data-ttu-id="8f515-143">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="8f515-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8f515-144">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8f515-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8f515-145">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8f515-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8f515-146">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="8f515-146">Data privacy and compliance</span></span>

<span data-ttu-id="8f515-147">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a Constant Contact, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="8f515-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8f515-148">A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que a Constant Contact cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="8f515-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8f515-149">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8f515-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8f515-150">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="8f515-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
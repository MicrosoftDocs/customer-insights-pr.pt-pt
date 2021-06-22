---
title: Exportar dados Customer Insights para a Mailchimp
description: Aprenda a configurar a ligação e exportar para o Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124241"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="b98cd-103">Exportar segmentos para o Mailchimp (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="b98cd-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="b98cd-104">Exportar segmentos de perfis unificados de clientes para Mailchimp para criar boletins informativos e campanhas de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="b98cd-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b98cd-105">Pré-requisitos para a ligação</span><span class="sxs-lookup"><span data-stu-id="b98cd-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="b98cd-106">Tem uma [conta Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="b98cd-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b98cd-107">Existem audiências na Mailchimp e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="b98cd-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="b98cd-108">Para mais informações, consulte [audiências da Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="b98cd-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="b98cd-109">Tem [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="b98cd-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="b98cd-110">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="b98cd-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b98cd-111">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="b98cd-111">Known limitations</span></span>

- <span data-ttu-id="b98cd-112">Até 1 milhão de perfis por exportar para a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="b98cd-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="b98cd-113">A exportação para a Mailchimp é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="b98cd-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="b98cd-114">Exportar segmentos com 1 milhão de perfis pode demorar até três horas.</span><span class="sxs-lookup"><span data-stu-id="b98cd-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="b98cd-115">O número de perfis que pode exportar para a Mailchimp está dependente e limitado ao seu contrato com a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="b98cd-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="b98cd-116">Configurar ligação ao Mailchimp</span><span class="sxs-lookup"><span data-stu-id="b98cd-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="b98cd-117">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="b98cd-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b98cd-118">Selecione **Adicionar ligação** e escolha **Autopilot** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="b98cd-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="b98cd-119">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="b98cd-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b98cd-120">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="b98cd-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b98cd-121">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="b98cd-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b98cd-122">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="b98cd-122">Choose who can use this connection.</span></span> <span data-ttu-id="b98cd-123">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="b98cd-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b98cd-124">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b98cd-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b98cd-125">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="b98cd-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b98cd-126">Selecione **Ligar** para inicializar a ligação ao Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="b98cd-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="b98cd-127">Selecione **Autenticar com a Mailchimp** e forneça as suas credenciais da Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="b98cd-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="b98cd-128">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b98cd-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b98cd-129">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="b98cd-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="b98cd-130">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="b98cd-130">Configure the connector</span></span>

<span data-ttu-id="b98cd-131">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="b98cd-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b98cd-132">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b98cd-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b98cd-133">Aceda a **Dados**> **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="b98cd-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="b98cd-134">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="b98cd-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b98cd-135">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="b98cd-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="b98cd-136">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="b98cd-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b98cd-137">Introduza o seu **[ID da audiência do Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="b98cd-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="b98cd-138">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="b98cd-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="b98cd-139">Opcionalmente, pode exportar **Nome próprio** e **Apelido** para criar e-mails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="b98cd-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="b98cd-140">Selecione **Adicionar atributo** para mapear estes campos.</span><span class="sxs-lookup"><span data-stu-id="b98cd-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="b98cd-141">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="b98cd-141">Select the segments you want to export.</span></span> <span data-ttu-id="b98cd-142">Pode exportar até 1 milhão de perfis de clientes no total para a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="b98cd-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="b98cd-143">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b98cd-143">Select **Save**.</span></span>

<span data-ttu-id="b98cd-144">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b98cd-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b98cd-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b98cd-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b98cd-146">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b98cd-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b98cd-147">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="b98cd-147">Data privacy and compliance</span></span>

<span data-ttu-id="b98cd-148">Quando ativa Dynamics 365 Customer Insights para transmitir dados à Mailchimp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="b98cd-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b98cd-149">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Mailchimp cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="b98cd-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b98cd-150">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b98cd-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b98cd-151">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="b98cd-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Exportar dados do Customer Insights para a Sendinblue
description: Aprenda a configurar a ligação e a exportar para a Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314658"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="47062-103">Exportar segmentos para a Sendinblue (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="47062-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="47062-104">Exporte segmentos de perfis de clientes unificados para gerar campanhas, fornecer marketing por e-mail e utilizar grupos de clientes específicos com a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="47062-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="47062-105">Pré-requisitos para a ligação</span><span class="sxs-lookup"><span data-stu-id="47062-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="47062-106">Tem uma [conta Sendinblue](https://www.sendinblue.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="47062-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="47062-107">Existem listas existentes na Sendinblue e nos IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="47062-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="47062-108">Tem [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="47062-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="47062-109">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="47062-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="47062-110">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="47062-110">Known limitations</span></span>

- <span data-ttu-id="47062-111">Até 1 milhão de perfis por exportação para a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="47062-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="47062-112">A exportação para Sendinblue está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="47062-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="47062-113">Exportar segmentos com um total de 1 milhão de perfis pode demorar até 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="47062-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="47062-114">O número de perfis que pode exportar para a Sendinblue está dependente e limitado no seu contrato com a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="47062-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="47062-115">Configurar ligação à Sendinblue</span><span class="sxs-lookup"><span data-stu-id="47062-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="47062-116">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="47062-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="47062-117">Selecione **Adicionar ligação** e escolha **Sendinblue** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="47062-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="47062-118">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="47062-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="47062-119">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="47062-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="47062-120">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="47062-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="47062-121">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="47062-121">Choose who can use this connection.</span></span> <span data-ttu-id="47062-122">Por predefinição, são apenas administradores.</span><span class="sxs-lookup"><span data-stu-id="47062-122">By default it's only administrators.</span></span> <span data-ttu-id="47062-123">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="47062-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="47062-124">Introduza a **[chave de API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="47062-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="47062-125">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados** e selecione **Ligar** para inicializar a ligação à Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="47062-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="47062-126">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="47062-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="47062-127">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="47062-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="47062-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="47062-128">Configure an export</span></span>

<span data-ttu-id="47062-129">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="47062-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="47062-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="47062-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="47062-131">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="47062-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="47062-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="47062-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="47062-133">No campo **Ligação à exportação**, escolha uma ligação a partir da secção Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="47062-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="47062-134">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="47062-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="47062-135">Introduza o **ID de lista Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="47062-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="47062-136">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="47062-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="47062-137">Opcionalmente, pode exportar **Nome próprio**, **Apelido** e **Telefone** para criar e-mails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="47062-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="47062-138">Selecione **Adicionar atributo** para mapear estes campos.</span><span class="sxs-lookup"><span data-stu-id="47062-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="47062-139">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="47062-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="47062-140">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47062-140">Select **Save**.</span></span>

<span data-ttu-id="47062-141">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="47062-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="47062-142">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="47062-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="47062-143">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="47062-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="47062-144">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="47062-144">Data privacy and compliance</span></span>

<span data-ttu-id="47062-145">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a Sendinblue, permite a transferência de dados para fora do limite de conformidade para o Dynamics 365 Customer Insights , incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="47062-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="47062-146">A Microsoft transferirá esses dados conforme as suas instruções, mas você é responsável por garantir que a Sendinblue cumpre quaisquer obrigações de privacidade ou de segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="47062-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="47062-147">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="47062-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="47062-148">O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="47062-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

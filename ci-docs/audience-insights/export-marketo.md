---
title: Exportar dados Customer Insights para a Marketo
description: Aprenda a configurar a ligação e exportar para a Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759835"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="bbb3c-103">Exportar segmentos para a Marketo (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="bbb3c-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="bbb3c-104">Exportar segmentos de perfis unificados de clientes para gerar campanhas, fornecer marketing por e-mail e utilizar grupos específicos de clientes com Marketo.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bbb3c-105">Pré-requisitos para a ligação</span><span class="sxs-lookup"><span data-stu-id="bbb3c-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="bbb3c-106">Tem uma [conta Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bbb3c-107">Existem listas na Marketo e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="bbb3c-108">Para mais informações, consulte [listas da Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="bbb3c-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="bbb3c-109">Tem [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bbb3c-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="bbb3c-110">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bbb3c-111">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="bbb3c-111">Known limitations</span></span>

- <span data-ttu-id="bbb3c-112">Até 1 milhão de perfis por exportar para a Marketo.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="bbb3c-113">A exportação para a Marketo é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="bbb3c-114">A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 3 horas.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="bbb3c-115">O número de perfis que pode exportar para a Marketo está dependente e limitado ao seu contrato com a Marketo.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="bbb3c-116">Configure a ligação para a Marketo</span><span class="sxs-lookup"><span data-stu-id="bbb3c-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="bbb3c-117">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bbb3c-118">Selecione **Adicionar ligação** e escolha **Marketo** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="bbb3c-119">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bbb3c-120">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bbb3c-121">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bbb3c-122">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-122">Choose who can use this connection.</span></span> <span data-ttu-id="bbb3c-123">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bbb3c-124">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bbb3c-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bbb3c-125">Introduza a sua **[ID de cliente da Marketo, segredo do cliente e nome do ponto final REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="bbb3c-126">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados** e selecione **Ligar** para iniciar a ligação a Marketo.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="bbb3c-127">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bbb3c-128">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bbb3c-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="bbb3c-129">Configure an export</span></span>

<span data-ttu-id="bbb3c-130">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bbb3c-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bbb3c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bbb3c-132">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bbb3c-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bbb3c-134">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Marketo.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="bbb3c-135">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bbb3c-136">Introduza a sua **[Id da lista Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="bbb3c-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="bbb3c-137">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="bbb3c-138">Opcionalmente, pode exportar **Nome próprio**, **Apelido**, **Cidade**, **Estado** e **País/Região** para criar e-mails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="bbb3c-139">Selecione **Adicionar atributo** para mapear estes campos.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="bbb3c-140">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-140">Select the segments you want to export.</span></span> <span data-ttu-id="bbb3c-141">Pode exportar até 1 milhão de perfis de clientes no total para a Marketo.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="bbb3c-142">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-142">Select **Save**.</span></span>

<span data-ttu-id="bbb3c-143">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bbb3c-144">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bbb3c-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bbb3c-145">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bbb3c-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="bbb3c-146">Na Marketo, pode agora encontrar os seus segmentos nas [listas da Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="bbb3c-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bbb3c-147">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="bbb3c-147">Data privacy and compliance</span></span>

<span data-ttu-id="bbb3c-148">Quando ativa Dynamics 365 Customer Insights para transmitir dados à Marketo, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bbb3c-149">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Marketo cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bbb3c-150">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bbb3c-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bbb3c-151">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="bbb3c-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
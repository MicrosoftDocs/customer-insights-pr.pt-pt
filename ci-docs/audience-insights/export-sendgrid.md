---
title: Exportar dados do Customer Insights para o SendGrid
description: Aprenda a configurar a ligação e exportar para o SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759779"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="ae3e7-103">Exportar segmentos para o SendGrid (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="ae3e7-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="ae3e7-104">Exportar segmentos de perfis unificados de clientes para listas de contactos do SendGrid e utilizá-los para campanhas e marketing de e-mail no SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ae3e7-105">Pré-requisitos para uma ligação</span><span class="sxs-lookup"><span data-stu-id="ae3e7-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ae3e7-106">Tem uma [conta do SendGrid](https://sendgrid.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ae3e7-107">Existem listas de contactos existentes no SendGrid e IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="ae3e7-108">Para mais informações, consulte [SendGrid – Gerir contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="ae3e7-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="ae3e7-109">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ae3e7-110">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ae3e7-111">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="ae3e7-111">Known limitations</span></span>

- <span data-ttu-id="ae3e7-112">Até 100.000 perfis no total para SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="ae3e7-113">A exportação para o SendGrid está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="ae3e7-114">Exportar até 100.000 perfis para o SendGrid pode demorar até algumas horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ae3e7-115">O número de perfis que pode exportar para o SendGrid é dependente e limitado no seu contrato com o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="ae3e7-116">Configurar ligação ao SendGrid</span><span class="sxs-lookup"><span data-stu-id="ae3e7-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="ae3e7-117">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ae3e7-118">Selecione **Adicionar ligação** e escolha **SendGrid** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="ae3e7-119">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ae3e7-120">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ae3e7-121">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ae3e7-122">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-122">Choose who can use this connection.</span></span> <span data-ttu-id="ae3e7-123">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ae3e7-124">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ae3e7-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ae3e7-125">Insira a sua **Chave de API do SendGrid** [Chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="ae3e7-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="ae3e7-126">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ae3e7-127">Selecione **Ligar** para inicializar a ligação ao SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="ae3e7-128">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ae3e7-129">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ae3e7-130">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="ae3e7-130">Configure an export</span></span>

<span data-ttu-id="ae3e7-131">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ae3e7-132">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ae3e7-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ae3e7-133">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ae3e7-134">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ae3e7-135">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="ae3e7-136">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ae3e7-137">Insira o seu **[ID da lista SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="ae3e7-138">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ae3e7-139">Repita os mesmos passos para outros campos opcionais como **Nome próprio**, **Apelido**, **País/Região**, **Estado**, **Cidade** e **Código Postal**.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="ae3e7-140">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-140">Select the segments you want to export.</span></span> <span data-ttu-id="ae3e7-141">**Recomendamos que não exporte mais de 100.000 perfis de clientes no total** para o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="ae3e7-142">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-142">Select **Save**.</span></span>

<span data-ttu-id="ae3e7-143">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ae3e7-144">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ae3e7-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ae3e7-145">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ae3e7-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ae3e7-146">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="ae3e7-146">Data privacy and compliance</span></span>

<span data-ttu-id="ae3e7-147">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o SendGrid, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ae3e7-148">A Microsoft transferirá esses dados a seu pedido, mas você é responsável por garantir que o SendGrid cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ae3e7-149">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ae3e7-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ae3e7-150">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ae3e7-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Exportar dados Customer Insights para a DotDigital
description: Aprenda a configurar a ligação e exportar para a DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759973"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="79707-103">Exportar listas de segmentos para a DotDigital (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="79707-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="79707-104">Exportar segmentos de perfis unificados de clientes para a DotDigital e utilizá-los em campanhas, marketing por e-mail, e construir segmentos de clientes com a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="79707-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="79707-105">Pré-requisitos para uma ligação</span><span class="sxs-lookup"><span data-stu-id="79707-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="79707-106">Tem uma [conta DotDigital](https://dotdigital.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="79707-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="79707-107">Existem livros de endereços na DotDigital e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="79707-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="79707-108">A ID pode ser encontrada no URL ao selecionar e abrir um livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="79707-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="79707-109">Para mais informações, ver [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="79707-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="79707-110">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="79707-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="79707-111">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="79707-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="79707-112">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="79707-112">Known limitations</span></span>

- <span data-ttu-id="79707-113">Até 1 milhão de perfis por exportar para a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="79707-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="79707-114">A exportação para a DotDigital é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="79707-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="79707-115">A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 3 horas devido a limitações do lado do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="79707-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="79707-116">O número de perfis que pode exportar para a DotDigital está dependente e limitado ao seu contrato com a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="79707-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="79707-117">Configurar ligação à DotDigital</span><span class="sxs-lookup"><span data-stu-id="79707-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="79707-118">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="79707-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="79707-119">Selecione **Adicionar ligação** e escolha **DotDigital** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="79707-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="79707-120">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="79707-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="79707-121">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="79707-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="79707-122">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="79707-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="79707-123">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="79707-123">Choose who can use this connection.</span></span> <span data-ttu-id="79707-124">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="79707-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="79707-125">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="79707-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="79707-126">Introduza o seu **nome de utilizador e a palavra-passe DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="79707-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="79707-127">Introduza a sua **[ID do livro de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="79707-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="79707-128">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="79707-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="79707-129">Selecione **Ligar** para iniciar a ligação a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="79707-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="79707-130">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="79707-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="79707-131">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="79707-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="79707-132">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="79707-132">Configure an export</span></span>

<span data-ttu-id="79707-133">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="79707-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="79707-134">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="79707-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="79707-135">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="79707-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="79707-136">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="79707-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="79707-137">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção DotDigital.</span><span class="sxs-lookup"><span data-stu-id="79707-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="79707-138">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="79707-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="79707-139">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="79707-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="79707-140">Repita os mesmos passos para outros campos opcionais, tais como **nome próprio**, **nome próprio**, **nome completo**, **género**, e **código postal**.</span><span class="sxs-lookup"><span data-stu-id="79707-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="79707-141">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="79707-141">Select the segments you want to export.</span></span> <span data-ttu-id="79707-142">Pode exportar até 1 milhão de perfis de clientes no total para a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="79707-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="79707-143">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="79707-143">Select **Save**.</span></span>

<span data-ttu-id="79707-144">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="79707-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="79707-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="79707-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="79707-146">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="79707-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="79707-147">Na DotDigital, pode agora encontrar os seus segmentos nos [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="79707-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="79707-148">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="79707-148">Data privacy and compliance</span></span>

<span data-ttu-id="79707-149">Quando ativa Dynamics 365 Customer Insights para transmitir dados à DotDigital, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="79707-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="79707-150">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a DotDigital cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="79707-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="79707-151">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="79707-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="79707-152">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="79707-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

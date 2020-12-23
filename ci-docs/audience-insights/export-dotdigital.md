---
title: Exportar dados Customer Insights para a DotDigital
description: Saiba como configurar a ligação a DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644462"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="03d70-103">Ligação para DotDigital (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="03d70-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="03d70-104">Exportar segmentos de perfis unificados de clientes para a DotDigital e utilizá-los em campanhas, marketing por e-mail, e construir segmentos de clientes com a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="03d70-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="03d70-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="03d70-105">Prerequisites</span></span>

-   <span data-ttu-id="03d70-106">Tem uma [conta DotDigital](https://dotdigital.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="03d70-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="03d70-107">Existem livros de endereços na DotDigital e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="03d70-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="03d70-108">A ID pode ser encontrada no URL ao selecionar e abrir um livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="03d70-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="03d70-109">Para mais informações, ver [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="03d70-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="03d70-110">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="03d70-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="03d70-111">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="03d70-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="03d70-112">Ligar a DotDigital</span><span class="sxs-lookup"><span data-stu-id="03d70-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="03d70-113">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="03d70-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="03d70-114">Em **DotDigital**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="03d70-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="03d70-115">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="03d70-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Painel de configuração para exportação DotDigital.":::

1. <span data-ttu-id="03d70-117">Introduza o seu **nome de utilizador e a palavra-passe DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="03d70-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="03d70-118">Introduza a sua **[ID do livro de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="03d70-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="03d70-119">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="03d70-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="03d70-120">Selecione **Ligar** para iniciar a ligação a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="03d70-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="03d70-121">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="03d70-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="03d70-122">Selecione **Seguinte** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="03d70-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="03d70-123">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="03d70-123">Configure the connector</span></span>

1. <span data-ttu-id="03d70-124">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="03d70-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="03d70-125">Repita os mesmos passos para outros campos opcionais, tais como **nome próprio**, **nome próprio**, **nome completo**, **género**, e **código postal**.</span><span class="sxs-lookup"><span data-stu-id="03d70-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="03d70-126">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="03d70-126">Select the segments you want to export.</span></span> <span data-ttu-id="03d70-127">Pode exportar até 1 milhão de perfis de clientes no total para a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="03d70-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="03d70-128">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="03d70-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="03d70-129">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="03d70-129">Export the data</span></span>

<span data-ttu-id="03d70-130">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="03d70-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="03d70-131">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="03d70-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="03d70-132">Na DotDigital, pode agora encontrar os seus segmentos nos [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="03d70-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="03d70-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="03d70-133">Known limitations</span></span>

- <span data-ttu-id="03d70-134">Até 1 milhão de perfis por exportar para a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="03d70-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="03d70-135">A exportação para a DotDigital é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="03d70-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="03d70-136">A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 3 horas devido a limitações do lado do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="03d70-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="03d70-137">O número de perfis que pode exportar para a DotDigital está dependente e limitado ao seu contrato com a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="03d70-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="03d70-138">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="03d70-138">Data privacy and compliance</span></span>

<span data-ttu-id="03d70-139">Quando ativa Dynamics 365 Customer Insights para transmitir dados à DotDigital, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="03d70-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="03d70-140">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a DotDigital cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="03d70-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="03d70-141">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="03d70-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="03d70-142">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="03d70-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

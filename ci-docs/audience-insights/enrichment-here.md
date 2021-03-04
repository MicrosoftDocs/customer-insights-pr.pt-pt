---
title: Enriquecimento com o enriquecimento de terceiros HERE Technologies
description: Informação geral sobre o enriquecimento de terceiros HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269528"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="f7032-103">Enriquecimento de perfis de clientes com HERE Technologies (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="f7032-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="f7032-104">A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização.</span><span class="sxs-lookup"><span data-stu-id="f7032-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="f7032-105">Com os serviços de melhoramento de dados da HERE Technologies, pode construir uma compreensão mais precisa da localização dos seus clientes com normalização de endereços, extração de latitude e longitude, e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f7032-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7032-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f7032-106">Prerequisites</span></span>

<span data-ttu-id="f7032-107">Para configurar o enriquecimento com a HERE Technologies, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="f7032-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f7032-108">Tem de ter uma subscrição ativa da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7032-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="f7032-109">Para obter uma subscrição, pode [inscreva-se aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacte a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente.</span><span class="sxs-lookup"><span data-stu-id="f7032-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="f7032-110">Saiba mais sobre o enriquecimento da localização da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7032-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="f7032-111">Tem a chave API da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7032-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="f7032-112">Tem permissões de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="f7032-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="f7032-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="f7032-113">Configuration</span></span>

1. <span data-ttu-id="f7032-114">Aceda a **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="f7032-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="f7032-115">Selecione **Melhorar os meus dados** no mosaico HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7032-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7032-116">![Mosaico HERE Technologies](media/HERE-tile.png "Mosaico HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="f7032-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="f7032-117">Insira uma **chave API da HERE Technologies** ativa.</span><span class="sxs-lookup"><span data-stu-id="f7032-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="f7032-118">Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="f7032-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="f7032-119">Confirmar ambas as entradas, selecionando **Ligar a HERE**.</span><span class="sxs-lookup"><span data-stu-id="f7032-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="f7032-120">Selecione **Adicionar dados** e escolha **Conjunto de dados do cliente** que pretende melhorar com os dados de localização da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7032-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="f7032-121">Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="f7032-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. <span data-ttu-id="f7032-123">Escolha se deseja mapear campos para o endereço primário e/ou secundário.</span><span class="sxs-lookup"><span data-stu-id="f7032-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="f7032-124">Pode especificar um mapeamento de campo para ambos os endereços (por exemplo, um endereço de casa e um endereço comercial) e melhorar os perfis para ambos os endereços separadamente.</span><span class="sxs-lookup"><span data-stu-id="f7032-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="f7032-125">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="f7032-125">Select **Next**.</span></span>

1. <span data-ttu-id="f7032-126">Defina que campos dos seus perfis unificados devem ser utilizados para procurar dados de localização correspondentes da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7032-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="f7032-127">Os campos **Rua 1** e **Código Postal** são necessários para o endereço primário e/ou secundário selecionado.</span><span class="sxs-lookup"><span data-stu-id="f7032-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="f7032-128">Para uma maior precisão de correspondência, podem ser acrescentados mais campos.</span><span class="sxs-lookup"><span data-stu-id="f7032-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7032-129">![Página de configuração de melhoramento da HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuração de melhoramento da HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="f7032-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="f7032-130">Selecione **Aplicar** para completar o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="f7032-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f7032-131">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="f7032-131">Enrichment results</span></span>

<span data-ttu-id="f7032-132">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="f7032-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f7032-133">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7032-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f7032-134">O tempo de processamento dependerá do tamanho dos seus dados de cliente e dos tempos de resposta API da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7032-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="f7032-135">Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="f7032-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f7032-136">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="f7032-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f7032-137">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="f7032-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7032-138">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="f7032-138">Next steps</span></span>

<span data-ttu-id="f7032-139">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="f7032-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f7032-140">Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="f7032-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7032-141">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="f7032-141">Data privacy and compliance</span></span>

<span data-ttu-id="f7032-142">Quando ativa Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="f7032-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7032-143">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a HERE Technologies cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="f7032-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7032-144">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f7032-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f7032-145">O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f7032-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
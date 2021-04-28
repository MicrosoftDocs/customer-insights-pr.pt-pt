---
title: Enriquecimento com o enriquecimento de terceiros HERE Technologies
description: Informação geral sobre o enriquecimento de terceiros HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896065"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="d818e-103">Enriquecimento de perfis de clientes com HERE Technologies (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="d818e-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="d818e-104">A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização.</span><span class="sxs-lookup"><span data-stu-id="d818e-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="d818e-105">Com os serviços de melhoramento de dados da HERE Technologies, pode construir uma compreensão mais precisa da localização dos seus clientes com normalização de endereços, extração de latitude e longitude, e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d818e-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d818e-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d818e-106">Prerequisites</span></span>

<span data-ttu-id="d818e-107">Para configurar o enriquecimento com a HERE Technologies, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="d818e-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d818e-108">Tem de ter uma subscrição ativa da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="d818e-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="d818e-109">Para obter uma subscrição, pode [inscreva-se aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacte a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente.</span><span class="sxs-lookup"><span data-stu-id="d818e-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="d818e-110">Saiba mais sobre o enriquecimento da localização da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="d818e-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="d818e-111">Existe uma [ligação](connections.md) HERE disponível *ou* tem permissões de [administrador](permissions.md#administrator) e a chave de API da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="d818e-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d818e-112">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="d818e-112">Configure the enrichment</span></span>

1. <span data-ttu-id="d818e-113">Aceda a **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="d818e-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="d818e-114">Selecione **Enriquecer os meus dados** no mosaico da HERE Technologies e selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="d818e-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d818e-115">![Mosaico HERE Technologies](media/HERE-tile.png "Mosaico HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="d818e-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="d818e-116">Selecione uma [ligação](connections.md) na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="d818e-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="d818e-117">Contacte um administrador se não houver nenhuma ligação disponível.</span><span class="sxs-lookup"><span data-stu-id="d818e-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="d818e-118">Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação**.</span><span class="sxs-lookup"><span data-stu-id="d818e-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="d818e-119">Escolha **HERE Technologies** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="d818e-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="d818e-120">Selecione **Ligar à HERE Technologies** para confirmar a seleção da ligação.</span><span class="sxs-lookup"><span data-stu-id="d818e-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="d818e-121">Selecione **Seguinte** e escolha o **Conjunto de dados de cliente** que pretende enriquecer com dados de localização da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="d818e-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="d818e-122">Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="d818e-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. <span data-ttu-id="d818e-124">Escolha se deseja mapear campos para o endereço primário e/ou secundário.</span><span class="sxs-lookup"><span data-stu-id="d818e-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="d818e-125">Pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis de ambos os endereços separadamente.</span><span class="sxs-lookup"><span data-stu-id="d818e-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="d818e-126">Por exemplo, se houver um endereço residencial e de negócios.</span><span class="sxs-lookup"><span data-stu-id="d818e-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="d818e-127">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="d818e-127">Select **Next**.</span></span>

1. <span data-ttu-id="d818e-128">Defina que campos dos seus perfis unificados devem ser utilizados para procurar dados de localização correspondentes da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="d818e-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="d818e-129">Os campos **Rua 1** e **Código Postal** são necessários para o endereço primário e/ou secundário selecionado.</span><span class="sxs-lookup"><span data-stu-id="d818e-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="d818e-130">Para uma maior precisão de correspondência, podem ser acrescentados mais campos.</span><span class="sxs-lookup"><span data-stu-id="d818e-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d818e-131">![Página de configuração de melhoramento da HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuração de melhoramento da HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="d818e-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="d818e-132">Selecione **Seguinte** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="d818e-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="d818e-133">Forneça um nome para o enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="d818e-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="d818e-134">1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="d818e-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="d818e-135">Configurar a ligação para a HERE technologies</span><span class="sxs-lookup"><span data-stu-id="d818e-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="d818e-136">Tens de ser um administrador para configurar ligações.</span><span class="sxs-lookup"><span data-stu-id="d818e-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d818e-137">Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="d818e-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="d818e-138">Introduza um nome para a ligação na caixa **Nome a Apresentar**.</span><span class="sxs-lookup"><span data-stu-id="d818e-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d818e-139">Forneça uma chave de API válida da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="d818e-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="d818e-140">Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**</span><span class="sxs-lookup"><span data-stu-id="d818e-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="d818e-141">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="d818e-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d818e-142">Depois de concluir a verificação, selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d818e-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="d818e-143">![Página de configuração de ligação à HERE Technologies](media/enrichment-HERE-connection.png "Página de configuração de ligação à HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="d818e-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="d818e-144">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="d818e-144">Enrichment results</span></span>

<span data-ttu-id="d818e-145">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="d818e-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d818e-146">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d818e-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d818e-147">O tempo de processamento dependerá do tamanho dos seus dados de cliente e dos tempos de resposta API da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="d818e-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="d818e-148">Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="d818e-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="d818e-149">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="d818e-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d818e-150">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="d818e-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d818e-151">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="d818e-151">Next steps</span></span>

<span data-ttu-id="d818e-152">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="d818e-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d818e-153">Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="d818e-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d818e-154">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="d818e-154">Data privacy and compliance</span></span>

<span data-ttu-id="d818e-155">Quando ativa Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="d818e-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d818e-156">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a HERE Technologies cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="d818e-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d818e-157">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d818e-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d818e-158">O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d818e-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Melhoramento dos perfis de empresas com o melhoramento de terceiros Leadspace
description: Informação geral sobre o melhoramento de terceiros Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305216"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="0fb6e-103">Enriquecimento de perfis da empresa com Leadspace (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="0fb6e-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="0fb6e-104">A Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="0fb6e-105">Permite que os clientes com perfis de clientes unificados para as empresas enriqueçam os seus dados.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="0fb6e-106">Os enriquecimentos incluem mais atributos, como o tamanho da empresa, a localização, o setor e muito mais.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0fb6e-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0fb6e-107">Prerequisites</span></span>

<span data-ttu-id="0fb6e-108">Para configurar o Leadspace, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="0fb6e-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0fb6e-109">Tem uma licença de Leadspace ativa.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="0fb6e-110">Tem [perfis de clientes unificados](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="0fb6e-111">Uma ligação Leadspace já foi configurada por um administrador ou tem permissões de [administrador](permissions.md#administrator) e a "chave perpétua" (designada por **token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="0fb6e-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="0fb6e-112">Contacte a [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) diretamente para obter mais detalhes sobre o respetivo produto.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0fb6e-113">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="0fb6e-113">Configure the enrichment</span></span>

1. <span data-ttu-id="0fb6e-114">Nos insights de audiência, vá a **Dados** > **Melhoramento**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0fb6e-115">Selecione **Enriquecer os meus dados** no mosaico da Leadspace e selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de ecrã do mosaico Leadscape.":::

1. <span data-ttu-id="0fb6e-117">Selecione uma [ligação](connections.md) na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="0fb6e-118">Contacte um administrador se não houver nenhuma ligação disponível.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0fb6e-119">Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação** e escolhendo a **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="0fb6e-120">Selecione **Ligar à Leadspace** para confirmar a ligação.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="0fb6e-121">Selecione **Seguinte** e escolha o **Conjunto de dados de cliente** que pretende enriquecer com os dados da empresa da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="0fb6e-122">Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. <span data-ttu-id="0fb6e-124">Selecione **Seguinte** e defina que campos dos seus perfis unificados são utilizados para procurar dados da empresa correspondentes a partir da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="0fb6e-125">O campo **Nome da empresa** é necessário.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-125">The **Name of company** field is required.</span></span> <span data-ttu-id="0fb6e-126">Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Website da empresa** e **Localização da empresa**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo Leadspace.":::

1. <span data-ttu-id="0fb6e-128">Selecione **Seguinte** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="0fb6e-129">Forneça um nome para o enriquecimento e selecione **Guardar enriquecimento** depois de rever as suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="0fb6e-130">Configurar a ligação para a Leadspace</span><span class="sxs-lookup"><span data-stu-id="0fb6e-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="0fb6e-131">Tens de ser um administrador para configurar ligações.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0fb6e-132">Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="0fb6e-133">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="0fb6e-134">Introduza um nome para a ligação na caixa **Nome a Apresentar**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0fb6e-135">Forneça um token da Leadspace válido.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="0fb6e-136">Reveja e forneça o seu consentimento para a **Privacidade e conformidade dos dados** selecionando **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="0fb6e-137">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0fb6e-138">Depois de concluir a verificação, selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuração de ligação à Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="0fb6e-140">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="0fb6e-140">Enrichment results</span></span>

<span data-ttu-id="0fb6e-141">Depois de atualizar o enriquecimento, pode rever os dados da empresa recentemente enriquecidos em [Os meus enriquecimentos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="0fb6e-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="0fb6e-142">Pode encontrar a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0fb6e-143">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="0fb6e-144">Para mais informações, consulte [APIs do Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="0fb6e-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0fb6e-145">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="0fb6e-145">Next steps</span></span>

<span data-ttu-id="0fb6e-146">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0fb6e-147">Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0fb6e-148">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="0fb6e-148">Data privacy and compliance</span></span>

<span data-ttu-id="0fb6e-149">Quando ativa Dynamics 365 Customer Insights para transmitir dados à Leadspace, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0fb6e-150">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Leadspace cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0fb6e-151">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0fb6e-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0fb6e-152">O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

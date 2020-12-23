---
title: Melhoramento dos perfis de empresas com o melhoramento de terceiros Leadspace
description: Informação geral sobre o melhoramento de terceiros Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668737"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="9fcb6-103">Enriquecimento de perfis da empresa com Leadspace (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="9fcb6-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="9fcb6-104">A Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="9fcb6-105">Permite que os clientes com perfis de clientes unificados para as empresas enriqueçam os seus dados.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="9fcb6-106">Os melhoramentos incluem atributos adicionais tais como tamanho da empresa, localização, indústria, e muito mais.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9fcb6-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9fcb6-107">Prerequisites</span></span>

<span data-ttu-id="9fcb6-108">Para configurar o Leadspace, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="9fcb6-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9fcb6-109">Tem uma licença Leadspace ativa e a "chave perpétua" (referida como **token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="9fcb6-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="9fcb6-110">Contacte diretamente a [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obter mais detalhes sobre o seu produto.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="9fcb6-111">Tem permissões de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="9fcb6-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="9fcb6-112">Tem [perfis de clientes unificados](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="9fcb6-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="9fcb6-113">Configuration</span></span>

1. <span data-ttu-id="9fcb6-114">Nos insights de audiência, vá a **Dados** > **Melhoramento**.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="9fcb6-115">Selecione **Enriquecer os meus dados** no mosaico Leadspace.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de ecrã do mosaico Leadscape.":::

1. <span data-ttu-id="9fcb6-117">Selecione **Iniciar** e depois introduzir um **token Leadspace** ativo (chave perpétua).</span><span class="sxs-lookup"><span data-stu-id="9fcb6-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="9fcb6-118">Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="9fcb6-119">Confirmar ambas as entradas, selecionando **Ligar a Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="9fcb6-120">Selecione **Dados do mapa** e definir quais os campos dos seus perfis unificados que devem ser utilizados para procurar os dados correspondentes da empresa a partir da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="9fcb6-121">O campo **Nome da empresa** é necessário.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-121">The **Name of company** field is required.</span></span> <span data-ttu-id="9fcb6-122">Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Website da empresa** e **Localização da empresa**.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo Leadspace.":::
   
1. <span data-ttu-id="9fcb6-124">Selecione **Aplicar** para completar o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="9fcb6-125">Selecione **Executar** para enriquecer os perfis da empresa.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="9fcb6-126">A duração de um melhoramento depende do número de perfis unificados de clientes.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="9fcb6-127">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="9fcb6-127">Enrichment results</span></span>

<span data-ttu-id="9fcb6-128">Depois de atualizar o enriquecimento, pode rever os dados da empresa recentemente enriquecidos em [Os meus enriquecimentos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="9fcb6-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="9fcb6-129">Pode encontrar a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9fcb6-130">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="9fcb6-131">Para mais informações, consulte [APIs do Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="9fcb6-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9fcb6-132">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="9fcb6-132">Next steps</span></span>

<span data-ttu-id="9fcb6-133">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9fcb6-134">Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9fcb6-135">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="9fcb6-135">Data privacy and compliance</span></span>

<span data-ttu-id="9fcb6-136">Quando ativa Dynamics 365 Customer Insights para transmitir dados à Leadspace, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9fcb6-137">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Leadspace cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9fcb6-138">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9fcb6-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9fcb6-139">O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="9fcb6-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
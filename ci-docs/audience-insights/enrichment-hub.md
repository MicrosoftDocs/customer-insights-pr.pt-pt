---
title: Melhorar perfis unificados de clientes
description: Utilize as capacidades para melhorar os dados dos seus clientes.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954501"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="e2999-103">Enriquecimento para perfis de clientes (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="e2999-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="e2999-104">Utilize dados de origens como a Microsoft e outros parceiros para enriquecer os dados dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="e2999-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do Hub de enriquecimento":::

<span data-ttu-id="e2999-106">Nos insights de audiência, vá a **Dados** > **Melhoramento** para trabalhar com opções de melhoramento.</span><span class="sxs-lookup"><span data-stu-id="e2999-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="e2999-107">É preciso ter permissões de Contribuidor ou Administrador para criar ou editar enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="e2999-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="e2999-108">Para mais informações, consulte [Permissões](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e2999-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="e2999-109">No separador **Descobrir**, encontrará os seguintes enriquecimentos:</span><span class="sxs-lookup"><span data-stu-id="e2999-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="e2999-110">[Marcas](enrichment-microsoft.md) fornecidas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2999-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="e2999-111">[Interesses](enrichment-microsoft.md) fornecidos pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2999-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="e2999-112">[Endereços melhorados](enrichment-enhanced-addresses.md) fornecidos pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2999-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="e2999-113">[Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace</span><span class="sxs-lookup"><span data-stu-id="e2999-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="e2999-114">[Dados demográficos](enrichment-experian.md) fornecidos pela Experian</span><span class="sxs-lookup"><span data-stu-id="e2999-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="e2999-115">[Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="e2999-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="e2999-116">[Dados personalizados](enrichment-SFTP-custom-import.md) através de Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="e2999-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="e2999-117">No separador **Meus enriquecimentos**, pode ver os enriquecimentos que configurou e editar as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="e2999-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="e2999-118">Gerir enriquecimentos existentes</span><span class="sxs-lookup"><span data-stu-id="e2999-118">Manage existing enrichments</span></span>

<span data-ttu-id="e2999-119">Vá a **Meus enriquecimentos** para ver todos os enriquecimentos configurados.</span><span class="sxs-lookup"><span data-stu-id="e2999-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="e2999-120">Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="e2999-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="e2999-121">Selecione um enriquecimento para ver as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e2999-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="e2999-122">Também pode selecionar as reticências (...) num item de lista para ver as opções.</span><span class="sxs-lookup"><span data-stu-id="e2999-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerir enriquecimentos na lista de enriquecimentos":::

- <span data-ttu-id="e2999-124">**Ver** os detalhes do enriquecimento com o número de perfis de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="e2999-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="e2999-125">**Editar** a configuração de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="e2999-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="e2999-126">**Executar** o enriquecimento para atualizar perfis de clientes com os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e2999-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="e2999-127">**Desativar** um enriquecimento existente para impedir que atualize automaticamente com cada atualização programada.</span><span class="sxs-lookup"><span data-stu-id="e2999-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="e2999-128">Os dados da última atualização bem sucedida continuarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e2999-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="e2999-129">**Ativar** um enriquecimento inativo para reiniciar a atualização automática com cada atualização programada.</span><span class="sxs-lookup"><span data-stu-id="e2999-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="e2999-130">**Eliminar** um melhoramento.</span><span class="sxs-lookup"><span data-stu-id="e2999-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="e2999-131">Pode executar ou desativar vários enriquecimentos de uma só vez selecionando-os na lista.</span><span class="sxs-lookup"><span data-stu-id="e2999-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="e2999-132">As opções de ver e editar não estão disponíveis como ação em massa e só funcionam para um enriquecimento de cada vez.</span><span class="sxs-lookup"><span data-stu-id="e2999-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="e2999-133">Enriquecimentos e ligações</span><span class="sxs-lookup"><span data-stu-id="e2999-133">Enrichments and connections</span></span>

<span data-ttu-id="e2999-134">Os enriquecimentos de terceiros são configurados através de [ligações](connections.md), que um administrador configura com credenciais e fornece consentimento para transferências de dados.</span><span class="sxs-lookup"><span data-stu-id="e2999-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="e2999-135">A ligação pode então ser utilizada por administradores e contribuidores para configurar enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="e2999-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="e2999-136">Múltiplos enriquecimentos do mesmo tipo</span><span class="sxs-lookup"><span data-stu-id="e2999-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="e2999-137">A entidade a enriquecer é especificada durante a configuração do enriquecimento, o que lhe permite enriquecer apenas um subconjunto dos seus perfis.</span><span class="sxs-lookup"><span data-stu-id="e2999-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="e2999-138">Por exemplo, enriqueça dados apenas para um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="e2999-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="e2999-139">Pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma ligação.</span><span class="sxs-lookup"><span data-stu-id="e2999-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="e2999-140">Alguns enriquecimentos terão limites ao número de enriquecimentos do mesmo tipo que podem ser criados.</span><span class="sxs-lookup"><span data-stu-id="e2999-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="e2999-141">Os limites e a utilização atual podem ser vistos na página de **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="e2999-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896019"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="8ebba-103">Enriquecimento para perfis de clientes (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="8ebba-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="8ebba-104">Utilize dados de origens como a Microsoft e outros parceiros para enriquecer os dados dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="8ebba-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do Hub de enriquecimento":::

<span data-ttu-id="8ebba-106">Nos insights de audiência, vá a **Dados** > **Melhoramento** para trabalhar com opções de melhoramento.</span><span class="sxs-lookup"><span data-stu-id="8ebba-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="8ebba-107">É preciso ter permissões de Contribuidor ou Administrador para criar ou editar enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="8ebba-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="8ebba-108">Para mais informações, consulte [Permissões](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8ebba-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="8ebba-109">No separador **Descobrir**, encontrará os seguintes enriquecimentos:</span><span class="sxs-lookup"><span data-stu-id="8ebba-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="8ebba-110">[Marcas](enrichment-microsoft.md) fornecidas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ebba-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="8ebba-111">[Interesses](enrichment-microsoft.md) fornecidos pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ebba-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="8ebba-112">[Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace</span><span class="sxs-lookup"><span data-stu-id="8ebba-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="8ebba-113">[Dados demográficos](enrichment-experian.md) fornecidos pela Experian</span><span class="sxs-lookup"><span data-stu-id="8ebba-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="8ebba-114">[Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="8ebba-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="8ebba-115">[Dados personalizados](enrichment-SFTP-custom-import.md) através de Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="8ebba-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="8ebba-116">No separador **Meus enriquecimentos**, pode ver os enriquecimentos que configurou e editar as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="8ebba-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="8ebba-117">Gerir enriquecimentos existentes</span><span class="sxs-lookup"><span data-stu-id="8ebba-117">Manage existing enrichments</span></span>

<span data-ttu-id="8ebba-118">Vá a **Meus enriquecimentos** para ver todos os enriquecimentos configurados.</span><span class="sxs-lookup"><span data-stu-id="8ebba-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="8ebba-119">Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="8ebba-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="8ebba-120">Selecione um enriquecimento para ver as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8ebba-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="8ebba-121">Também pode selecionar as reticências (...) num item de lista para ver as opções.</span><span class="sxs-lookup"><span data-stu-id="8ebba-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerir enriquecimentos na lista de enriquecimentos":::

- <span data-ttu-id="8ebba-123">**Ver** os detalhes do enriquecimento com o número de perfis de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="8ebba-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="8ebba-124">**Editar** a configuração de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="8ebba-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="8ebba-125">**Executar** o enriquecimento para atualizar perfis de clientes com os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="8ebba-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="8ebba-126">**Desativar** um enriquecimento existente para impedir que atualize automaticamente com cada atualização programada.</span><span class="sxs-lookup"><span data-stu-id="8ebba-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="8ebba-127">Os dados da última atualização bem sucedida continuarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8ebba-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="8ebba-128">**Ativar** um enriquecimento inativo para reiniciar a atualização automática com cada atualização programada.</span><span class="sxs-lookup"><span data-stu-id="8ebba-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="8ebba-129">**Eliminar** um melhoramento.</span><span class="sxs-lookup"><span data-stu-id="8ebba-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="8ebba-130">Pode executar ou desativar vários enriquecimentos de uma só vez selecionando-os na lista.</span><span class="sxs-lookup"><span data-stu-id="8ebba-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="8ebba-131">As opções de ver e editar não estão disponíveis como ação em massa e só funcionam para um enriquecimento de cada vez.</span><span class="sxs-lookup"><span data-stu-id="8ebba-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="8ebba-132">Enriquecimentos e ligações</span><span class="sxs-lookup"><span data-stu-id="8ebba-132">Enrichments and connections</span></span>

<span data-ttu-id="8ebba-133">Os enriquecimentos de terceiros são configurados através de [ligações](connections.md), que um administrador configura com credenciais e fornece consentimento para transferências de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebba-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="8ebba-134">A ligação pode então ser utilizada por administradores e contribuidores para configurar enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="8ebba-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="8ebba-135">Múltiplos enriquecimentos do mesmo tipo</span><span class="sxs-lookup"><span data-stu-id="8ebba-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="8ebba-136">A entidade a enriquecer é especificada durante a configuração do enriquecimento, o que lhe permite enriquecer apenas um subconjunto dos seus perfis.</span><span class="sxs-lookup"><span data-stu-id="8ebba-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="8ebba-137">Por exemplo, enriqueça dados apenas para um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="8ebba-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="8ebba-138">Pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma ligação.</span><span class="sxs-lookup"><span data-stu-id="8ebba-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="8ebba-139">Alguns enriquecimentos terão limites ao número de enriquecimentos do mesmo tipo que podem ser criados.</span><span class="sxs-lookup"><span data-stu-id="8ebba-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="8ebba-140">Os limites e a utilização atual podem ser vistos na página de **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="8ebba-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

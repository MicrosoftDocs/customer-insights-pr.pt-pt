---
title: Melhorar perfis unificados de clientes
description: Utilize as capacidades para melhorar os dados dos seus clientes.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269482"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="b3353-103">Enriquecimento para perfis de clientes (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="b3353-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="b3353-104">Utilize dados de origens como a Microsoft e outros parceiros para enriquecer os dados dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="b3353-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do Hub de enriquecimento":::

<span data-ttu-id="b3353-106">Nos insights de audiência, vá a **Dados** > **Melhoramento** para trabalhar com opções de melhoramento.</span><span class="sxs-lookup"><span data-stu-id="b3353-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="b3353-107">É preciso ter permissões de Contribuidor ou Administrador para criar ou editar enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="b3353-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="b3353-108">Para mais informações, consulte [Permissões](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b3353-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="b3353-109">No separador **Descobrir**, encontrará os seguintes enriquecimentos:</span><span class="sxs-lookup"><span data-stu-id="b3353-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="b3353-110">[Marcas](enrichment-microsoft-graph.md) fornecidas pelo Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b3353-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="b3353-111">[Interesses](enrichment-microsoft-graph.md) fornecidos pelo Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b3353-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="b3353-112">[Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace</span><span class="sxs-lookup"><span data-stu-id="b3353-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="b3353-113">[Dados demográficos](enrichment-experian.md) fornecidos pela Experian</span><span class="sxs-lookup"><span data-stu-id="b3353-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="b3353-114">[Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="b3353-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="b3353-115">[Dados personalizados](enrichment-SFTP-custom-import.md) através de Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="b3353-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="b3353-116">No separador **Meus enriquecimentos**, pode ver os enriquecimentos que configurou e editar as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="b3353-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="b3353-117">Gerir enriquecimentos existentes</span><span class="sxs-lookup"><span data-stu-id="b3353-117">Manage existing enrichments</span></span>

<span data-ttu-id="b3353-118">Vá a **Meus enriquecimentos** para ver todos os enriquecimentos configurados.</span><span class="sxs-lookup"><span data-stu-id="b3353-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="b3353-119">Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="b3353-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="b3353-120">Selecione um enriquecimento para ver as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b3353-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="b3353-121">Em alternativa, pode selecionar as reticências (...) num item de lista para ver as opções.</span><span class="sxs-lookup"><span data-stu-id="b3353-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerir enriquecimentos na lista de enriquecimentos":::

- <span data-ttu-id="b3353-123">**Ver** os detalhes do enriquecimento com o número de perfis de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="b3353-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="b3353-124">**Editar** a configuração de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="b3353-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="b3353-125">**Executar** o enriquecimento para atualizar perfis de clientes com os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="b3353-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="b3353-126">**Desativar** um enriquecimento existente para impedir que atualize automaticamente com cada atualização programada.</span><span class="sxs-lookup"><span data-stu-id="b3353-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="b3353-127">Os dados da última atualização bem sucedida continuarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b3353-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="b3353-128">**Ativar** um enriquecimento inativo para reiniciar a atualização automática com cada atualização programada.</span><span class="sxs-lookup"><span data-stu-id="b3353-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="b3353-129">**Eliminar** um melhoramento.</span><span class="sxs-lookup"><span data-stu-id="b3353-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="b3353-130">Pode executar ou desativar vários enriquecimentos de uma só vez selecionando-os na lista.</span><span class="sxs-lookup"><span data-stu-id="b3353-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="b3353-131">As opções de ver e editar não estão disponíveis como ação em massa e só funcionam para um enriquecimento de cada vez.</span><span class="sxs-lookup"><span data-stu-id="b3353-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
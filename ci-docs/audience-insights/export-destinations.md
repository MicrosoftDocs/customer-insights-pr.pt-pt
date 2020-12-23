---
title: Destinos de exportação
description: Exportar dados e gerir destinos de exportação.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643877"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="42e24-103">Destinos de exportação (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="42e24-103">Export destinations (preview)</span></span>

<span data-ttu-id="42e24-104">A página **Exportar destinos** mostra-lhe todos os locais que configurou para onde exportar dados.</span><span class="sxs-lookup"><span data-stu-id="42e24-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="42e24-105">Também pode adicionar novos destinos para exportação.</span><span class="sxs-lookup"><span data-stu-id="42e24-105">You can also add new destinations for export.</span></span> <span data-ttu-id="42e24-106">Além disso, mostra as opções de exportação atualmente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="42e24-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="42e24-107">Obtenha uma descrição geral rápida e saiba o que pode fazer com cada opção de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="42e24-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="42e24-108">Exporte perfis, medidas e segmentos unificados para aplicações suportadas relevantes para o seu negócio.</span><span class="sxs-lookup"><span data-stu-id="42e24-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="42e24-109">Aceda a **Administração** > **Exportar destinos** para localizar as seguintes opções de extensibilidade:</span><span class="sxs-lookup"><span data-stu-id="42e24-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="42e24-110">Suplemento de Cartões de Clientes do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="42e24-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="42e24-111">Conector Gestor de Anúncios do Facebook</span><span class="sxs-lookup"><span data-stu-id="42e24-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="42e24-112">Conector do Power Automate</span><span class="sxs-lookup"><span data-stu-id="42e24-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="42e24-113">Conector do Power Apps</span><span class="sxs-lookup"><span data-stu-id="42e24-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="42e24-114">Conector do Power BI</span><span class="sxs-lookup"><span data-stu-id="42e24-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="42e24-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="42e24-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="42e24-116">Vendas do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="42e24-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="42e24-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="42e24-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="42e24-118">Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="42e24-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="42e24-119">Conector do LiveRamp&reg;</span><span class="sxs-lookup"><span data-stu-id="42e24-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="42e24-120">Bot para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42e24-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="42e24-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="42e24-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="42e24-122">API do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="42e24-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="42e24-123">Adicionar um novo destino de exportação</span><span class="sxs-lookup"><span data-stu-id="42e24-123">Add a new export destination</span></span>

<span data-ttu-id="42e24-124">Para adicionar destinos de exportação, tem [permissões de administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="42e24-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="42e24-125">Se exportar para serviços da Microsoft, vamos supor que ambos os serviços estão na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="42e24-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="42e24-126">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="42e24-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="42e24-127">Alterne para o separador **Os meus destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="42e24-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="42e24-128">Selecione **Adicionar destino** para criar um novo destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="42e24-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="42e24-129">No painel **Adicionar destino**, selecione o **Tipo** de destino de exportação na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="42e24-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="42e24-130">Forneça os detalhes necessários e selecione **Seguinte** para criar o destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="42e24-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="42e24-131">Também pode selecionar **Configurar** num mosaico no separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="42e24-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="42e24-132">Ver Destinos de exportação</span><span class="sxs-lookup"><span data-stu-id="42e24-132">View Export destinations</span></span>

<span data-ttu-id="42e24-133">Depois de criar os destinos de exportação, irá encontrá-los numa tabela no separador **Os meus destinos de exportação**. Esta tabela tem três colunas:</span><span class="sxs-lookup"><span data-stu-id="42e24-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="42e24-134">**Nome a apresentar**: o nome que introduziu ao criar o destino.</span><span class="sxs-lookup"><span data-stu-id="42e24-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="42e24-135">**Tipo**: o tipo de destino de exportação que definiu ao criar o destino.</span><span class="sxs-lookup"><span data-stu-id="42e24-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="42e24-136">**Criado em**: a data de criação do destino.</span><span class="sxs-lookup"><span data-stu-id="42e24-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="42e24-137">Editar um destino de exportação</span><span class="sxs-lookup"><span data-stu-id="42e24-137">Edit an export destination</span></span>

1. <span data-ttu-id="42e24-138">Selecione as reticências verticais do destino de Exportação que pretende editar.</span><span class="sxs-lookup"><span data-stu-id="42e24-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42e24-139">![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")</span><span class="sxs-lookup"><span data-stu-id="42e24-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="42e24-140">Selecione **Editar** no menu pendente.</span><span class="sxs-lookup"><span data-stu-id="42e24-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="42e24-141">Altere os valores que necessitam de atualização e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="42e24-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="42e24-142">Exportar dados a pedido</span><span class="sxs-lookup"><span data-stu-id="42e24-142">Export data on demand</span></span>

<span data-ttu-id="42e24-143">Depois de configurar um conector para um destino de exportação, as exportações serão executadas com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="42e24-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="42e24-144">Para exportar dados sem aguardar uma atualização agendada, vá para o separador **Os meus destinos de exportação** em **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="42e24-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42e24-145">![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")</span><span class="sxs-lookup"><span data-stu-id="42e24-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="42e24-146">Selecione **Exportar** acima da lista para executar a exportação para todos os destinos de exportação simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="42e24-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="42e24-147">Selecione as reticências (...) à frente de um item de lista e, em seguida, escolha a opção **Exportar** para executar a exportação para um único destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="42e24-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="42e24-148">Remover um destino de Exportação</span><span class="sxs-lookup"><span data-stu-id="42e24-148">Remove an Export destination</span></span>

<span data-ttu-id="42e24-149">Para remover um destino de Exportação, inicie a partir da página principal **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="42e24-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="42e24-150">Selecione as reticências verticais do destino de Exportação que pretende remover.</span><span class="sxs-lookup"><span data-stu-id="42e24-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42e24-151">![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")</span><span class="sxs-lookup"><span data-stu-id="42e24-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="42e24-152">Selecione **Remover** no menu pendente.</span><span class="sxs-lookup"><span data-stu-id="42e24-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="42e24-153">Confirme a remoção selecionando **Remover** no ecrã de confirmação.</span><span class="sxs-lookup"><span data-stu-id="42e24-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>

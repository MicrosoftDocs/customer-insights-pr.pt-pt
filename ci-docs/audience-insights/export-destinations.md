---
title: Exportar dados do Customer Insights
description: Gerir exportações para partilhar dados.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016650"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="a031d-103">Descrição geral de exportações (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="a031d-103">Exports (preview) overview</span></span>

<span data-ttu-id="a031d-104">A página **Exportações** mostra todas as exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="a031d-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="a031d-105">As exportações partilham dados específicos com várias aplicações.</span><span class="sxs-lookup"><span data-stu-id="a031d-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="a031d-106">Podem incluir perfis de clientes ou entidades, esquemas e detalhes de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="a031d-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="a031d-107">Cada exportação requer uma [ligação, configurada por um administrador, para gerir a autenticação e o acesso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="a031d-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="a031d-108">Vá a **Dados** > **Exportações** para ver a página de exportações.</span><span class="sxs-lookup"><span data-stu-id="a031d-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="a031d-109">Todas as funções de utilizador têm acesso a ver exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="a031d-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="a031d-110">Utilização do campo de pesquisa na barra de comandos para encontrar exportações pelo nome, nome da ligação ou tipo de ligação.</span><span class="sxs-lookup"><span data-stu-id="a031d-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="a031d-111">Configurar uma nova exportação</span><span class="sxs-lookup"><span data-stu-id="a031d-111">Set up a new export</span></span>

<span data-ttu-id="a031d-112">Para configurar ou editar uma exportação, precisa de ter ligações disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="a031d-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="a031d-113">As ligações dependem da sua [função de utilizador](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="a031d-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="a031d-114">Os administradores têm acesso a todas as ligações.</span><span class="sxs-lookup"><span data-stu-id="a031d-114">Administrators have access to all connections.</span></span> <span data-ttu-id="a031d-115">Podem também criar novas ligações ao configurar uma exportação.</span><span class="sxs-lookup"><span data-stu-id="a031d-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="a031d-116">Os contribuidores podem ter acesso a ligações específicas.</span><span class="sxs-lookup"><span data-stu-id="a031d-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="a031d-117">Dependem dos administradores para configurar e partilhar ligações.</span><span class="sxs-lookup"><span data-stu-id="a031d-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="a031d-118">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a031d-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="a031d-119">Os visualizadores só podem ver exportações existentes, mas não criá-las.</span><span class="sxs-lookup"><span data-stu-id="a031d-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="a031d-120">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="a031d-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a031d-121">Selecione **Adicionar exportação** para criar um novo destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="a031d-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="a031d-122">No painel **Configurar exportação**, selecione que ligação utilizar.</span><span class="sxs-lookup"><span data-stu-id="a031d-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="a031d-123">As [Ligações](connections.md) são geridas por administradores.</span><span class="sxs-lookup"><span data-stu-id="a031d-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="a031d-124">Forneça os detalhes necessários e selecione **Guardar** para criar a exportação.</span><span class="sxs-lookup"><span data-stu-id="a031d-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="a031d-125">Editar uma exportação</span><span class="sxs-lookup"><span data-stu-id="a031d-125">Edit an export</span></span>

1. <span data-ttu-id="a031d-126">Selecione as reticências verticais do destino de exportação que pretende editar.</span><span class="sxs-lookup"><span data-stu-id="a031d-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="a031d-127">Selecione **Editar** no menu pendente.</span><span class="sxs-lookup"><span data-stu-id="a031d-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="a031d-128">Altere os valores que pretende atualizar e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a031d-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="a031d-129">Ver Exportações e detalhes da exportação</span><span class="sxs-lookup"><span data-stu-id="a031d-129">View Exports and export details</span></span>

<span data-ttu-id="a031d-130">Depois de criar destinos de exportação, são listados em **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="a031d-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="a031d-131">Todos os utilizadores podem ver que dados são partilhados e o respetivo estado mais recente.</span><span class="sxs-lookup"><span data-stu-id="a031d-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="a031d-132">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="a031d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a031d-133">Os utilizadores sem permissões de edição selecionam **Ver** em vez de **Editar** para ver os detalhes da exportação.</span><span class="sxs-lookup"><span data-stu-id="a031d-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="a031d-134">Este painel lateral mostra a configuração desta exportação.</span><span class="sxs-lookup"><span data-stu-id="a031d-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="a031d-135">Sem permissões de edição, não é possível alterar valores.</span><span class="sxs-lookup"><span data-stu-id="a031d-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="a031d-136">Selecione **Fechar** para regressar à página de exportações.</span><span class="sxs-lookup"><span data-stu-id="a031d-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="a031d-137">Executar exportações a pedido</span><span class="sxs-lookup"><span data-stu-id="a031d-137">Run exports on demand</span></span>

<span data-ttu-id="a031d-138">Depois de configurar uma exportação, será executada a cada [atualização agendada](system.md#schedule-tab), desde que tenha uma ligação funcional.</span><span class="sxs-lookup"><span data-stu-id="a031d-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="a031d-139">Para exportar dados sem esperar por uma atualização agendada, vá a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="a031d-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="a031d-140">Tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="a031d-140">You have two options:</span></span>

- <span data-ttu-id="a031d-141">Para executar todas as exportações, selecione **Executar todas** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="a031d-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="a031d-142">Para executar uma única exportação, selecione as reticências (...) num item de lista e, em seguida, escolha **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a031d-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="a031d-143">Remover uma Exportação</span><span class="sxs-lookup"><span data-stu-id="a031d-143">Remove an Export</span></span>

1. <span data-ttu-id="a031d-144">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="a031d-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a031d-145">Selecione as reticências verticais da Exportação que pretende remover.</span><span class="sxs-lookup"><span data-stu-id="a031d-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="a031d-146">Selecione **Remover** no menu pendente.</span><span class="sxs-lookup"><span data-stu-id="a031d-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="a031d-147">Confirme a remoção selecionando **Remover** no ecrã de confirmação.</span><span class="sxs-lookup"><span data-stu-id="a031d-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

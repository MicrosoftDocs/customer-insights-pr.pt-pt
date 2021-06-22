---
title: Exportar dados do Customer Insights
description: Gerir exportações para partilhar dados.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253054"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="ef2a0-103">Descrição geral de exportações (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="ef2a0-103">Exports (preview) overview</span></span>

<span data-ttu-id="ef2a0-104">A página **Exportações** mostra todas as exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="ef2a0-105">As exportações partilham dados específicos com várias aplicações.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="ef2a0-106">Podem incluir perfis de clientes ou entidades, esquemas e detalhes de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="ef2a0-107">Cada exportação requer uma [ligação, configurada por um administrador, para gerir a autenticação e o acesso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="ef2a0-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="ef2a0-108">Vá a **Dados** > **Exportações** para ver a página de exportações.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="ef2a0-109">Todas as funções de utilizador têm acesso a ver exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="ef2a0-110">Utilização do campo de pesquisa na barra de comandos para encontrar exportações pelo nome, nome da ligação ou tipo de ligação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="ef2a0-111">Configurar uma nova exportação</span><span class="sxs-lookup"><span data-stu-id="ef2a0-111">Set up a new export</span></span>

<span data-ttu-id="ef2a0-112">Para configurar ou editar uma exportação, precisa de ter ligações disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="ef2a0-113">As ligações dependem da sua [função de utilizador](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="ef2a0-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="ef2a0-114">Os administradores têm acesso a todas as ligações.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-114">Administrators have access to all connections.</span></span> <span data-ttu-id="ef2a0-115">Podem também criar novas ligações ao configurar uma exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="ef2a0-116">Os contribuidores podem ter acesso a ligações específicas.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="ef2a0-117">Dependem dos administradores para configurar e partilhar ligações.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="ef2a0-118">A lista de exportações mostra aos contribuidores se podem editar ou apenas ver uma exportação na coluna **As suas permissões**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="ef2a0-119">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ef2a0-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="ef2a0-120">Os visualizadores só podem ver exportações existentes, mas não criá-las.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="ef2a0-121">Definir uma nova exportação</span><span class="sxs-lookup"><span data-stu-id="ef2a0-121">Define a new export</span></span>

1. <span data-ttu-id="ef2a0-122">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ef2a0-123">Selecione **Adicionar exportação** para criar um nova exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="ef2a0-124">No painel **Configurar exportação**, selecione que ligação utilizar.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="ef2a0-125">As [Ligações](connections.md) são geridas por administradores.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="ef2a0-126">Forneça os detalhes necessários e selecione **Guardar** para criar a exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="ef2a0-127">Defina uma nova exportação com base numa exportação existente</span><span class="sxs-lookup"><span data-stu-id="ef2a0-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="ef2a0-128">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ef2a0-129">Na lista de exportações, selecione a exportação que pretende duplicar.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="ef2a0-130">Selecione **Criar duplicado** na barra de comandos para abrir o painel **Configurar exportação** com os detalhes da exportação selecionada.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="ef2a0-131">Reveja e adapte a exportação e selecione **Guardar** para criar uma nova exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="ef2a0-132">Editar uma exportação</span><span class="sxs-lookup"><span data-stu-id="ef2a0-132">Edit an export</span></span>

1. <span data-ttu-id="ef2a0-133">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ef2a0-134">Na lista de exportações, selecione a exportação que pretende editar.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="ef2a0-135">Selecione **Editar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="ef2a0-136">Altere os valores que pretende atualizar e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="ef2a0-137">Ver exportações e detalhes da exportação</span><span class="sxs-lookup"><span data-stu-id="ef2a0-137">View exports and export details</span></span>

<span data-ttu-id="ef2a0-138">Depois de criar destinos de exportação, são listados em **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="ef2a0-139">Todos os utilizadores podem ver que dados são partilhados e o respetivo estado mais recente.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="ef2a0-140">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ef2a0-141">Os utilizadores sem permissões de edição selecionam **Ver** em vez de **Editar** para ver os detalhes da exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="ef2a0-142">O painel lateral mostra a configuração de uma exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="ef2a0-143">Sem permissões de edição, não é possível alterar valores.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="ef2a0-144">Selecione **Fechar** para regressar à página de exportações.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="ef2a0-145">Agendar e executar exportações</span><span class="sxs-lookup"><span data-stu-id="ef2a0-145">Schedule and run exports</span></span>

<span data-ttu-id="ef2a0-146">Cada exportação que configura tem uma agenda de atualização.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="ef2a0-147">Durante uma atualização, o sistema procura dados novos ou atualizados a incluir numa exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="ef2a0-148">Por predefinição, as exportações são executadas como parte de cada [atualização de sistema agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ef2a0-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ef2a0-149">Pode personalizar a agenda de atualização ou desativá-la para executar exportações manualmente.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="ef2a0-150">As agendas de exportação dependem do estado do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="ef2a0-151">Se existirem atualizações sobre [dependências](system.md#refresh-policies) em curso quando uma exportação agendada deve começar, o sistema completará primeiro as dependências e, em seguida, executará a exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="ef2a0-152">Pode ver quando uma exportação foi atualizada pela última vez na coluna **Atualizadas**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="ef2a0-153">Agendar exportações</span><span class="sxs-lookup"><span data-stu-id="ef2a0-153">Schedule exports</span></span>

<span data-ttu-id="ef2a0-154">Pode definir agendas de atualização personalizadas para exportações individuais ou várias exportações ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="ef2a0-155">A agenda atualmente definida está listada na coluna **Agenda** da lista de exportação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="ef2a0-156">A permissão para alterar a agenda é a mesma que para [editar e definir exportações](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ef2a0-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="ef2a0-157">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ef2a0-158">Selecione a exportação que pretende agendar.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="ef2a0-159">Selecione **Agendar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="ef2a0-160">No painel **Agendar exportação**, defina **Agendar execução** para **Ativada** para executar a exportação automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="ef2a0-161">Defina-a como **Desativada** para a atualizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="ef2a0-162">Para exportações automaticamente atualizadas, escolha um valor de **Periodicidade** e especifique os respetivos detalhes.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="ef2a0-163">O tempo definido aplica-se a todas as instâncias de periodicidade.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="ef2a0-164">É o momento em que uma exportação deve começar a atualizar.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="ef2a0-165">Aplique e ative as suas alterações selecionando **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="ef2a0-166">Ao editar a agenda para várias exportações, precisa de fazer uma seleção sob **Manter ou substituir agendas**:</span><span class="sxs-lookup"><span data-stu-id="ef2a0-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="ef2a0-167">**Manter agendas individuais**: persiste a agenda previamente definida para as exportações selecionadas e apenas as desativa ou ativa.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="ef2a0-168">**Definir nova agenda para todas as exportações selecionadas**: substitui as agendas existentes das exportações selecionadas.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="ef2a0-169">Executar exportações a pedido</span><span class="sxs-lookup"><span data-stu-id="ef2a0-169">Run exports on demand</span></span>

<span data-ttu-id="ef2a0-170">Para exportar dados sem esperar por uma atualização agendada, vá a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="ef2a0-171">Para executar todas as exportações, selecione **Executar todas** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="ef2a0-172">Esta ação só irá executar exportações que tenham uma agenda ativa.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="ef2a0-173">Para executar uma única exportação, selecione-a na lista e selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="ef2a0-174">É assim que se executam exportações sem agenda ativa.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="ef2a0-175">Remover uma Exportação</span><span class="sxs-lookup"><span data-stu-id="ef2a0-175">Remove an Export</span></span>

1. <span data-ttu-id="ef2a0-176">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ef2a0-177">Selecione a exportação que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="ef2a0-178">Selecione **Remover** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="ef2a0-179">Confirme a remoção selecionando **Remover** no ecrã de confirmação.</span><span class="sxs-lookup"><span data-stu-id="ef2a0-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

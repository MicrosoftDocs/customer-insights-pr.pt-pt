---
title: Fundir entidades na unificação de dados
description: Fundir entidades para criar perfis unificados de clientes.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597847"
---
# <a name="merge-entities"></a><span data-ttu-id="232e7-103">Unir entidades</span><span class="sxs-lookup"><span data-stu-id="232e7-103">Merge entities</span></span>

<span data-ttu-id="232e7-104">A fase de intercalação é a última fase no processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="232e7-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="232e7-105">Tem como objetivo reconciliar os dados em conflito.</span><span class="sxs-lookup"><span data-stu-id="232e7-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="232e7-106">Os exemplos de dados em conflito poderão incluir um nome de cliente que se encontra em dois dos seus conjuntos de dados, mas que apresenta pequenas diferenças ("Grant Marshall" versus "Grant Marshal"), ou um número de telefone com que difere no formato (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="232e7-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="232e7-107">A intercalação destes pontos de dados em conflito é feita numa base atributo a atributo.</span><span class="sxs-lookup"><span data-stu-id="232e7-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="232e7-108">Depois de concluir a [fase de intercalação](match-entities.md), pode iniciar a fase de intercalação ao selecione o título **Intercalar** na página **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="232e7-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="232e7-109">Rever recomendações de sistema</span><span class="sxs-lookup"><span data-stu-id="232e7-109">Review system recommendations</span></span>

<span data-ttu-id="232e7-110">Na página **Intercalar**, poderá optar escolher e excluir os atributos a unir na sua entidade de perfil de cliente unificada (o resultado do processo de configuração).</span><span class="sxs-lookup"><span data-stu-id="232e7-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="232e7-111">Alguns atributos são intercalados automaticamente pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="232e7-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="232e7-112">Ver atributos intercalados</span><span class="sxs-lookup"><span data-stu-id="232e7-112">View merged attributes</span></span>

<span data-ttu-id="232e7-113">Para ver os atributos que estão incluídos num dos seus atributos intercalados automaticamente, selecione o atributo intercalado.</span><span class="sxs-lookup"><span data-stu-id="232e7-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="232e7-114">Os dois atributos que compõem o atributo unido serão apresentados em duas novas linhas abaixo do atributo intercalado.</span><span class="sxs-lookup"><span data-stu-id="232e7-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="232e7-115">![Selecionar o atributo intercalado](media/configure-data-merge-profile-attributes.png "Selecionar o atributo intercalado")</span><span class="sxs-lookup"><span data-stu-id="232e7-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="232e7-116">Atributos intercalados separados</span><span class="sxs-lookup"><span data-stu-id="232e7-116">Separate merged attributes</span></span>

<span data-ttu-id="232e7-117">Para separar ou intercalar qualquer um dos atributos intercalados automaticamente, localize o atributo na tabela **Atributos de perfil**.</span><span class="sxs-lookup"><span data-stu-id="232e7-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="232e7-118">Selecione o botão de elipse (...).</span><span class="sxs-lookup"><span data-stu-id="232e7-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="232e7-119">Na lista pendente, selecione **Separar campos**.</span><span class="sxs-lookup"><span data-stu-id="232e7-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="232e7-120">Remover atributos intercalados</span><span class="sxs-lookup"><span data-stu-id="232e7-120">Remove merged attributes</span></span>

<span data-ttu-id="232e7-121">Para excluir um atributo da entidade de perfil de cliente final, localize-o na tabela **Atributos de perfil**.</span><span class="sxs-lookup"><span data-stu-id="232e7-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="232e7-122">Selecione o botão de elipse (...).</span><span class="sxs-lookup"><span data-stu-id="232e7-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="232e7-123">Na lista pendente, selecione **Não unir**.</span><span class="sxs-lookup"><span data-stu-id="232e7-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="232e7-124">O atributo é movido para a secção **Removido do registo de cliente**.</span><span class="sxs-lookup"><span data-stu-id="232e7-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="232e7-125">Adicionar manualmente um atributo intercalado</span><span class="sxs-lookup"><span data-stu-id="232e7-125">Manually add a merged attribute</span></span>

<span data-ttu-id="232e7-126">Para adicionar um atributo intercalado, vá para a página **Intercalar**.</span><span class="sxs-lookup"><span data-stu-id="232e7-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="232e7-127">Selecione **Adicionar atributo intercalado**.</span><span class="sxs-lookup"><span data-stu-id="232e7-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="232e7-128">Forneça um **Nome** para o identificar mais tarde na página **Intercalar**.</span><span class="sxs-lookup"><span data-stu-id="232e7-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="232e7-129">Opcionalmente, forneça um **Nome a apresentar** para aparecer na entidade Perfil de Cliente Unificado.</span><span class="sxs-lookup"><span data-stu-id="232e7-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="232e7-130">Configure **Selecionar atributos duplicados** para selecionar os atributos que pretende intercalar das entidades correspondidas.</span><span class="sxs-lookup"><span data-stu-id="232e7-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="232e7-131">Também pode procurar atributos.</span><span class="sxs-lookup"><span data-stu-id="232e7-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="232e7-132">Defina **Classificar por importância** para dar prioridade a um atributo acima de outros.</span><span class="sxs-lookup"><span data-stu-id="232e7-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="232e7-133">Por exemplo, se a entidade *WebAccountCSV* incluir os dados com maior precisão sobre o atributo *Nome Completos*, poderá dar prioridade a esta entidade em detrimento de *ContactCSV* ao selecionar *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="232e7-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="232e7-134">Como resultado, *WebAccountCSV* é movido para a primeira prioridade, enquanto *ContactCSV* é movido para a segunda prioridade ao solicitar valores para o atributo *Nome Completo*.</span><span class="sxs-lookup"><span data-stu-id="232e7-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="232e7-135">Executar a intercalação</span><span class="sxs-lookup"><span data-stu-id="232e7-135">Run your merge</span></span>

<span data-ttu-id="232e7-136">Quer intercale manualmente os atributos ou deixe que o sistema o faça, poderá sempre executar a intercalação.</span><span class="sxs-lookup"><span data-stu-id="232e7-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="232e7-137">Selecione **Executar** na página **Intercalar** para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="232e7-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="232e7-138">![Guardar e Executar a intercalação de dados](media/configure-data-merge-save-run.png "Guardar e Executar a intercalação de dados")</span><span class="sxs-lookup"><span data-stu-id="232e7-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="232e7-139">Para efetuar alterações adicionais e executar novamente o passo, poderá cancelar uma união em curso.</span><span class="sxs-lookup"><span data-stu-id="232e7-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="232e7-140">Selecione **A atualizar...** e selecione **Cancelar tarefa** no painel lateral apresentado.</span><span class="sxs-lookup"><span data-stu-id="232e7-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="232e7-141">Depois de o texto **A atualizar...** mudar para **Com êxito**, a união foi concluída e as contradições foram resolvidas nos seus dados, em conformidade com as políticas que definiu.</span><span class="sxs-lookup"><span data-stu-id="232e7-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="232e7-142">Os atributos intercalados e não intercalados são incluídos na entidade de perfil unificada.</span><span class="sxs-lookup"><span data-stu-id="232e7-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="232e7-143">Os atributos excluídos não são incluídos na entidade de perfil unificada.</span><span class="sxs-lookup"><span data-stu-id="232e7-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="232e7-144">Se não foi a primeira vez que executou uma intercalação com êxito, todos os processos de a jusante, incluindo o melhoramento, a segmentação e as medidas, serão novamente executados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="232e7-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="232e7-145">Depois de todos os processos a jusante serem novamente executados, os perfis de cliente refletem quaisquer alterações que tenha efetuado.</span><span class="sxs-lookup"><span data-stu-id="232e7-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="232e7-146">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="232e7-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="232e7-147">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="232e7-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="232e7-148">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="232e7-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="232e7-149">Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="232e7-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="232e7-150">Passo Seguinte</span><span class="sxs-lookup"><span data-stu-id="232e7-150">Next Step</span></span>

<span data-ttu-id="232e7-151">Configure [atividades](activities.md), [melhoramento](enrichment-microsoft-graph.md) ou [relações](relationships.md) para obter mais informações sobre os seus clientes.</span><span class="sxs-lookup"><span data-stu-id="232e7-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="232e7-152">Se já tiver configurado atividades, enriquecimento ou relações, ou se tiver definido segmentos, estes serão processados automaticamente para utilizar os dados mais recentes do cliente.</span><span class="sxs-lookup"><span data-stu-id="232e7-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]
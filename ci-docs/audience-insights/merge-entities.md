---
title: Fundir entidades na unificação de dados
description: Fundir entidades para criar perfis unificados de clientes.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305666"
---
# <a name="merge-entities"></a><span data-ttu-id="135e5-103">Unir entidades</span><span class="sxs-lookup"><span data-stu-id="135e5-103">Merge entities</span></span>

<span data-ttu-id="135e5-104">A fase de intercalação é a última fase no processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="135e5-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="135e5-105">Tem como objetivo reconciliar os dados em conflito.</span><span class="sxs-lookup"><span data-stu-id="135e5-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="135e5-106">Os exemplos de dados em conflito poderão incluir um nome de cliente que se encontra em dois dos seus conjuntos de dados, mas que apresenta pequenas diferenças ("Grant Marshall" versus "Grant Marshal"), ou um número de telefone com que difere no formato (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="135e5-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="135e5-107">A intercalação destes pontos de dados em conflito é feita numa base atributo a atributo.</span><span class="sxs-lookup"><span data-stu-id="135e5-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Unir página no processo de unificação de dados a mostrar tabela com campos unidos que definem o perfil do cliente unificado.":::

<span data-ttu-id="135e5-109">Depois de concluir a [fase de intercalação](match-entities.md), pode iniciar a fase de intercalação ao selecione o título **Intercalar** na página **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="135e5-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="135e5-110">Rever recomendações de sistema</span><span class="sxs-lookup"><span data-stu-id="135e5-110">Review system recommendations</span></span>

<span data-ttu-id="135e5-111">Em **Dados** > **Unificar** > **Unir**, escolhe e exclui atributos para unir dentro da sua entidade de perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="135e5-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="135e5-112">O perfil de cliente unificado é o resultado do processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="135e5-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="135e5-113">Alguns atributos são intercalados automaticamente pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="135e5-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="135e5-114">Para ver os atributos incluídos num dos seus atributos automaticamente unidos, selecione o atributo unido no separador **Campos de cliente** da tabela.</span><span class="sxs-lookup"><span data-stu-id="135e5-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="135e5-115">Os atributos que compõem o atributo unido apresentam duas novas linhas abaixo do atributo unido.</span><span class="sxs-lookup"><span data-stu-id="135e5-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="135e5-116">Separar, mudar o nome, excluir e editar campos unidos</span><span class="sxs-lookup"><span data-stu-id="135e5-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="135e5-117">Pode alterar a forma como o sistema processa atributos unidos para gerar o perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="135e5-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="135e5-118">Selecione **Mostrar mais** e escolha o que pretende alterar.</span><span class="sxs-lookup"><span data-stu-id="135e5-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opções no menu pendente Mostrar mais para gerir atributos unidos.":::

<span data-ttu-id="135e5-120">Para mais informações, consulte as secções seguintes.</span><span class="sxs-lookup"><span data-stu-id="135e5-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="135e5-121">Separar campos unidos</span><span class="sxs-lookup"><span data-stu-id="135e5-121">Separate merged fields</span></span>

<span data-ttu-id="135e5-122">Para separar campos unidos, encontre o atributo na tabela.</span><span class="sxs-lookup"><span data-stu-id="135e5-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="135e5-123">Os campos separados mostram como pontos de dados individuais no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="135e5-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="135e5-124">Selecione o campo unido.</span><span class="sxs-lookup"><span data-stu-id="135e5-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="135e5-125">Selecione **Mostrar mais** e escolha **Separar campos**.</span><span class="sxs-lookup"><span data-stu-id="135e5-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="135e5-126">Confirme a separação.</span><span class="sxs-lookup"><span data-stu-id="135e5-126">Confirm the separation.</span></span>

1. <span data-ttu-id="135e5-127">Selecione **Guardar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="135e5-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="135e5-128">Renomear campos unidos</span><span class="sxs-lookup"><span data-stu-id="135e5-128">Rename merged fields</span></span>

<span data-ttu-id="135e5-129">Altere o nome a apresentar dos atributos unidos.</span><span class="sxs-lookup"><span data-stu-id="135e5-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="135e5-130">Não é possível alterar o nome da entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="135e5-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="135e5-131">Selecione o campo unido.</span><span class="sxs-lookup"><span data-stu-id="135e5-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="135e5-132">Selecione **Mostrar mais** e escolha **Mudar o nome**.</span><span class="sxs-lookup"><span data-stu-id="135e5-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="135e5-133">Confirme o nome a apresentar alterado.</span><span class="sxs-lookup"><span data-stu-id="135e5-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="135e5-134">Selecione **Guardar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="135e5-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="135e5-135">Excluir campos unidos</span><span class="sxs-lookup"><span data-stu-id="135e5-135">Exclude merged fields</span></span>

<span data-ttu-id="135e5-136">Excluir um atributo do perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="135e5-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="135e5-137">Se o campo for utilizado noutros processos, por exemplo num segmento, remova-o destes processos antes de o excluir do perfil do cliente.</span><span class="sxs-lookup"><span data-stu-id="135e5-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="135e5-138">Selecione o campo unido.</span><span class="sxs-lookup"><span data-stu-id="135e5-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="135e5-139">Selecione **Mostrar mais** e escolha **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="135e5-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="135e5-140">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="135e5-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="135e5-141">Selecione **Guardar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="135e5-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="135e5-142">Na página **Unir**, selecione **Campos excluídos** para ver a lista de todos os campos excluídos.</span><span class="sxs-lookup"><span data-stu-id="135e5-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="135e5-143">Este painel permite-lhe adicionar novamente campos excluídos.</span><span class="sxs-lookup"><span data-stu-id="135e5-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="135e5-144">Combinar campos manualmente</span><span class="sxs-lookup"><span data-stu-id="135e5-144">Manually combine fields</span></span>

<span data-ttu-id="135e5-145">Especifique manualmente um atributo unido.</span><span class="sxs-lookup"><span data-stu-id="135e5-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="135e5-146">Na página **Unir**, selecione **Combinar campos**.</span><span class="sxs-lookup"><span data-stu-id="135e5-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="135e5-147">Forneça um **Nome** e um **Nome de campo de saída**.</span><span class="sxs-lookup"><span data-stu-id="135e5-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="135e5-148">Escolha um campo a adicionar.</span><span class="sxs-lookup"><span data-stu-id="135e5-148">Choose a field to add.</span></span> <span data-ttu-id="135e5-149">Selecione **Adicionar campos** para combinar mais campos.</span><span class="sxs-lookup"><span data-stu-id="135e5-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="135e5-150">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="135e5-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="135e5-151">Selecione **Guardar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="135e5-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="135e5-152">Alterar a ordem dos campos</span><span class="sxs-lookup"><span data-stu-id="135e5-152">Change the order of fields</span></span>

<span data-ttu-id="135e5-153">Algumas entidades contêm mais detalhes do que outras.</span><span class="sxs-lookup"><span data-stu-id="135e5-153">Some entities contain more details than others.</span></span> <span data-ttu-id="135e5-154">Se uma entidade incluir os dados mais recentes sobre um campo, pode priorizá-lo sobre outras entidades quando unir valores.</span><span class="sxs-lookup"><span data-stu-id="135e5-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="135e5-155">Selecione o campo unido.</span><span class="sxs-lookup"><span data-stu-id="135e5-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="135e5-156">Selecione **Mostrar mais** e escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="135e5-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="135e5-157">No painel **Combinar campos**, selecione **Mover para cima/baixo** para definir a ordem ou arraste e largue-os na posição desejada.</span><span class="sxs-lookup"><span data-stu-id="135e5-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="135e5-158">Confirme a alteração.</span><span class="sxs-lookup"><span data-stu-id="135e5-158">Confirm the change.</span></span>

1. <span data-ttu-id="135e5-159">Selecione **Guardar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="135e5-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="135e5-160">Executar a intercalação</span><span class="sxs-lookup"><span data-stu-id="135e5-160">Run your merge</span></span>

<span data-ttu-id="135e5-161">Quer intercale manualmente os atributos ou deixe que o sistema o faça, poderá sempre executar a intercalação.</span><span class="sxs-lookup"><span data-stu-id="135e5-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="135e5-162">Selecione **Executar** na página **Intercalar** para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="135e5-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="135e5-163">![Guardar e Executar a intercalação de dados](media/configure-data-merge-save-run.png "Guardar e Executar a intercalação de dados")</span><span class="sxs-lookup"><span data-stu-id="135e5-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="135e5-164">Escolha **Executar apenas União** se pretender apenas ver a saída refletida na entidade de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="135e5-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="135e5-165">Os processos a jusante serão atualizados conforme [definido na agenda de atualização](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="135e5-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="135e5-166">Escolha **Executar processos de União e a jusante** para atualizar o sistema com as suas alterações.</span><span class="sxs-lookup"><span data-stu-id="135e5-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="135e5-167">Todos os processos, incluindo enriquecimento, segmentos e medidas serão executados novamente automaticamente.</span><span class="sxs-lookup"><span data-stu-id="135e5-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="135e5-168">Depois de todos os processos a jusante estarem concluídos, os perfis de cliente refletem quaisquer alterações que tenha feito.</span><span class="sxs-lookup"><span data-stu-id="135e5-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="135e5-169">Para fazer mais alterações e voltar a executar o passo, pode cancelar uma união em curso.</span><span class="sxs-lookup"><span data-stu-id="135e5-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="135e5-170">Selecione **A atualizar...** e selecione **Cancelar tarefa** no painel lateral apresentado.</span><span class="sxs-lookup"><span data-stu-id="135e5-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="135e5-171">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="135e5-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="135e5-172">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="135e5-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="135e5-173">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="135e5-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="135e5-174">Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="135e5-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="135e5-175">Passo Seguinte</span><span class="sxs-lookup"><span data-stu-id="135e5-175">Next Step</span></span>

<span data-ttu-id="135e5-176">Configure [atividades](activities.md), [melhoramento](enrichment-hub.md) ou [relações](relationships.md) para obter mais informações sobre os seus clientes.</span><span class="sxs-lookup"><span data-stu-id="135e5-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="135e5-177">Se já configurou atividades, enriquecimento ou segmentos, estes serão processados automaticamente para utilizarem os dados mais recentes do cliente.</span><span class="sxs-lookup"><span data-stu-id="135e5-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

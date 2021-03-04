---
title: Criar e gerir segmentos
description: Crie segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270370"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="e8c6f-103">Criar e gerir segmentos</span><span class="sxs-lookup"><span data-stu-id="e8c6f-103">Create and manage segments</span></span>

<span data-ttu-id="e8c6f-104">Os segmentos permitem-lhe agrupar os seus clientes com base em atributos demográficos, transacionais, ou comportamentais.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="e8c6f-105">Pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para alcançar os seus objetivos de negócio.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="e8c6f-106">Poderá definir filtros complexos à volta da entidade Perfil de Cliente e das entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="e8c6f-107">Cada segmento, após o processamento, cria um conjunto de registos de clientes que pode exportar e tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="e8c6f-108">Aplicam-se alguns [limites de serviço](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="e8c6f-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="e8c6f-109">Salvo indicação em contrário, todos os segmentos são **Segmentos dinâmicos**, que são atualizados num horário recorrente.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="e8c6f-110">O exemplo seguinte ilustra a capacidade de segmentação.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="e8c6f-111">Definimos um segmento para os clientes que encomendaram pelo menos 500 $ de bens nos últimos 90 dias *e* que estavam envolvidos numa chamada de suporte ao cliente que foi escalada.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e8c6f-112">![Múltiplos grupos](media/segmentation-group1-2.png "Múltiplos grupos")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="e8c6f-113">Criar um novo segmento</span><span class="sxs-lookup"><span data-stu-id="e8c6f-113">Create a new segment</span></span>

<span data-ttu-id="e8c6f-114">Os segmentos são geridos na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="e8c6f-115">Nas informações de audiência, vá à página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="e8c6f-116">Selecione **Novo** > **Segmento em branco**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="e8c6f-117">No painel **Novo segmento**, escolha um tipo de segmento e atribua um **Nome**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="e8c6f-118">Opcionalmente, forneça um nome a apresentar e uma descrição que ajude a identificar o segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="e8c6f-119">Selecione **Seguinte** para ir para a página **Construtor de segmentos** onde define um grupo.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="e8c6f-120">Um grupo é um conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="e8c6f-121">Escolha a entidade que inclui o atributo pelo qual pretende segmentar.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="e8c6f-122">Escolha o atributo pelo qual pretende segmentar.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="e8c6f-123">Este atributo pode ter um de quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="e8c6f-124">Escolha um operador e um valor para o atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e8c6f-125">![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo do cliente")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="e8c6f-126">Número</span><span class="sxs-lookup"><span data-stu-id="e8c6f-126">Number</span></span> |<span data-ttu-id="e8c6f-127">Definição</span><span class="sxs-lookup"><span data-stu-id="e8c6f-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="e8c6f-128">1</span><span class="sxs-lookup"><span data-stu-id="e8c6f-128">1</span></span>     |<span data-ttu-id="e8c6f-129">Entity</span><span class="sxs-lookup"><span data-stu-id="e8c6f-129">Entity</span></span>          |
   |<span data-ttu-id="e8c6f-130">2</span><span class="sxs-lookup"><span data-stu-id="e8c6f-130">2</span></span>     |<span data-ttu-id="e8c6f-131">Atributo</span><span class="sxs-lookup"><span data-stu-id="e8c6f-131">Attribute</span></span>          |
   |<span data-ttu-id="e8c6f-132">3</span><span class="sxs-lookup"><span data-stu-id="e8c6f-132">3</span></span>    |<span data-ttu-id="e8c6f-133">Operador</span><span class="sxs-lookup"><span data-stu-id="e8c6f-133">Operator</span></span>         |
   |<span data-ttu-id="e8c6f-134">4</span><span class="sxs-lookup"><span data-stu-id="e8c6f-134">4</span></span>    |<span data-ttu-id="e8c6f-135">valor</span><span class="sxs-lookup"><span data-stu-id="e8c6f-135">Value</span></span>         |

8. <span data-ttu-id="e8c6f-136">Se a entidade estiver ligada à entidade de cliente unificada através das [relações](relationships.md), terá de definir o caminho da relação para criar um segmento válido.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="e8c6f-137">Adicione as entidades a partir do caminho da relação até poder selecionar a entidade **Customer : CustomerInsights** a partir da lista pendente.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="e8c6f-138">Em seguida, escolha **Todos os registos** para cada condição.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e8c6f-139">![Caminho da relação durante a criação do segmento](media/segments-multiple-relationships.png "Caminho da relação durante a criação do segmento")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="e8c6f-140">Selecione **Guardar** para guardar o segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="e8c6f-141">O seu segmento será guardado e processado se todos os requisitos forem validados.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="e8c6f-142">Caso contrário, será guardado como rascunho.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="e8c6f-143">Selecione **Regressar a segmentos** para regressar à página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="e8c6f-144">Gerir segmentos existentes</span><span class="sxs-lookup"><span data-stu-id="e8c6f-144">Manage existing segments</span></span>

<span data-ttu-id="e8c6f-145">Na página **Segmentos**, pode ver todos os segmentos guardados e geri-los.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="e8c6f-146">Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="e8c6f-147">Pode ordenar os segmentos numa coluna ao selecionar o cabeçalho da coluna.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="e8c6f-148">Utilize a caixa de **Pesquisa** no canto superior direito para filtrar os segmentos.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e8c6f-149">![Opções para gerir um segmento existente](media/segments-selected-segment.png "Opções para gerir um segmento existente")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="e8c6f-150">A seguinte ação está disponível quando seleciona um segmento:</span><span class="sxs-lookup"><span data-stu-id="e8c6f-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="e8c6f-151">**Ver** os detalhes do segmento, incluindo a tendência da contagem de membros e uma pré-visualização dos membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="e8c6f-152">**Editar** o segmento para alterar as respetivas propriedades.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="e8c6f-153">**Atualizar** o segmento para incluir os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="e8c6f-154">**Ativar** ou **desativar** o segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="e8c6f-155">Os segmentos têm dois estados possíveis – ativos ou inativos.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="e8c6f-156">Estes estados são úteis ao editar um segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="e8c6f-157">Para segmentos inativos, a definição de segmento existe, mas ainda não contém nenhum cliente.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="e8c6f-158">Quando ativa um segmento, o seu estado muda de "inativo" para "ativo" e começa a procurar clientes que correspondam à definição do segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="e8c6f-159">Se uma [atualização agendada](system.md#schedule-tab) for configurada, os segmentos inativos têm o **Estado** listado como **Ignorado** indicando que uma atualização nem sequer foi tentada.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="e8c6f-160">Quando um segmento inativo é ativado, ele irá atualizar e será incluído em atualizações agendadas.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="e8c6f-161">Em alternativa, pode utilizar a funcionalidade **Agendar mais tarde** no menu pendente **Ativar/Desativar** para especificar uma data e hora futuras para ativação e desativação de um determinado segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="e8c6f-162">**Mudar nome** do segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-162">**Rename** the segment.</span></span>
- <span data-ttu-id="e8c6f-163">**Transferir** a lista de membros como um ficheiro .CSV.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="e8c6f-164">A opção **Adicionar a** envia a lista de IDs do cliente no segmento para processamento noutra aplicação.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="e8c6f-165">**Eliminar** o segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="e8c6f-166">Atualizar segmentos</span><span class="sxs-lookup"><span data-stu-id="e8c6f-166">Refresh segments</span></span>

<span data-ttu-id="e8c6f-167">Pode atualizar todos os segmentos de uma só vez selecionando **Atualizar tudo** na página **Segmentos** ou pode atualizar um ou vários segmentos quando os seleciona e escolher **Atualizar** nas opções.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="e8c6f-168">Em alternativa, poderá configurar uma atualização recorrente em **Administração** > **Sistema** > **Agendar**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="e8c6f-169">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e8c6f-170">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e8c6f-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e8c6f-171">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e8c6f-172">Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="e8c6f-173">Transferir e exportar segmentos</span><span class="sxs-lookup"><span data-stu-id="e8c6f-173">Download and export segments</span></span>

<span data-ttu-id="e8c6f-174">Poderá transferir os seus segmentos para um ficheiro CSV ou exportá-los para o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="e8c6f-175">Transferir segmentos para um ficheiro CSV</span><span class="sxs-lookup"><span data-stu-id="e8c6f-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="e8c6f-176">Nas informações de audiência, vá à página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="e8c6f-177">Selecione as reticências no mosaico de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="e8c6f-178">Selecione **Transferir como CSV** na lista pendente de ações.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="e8c6f-179">Exportar segmentos para o Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="e8c6f-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="e8c6f-180">Antes de exportar os segmentos para o Dynamics 365 Sales, um administrador precisa de [criar o destino de exportação](export-destinations.md) para o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="e8c6f-181">Nas informações de audiência, vá à página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="e8c6f-182">Selecione as reticências no mosaico de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="e8c6f-183">Selecione **Adicionar a** na lista pendente de ações e selecione o destino de exportação para o qual pretende enviar os dados.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="e8c6f-184">Modo Rascunho para segmentos</span><span class="sxs-lookup"><span data-stu-id="e8c6f-184">Draft mode for segments</span></span>

<span data-ttu-id="e8c6f-185">Se nem todos os requisitos para processar um segmento forem satisfeitos, pode guardar o segmento como rascunho e aceder ao mesmo na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="e8c6f-186">Será guardado como um segmento inativo e não poderá ser ativado enquanto não for válido.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="e8c6f-187">Adicionar mais condições a um grupo</span><span class="sxs-lookup"><span data-stu-id="e8c6f-187">Add more conditions to a group</span></span>

<span data-ttu-id="e8c6f-188">Para adicionar mais condições a um grupo, poderá utilizar dois operadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="e8c6f-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="e8c6f-189">Operador **AND**: ambas as condições têm de ser satisfeitas como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="e8c6f-190">Esta opção é mais útil quando define condições em diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="e8c6f-191">Operador **OR**: qualquer uma das condições tem de ser satisfeita como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="e8c6f-192">Esta opção é mais útil quando define múltiplas condições para a mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e8c6f-193">![Operador OR onde qualquer condição tem de ser satisfeita](media/segmentation-either-condition.png "Operador OR onde qualquer condição tem de ser satisfeita")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="e8c6f-194">Atualmente, é possível aninhar um operador **OR** num operador **AND**, mas não o contrário.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="e8c6f-195">Combinar múltiplos grupos</span><span class="sxs-lookup"><span data-stu-id="e8c6f-195">Combine multiple groups</span></span>

<span data-ttu-id="e8c6f-196">Cada grupo produz um conjunto de clientes específico.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="e8c6f-197">Poderá combinar estes grupos para incluir os clientes necessários para o seu caso de negócio.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="e8c6f-198">Nas informações de audiência, aceda à página **Segmentos** e selecione um segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="e8c6f-199">Selecione **Adicionar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e8c6f-200">![Grupo de clientes - adicionar grupo](media/customer-group-add-group.png "Grupo de clientes - adicionar grupo")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="e8c6f-201">Selecione um dos seguintes operadores de definição: **União**, **Interseção** ou **Exceto**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e8c6f-202">![Grupo de clientes - adicionar união](media/customer-group-union.png "Grupo de clientes - adicionar união")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="e8c6f-203">Selecione um operador de definição para definir um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="e8c6f-204">Guardar diferentes grupos para determinar que dados são retidos:</span><span class="sxs-lookup"><span data-stu-id="e8c6f-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="e8c6f-205">**União** une os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="e8c6f-206">**Interseção** sobrepõe os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="e8c6f-207">Apenas os dados que *são comuns* a ambos os grupos são mantidos no grupo unificado.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="e8c6f-208">**Exceto** combina os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-208">**Except** combines the two groups.</span></span> <span data-ttu-id="e8c6f-209">Apenas os dados do grupo A que *não são comuns* aos dados do grupo B são mantidos.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="e8c6f-210">Ver histórico de processamento e membros do segmento</span><span class="sxs-lookup"><span data-stu-id="e8c6f-210">View processing history and segment members</span></span>

<span data-ttu-id="e8c6f-211">Poderá ver os dados consolidados sobre um segmento ao analisar os respetivos detalhes.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="e8c6f-212">Na página **Segmentos**, selecione o segmento que pretende analisar.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="e8c6f-213">A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="e8c6f-214">Passe o rato sobre os pontos de dados para ver a contagem de membros numa data específica.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="e8c6f-215">Poderá atualizar o intervalo de tempo da visualização.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e8c6f-216">![Intervalo de tempo do segmento](media/segment-time-range.png "Intervalo de tempo do segmento")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="e8c6f-217">A parte inferior contém uma lista dos membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="e8c6f-218">Os campos apresentados nesta lista baseiam-se nos atributos das entidades do segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="e8c6f-219">A lista é uma pré-visualização dos membros do segmento correspondente e mostra os primeiros 100 registos do seu segmento para poder avaliá-lo rapidamente e rever as definições, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="e8c6f-220">Para ver todos os registos correspondentes, tem de [exportar o segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e8c6f-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="e8c6f-221">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="e8c6f-221">Quick segments</span></span>

<span data-ttu-id="e8c6f-222">Para além do construtor de segmentos, há outro caminho para a criação de segmentos.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="e8c6f-223">Os segmentos rápidos permitem criar segmentos simples (com um único operador) rapidamente e com informações instantâneas.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="e8c6f-224">Na página **Segmentos**, selecione **Novo** > **Criar rapidamente a partir de**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="e8c6f-225">Selecione a opção **Perfis** para criar um segmento baseado na entidade Cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="e8c6f-226">Selecione a opção **Medidas** para criar um segmento à volta de cada tipo de Atributo de Cliente das medidas que criou anteriormente na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="e8c6f-227">Selecione a opção **Inteligência** para criar um segmento à volta de uma das entidades de saída geradas com as capacidades **Predições** ou **Modelos Personalizados**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="e8c6f-228">Na caixa de diálogo **Novo segmento rápido**, selecione um atributo na lista pendente **Campo**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="e8c6f-229">O sistema fornecerá algumas informações adicionais que o ajudam a criar melhores segmentos dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="e8c6f-230">Para campos categóricos, mostraremos as 10 melhores contagens de clientes.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="e8c6f-231">Escolha um **Valor** e selecione **Rever**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="e8c6f-232">Para um atributo numérico, o sistema mostrará que valor do atributo se situa no percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="e8c6f-233">Escolha um **Operador** e um **Valor** e, em seguida, selecione **Rever**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="e8c6f-234">O sistema fornecerá um **Tamanho do segmento estimado**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="e8c6f-235">Poderá selecionar se pretende gerar ou não o segmento que definiu ou, primeiro, revisitá-lo para obter um tamanho de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e8c6f-236">![Nome e estimativa para um segmento rápido](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="e8c6f-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="e8c6f-237">Indique um **Nome** para o seu segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="e8c6f-238">Opcionalmente, indique um **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="e8c6f-239">Selecione **Guardar** para criar o segmento.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="e8c6f-240">Depois de concluído o processamento do segmento, poderá vê-lo como qualquer outro segmento que tenha criado.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="e8c6f-241">Para os cenários seguintes, recomendamos a utilização do construtor de segmentos em vez da funcionalidade de segmentos recomendada:</span><span class="sxs-lookup"><span data-stu-id="e8c6f-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="e8c6f-242">Criar segmentos com filtros em campos categóricos onde o operador é diferente do operador **É**</span><span class="sxs-lookup"><span data-stu-id="e8c6f-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="e8c6f-243">Criar segmentos com filtros em campos numéricos onde o operador é diferente dos operadores **Entre**, **Maior que** e **Menor que**</span><span class="sxs-lookup"><span data-stu-id="e8c6f-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="e8c6f-244">Criar segmentos com filtros nos campos de tipo de data</span><span class="sxs-lookup"><span data-stu-id="e8c6f-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="e8c6f-245">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="e8c6f-245">Next steps</span></span>

<span data-ttu-id="e8c6f-246">[Exportar um segmento](export-destinations.md) e explore a [Ficha de Cliente](customer-card-add-in.md) e [Conectores](export-power-bi.md) para obter informações a nível do cliente.</span><span class="sxs-lookup"><span data-stu-id="e8c6f-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
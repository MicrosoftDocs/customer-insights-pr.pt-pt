---
title: Criar e gerir medidas
description: Defina medidas para analisar e refletir o desempenho do seu negócio.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654746"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="ee65e-103">Definir e gerir medidas</span><span class="sxs-lookup"><span data-stu-id="ee65e-103">Define and manage measures</span></span>

<span data-ttu-id="ee65e-104">As medidas ajudam-no a compreender melhor os comportamentos dos clientes e o desempenho do negócio ao obter valores relevantes a partir de [perfis unificados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="ee65e-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="ee65e-105">Por exemplo, uma empresa quer ver o *gasto total por cliente* para entender o histórico de compras de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="ee65e-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="ee65e-106">Ou medir as *vendas totais da empresa* para entender as receitas ao nível do agregado em todo o negócio.</span><span class="sxs-lookup"><span data-stu-id="ee65e-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="ee65e-107">As medidas são criadas utilizando o criador de medidas, uma plataforma de consulta de dados com vários operadores e opções simples de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ee65e-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="ee65e-108">Permite filtrar os dados, agrupar os resultados, detetar [caminhos de relações entres entidades](relationships.md) e pré-visualizar a saída.</span><span class="sxs-lookup"><span data-stu-id="ee65e-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="ee65e-109">Utilize o criador de medidas para planear as atividades empresariais consultando os dados dos clientes e extraindo informações.</span><span class="sxs-lookup"><span data-stu-id="ee65e-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="ee65e-110">Por exemplo, criar uma medida de *gasto total por cliente* e *devoluções totais por cliente* ajuda a identificar um grupo de clientes com elevado gasto mas com elevadas devoluções também.</span><span class="sxs-lookup"><span data-stu-id="ee65e-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="ee65e-111">Pode [criar um segmento](segments.md) para impulsionar as próximas melhores ações.</span><span class="sxs-lookup"><span data-stu-id="ee65e-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="ee65e-112">Criar uma medida</span><span class="sxs-lookup"><span data-stu-id="ee65e-112">Create a measure</span></span>

<span data-ttu-id="ee65e-113">Esta secção acompanha-o através da criação de uma nova medida a partir do zero.</span><span class="sxs-lookup"><span data-stu-id="ee65e-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="ee65e-114">Pode criar uma medida com atributos de dados de entidades de dados que tenham uma relação configurada para ligar à entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="ee65e-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="ee65e-115">Nas informações de audiência, vá a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="ee65e-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="ee65e-116">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ee65e-116">Select **New**.</span></span>

1. <span data-ttu-id="ee65e-117">Selecione **Editar nome** e forneça um **Nome** para a medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="ee65e-118">Se a sua nova configuração de medida tiver apenas dois campos, para exemplo, CustomerID e um cálculo, a saída será adicionada como uma nova coluna à entidade gerada pelo sistema chamada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="ee65e-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="ee65e-119">E poderá ver o valor da medida no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="ee65e-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="ee65e-120">Outras medidas irão gerar as suas próprias entidades.</span><span class="sxs-lookup"><span data-stu-id="ee65e-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="ee65e-121">Na área de configuração, escolha a função de agregação no menu pendente **Selecionar Função**.</span><span class="sxs-lookup"><span data-stu-id="ee65e-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="ee65e-122">As funções de agregação incluem:</span><span class="sxs-lookup"><span data-stu-id="ee65e-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="ee65e-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="ee65e-123">**Sum**</span></span>
   - <span data-ttu-id="ee65e-124">**Média**</span><span class="sxs-lookup"><span data-stu-id="ee65e-124">**Average**</span></span>
   - <span data-ttu-id="ee65e-125">**Contagem**</span><span class="sxs-lookup"><span data-stu-id="ee65e-125">**Count**</span></span>
   - <span data-ttu-id="ee65e-126">**Contagem Exclusiva**</span><span class="sxs-lookup"><span data-stu-id="ee65e-126">**Count Unique**</span></span>
   - <span data-ttu-id="ee65e-127">**Máx.**</span><span class="sxs-lookup"><span data-stu-id="ee65e-127">**Max**</span></span>
   - <span data-ttu-id="ee65e-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="ee65e-128">**Min**</span></span>
   - <span data-ttu-id="ee65e-129">**Primeiro:** pega no primeiro valor do registo de dados</span><span class="sxs-lookup"><span data-stu-id="ee65e-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="ee65e-130">**Último**: pega no último valor que foi adicionado ao registo de dados</span><span class="sxs-lookup"><span data-stu-id="ee65e-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. <span data-ttu-id="ee65e-132">Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="ee65e-133">Selecione o separador **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="ee65e-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="ee65e-134">Entidade de dados: escolha a entidade que inclui o atributo que pretende medir.</span><span class="sxs-lookup"><span data-stu-id="ee65e-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="ee65e-135">Atributo de dados: escolha o atributo que pretende utilizar na função agregação para calcular a medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="ee65e-136">Só pode selecionar um atributo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="ee65e-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="ee65e-137">Também pode selecionar um atributo de dados a partir de uma medida existente selecionando o separador **Medidas**. Ou, pode procurar uma entidade ou um nome de medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="ee65e-138">Selecione **Adicionar** para adicionar o atributo selecionado à medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecionar um atributo a usar em cálculos.":::

1. <span data-ttu-id="ee65e-140">Para criar medidas mais complexas, pode adicionar mais atributos ou utilizar operadores de matemática na sua função de medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Criar uma medida complexa com operadores de matemática.":::

1. <span data-ttu-id="ee65e-142">Para adicionar filtros, selecione **Filtro** na área de configuração.</span><span class="sxs-lookup"><span data-stu-id="ee65e-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="ee65e-143">Na secção **Adicionar atributos** do painel **Filtros**, selecione o atributo que pretende utilizar para criar filtros.</span><span class="sxs-lookup"><span data-stu-id="ee65e-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="ee65e-144">Defina os operadores de filtro para definir o filtro para cada atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="ee65e-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="ee65e-145">Selecione **Aplicar** para adicionar os filtros à medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="ee65e-146">Para adicionar dimensões, selecione **Dimensão** na área de configuração.</span><span class="sxs-lookup"><span data-stu-id="ee65e-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="ee65e-147">Dimensões mostrarão como colunas na entidade de saída da medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="ee65e-148">Selecione **Editar dimensões** para adicionar atributos de dados pelos quais pretende agrupar os valores da medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="ee65e-149">Por exemplo, cidade ou sexo.</span><span class="sxs-lookup"><span data-stu-id="ee65e-149">For example, city or gender.</span></span> <span data-ttu-id="ee65e-150">Por predefinição, a dimensão *CustomerID* é selecionada para criar *medidas ao nível do cliente*.</span><span class="sxs-lookup"><span data-stu-id="ee65e-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="ee65e-151">Pode remover a dimensão predefinida se pretender criar *medidas ao nível do negócio*.</span><span class="sxs-lookup"><span data-stu-id="ee65e-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="ee65e-152">Selecione **Concluído** para adicionar as dimensões à medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="ee65e-153">Se existirem múltiplos caminhos entre a entidade de dados que mapeou e a entidade *Cliente*, tem de escolher um dos [caminhos de relação entre entidades identificados](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="ee65e-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="ee65e-154">Os resultados da medida podem variar dependendo do caminho selecionado.</span><span class="sxs-lookup"><span data-stu-id="ee65e-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="ee65e-155">Selecione **Preferências de dados** e escolha o caminho da entidade que deve ser usado para identificar a sua medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="ee65e-156">Se houver apenas um único caminho para a entidade *Cliente*, este controlo não aparecerá.</span><span class="sxs-lookup"><span data-stu-id="ee65e-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="ee65e-157">Selecione **Concluído** para aplicar a sua seleção.</span><span class="sxs-lookup"><span data-stu-id="ee65e-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecionar o caminho da entidade para a medida.":::

1. <span data-ttu-id="ee65e-159">Para adicionar mais cálculos para a medida, selecione **Novo cálculo**.</span><span class="sxs-lookup"><span data-stu-id="ee65e-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="ee65e-160">Só é possível utilizar entidades no mesmo caminho da entidade para novos cálculos.</span><span class="sxs-lookup"><span data-stu-id="ee65e-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="ee65e-161">Mais cálculos mostrarão como novas colunas na entidade de saída da medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="ee65e-162">Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="ee65e-163">Na área **Pré-visualização**, verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões.</span><span class="sxs-lookup"><span data-stu-id="ee65e-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="ee65e-164">A pré-visualização reage dinamicamente a alterações na configuração.</span><span class="sxs-lookup"><span data-stu-id="ee65e-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="ee65e-165">Selecione **Executar** para calcular os resultados da medida configurada.</span><span class="sxs-lookup"><span data-stu-id="ee65e-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="ee65e-166">Selecione **Guardar e fechar** se pretender manter a configuração atual e executar a medida mais tarde.</span><span class="sxs-lookup"><span data-stu-id="ee65e-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="ee65e-167">Vá a **Medidas** para ver a nova medida criada na lista.</span><span class="sxs-lookup"><span data-stu-id="ee65e-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="ee65e-168">Gerir as medidas</span><span class="sxs-lookup"><span data-stu-id="ee65e-168">Manage your measures</span></span>

<span data-ttu-id="ee65e-169">Depois de [criar uma medida](#create-a-measure), vê uma lista de medidas na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="ee65e-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="ee65e-170">Encontrará informações sobre o tipo de medida, o criador, data de criação e estado.</span><span class="sxs-lookup"><span data-stu-id="ee65e-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="ee65e-171">Quando seleciona uma medida da lista, pode pré-visualizar a saída e transferir um ficheiro .CSV.</span><span class="sxs-lookup"><span data-stu-id="ee65e-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="ee65e-172">Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.</span><span class="sxs-lookup"><span data-stu-id="ee65e-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ee65e-173">![Ações para gerir medidas únicas](media/measure-actions.png "Ações para gerir medidas únicas")</span><span class="sxs-lookup"><span data-stu-id="ee65e-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="ee65e-174">Selecione uma medida da lista para as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ee65e-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="ee65e-175">Selecione o nome da medida para ver os respetivos detalhes.</span><span class="sxs-lookup"><span data-stu-id="ee65e-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="ee65e-176">**Edite** a configuração da medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="ee65e-177">**Atualize** a medida com base nos dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="ee65e-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="ee65e-178">**Mude o nome** da medida.</span><span class="sxs-lookup"><span data-stu-id="ee65e-178">**Rename** the measure.</span></span>
- <span data-ttu-id="ee65e-179">**Elimine** a medição.</span><span class="sxs-lookup"><span data-stu-id="ee65e-179">**Delete** the measure.</span></span>
- <span data-ttu-id="ee65e-180">**Ativar** ou **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="ee65e-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="ee65e-181">As medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ee65e-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="ee65e-182">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="ee65e-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ee65e-183">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ee65e-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ee65e-184">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="ee65e-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ee65e-185">Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="ee65e-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ee65e-186">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="ee65e-186">Next step</span></span>

<span data-ttu-id="ee65e-187">Pode utilizar as medidas existentes para criar [um segmento de cliente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ee65e-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
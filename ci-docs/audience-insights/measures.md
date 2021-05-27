---
title: Criar e gerir medidas
description: Defina medidas para analisar e refletir o desempenho do seu negócio.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049264"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="482ab-103">Definir e gerir medidas</span><span class="sxs-lookup"><span data-stu-id="482ab-103">Define and manage measures</span></span>

<span data-ttu-id="482ab-104">As medidas ajudam-no a compreender melhor os comportamentos dos clientes e o desempenho do negócio.</span><span class="sxs-lookup"><span data-stu-id="482ab-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="482ab-105">Olham para os valores relevantes dos [perfis unificados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="482ab-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="482ab-106">Por exemplo, uma empresa quer ver o *gasto total por cliente* para entender o histórico de compras de cada cliente ou medir as *vendas totais da empresa* para entender a receita agregada de todo o negócio.</span><span class="sxs-lookup"><span data-stu-id="482ab-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="482ab-107">As medidas são criadas utilizando o criador de medidas, uma plataforma de consulta de dados com vários operadores e opções simples de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="482ab-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="482ab-108">Permite filtrar os dados, agrupar os resultados, detetar [caminhos de relações entres entidades](relationships.md) e pré-visualizar a saída.</span><span class="sxs-lookup"><span data-stu-id="482ab-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="482ab-109">Utilize o criador de medidas para planear as atividades empresariais consultando os dados dos clientes e extraindo informações.</span><span class="sxs-lookup"><span data-stu-id="482ab-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="482ab-110">Por exemplo, criar uma medida de *gasto total por cliente* e *devoluções totais por cliente* ajuda a identificar um grupo de clientes com elevado gasto mas com elevadas devoluções também.</span><span class="sxs-lookup"><span data-stu-id="482ab-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="482ab-111">Pode [criar um segmento](segments.md) para impulsionar as próximas melhores ações.</span><span class="sxs-lookup"><span data-stu-id="482ab-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="482ab-112">Criar a sua própria medida de raiz</span><span class="sxs-lookup"><span data-stu-id="482ab-112">Build your own measure from scratch</span></span>

<span data-ttu-id="482ab-113">Esta secção acompanha-o através da criação de uma nova medida a partir do zero.</span><span class="sxs-lookup"><span data-stu-id="482ab-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="482ab-114">Pode criar uma medida com atributos de dados de entidades de dados que tenham uma relação configurada para ligar à entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="482ab-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="482ab-115">Nas informações de audiência, vá a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="482ab-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="482ab-116">Selecione **Nova** e escolha **Criar a sua própria**.</span><span class="sxs-lookup"><span data-stu-id="482ab-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="482ab-117">Selecione **Editar nome** e forneça um **Nome** para a medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="482ab-118">Se a sua nova configuração de medidas tiver apenas dois campos, por exemplo, CustomerID e um cálculo, a saída será adicionada como uma nova coluna à entidade gerada pelo sistema chamada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="482ab-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="482ab-119">E poderá ver o valor da medida no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="482ab-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="482ab-120">Outras medidas irão gerar as suas próprias entidades.</span><span class="sxs-lookup"><span data-stu-id="482ab-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="482ab-121">Na área de configuração, escolha a função de agregação no menu pendente **Selecionar Função**.</span><span class="sxs-lookup"><span data-stu-id="482ab-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="482ab-122">As funções de agregação incluem:</span><span class="sxs-lookup"><span data-stu-id="482ab-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="482ab-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="482ab-123">**Sum**</span></span>
   - <span data-ttu-id="482ab-124">**Média**</span><span class="sxs-lookup"><span data-stu-id="482ab-124">**Average**</span></span>
   - <span data-ttu-id="482ab-125">**Contagem**</span><span class="sxs-lookup"><span data-stu-id="482ab-125">**Count**</span></span>
   - <span data-ttu-id="482ab-126">**Contagem Exclusiva**</span><span class="sxs-lookup"><span data-stu-id="482ab-126">**Count Unique**</span></span>
   - <span data-ttu-id="482ab-127">**Máx.**</span><span class="sxs-lookup"><span data-stu-id="482ab-127">**Max**</span></span>
   - <span data-ttu-id="482ab-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="482ab-128">**Min**</span></span>
   - <span data-ttu-id="482ab-129">**Primeiro:** pega no primeiro valor do registo de dados</span><span class="sxs-lookup"><span data-stu-id="482ab-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="482ab-130">**Último**: pega no último valor que foi adicionado ao registo de dados</span><span class="sxs-lookup"><span data-stu-id="482ab-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. <span data-ttu-id="482ab-132">Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="482ab-133">Selecione o separador **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="482ab-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="482ab-134">Entidade de dados: escolha a entidade que inclui o atributo que pretende medir.</span><span class="sxs-lookup"><span data-stu-id="482ab-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="482ab-135">Atributo de dados: escolha o atributo que pretende utilizar na função agregação para calcular a medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="482ab-136">Só pode selecionar um atributo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="482ab-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="482ab-137">Também pode selecionar um atributo de dados a partir de uma medida existente selecionando o separador **Medidas**. Ou, pode procurar uma entidade ou um nome de medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="482ab-138">Selecione **Adicionar** para adicionar o atributo selecionado à medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecionar um atributo a usar em cálculos.":::

1. <span data-ttu-id="482ab-140">Para criar medidas mais complexas, pode adicionar mais atributos ou utilizar operadores de matemática na sua função de medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Criar uma medida complexa com operadores de matemática.":::

1. <span data-ttu-id="482ab-142">Para adicionar filtros, selecione **Filtro** na área de configuração.</span><span class="sxs-lookup"><span data-stu-id="482ab-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="482ab-143">Na secção **Adicionar atributos** do painel **Filtros**, selecione o atributo que pretende utilizar para criar filtros.</span><span class="sxs-lookup"><span data-stu-id="482ab-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="482ab-144">Defina os operadores de filtro para definir o filtro para cada atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="482ab-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="482ab-145">Selecione **Aplicar** para adicionar os filtros à medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="482ab-146">Para adicionar dimensões, selecione **Dimensão** na área de configuração.</span><span class="sxs-lookup"><span data-stu-id="482ab-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="482ab-147">Dimensões mostrarão como colunas na entidade de saída da medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="482ab-148">Selecione **Editar dimensões** para adicionar atributos de dados pelos quais pretende agrupar os valores da medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="482ab-149">Por exemplo, cidade ou sexo.</span><span class="sxs-lookup"><span data-stu-id="482ab-149">For example, city or gender.</span></span> <span data-ttu-id="482ab-150">Por predefinição, a dimensão *CustomerID* é selecionada para criar *medidas ao nível do cliente*.</span><span class="sxs-lookup"><span data-stu-id="482ab-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="482ab-151">Pode remover a dimensão predefinida se pretender criar *medidas ao nível do negócio*.</span><span class="sxs-lookup"><span data-stu-id="482ab-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="482ab-152">Selecione **Concluído** para adicionar as dimensões à medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="482ab-153">Se houver valores nos seus dados que precisa de substituir por um número inteiro, por exemplo, substitua *nulo* por *0*, selecione **Regras**.</span><span class="sxs-lookup"><span data-stu-id="482ab-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="482ab-154">Configure a regra e certifique-se de que escolhe apenas números inteiros como substitutos.</span><span class="sxs-lookup"><span data-stu-id="482ab-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="482ab-155">Se existirem múltiplos caminhos entre a entidade de dados que mapeou e a entidade *Cliente*, tem de escolher um dos [caminhos de relação entre entidades identificados](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="482ab-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="482ab-156">Os resultados da medida podem variar dependendo do caminho selecionado.</span><span class="sxs-lookup"><span data-stu-id="482ab-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="482ab-157">Selecione **Preferências de dados** e escolha o caminho da entidade que deve ser usado para identificar a sua medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="482ab-158">Se houver apenas um único caminho para a entidade *Cliente*, este controlo não aparecerá.</span><span class="sxs-lookup"><span data-stu-id="482ab-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="482ab-159">Selecione **Concluído** para aplicar a sua seleção.</span><span class="sxs-lookup"><span data-stu-id="482ab-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecionar o caminho da entidade para a medida.":::

1. <span data-ttu-id="482ab-161">Para adicionar mais cálculos para a medida, selecione **Novo cálculo**.</span><span class="sxs-lookup"><span data-stu-id="482ab-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="482ab-162">Só é possível utilizar entidades no mesmo caminho da entidade para novos cálculos.</span><span class="sxs-lookup"><span data-stu-id="482ab-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="482ab-163">Mais cálculos mostrarão como novas colunas na entidade de saída da medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="482ab-164">Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="482ab-165">Na área **Pré-visualização**, verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões.</span><span class="sxs-lookup"><span data-stu-id="482ab-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="482ab-166">A pré-visualização reage dinamicamente a alterações na configuração.</span><span class="sxs-lookup"><span data-stu-id="482ab-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="482ab-167">Selecione **Executar** para calcular os resultados da medida configurada.</span><span class="sxs-lookup"><span data-stu-id="482ab-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="482ab-168">Selecione **Guardar e fechar** se pretender manter a configuração atual e executar a medida mais tarde.</span><span class="sxs-lookup"><span data-stu-id="482ab-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="482ab-169">Vá a **Medidas** para ver a nova medida criada na lista.</span><span class="sxs-lookup"><span data-stu-id="482ab-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="482ab-170">Utilize um modelo para criar uma medida</span><span class="sxs-lookup"><span data-stu-id="482ab-170">Use a template to build a measure</span></span>

<span data-ttu-id="482ab-171">Pode utilizar modelos predefinidos de medidas utilizadas frequentemente para criá-las.</span><span class="sxs-lookup"><span data-stu-id="482ab-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="482ab-172">Descrições detalhadas dos modelos e uma experiência guiada ajudam-no com a criação de medidas eficientes.</span><span class="sxs-lookup"><span data-stu-id="482ab-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="482ab-173">Os modelos são criados a partir de dados mapeados da entidade de *Atividade Unificada*.</span><span class="sxs-lookup"><span data-stu-id="482ab-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="482ab-174">Por isso, certifique-se de que configurou [atividades de cliente](activities.md) antes de criar uma medida a partir de um modelo.</span><span class="sxs-lookup"><span data-stu-id="482ab-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="482ab-175">Modelos de medidas disponíveis:</span><span class="sxs-lookup"><span data-stu-id="482ab-175">Available measure templates:</span></span> 
- <span data-ttu-id="482ab-176">Valor médio da transação (ATV)</span><span class="sxs-lookup"><span data-stu-id="482ab-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="482ab-177">Valor total das transações</span><span class="sxs-lookup"><span data-stu-id="482ab-177">Total transaction value</span></span>
- <span data-ttu-id="482ab-178">Receita média diária</span><span class="sxs-lookup"><span data-stu-id="482ab-178">Average daily revenue</span></span>
- <span data-ttu-id="482ab-179">Receita média anual</span><span class="sxs-lookup"><span data-stu-id="482ab-179">Average yearly revenue</span></span>
- <span data-ttu-id="482ab-180">Contagem de transações</span><span class="sxs-lookup"><span data-stu-id="482ab-180">Transaction count</span></span>
- <span data-ttu-id="482ab-181">Pontos de fidelização ganhos</span><span class="sxs-lookup"><span data-stu-id="482ab-181">Loyalty points earned</span></span>
- <span data-ttu-id="482ab-182">Pontos de fidelização resgatados</span><span class="sxs-lookup"><span data-stu-id="482ab-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="482ab-183">Saldo de pontos de fidelização</span><span class="sxs-lookup"><span data-stu-id="482ab-183">Loyalty points balance</span></span>
- <span data-ttu-id="482ab-184">Período de tempo ativo do cliente</span><span class="sxs-lookup"><span data-stu-id="482ab-184">Active customer lifespan</span></span>
- <span data-ttu-id="482ab-185">Duração da adesão à fidelidade</span><span class="sxs-lookup"><span data-stu-id="482ab-185">Loyalty membership duration</span></span>
- <span data-ttu-id="482ab-186">Tempo desde a última compra</span><span class="sxs-lookup"><span data-stu-id="482ab-186">Time since last purchase</span></span>

<span data-ttu-id="482ab-187">O procedimento a seguir descreve os passos para criar uma nova medida utilizando um modelo.</span><span class="sxs-lookup"><span data-stu-id="482ab-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="482ab-188">Nas informações de audiência, vá a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="482ab-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="482ab-189">Selecione **Novo** e, em seguida, selecione **Escolher um modelo**.</span><span class="sxs-lookup"><span data-stu-id="482ab-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de ecrã do menu suspenso ao criar uma nova medida com o modelo realçado.":::

1. <span data-ttu-id="482ab-191">Encontre o modelo que se adequa à sua necessidade e selecione **Escolher modelo**.</span><span class="sxs-lookup"><span data-stu-id="482ab-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="482ab-192">Reveja os dados necessários e selecione **Começar** se tiver todos os dados preparados.</span><span class="sxs-lookup"><span data-stu-id="482ab-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="482ab-193">No painel **Editar nome**, defina o nome da sua medida e a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="482ab-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="482ab-194">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="482ab-194">Select **Done**.</span></span>

1. <span data-ttu-id="482ab-195">Na secção **Definir período de tempo**, defina o período de tempo dos dados a utilizar.</span><span class="sxs-lookup"><span data-stu-id="482ab-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="482ab-196">Escolha se pretende que a nova medida cubra todo o conjunto de dados selecionando **De Sempre**.</span><span class="sxs-lookup"><span data-stu-id="482ab-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="482ab-197">Ou se quiser que a medida se concentre num **Período de tempo específico**.</span><span class="sxs-lookup"><span data-stu-id="482ab-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de ecrã a mostrar a secção do período de tempo ao configurar uma medida a partir de um modelo.":::

1. <span data-ttu-id="482ab-199">Na secção seguinte, selecione **Adicionar dados** para escolher as atividades e mapear os dados correspondentes da sua entidade *Atividade Unificada*.</span><span class="sxs-lookup"><span data-stu-id="482ab-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="482ab-200">Passo 1 de 2: sob **Tipo de atividade**, escolha o tipo de entidade que pretende utilizar.</span><span class="sxs-lookup"><span data-stu-id="482ab-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="482ab-201">Para **Atividades**, selecione as entidades que pretende mapear.</span><span class="sxs-lookup"><span data-stu-id="482ab-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="482ab-202">Passo 2 de 2: escolha o atributo da entidade *Atividade Unificada* para o componente exigido pela fórmula.</span><span class="sxs-lookup"><span data-stu-id="482ab-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="482ab-203">Por exemplo, para o valor de transação Médio, é o atributo que representa o valor da Transação.</span><span class="sxs-lookup"><span data-stu-id="482ab-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="482ab-204">Para **Carimbo data/hora da atividade**, escolha o atributo da entidade Atividade Unificada que representa a data e a hora da atividade.</span><span class="sxs-lookup"><span data-stu-id="482ab-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="482ab-205">Quando o mapeamento de dados for bem sucedido, pode ver o estado como **Concluído** e o nome das atividades e atributos mapeados.</span><span class="sxs-lookup"><span data-stu-id="482ab-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de ecrã de uma configuração de modelo de medida concluída.":::

1. <span data-ttu-id="482ab-207">Agora pode selecionar **Executar** para calcular os resultados da medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="482ab-208">Para refiná-la mais tarde, selecione **Guardar rascunho**.</span><span class="sxs-lookup"><span data-stu-id="482ab-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="482ab-209">Gerir as medidas</span><span class="sxs-lookup"><span data-stu-id="482ab-209">Manage your measures</span></span>

<span data-ttu-id="482ab-210">Pode encontrar a lista de medidas na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="482ab-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="482ab-211">Encontrará informações sobre o tipo de medida, o criador, data de criação e estado.</span><span class="sxs-lookup"><span data-stu-id="482ab-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="482ab-212">Quando seleciona uma medida da lista, pode pré-visualizar a saída e transferir um ficheiro .CSV.</span><span class="sxs-lookup"><span data-stu-id="482ab-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="482ab-213">Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.</span><span class="sxs-lookup"><span data-stu-id="482ab-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="482ab-214">![Ações para gerir medidas únicas](media/measure-actions.png "Ações para gerir medidas únicas")</span><span class="sxs-lookup"><span data-stu-id="482ab-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="482ab-215">Selecione uma medida da lista para as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="482ab-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="482ab-216">Selecione o nome da medida para ver os respetivos detalhes.</span><span class="sxs-lookup"><span data-stu-id="482ab-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="482ab-217">**Edite** a configuração da medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="482ab-218">**Atualize** a medida com base nos dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="482ab-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="482ab-219">**Mude o nome** da medida.</span><span class="sxs-lookup"><span data-stu-id="482ab-219">**Rename** the measure.</span></span>
- <span data-ttu-id="482ab-220">**Elimine** a medição.</span><span class="sxs-lookup"><span data-stu-id="482ab-220">**Delete** the measure.</span></span>
- <span data-ttu-id="482ab-221">**Ativar** ou **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="482ab-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="482ab-222">As medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="482ab-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="482ab-223">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="482ab-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="482ab-224">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="482ab-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="482ab-225">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="482ab-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="482ab-226">Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="482ab-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="482ab-227">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="482ab-227">Next step</span></span>

<span data-ttu-id="482ab-228">Pode utilizar as medidas existentes para criar [um segmento de cliente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="482ab-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

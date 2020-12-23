---
title: Criar e editar medidas
description: Defina medidas relacionadas com os clientes para analisar e refletir o desempenho de determinadas áreas de negócio.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406648"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="6d0fe-103">Definir e gerir medidas</span><span class="sxs-lookup"><span data-stu-id="6d0fe-103">Define and manage measures</span></span>

<span data-ttu-id="6d0fe-104">**Medidas** representa os indicadores de desempenho-chave (KPIs) que refletem o desempenho e o estado de áreas de negócio específicas.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="6d0fe-105">As informações da audiência proporcionam uma experiência intuitiva para a construção de diferentes tipos de medidas, utilizando um construtor de questões que não exige que codifique ou valide manualmente as suas medidas.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="6d0fe-106">Pode monitorizar as medidas de negócio na **Home** page, ver as medidas para clientes específicos na **Ficha de Cliente** e utilizar medidas para definir segmentos de clientes na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="6d0fe-107">Criar uma medida</span><span class="sxs-lookup"><span data-stu-id="6d0fe-107">Create a measure</span></span>

<span data-ttu-id="6d0fe-108">Esta secção orienta-o ao longo da criação de uma medida de raiz.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="6d0fe-109">Pode criar medidas com dados de várias origens de dados que estão ligadas através da entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="6d0fe-110">Aplicam-se alguns [limites de serviço](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="6d0fe-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="6d0fe-111">Nas informações de audiência, vá a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="6d0fe-112">Selecione **Nova medida**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-112">Select **New measure**.</span></span>

3. <span data-ttu-id="6d0fe-113">Escolha a medida **Tipo**:</span><span class="sxs-lookup"><span data-stu-id="6d0fe-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="6d0fe-114">**Atributo de cliente**: um único campo por cliente que reflete uma classificação, valor ou estado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="6d0fe-115">Os atributos de cliente são criados como atributos numa nova entidade gerada pelo sistema denominada **Medida de Cliente**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="6d0fe-116">**Medida de cliente**: informações sobre o comportamento do cliente discriminadas pelas dimensões selecionadas.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="6d0fe-117">É gerada uma nova entidade para cada medida, potencialmente com vários registos por cliente.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="6d0fe-118">**Medida de negócio**: monitoriza o desempenho e o estado do negócio.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="6d0fe-119">As medidas de negócio podem ter duas saídas diferentes: uma saída numérica que é mostrada na **Home** ou uma nova entidade que está disponível na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="6d0fe-120">Forneça um **Nome** e um **Nome a apresentar** opcional e, depois, selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="6d0fe-121">Na secção **Entidades**, selecione a primeira entidade na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="6d0fe-122">Neste ponto, deve decidir se são necessárias entidades adicionais como parte da definição da medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d0fe-123">![Definição da medida](media/measure-definition.png "Definição da medição")</span><span class="sxs-lookup"><span data-stu-id="6d0fe-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="6d0fe-124">Para adicionar mais entidades, selecione **Adicionar entidade** e selecione as entidades que pretende utilizar para a medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6d0fe-125">Só pode selecionar as entidades que tenham relações com a entidade inicial.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="6d0fe-126">Para mais informações sobre como definir relações, consulte [Relações](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="6d0fe-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="6d0fe-127">Opcionalmente, pode configurar variáveis.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="6d0fe-128">Na secção **Variáveis**, selecione **Nova variável**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="6d0fe-129">As variáveis são cálculos efetuados em cada um dos registos selecionados.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="6d0fe-130">Por exemplo, somar as vendas do ponto de venda (POS) e online para cada um dos registos dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="6d0fe-131">Forneça um **Nome** para a variável.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="6d0fe-132">Na área **Expressão**, escolha um campo com o qual iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="6d0fe-133">Introduza uma expressão na área **Expressão** ao mesmo tempo que escolhe mais campos a incluir no cálculo.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6d0fe-134">Atualmente, apenas as expressões aritméticas são suportadas.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="6d0fe-135">Além disso, o cálculo da variável não é suportado para as entidades de diferentes [caminhos de entidade](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="6d0fe-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="6d0fe-136">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-136">Select **Done**.</span></span>

11. <span data-ttu-id="6d0fe-137">Na secção **Definição da medida**, defina como as entidades escolhidas e as variáveis calculadas são agregadas num novo atributo ou entidade de medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="6d0fe-138">Selecione **Nova dimensão**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-138">Select **New dimension**.</span></span> <span data-ttu-id="6d0fe-139">Pode encarar uma dimensão como uma função *agrupar por*.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="6d0fe-140">A saída de dados do seu atributo ou entidade Medida será agrupada por todas as suas dimensões definidas.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6d0fe-141">![Escolher ciclo agregado](media/measures-businessreport-measure-definition2.png "Escolher ciclo agregado")</span><span class="sxs-lookup"><span data-stu-id="6d0fe-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="6d0fe-142">Selecione ou introduza as seguintes informações como parte da definição da sua dimensão:</span><span class="sxs-lookup"><span data-stu-id="6d0fe-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="6d0fe-143">**Entidade**: se definir uma entidade Medida, deverá incluir pelo menos um atributo.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="6d0fe-144">Se definir um atributo Medida, incluirá apenas um atributo por predefinição.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="6d0fe-145">Esta seleção pretende escolher a entidade que inclui esse atributo.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="6d0fe-146">**Campo**: escolha o atributo específico a incluir no atributo ou entidade Medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="6d0fe-147">**Registo**: escolha se pretende agregar dados numa base diária, mensal ou anual.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="6d0fe-148">Trata-se de uma seleção necessária apenas se tiver selecionado um atributo de Tipo de data.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="6d0fe-149">**Como**: define o nome do novo campo.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="6d0fe-150">**Nome a apresentar**: define o nome a apresentar do campo.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6d0fe-151">A medida de negócio será guardada como uma entidade de número único e será apresentada na **Home** page, a menos que adicione mais dimensões à medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="6d0fe-152">Depois de adicionar mais dimensões, a medida *não* será mostrada na **Home** page.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="6d0fe-153">Opcionalmente, adicione funções de agregação.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="6d0fe-154">Qualquer agregação que crie resulta num novo valor no atributo ou entidade Medidas.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="6d0fe-155">As funções de agregação suportadas são: **Mín**, **Máx**, **Média**, **Mediana**, **Soma**, **Contagem Exclusiva**, **Primeiro** (assume o primeiro registo de um valor de dimensão) e **Último** (assume o último registo adicionado a um valor de dimensão).</span><span class="sxs-lookup"><span data-stu-id="6d0fe-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="6d0fe-156">Selecione **Guardar** para aplicar as alterações à medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="6d0fe-157">Gerir as medidas</span><span class="sxs-lookup"><span data-stu-id="6d0fe-157">Manage your measures</span></span>

<span data-ttu-id="6d0fe-158">Depois de criar pelo menos uma medida, verá uma lista de medidas na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="6d0fe-159">Encontrará informações sobre o tipo de medida, o criador, a data e hora de criação, a data e hora da última edição, o estado (se a medida está ativa, inativo ou com falhas), e a data e hora da última atualização.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="6d0fe-160">Quando selecionar uma medida a partir da lista, poderá ter uma pré-visualização da respetiva saída.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="6d0fe-161">Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6d0fe-162">![Ações para gerir medidas únicas](media/measure-actions.png "Ações para gerir medidas únicas")</span><span class="sxs-lookup"><span data-stu-id="6d0fe-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="6d0fe-163">Em alternativa, selecione uma medida a partir da lista e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6d0fe-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="6d0fe-164">Selecione o nome da medida para ver os respetivos detalhes.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="6d0fe-165">**Edite** a configuração da medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="6d0fe-166">**Mude o nome** da medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-166">**Rename** the measure.</span></span>
- <span data-ttu-id="6d0fe-167">**Elimine** a medição.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-167">**Delete** the measure.</span></span>
- <span data-ttu-id="6d0fe-168">Selecione as reticências (...) e, em seguida, **Atualizar** para iniciar o processo de atualização para a medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="6d0fe-169">Selecione as reticências (...) e, em seguida, **Transferir** para obter um ficheiro CSV da medida.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="6d0fe-170">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6d0fe-171">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6d0fe-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6d0fe-172">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6d0fe-173">Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="6d0fe-174">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="6d0fe-174">Next step</span></span>

<span data-ttu-id="6d0fe-175">Pode utilizar as medidas existentes para criar o seu primeiro segmento de cliente na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="6d0fe-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="6d0fe-176">Para mais informações, consulte [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6d0fe-176">For more information, see [Segments](segments.md).</span></span>

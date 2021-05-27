---
title: Criar e gerir segmentos
description: Crie segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064951"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="9bc96-103">Criar e gerir segmentos</span><span class="sxs-lookup"><span data-stu-id="9bc96-103">Create and manage segments</span></span>

<span data-ttu-id="9bc96-104">Defina filtros complexos em torno da entidade de cliente unificado e as suas entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9bc96-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="9bc96-105">Cada segmento, após o processamento, cria um conjunto de registos de clientes que pode exportar e tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="9bc96-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="9bc96-106">Os segmentos são geridos na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="9bc96-107">O exemplo seguinte ilustra a capacidade de segmentação.</span><span class="sxs-lookup"><span data-stu-id="9bc96-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="9bc96-108">Definimos um segmento para os clientes que encomendaram pelo menos 500 $ de bens nos últimos 90 dias *e* que estavam envolvidos numa chamada de suporte ao cliente que foi escalada.</span><span class="sxs-lookup"><span data-stu-id="9bc96-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de ecrã da IU do construtor de segmentos com dois grupos que especificam um segmento de cliente.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="9bc96-110">Criar um novo segmento</span><span class="sxs-lookup"><span data-stu-id="9bc96-110">Create a new segment</span></span>

<span data-ttu-id="9bc96-111">Existem várias formas de criar um novo segmento.</span><span class="sxs-lookup"><span data-stu-id="9bc96-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="9bc96-112">Esta secção descreve como criar um *segmento em branco* a partir do zero.</span><span class="sxs-lookup"><span data-stu-id="9bc96-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="9bc96-113">Também pode criar um *segmento rápido* baseado em entidades existentes ou fazer uso de modelos de aprendizagem automática para obter *segmentos sugeridos*.</span><span class="sxs-lookup"><span data-stu-id="9bc96-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="9bc96-114">Mais informações: [Descrição geral de segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9bc96-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="9bc96-115">Ao criar um segmento, pode guardar um rascunho.</span><span class="sxs-lookup"><span data-stu-id="9bc96-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="9bc96-116">Será guardado como um segmento inativo e não pode ser ativado se terminado com uma configuração válida.</span><span class="sxs-lookup"><span data-stu-id="9bc96-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="9bc96-117">Ir para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="9bc96-118">Selecione **Novo** > **Segmento em branco**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="9bc96-119">No painel **Novo segmento**, escolha um tipo de segmento:</span><span class="sxs-lookup"><span data-stu-id="9bc96-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="9bc96-120">**Segmentos dinâmicos** [atualizam-se](segments.md#refresh-segments) numa agenda recorrente.</span><span class="sxs-lookup"><span data-stu-id="9bc96-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="9bc96-121">**Segmentos estáticos** são executados uma vez quando os cria.</span><span class="sxs-lookup"><span data-stu-id="9bc96-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="9bc96-122">Forneça um **Nome de entidade de saída** para o segmento.</span><span class="sxs-lookup"><span data-stu-id="9bc96-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="9bc96-123">Opcionalmente, forneça um nome a apresentar e uma descrição que ajude a identificar o segmento.</span><span class="sxs-lookup"><span data-stu-id="9bc96-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="9bc96-124">Selecione **Seguinte** para ir para a página **Construtor de segmentos** onde define um grupo.</span><span class="sxs-lookup"><span data-stu-id="9bc96-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="9bc96-125">Um grupo é um conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="9bc96-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="9bc96-126">Escolha a entidade que inclui o atributo pelo qual pretende segmentar.</span><span class="sxs-lookup"><span data-stu-id="9bc96-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="9bc96-127">Escolha o atributo pelo qual pretende segmentar.</span><span class="sxs-lookup"><span data-stu-id="9bc96-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="9bc96-128">Este atributo pode ter um de quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.</span><span class="sxs-lookup"><span data-stu-id="9bc96-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="9bc96-129">Escolha um operador e um valor para o atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="9bc96-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9bc96-130">![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo do cliente")</span><span class="sxs-lookup"><span data-stu-id="9bc96-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="9bc96-131">Número</span><span class="sxs-lookup"><span data-stu-id="9bc96-131">Number</span></span> |<span data-ttu-id="9bc96-132">Definição</span><span class="sxs-lookup"><span data-stu-id="9bc96-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="9bc96-133">1</span><span class="sxs-lookup"><span data-stu-id="9bc96-133">1</span></span>     |<span data-ttu-id="9bc96-134">Entity</span><span class="sxs-lookup"><span data-stu-id="9bc96-134">Entity</span></span>          |
   |<span data-ttu-id="9bc96-135">2</span><span class="sxs-lookup"><span data-stu-id="9bc96-135">2</span></span>     |<span data-ttu-id="9bc96-136">Atributo</span><span class="sxs-lookup"><span data-stu-id="9bc96-136">Attribute</span></span>          |
   |<span data-ttu-id="9bc96-137">3</span><span class="sxs-lookup"><span data-stu-id="9bc96-137">3</span></span>    |<span data-ttu-id="9bc96-138">Operador</span><span class="sxs-lookup"><span data-stu-id="9bc96-138">Operator</span></span>         |
   |<span data-ttu-id="9bc96-139">4</span><span class="sxs-lookup"><span data-stu-id="9bc96-139">4</span></span>    |<span data-ttu-id="9bc96-140">valor</span><span class="sxs-lookup"><span data-stu-id="9bc96-140">Value</span></span>         |

   1. <span data-ttu-id="9bc96-141">Para adicionar mais condições a um grupo, poderá utilizar dois operadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="9bc96-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="9bc96-142">Operador **AND**: ambas as condições têm de ser satisfeitas como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="9bc96-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="9bc96-143">Esta opção é mais útil quando define condições em diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="9bc96-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="9bc96-144">Operador **OR**: qualquer uma das condições tem de ser satisfeita como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="9bc96-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="9bc96-145">Esta opção é mais útil quando define múltiplas condições para a mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="9bc96-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="9bc96-146">![Operador OR onde qualquer condição tem de ser satisfeita](media/segmentation-either-condition.png "Operador OR onde qualquer condição tem de ser satisfeita")</span><span class="sxs-lookup"><span data-stu-id="9bc96-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="9bc96-147">Atualmente, é possível aninhar um operador **OR** num operador **AND**, mas não o contrário.</span><span class="sxs-lookup"><span data-stu-id="9bc96-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="9bc96-148">Cada grupo corresponde a um conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="9bc96-148">Each group matches set of customers.</span></span> <span data-ttu-id="9bc96-149">Pode combinar grupos para incluir os clientes necessários para o seu caso de negócio.</span><span class="sxs-lookup"><span data-stu-id="9bc96-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="9bc96-150">Selecione **Adicionar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="9bc96-151">![Grupo de clientes - adicionar grupo](media/customer-group-add-group.png "Grupo de clientes - adicionar grupo")</span><span class="sxs-lookup"><span data-stu-id="9bc96-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="9bc96-152">Selecione um dos operadores definidos: **União**, **Intersetar** ou **Exceto**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9bc96-153">![Grupo de clientes - adicionar união](media/customer-group-union.png "Grupo de clientes - adicionar união")</span><span class="sxs-lookup"><span data-stu-id="9bc96-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="9bc96-154">**União** une os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="9bc96-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="9bc96-155">**Interseção** sobrepõe os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="9bc96-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="9bc96-156">Apenas os dados que *são comuns* a ambos os grupos são mantidos no grupo unificado.</span><span class="sxs-lookup"><span data-stu-id="9bc96-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="9bc96-157">**Exceto** combina os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="9bc96-157">**Except** combines the two groups.</span></span> <span data-ttu-id="9bc96-158">Apenas os dados do grupo A que *não são comuns* aos dados do grupo B são mantidos.</span><span class="sxs-lookup"><span data-stu-id="9bc96-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="9bc96-159">Se a entidade estiver ligada à entidade de cliente unificada através das [relações](relationships.md), terá de definir o caminho da relação para criar um segmento válido.</span><span class="sxs-lookup"><span data-stu-id="9bc96-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="9bc96-160">Adicione as entidades a partir do caminho da relação até poder selecionar a entidade **Customer : CustomerInsights** a partir da lista pendente.</span><span class="sxs-lookup"><span data-stu-id="9bc96-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="9bc96-161">Em seguida, escolha **Todos os registos** para cada passo.</span><span class="sxs-lookup"><span data-stu-id="9bc96-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9bc96-162">![Caminho da relação durante a criação do segmento](media/segments-multiple-relationships.png "Caminho da relação durante a criação do segmento")</span><span class="sxs-lookup"><span data-stu-id="9bc96-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="9bc96-163">Por predefinição, os segmentos geram uma entidade de saída que contém todos os atributos dos perfis de cliente que correspondem aos filtros definidos.</span><span class="sxs-lookup"><span data-stu-id="9bc96-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="9bc96-164">Se um segmento se basear noutras entidades diferentes da entidade *Cliente*, pode adicionar mais atributos destas entidades à entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="9bc96-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="9bc96-165">Selecione **Atributos do projeto** para escolher os atributos que serão acrescentados à entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="9bc96-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="9bc96-166">Exemplo: Um segmento baseia-se numa entidade que contém os dados de atividade do cliente que estão relacionados com a entidade *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="9bc96-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="9bc96-167">O segmento procura todos os clientes que ligaram para o suporte técnico nos últimos 60 dias.</span><span class="sxs-lookup"><span data-stu-id="9bc96-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="9bc96-168">Pode optar por acrescentar a duração da chamada e o número de chamadas a todos os registos de clientes correspondentes na entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="9bc96-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="9bc96-169">Esta informação pode ser útil para enviar um e-mail com ligações úteis para artigos de ajuda online e FAQs aos clientes que ligaram com frequência.</span><span class="sxs-lookup"><span data-stu-id="9bc96-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="9bc96-170">Os atributos projetados só funcionam para entidades que têm uma relação de um-para-muitos com a entidade de cliente.</span><span class="sxs-lookup"><span data-stu-id="9bc96-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="9bc96-171">Por exemplo, um cliente pode ter várias subscrições.</span><span class="sxs-lookup"><span data-stu-id="9bc96-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="9bc96-172">Só é possível projetar atributos de uma entidade que é utilizada em todos os grupos de consultas de segmento que está a criar.</span><span class="sxs-lookup"><span data-stu-id="9bc96-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="9bc96-173">Os atributos projetados são contabilizados quando utiliza operadores definidos.</span><span class="sxs-lookup"><span data-stu-id="9bc96-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="9bc96-174">Selecione **Guardar** para guardar o segmento.</span><span class="sxs-lookup"><span data-stu-id="9bc96-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="9bc96-175">O seu segmento será guardado e processado se todos os requisitos forem validados.</span><span class="sxs-lookup"><span data-stu-id="9bc96-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="9bc96-176">Caso contrário, será guardado como rascunho.</span><span class="sxs-lookup"><span data-stu-id="9bc96-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="9bc96-177">Selecione **Regressar a segmentos** para regressar à página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="9bc96-178">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="9bc96-178">Quick segments</span></span>

<span data-ttu-id="9bc96-179">Segmentos rápidos permitem criar segmentos simples com um único operador rapidamente para informações mais rápidas.</span><span class="sxs-lookup"><span data-stu-id="9bc96-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="9bc96-180">Na página **Segmentos**, selecione **Novo** > **Criar de**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="9bc96-181">Selecione a opção **Perfis** para criar um segmento baseado na entidade de *cliente unificado*.</span><span class="sxs-lookup"><span data-stu-id="9bc96-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="9bc96-182">Selecione a opção **Medidas** para criar um segmento em torno de medidas que criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9bc96-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="9bc96-183">Selecione a opção **Inteligência** para criar um segmento à volta de uma das entidades de saída geradas com as capacidades **Predições** ou **Modelos Personalizados**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="9bc96-184">Na caixa de diálogo **Novo segmento rápido**, selecione um atributo na lista pendente **Campo**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="9bc96-185">O sistema fornecerá algumas informações adicionais que o ajudam a criar melhores segmentos dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="9bc96-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="9bc96-186">Para campos categóricos, mostraremos as 10 melhores contagens de clientes.</span><span class="sxs-lookup"><span data-stu-id="9bc96-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="9bc96-187">Escolha um **Valor** e selecione **Rever**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="9bc96-188">Para um atributo numérico, o sistema mostrará que valor do atributo se situa no percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="9bc96-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="9bc96-189">Escolha um **Operador** e um **Valor** e, em seguida, selecione **Rever**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="9bc96-190">O sistema fornecerá um **Tamanho do segmento estimado**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="9bc96-191">Poderá selecionar se pretende gerar ou não o segmento que definiu ou, primeiro, revisitá-lo para obter um tamanho de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="9bc96-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9bc96-192">![Nome e estimativa para um segmento rápido](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="9bc96-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="9bc96-193">Indique um **Nome** para o seu segmento.</span><span class="sxs-lookup"><span data-stu-id="9bc96-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="9bc96-194">Opcionalmente, indique um **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="9bc96-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="9bc96-195">Selecione **Guardar** para criar o segmento.</span><span class="sxs-lookup"><span data-stu-id="9bc96-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="9bc96-196">Depois de concluído o processamento do segmento, poderá vê-lo como qualquer outro segmento que tenha criado.</span><span class="sxs-lookup"><span data-stu-id="9bc96-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9bc96-197">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="9bc96-197">Next steps</span></span>

<span data-ttu-id="9bc96-198">[Exportar um segmento](export-destinations.md) e explore a [Ficha de Cliente](customer-card-add-in.md) e [Conectores](export-power-bi.md) para obter informações a nível do cliente.</span><span class="sxs-lookup"><span data-stu-id="9bc96-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

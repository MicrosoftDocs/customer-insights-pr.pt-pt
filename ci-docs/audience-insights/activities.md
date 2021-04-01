---
title: Atividades do cliente
description: Defina as atividades do cliente e veja-as na linha cronológica do cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596743"
---
# <a name="customer-activities"></a><span data-ttu-id="427d9-103">Atividades do cliente</span><span class="sxs-lookup"><span data-stu-id="427d9-103">Customer activities</span></span>

<span data-ttu-id="427d9-104">Combine as atividades do cliente de [várias origens de dados](data-sources.md) no Dynamics 365 Customer Insights para criar uma linha cronológica do cliente que lista as atividades por ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="427d9-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="427d9-105">Pode incluir a linha cronológica nas aplicações do Customer Engagement no Dynamics 365 através do [suplemente do Cartão de Cliente](customer-card-add-in.md) ou num dashboard do Power BI.</span><span class="sxs-lookup"><span data-stu-id="427d9-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="427d9-106">Definir uma atividade</span><span class="sxs-lookup"><span data-stu-id="427d9-106">Define an activity</span></span>

<span data-ttu-id="427d9-107">As suas origens de dados incluem entidades com dados transacionais e de atividade a partir de várias origens de dados.</span><span class="sxs-lookup"><span data-stu-id="427d9-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="427d9-108">Identifique estas entidades e selecione as atividades que pretende ver na linha cronológica do cliente.</span><span class="sxs-lookup"><span data-stu-id="427d9-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="427d9-109">Escolha a entidade que inclui as atividades ou atividades de destino.</span><span class="sxs-lookup"><span data-stu-id="427d9-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="427d9-110">Em informações de audiência, aceda a **Dados** > **Atividades**.</span><span class="sxs-lookup"><span data-stu-id="427d9-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="427d9-111">Selecione **Adicionar atividade**.</span><span class="sxs-lookup"><span data-stu-id="427d9-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="427d9-112">Uma entidade tem de ter, pelo menos, um atributo do tipo **Data** a ser incluído na linha cronológica do cliente e não é possível adicionar entidades sem campos de **Data**.</span><span class="sxs-lookup"><span data-stu-id="427d9-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="427d9-113">O controlo **Adicionar atividade** está desativado se não for encontrada nenhuma entidade.</span><span class="sxs-lookup"><span data-stu-id="427d9-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="427d9-114">No painel **Adicionar atividade**, defina os valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="427d9-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="427d9-115">**Entidade**: Selecione uma entidade que inclua dados transacionais ou de atividade.</span><span class="sxs-lookup"><span data-stu-id="427d9-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="427d9-116">**Chave primária**: Selecione o campo que identifica exclusivamente um registo.</span><span class="sxs-lookup"><span data-stu-id="427d9-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="427d9-117">Não deve conter valores duplicados, valores vazios ou valores em falta.</span><span class="sxs-lookup"><span data-stu-id="427d9-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="427d9-118">**Carimbo de data/hora**: Selecione o campo que representa a hora de início da atividade.</span><span class="sxs-lookup"><span data-stu-id="427d9-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="427d9-119">**Evento**: Selecione o campo que é o evento para a atividade.</span><span class="sxs-lookup"><span data-stu-id="427d9-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="427d9-120">**Endereço web**: Selecione o campo que representa um URL fornecendo informações adicionais sobre esta atividade.</span><span class="sxs-lookup"><span data-stu-id="427d9-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="427d9-121">Por exemplo, o sistema transacional que fornece esta atividade.</span><span class="sxs-lookup"><span data-stu-id="427d9-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="427d9-122">Este URL pode ser qualquer campo da origem de dados, ou pode ser construído como um novo campo usando uma transformação Power Query.</span><span class="sxs-lookup"><span data-stu-id="427d9-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="427d9-123">Estes dados de URL serão armazenados na entidade de Atividade Unificada, que pode ser consumida a jusante usando APIs.</span><span class="sxs-lookup"><span data-stu-id="427d9-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="427d9-124">**Detalhes**: Opcionalmente, selecione o campo que é adicionado para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="427d9-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="427d9-125">**Ícone**: Opcionalmente, selecione o ícone que representa esta atividade.</span><span class="sxs-lookup"><span data-stu-id="427d9-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="427d9-126">**Tipo de Atividade**: Defina a referência do tipo de atividade ao Common Data Model que melhor descreve a definição semântica da atividade.</span><span class="sxs-lookup"><span data-stu-id="427d9-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="427d9-127">Na secção **Configurar relação**, configure os detalhes para ligar os seus dados de atividade ao seu cliente correspondente.</span><span class="sxs-lookup"><span data-stu-id="427d9-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="427d9-128">**Campo de entidade de atividade**: selecione o campo na sua entidade de atividade que será utilizado para estabelecer uma relação com outra entidade.</span><span class="sxs-lookup"><span data-stu-id="427d9-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="427d9-129">**Entidade Cliente** : selecione a entidade Cliente de origem correspondente com a qual a sua entidade Atividade terá uma relação.</span><span class="sxs-lookup"><span data-stu-id="427d9-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="427d9-130">Só poderá ter relação com as entidades Cliente de origem utilizadas no processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="427d9-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="427d9-131">**Campo Entidade cliente**: este campo mostra a chave primária da entidade Cliente de origem, conforme selecionada no processo de correspondência.</span><span class="sxs-lookup"><span data-stu-id="427d9-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="427d9-132">Este campo de chave primária na entidade Cliente de origem é utilizado para estabelecer uma relação com a entidade Atividade.</span><span class="sxs-lookup"><span data-stu-id="427d9-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="427d9-133">**Nome** : se já existir uma relação entre esta entidade Atividade e a entidade Cliente de origem selecionada, o nome da relação estará em modo só de leitura.</span><span class="sxs-lookup"><span data-stu-id="427d9-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="427d9-134">Se esta relação não existir, será criada uma nova relação com o nome aqui fornecido.</span><span class="sxs-lookup"><span data-stu-id="427d9-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="427d9-135">![Definir A relação entre entidades](media/activities-entities-define.png "Definir a relação entre entidades")</span><span class="sxs-lookup"><span data-stu-id="427d9-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="427d9-136">Selecione **Guardar** para aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="427d9-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="427d9-137">Na página **Atividades**, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="427d9-138">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="427d9-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="427d9-139">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="427d9-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="427d9-140">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="427d9-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="427d9-141">Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="427d9-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="427d9-142">Editar uma atividade</span><span class="sxs-lookup"><span data-stu-id="427d9-142">Edit an activity</span></span>

1. <span data-ttu-id="427d9-143">Em informações de audiência, aceda a **Dados** > **Atividades**.</span><span class="sxs-lookup"><span data-stu-id="427d9-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="427d9-144">Selecione a entidade Atividade que pretende editar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="427d9-145">Em alternativa, poderá passar com o cursor do rato sobre a linha e selecionar o ícone **Editar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="427d9-146">Clique no ícone **Editar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="427d9-147">No painel **Editar atividade**, atualize os valores e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="427d9-148">Na página **Atividades**, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="427d9-149">Eliminar uma atividade</span><span class="sxs-lookup"><span data-stu-id="427d9-149">Delete an activity</span></span>

1. <span data-ttu-id="427d9-150">Em informações de audiência, aceda a **Dados** > **Atividades**.</span><span class="sxs-lookup"><span data-stu-id="427d9-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="427d9-151">Selecione a entidade Atividade que pretende remover e selecione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="427d9-152">Em alternativa, poderá passar com o cursor do rato sobre a linha e selecionar o ícone **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="427d9-153">Além disso, poderá selecionar várias entidades Atividade a eliminar em simultâneo.</span><span class="sxs-lookup"><span data-stu-id="427d9-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="427d9-154">![Editar ou eliminar a relação entre entidades](media/activities-entities-edit-delete.png "Editar ou eliminar a relação entre entidades")</span><span class="sxs-lookup"><span data-stu-id="427d9-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="427d9-155">Selecione o ícone **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="427d9-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="427d9-156">Confirme a eliminação.</span><span class="sxs-lookup"><span data-stu-id="427d9-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
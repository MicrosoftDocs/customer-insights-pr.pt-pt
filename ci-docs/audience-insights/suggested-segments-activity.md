---
title: Segmentos sugeridos baseados em atividades.
description: Deixe que a aprendizagem automática o ajude a encontrar segmentos novos e interessantes baseados na atividade do cliente.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034103"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="eb25c-103">Segmentos sugeridos baseados em dados de atividades (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="eb25c-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="eb25c-104">Descubra segmentos interessantes dos seus clientes com base em dados de atividade do cliente que são ingeridos para o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eb25c-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="eb25c-105">Exemplos de dados de atividade são transações, duração de chamadas de suporte, compras ou devoluções.</span><span class="sxs-lookup"><span data-stu-id="eb25c-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="eb25c-106">Para sugerir segmentos, os dados da atividade são analisados por recência, frequência e valor monetário (ou duração).</span><span class="sxs-lookup"><span data-stu-id="eb25c-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="eb25c-107">Em alternativa, pode gerar [segmentos sugeridos para melhorar uma medida ou entender melhor o que influencia um atributo](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="eb25c-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Separador de segmentos sugeridos a mostrar sugestões de segmentos para segmentos baseados em atividades e em atributos.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="eb25c-109">Categorizar clientes por atividade</span><span class="sxs-lookup"><span data-stu-id="eb25c-109">Categorize customers by activity</span></span>

<span data-ttu-id="eb25c-110">Com os [dados de atividade](activities.md) disponíveis no Customer Insights, podemos gerar sugestões que representem grupos de clientes:</span><span class="sxs-lookup"><span data-stu-id="eb25c-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="eb25c-111">maioria dos clientes ativos</span><span class="sxs-lookup"><span data-stu-id="eb25c-111">most active customers</span></span> 
- <span data-ttu-id="eb25c-112">clientes que fizeram mais compras</span><span class="sxs-lookup"><span data-stu-id="eb25c-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="eb25c-113">clientes que geraram mais receitas</span><span class="sxs-lookup"><span data-stu-id="eb25c-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="eb25c-114">clientes que não têm estado ativos ultimamente</span><span class="sxs-lookup"><span data-stu-id="eb25c-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="eb25c-115">clientes que interagem frequentemente com o seu negócio</span><span class="sxs-lookup"><span data-stu-id="eb25c-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="eb25c-116">Se tiver um negócio de retalho, poderá descobrir que clientes geram mais receitas e recompensá-los com um cupão.</span><span class="sxs-lookup"><span data-stu-id="eb25c-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="eb25c-117">Ou pode identificar clientes ocasionais e oferecer-lhes para se juntarem a um programa de recompensas para que visitem o seu negócio com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="eb25c-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="eb25c-118">Se está no ramo dos cuidados de saúde, fornece cuidados de saúde públicos e o seu objetivo é minimizar as despesas para cada paciente.</span><span class="sxs-lookup"><span data-stu-id="eb25c-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="eb25c-119">Uma forma de o fazer poderia ser reduzir as visitas recorrentes, proporcionando o melhor cuidado possível no menor número possível de visitas.</span><span class="sxs-lookup"><span data-stu-id="eb25c-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="eb25c-120">Neste caso, o seu objetivo é manter a frequência de visitas baixa e minimizar os custos recorrentes para os pacientes.</span><span class="sxs-lookup"><span data-stu-id="eb25c-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="eb25c-121">Ou pode identificar segmentos de pacientes que têm consultas frequentes e custos recorrentes elevados e analisar estes casos para melhorar o tratamento do indivíduo.</span><span class="sxs-lookup"><span data-stu-id="eb25c-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="eb25c-122">Dados necessários</span><span class="sxs-lookup"><span data-stu-id="eb25c-122">Required data</span></span>

<span data-ttu-id="eb25c-123">As sugestões são geradas com base nos dados de entrada selecionados.</span><span class="sxs-lookup"><span data-stu-id="eb25c-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="eb25c-124">Perfis do cliente: todos os clientes ou membros de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="eb25c-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="eb25c-125">Período de tempo: Último mês, último ano ou em qualquer período de tempo personalizado.</span><span class="sxs-lookup"><span data-stu-id="eb25c-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="eb25c-126">Tipo de atividade: compras, transações de retalho, transações online, casos de suporte ao cliente, subscrições, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="eb25c-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="eb25c-127">Entidade no Customer Insights que contém os dados da atividade: a entidade UnifiedActivity ou a entidade para uma atividade específica.</span><span class="sxs-lookup"><span data-stu-id="eb25c-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="eb25c-128">Dimensões a incluir: recência, frequência ou dimensão monetária, dependendo dos requisitos do seu negócio.</span><span class="sxs-lookup"><span data-stu-id="eb25c-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="eb25c-129">Gerar segmentos sugeridos</span><span class="sxs-lookup"><span data-stu-id="eb25c-129">Generate suggested segments</span></span>

1. <span data-ttu-id="eb25c-130">Aceda a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="eb25c-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="eb25c-131">Selecione o separador **Sugestões (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="eb25c-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="eb25c-132">Selecione **Encontrar novas sugestões** e escolha **Ver ou antecipar o comportamento do cliente**.</span><span class="sxs-lookup"><span data-stu-id="eb25c-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="eb25c-133">Selecione **Começar** para executar a experiência guiada.</span><span class="sxs-lookup"><span data-stu-id="eb25c-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeiro passo do assistente de configuração para um segmento sugerido baseado em atividades.":::

1. <span data-ttu-id="eb25c-135">Forneça os dados de entrada necessários e selecione **Seguinte** para prosseguir.</span><span class="sxs-lookup"><span data-stu-id="eb25c-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="eb25c-136">Escolher clientes: inclua todos os clientes ou um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="eb25c-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="eb25c-137">Escolher atividade: selecione o tipo de atividade e as entidades que descrevem a atividade.</span><span class="sxs-lookup"><span data-stu-id="eb25c-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="eb25c-138">Preferências: defina o período de tempo a considerar, os fatores para sugestões e mapeie os atributos.</span><span class="sxs-lookup"><span data-stu-id="eb25c-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="eb25c-139">Reveja a sua entrada e selecione **Executar** para executar o modelo e gerar sugestões.</span><span class="sxs-lookup"><span data-stu-id="eb25c-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="eb25c-140">Dependendo do número de perfis de clientes e atividades selecionadas, pode levar alguns minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="eb25c-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="eb25c-141">Depois de gerar as sugestões, pode filtrá-las pela dimensão ou valor em que está mais interessado.</span><span class="sxs-lookup"><span data-stu-id="eb25c-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="eb25c-142">Ver detalhes de um segmento sugerido</span><span class="sxs-lookup"><span data-stu-id="eb25c-142">View details of a suggested segment</span></span>

<span data-ttu-id="eb25c-143">Assim que as sugestões forem geradas, irá encontrá-las listadas em **Sugestões** > **Segmentos (pré-visualização)** na secção **Sugestões baseadas em atividades**.</span><span class="sxs-lookup"><span data-stu-id="eb25c-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Painel lateral expandido a mostrar dados detalhados de um segmento sugerido.":::

<span data-ttu-id="eb25c-145">Selecione **Ver sugestão** de um segmento sugerido para ver os detalhes desse segmento.</span><span class="sxs-lookup"><span data-stu-id="eb25c-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="eb25c-146">O painel lateral fornece detalhes como a extensão de cada dimensão em comparação com o grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="eb25c-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="eb25c-147">Realça também o número de potenciais membros no segmento e a correspondente percentagem do total de clientes.</span><span class="sxs-lookup"><span data-stu-id="eb25c-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="eb25c-148">Se quiser manter a sugestão como um segmento, selecione **Criar segmento**.</span><span class="sxs-lookup"><span data-stu-id="eb25c-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="eb25c-149">Guardar uma sugestão como um segmento</span><span class="sxs-lookup"><span data-stu-id="eb25c-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="eb25c-150">Vá a **Segmentos** > **Sugestões (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="eb25c-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="eb25c-151">Selecione o segmento que pretende guardar.</span><span class="sxs-lookup"><span data-stu-id="eb25c-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="eb25c-152">No painel lateral, selecione **Criar segmento**.</span><span class="sxs-lookup"><span data-stu-id="eb25c-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="eb25c-153">Depois de guardar o segmento, aparecerá na lista de segmentos no separador **Todos os segmentos**. Pode agora ser [atualizado ou eliminado como qualquer outro segmento](segments.md).</span><span class="sxs-lookup"><span data-stu-id="eb25c-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="eb25c-154">Não pode editar os detalhes do segmento.</span><span class="sxs-lookup"><span data-stu-id="eb25c-154">You can't edit the segment details.</span></span> <span data-ttu-id="eb25c-155">No entanto, pode alterar os critérios de entrada para as sugestões e gerar diferentes sugestões.</span><span class="sxs-lookup"><span data-stu-id="eb25c-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="eb25c-156">Atualizar ou editar um conjunto de sugestões</span><span class="sxs-lookup"><span data-stu-id="eb25c-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="eb25c-157">Vá a **Segmentos** > **Sugestões (pré-visualização)** e procure o segmento na secção de **Sugestões baseadas em atividades**.</span><span class="sxs-lookup"><span data-stu-id="eb25c-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="eb25c-158">Selecione **Atualizar sugestões** para atualizar as sugestões mantendo os atributos configurados.</span><span class="sxs-lookup"><span data-stu-id="eb25c-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="eb25c-159">Ou selecione **Editar sugestões** para modificar os atributos configurados.</span><span class="sxs-lookup"><span data-stu-id="eb25c-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="eb25c-160">O sistema irá voltar a executar o processo, gerar sugestões de segmentos com base nos dados mais recentes e substituir as sugestões atuais.</span><span class="sxs-lookup"><span data-stu-id="eb25c-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Informações de segmentos para segmentos existentes
description: Obter informações sobre segmentos existentes para ver diferenças e pontos em comum.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270034"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="495d6-103">Informações de segmentos (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="495d6-103">Segment insights (preview)</span></span>

<span data-ttu-id="495d6-104">Descubra informações adicionais e informações sobre os segmentos existentes.</span><span class="sxs-lookup"><span data-stu-id="495d6-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="495d6-105">Descubra o que diferencia dois segmentos ou o que têm em comum.</span><span class="sxs-lookup"><span data-stu-id="495d6-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="495d6-106">Sobreposição de segmentos</span><span class="sxs-lookup"><span data-stu-id="495d6-106">Segment overlap</span></span>

<span data-ttu-id="495d6-107">A análise da sobreposição de segmentos mostra quantos e quais os clientes comuns a dois ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="495d6-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="495d6-108">Por exemplo, como um segmento de clientes frequentes se sobrepõe a um segmento que contém clientes que estão satisfeitos com o seu serviço ou produto.</span><span class="sxs-lookup"><span data-stu-id="495d6-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="495d6-109">Também pode analisar como a sobreposição muda para atributos específicos.</span><span class="sxs-lookup"><span data-stu-id="495d6-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="495d6-110">Executar uma análise de sobreposição</span><span class="sxs-lookup"><span data-stu-id="495d6-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="495d6-111">Vá a **Segmentos** e selecione o separador **Informações (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="495d6-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="495d6-112">Selecione **Novo** e escolha a opção **Sobreposição** no painel **Escolher Tipo de Informações**.</span><span class="sxs-lookup"><span data-stu-id="495d6-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="495d6-113">Escolha os segmentos de interesse e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="495d6-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="495d6-114">Opcionalmente, escolha um ou mais campos de interesse para analisar sobreposições para cada valor de campo possível e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="495d6-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="495d6-115">Forneça um nome para a sua análise de sobreposição, um nome a apresentar opcional e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="495d6-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="495d6-116">Selecione **Guardar** para iniciar a análise.</span><span class="sxs-lookup"><span data-stu-id="495d6-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="495d6-117">A análise de sobreposição está pronta quando o estado muda de Em Atualização para Bem Sucedida.</span><span class="sxs-lookup"><span data-stu-id="495d6-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="495d6-118">Ver e otimizar uma análise de sobreposição</span><span class="sxs-lookup"><span data-stu-id="495d6-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="495d6-119">Após completar a análise, encontre detalhes sobre esta informação em **Segmentos** > **Informações (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="495d6-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalhes de informações de sobreposição de segmentos":::

<span data-ttu-id="495d6-121">Selecione uma informação para ver os resultados da análise:</span><span class="sxs-lookup"><span data-stu-id="495d6-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="495d6-122">O número de membros que se sobrepõem aos segmentos selecionados para análise.</span><span class="sxs-lookup"><span data-stu-id="495d6-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="495d6-123">O número de membros incluídos num dos segmentos, mas não nos restantes segmentos.</span><span class="sxs-lookup"><span data-stu-id="495d6-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="495d6-124">Se selecionar campos enquanto configura a análise de sobreposição, irá encontrá-los nos separadores correspondentes.</span><span class="sxs-lookup"><span data-stu-id="495d6-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="495d6-125">Pode utilizar o filtro para selecionar qualquer nível de interesse do atributo e a tabela na parte inferior mostrará os dados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="495d6-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="495d6-126">Diferenciadores de segmentos</span><span class="sxs-lookup"><span data-stu-id="495d6-126">Segment differentiators</span></span>

<span data-ttu-id="495d6-127">Os diferenciadores de segmento ajudam-no a descobrir o que diferencia um segmento do resto dos seus clientes ou de outro segmento.</span><span class="sxs-lookup"><span data-stu-id="495d6-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="495d6-128">Basta selecionar um segmento e o sistema identificará atributos de perfil e medidas que distinguem o segmento selecionado.</span><span class="sxs-lookup"><span data-stu-id="495d6-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="495d6-129">Executar uma análise diferenciadora</span><span class="sxs-lookup"><span data-stu-id="495d6-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="495d6-130">Vá a **Segmentos** e selecione o separador **Informações (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="495d6-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="495d6-131">Selecione **Novo** e escolha a opção **Sobreposição** no painel **Escolher Tipo de Informações**.</span><span class="sxs-lookup"><span data-stu-id="495d6-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="495d6-132">Escolha o segmento que pretende analisar como **Segmento primário** e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="495d6-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="495d6-133">Escolha **Todos os clientes** ou um **Segmento secundário** para comparar o seu segmento primário com e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="495d6-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="495d6-134">Opcionalmente, escolha um ou mais campos de interesse para focar a análise em atributos específicos e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="495d6-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="495d6-135">Forneça um nome para a sua análise de sobreposição, um nome a apresentar opcional e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="495d6-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="495d6-136">Selecione **Guardar** para iniciar a análise.</span><span class="sxs-lookup"><span data-stu-id="495d6-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="495d6-137">A análise de sobreposição está pronta quando o estado muda de Em Atualização para Bem Sucedida.</span><span class="sxs-lookup"><span data-stu-id="495d6-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="495d6-138">Ver e otimizar uma análise de diferenciadores</span><span class="sxs-lookup"><span data-stu-id="495d6-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="495d6-139">Após completar a análise, encontre detalhes sobre esta informação em **Segmentos** > **Informações (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="495d6-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalhes de informações de diferenciador de segmentos":::

<span data-ttu-id="495d6-141">Selecione uma informação para ver os resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="495d6-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="495d6-142">Uma análise diferenciadora inclui dois separadores.</span><span class="sxs-lookup"><span data-stu-id="495d6-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="495d6-143">O separador **Atributos** lista atributos de perfil considerados diferenciadores.</span><span class="sxs-lookup"><span data-stu-id="495d6-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="495d6-144">O separador **Medidas** lista diferenciadores.</span><span class="sxs-lookup"><span data-stu-id="495d6-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="495d6-145">Cada separador inclui os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="495d6-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="495d6-146">Lista classificada de diferenciadores, ordenada pela pontuação da diferença.</span><span class="sxs-lookup"><span data-stu-id="495d6-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="495d6-147">A **Pontuação da diferença** para cada diferenciador.</span><span class="sxs-lookup"><span data-stu-id="495d6-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="495d6-148">A pontuação da diferença representa o grau de diferença de um atributo entre dois segmentos.</span><span class="sxs-lookup"><span data-stu-id="495d6-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="495d6-149">Quanto maior for a pontuação da diferença, mais os atributos diferem entre os dois segmentos.</span><span class="sxs-lookup"><span data-stu-id="495d6-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="495d6-150">Selecione uma pontuação para abrir o painel de **Pontuação da diferença** com as distribuições de valores para esse atributo.</span><span class="sxs-lookup"><span data-stu-id="495d6-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="495d6-151">Gerir informações de segmentos</span><span class="sxs-lookup"><span data-stu-id="495d6-151">Manage segment insights</span></span>

<span data-ttu-id="495d6-152">Pode utilizar as seguintes opções nas suas informações a partir da barra de comando:</span><span class="sxs-lookup"><span data-stu-id="495d6-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="495d6-153">**Anterior** para regressar à lista de informações</span><span class="sxs-lookup"><span data-stu-id="495d6-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="495d6-154">**Atualizar** para executar a análise novamente</span><span class="sxs-lookup"><span data-stu-id="495d6-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="495d6-155">**Eliminar** para remover esta informação</span><span class="sxs-lookup"><span data-stu-id="495d6-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Encontrar clientes semelhantes com IA
description: Encontre segmentos de clientes semelhantes com inteligência artificial.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268884"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="b91b6-103">Clientes semelhantes (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="b91b6-103">Similar Customers (preview)</span></span>

<span data-ttu-id="b91b6-104">Esta funcionalidade permite encontrar clientes semelhantes na sua base de clientes utilizando inteligência artificial.</span><span class="sxs-lookup"><span data-stu-id="b91b6-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="b91b6-105">Precisa de ter, pelo menos, um segmento criado para utilizar esta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="b91b6-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="b91b6-106">Expandir os critérios de um segmento existente ajuda a encontrar clientes semelhantes a esse segmento.</span><span class="sxs-lookup"><span data-stu-id="b91b6-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="b91b6-107">*Encontrar clientes semelhantes* utiliza meios automatizados para avaliar dados e fazer previsões com base nesses dados, pelo que tem a capacidade de ser usado como um método de criar perfis, uma vez que esse termo é definido pelo Regulamento Geral de Proteção de Dados ("RGPD").</span><span class="sxs-lookup"><span data-stu-id="b91b6-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="b91b6-108">A utilização desta funcionalidade por parte do Cliente para tratar os dados pode estar sujeita aos RGPD ou a outras leis ou regulamentos.</span><span class="sxs-lookup"><span data-stu-id="b91b6-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="b91b6-109">O utilizador é responsável por garantir que a sua utilização do Dynamics 365 Customer Insights, incluindo predições, cumpre com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas com a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.</span><span class="sxs-lookup"><span data-stu-id="b91b6-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="b91b6-110">Localizar clientes semelhantes</span><span class="sxs-lookup"><span data-stu-id="b91b6-110">Finding similar customers</span></span>

1. <span data-ttu-id="b91b6-111">Nos insights de audiência, aceda a **Segmentos** e selecione o segmento em que pretende basear o seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="b91b6-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="b91b6-112">É o seu *segmento de origem*.</span><span class="sxs-lookup"><span data-stu-id="b91b6-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="b91b6-113">Na barra de ação, selecione **Localizar clientes semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="b91b6-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="b91b6-114">Reveja o nome sugerido para o seu novo segmento e altere-o se necessário.</span><span class="sxs-lookup"><span data-stu-id="b91b6-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="b91b6-115">Reveja os campos que definem o seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="b91b6-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="b91b6-116">Estes campos definem a base em que o sistema tentará encontrar clientes semelhantes ao seu segmento de origem.</span><span class="sxs-lookup"><span data-stu-id="b91b6-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="b91b6-117">O sistema selecionará os campos recomendados por predefinição.</span><span class="sxs-lookup"><span data-stu-id="b91b6-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="b91b6-118">Os campos que podem reduzir significativamente o desempenho do modelo são automaticamente excluídos:</span><span class="sxs-lookup"><span data-stu-id="b91b6-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="b91b6-119">Campos com os seguintes tipos de dados: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="b91b6-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="b91b6-120">Campos com cardinalidade (número de elementos num campo) inferiores a 2 ou mais de 30</span><span class="sxs-lookup"><span data-stu-id="b91b6-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="b91b6-121">Escolha se pretende incluir **Todos os clientes** ou apenas clientes num **Segmento específico existente** no seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="b91b6-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="b91b6-122">Exclua os clientes no seu segmento de origem selecionando a caixa de verificação **Excluir todos os utilizadores no segmento de origem**.</span><span class="sxs-lookup"><span data-stu-id="b91b6-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="b91b6-123">Por predefinição, o sistema sugere que inclua apenas 20% do tamanho da audiência alvo na sua saída.</span><span class="sxs-lookup"><span data-stu-id="b91b6-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="b91b6-124">Edite este limiar conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b91b6-124">Edit this threshold as needed.</span></span> <span data-ttu-id="b91b6-125">Aumentar o limiar reduzirá a precisão.</span><span class="sxs-lookup"><span data-stu-id="b91b6-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="b91b6-126">Selecione **Executar** na parte inferior da página para iniciar uma tarefa de classificação binária (um método de aprendizagem automática) que analisa o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="b91b6-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="b91b6-127">Ver o segmento semelhante</span><span class="sxs-lookup"><span data-stu-id="b91b6-127">View the similar segment</span></span>

<span data-ttu-id="b91b6-128">Após o processamento do segmento semelhante, encontrará o novo segmento listado na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="b91b6-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b91b6-129">![Segmento de clientes semelhantes](media/expanded-segment.png "Segmento de clientes semelhantes")</span><span class="sxs-lookup"><span data-stu-id="b91b6-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="b91b6-130">Selecione **Ver** na barra de ação para abrir o detalhe do segmento.</span><span class="sxs-lookup"><span data-stu-id="b91b6-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="b91b6-131">Esta visão contém informações sobre a distribuição dos resultados entre [pontuações de semelhança](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="b91b6-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="b91b6-132">Também encontrará os valores de pontuação de semelhança na **Pré-visualização dos membros do segmento**.</span><span class="sxs-lookup"><span data-stu-id="b91b6-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="b91b6-133">Utilize a saída de um segmento semelhante</span><span class="sxs-lookup"><span data-stu-id="b91b6-133">Use the output of a similar segment</span></span>

<span data-ttu-id="b91b6-134">Pode [trabalhar com a saída de um segmento semelhante](segments.md) como faz com outros segmentos.</span><span class="sxs-lookup"><span data-stu-id="b91b6-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="b91b6-135">Por exemplo, exportar o segmento ou criar uma medida.</span><span class="sxs-lookup"><span data-stu-id="b91b6-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="b91b6-136">Atualizar e editar um segmento semelhante</span><span class="sxs-lookup"><span data-stu-id="b91b6-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="b91b6-137">Para atualizar um segmento semelhante, selecione-o na página **Segmentos** e selecione **Atualizar** na barra de ação.</span><span class="sxs-lookup"><span data-stu-id="b91b6-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="b91b6-138">Editar um segmento semelhante irá voltar a processar os seus dados.</span><span class="sxs-lookup"><span data-stu-id="b91b6-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="b91b6-139">O segmento anteriormente criado é atualizado com dados atualizados.</span><span class="sxs-lookup"><span data-stu-id="b91b6-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="b91b6-140">Para editar um segmento semelhante, selecione-o na página **Segmentos** e selecione **Editar** na barra de ação.</span><span class="sxs-lookup"><span data-stu-id="b91b6-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="b91b6-141">Aplique as alterações e selecione **Executar** para iniciar o processamento.</span><span class="sxs-lookup"><span data-stu-id="b91b6-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="b91b6-142">Eliminar um segmento semelhante</span><span class="sxs-lookup"><span data-stu-id="b91b6-142">Delete a similar segment</span></span>

<span data-ttu-id="b91b6-143">Selecione o segmento semelhante na página **Segmentos** e selecione **Eliminar** na barra de ação.</span><span class="sxs-lookup"><span data-stu-id="b91b6-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="b91b6-144">Em seguida, confirme a eliminação.</span><span class="sxs-lookup"><span data-stu-id="b91b6-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="b91b6-145">Sobre pontuações de semelhança</span><span class="sxs-lookup"><span data-stu-id="b91b6-145">About similarity scores</span></span>

<span data-ttu-id="b91b6-146">O modelo de machine learning de classificação binária atribui uma pontuação aos clientes do segmento semelhante.</span><span class="sxs-lookup"><span data-stu-id="b91b6-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="b91b6-147">A pontuação baseia-se na semelhança com os clientes do segmento de origem.</span><span class="sxs-lookup"><span data-stu-id="b91b6-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="b91b6-148">Pontuações de semelhança abaixo de 0,55 são clientes que o sistema classificou como *não semelhantes* aos clientes no segmento de origem</span><span class="sxs-lookup"><span data-stu-id="b91b6-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="b91b6-149">As pontuações de semelhança entre 0,55 e 0,7 são classificadas como *um pouco semelhantes*</span><span class="sxs-lookup"><span data-stu-id="b91b6-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="b91b6-150">As pontuações de semelhança entre 0,7 e 0,85 são classificadas como *semelhantes*</span><span class="sxs-lookup"><span data-stu-id="b91b6-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="b91b6-151">Pontuações de semelhança entre 0,85 e 1 são clientes que o sistema classifica como *muito semelhantes*</span><span class="sxs-lookup"><span data-stu-id="b91b6-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="b91b6-152">Os clientes com pontuações de semelhança inferiores a 0,4 não estão incluídos na saída do modelo.</span><span class="sxs-lookup"><span data-stu-id="b91b6-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="b91b6-153">O sistema não os considera semelhantes o suficiente ao segmento de origem.</span><span class="sxs-lookup"><span data-stu-id="b91b6-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
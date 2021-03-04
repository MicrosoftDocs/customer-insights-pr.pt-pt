---
title: Dados parciais completos utilizando previsões
description: Utilizar previsões para preencher os dados incompletos dos clientes.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268286"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="3a47d-103">Concluir os seus dados parciais com predições</span><span class="sxs-lookup"><span data-stu-id="3a47d-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3a47d-104">As predições permitem criar facilmente valores previstos que podem melhorar a sua compreensão de um cliente.</span><span class="sxs-lookup"><span data-stu-id="3a47d-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="3a47d-105">Na página **Inteligência** > **Predições**, pode selecionar **As minhas predições** para ver as predições que configurou noutras partes das informações de audiência, e pode personalizá-las ainda mais.</span><span class="sxs-lookup"><span data-stu-id="3a47d-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="3a47d-106">Não poderá utilizar esta funcionalidade se o seu ambiente utilizar o armazenamento do Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="3a47d-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="3a47d-107">A funcionalidade de predições utiliza meios automatizados para avaliar os dados e efetuar predições com base nesses dados e, por conseguinte, tem a capacidade de ser utilizada como método de criação de perfis, nos termos em que esse termo for definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD").</span><span class="sxs-lookup"><span data-stu-id="3a47d-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="3a47d-108">A utilização desta funcionalidade por parte do Cliente para tratar os dados pode estar sujeita aos RGPD ou a outras leis ou regulamentos.</span><span class="sxs-lookup"><span data-stu-id="3a47d-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="3a47d-109">O utilizador é responsável por garantir que a sua utilização do Dynamics 365 Customer Insights, incluindo predições, cumpre com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas com a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.</span><span class="sxs-lookup"><span data-stu-id="3a47d-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3a47d-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3a47d-110">Prerequisites</span></span>

<span data-ttu-id="3a47d-111">Antes de a sua organização poder utilizar a funcionalidade de predições, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="3a47d-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="3a47d-112">A sua organização tem uma instância [configurada no Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) e está na mesma organização que o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3a47d-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="3a47d-113">O seu ambiente está ligado à sua instância do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3a47d-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="3a47d-114">Se [criar um novo ambiente](manage-environments.md), configure-o na caixa de diálogo **Criar um ambiente** e selecione **Avançadas**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="3a47d-115">Se já tiver criado um ambiente, aceda às respetivas definições e **selecione** avançado.</span><span class="sxs-lookup"><span data-stu-id="3a47d-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="3a47d-116">De qualquer forma, na secção **Usar predições**, introduza a o URL da instância do Common Data Service a que deseja anexar o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="3a47d-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="3a47d-117">Criar uma predição na entidade de Cliente</span><span class="sxs-lookup"><span data-stu-id="3a47d-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="3a47d-118">Nas informações de audiência, vá a **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="3a47d-119">Selecione a entidade **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="3a47d-120">Na entidade **Cliente: CustomerInsights**, selecione o separador **Campos**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="3a47d-121">Localize o nome do atributo para o qual pretende prever os valores e, em seguida, no ícone **Descrição Geral** na coluna **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a47d-122">![Ícone Descrição Geral](media/intelligence-overviewicon.png "Ícone Descrição Geral")</span><span class="sxs-lookup"><span data-stu-id="3a47d-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="3a47d-123">Se existir uma taxa elevada de valores em falta para o atributo, selecione **Prever valores em falta** para continuar com a sua predição.</span><span class="sxs-lookup"><span data-stu-id="3a47d-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a47d-124">![Estado da descrição geral a mostrar o botão Prever valores em falta](media/intelligence-overviewpredictmissingvalues.png "Estado da descrição geral a mostrar o botão Prever valores em falta")</span><span class="sxs-lookup"><span data-stu-id="3a47d-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="3a47d-125">Forneça um **Nome a Apresentar** e um **Nome da entidade de saída** para obter os resultados da predição.</span><span class="sxs-lookup"><span data-stu-id="3a47d-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3a47d-126">Será aqui mostrada uma lista de opções preenchida previamente onde poderá mapear os valores para uma categoria prevista.</span><span class="sxs-lookup"><span data-stu-id="3a47d-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="3a47d-127">Neste caso, as únicas opções de categoria serão 0 ou 1, uma vez que são mapeadas para a natureza verdadeiro/falso, ou binária, da predição.</span><span class="sxs-lookup"><span data-stu-id="3a47d-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="3a47d-128">Na coluna Categoria, mapeie os valores de campo que pretende que sejam classificados como "0" na predição final como "0" e os itens que pretende que sejam classificados como "1" na predição final como "1".</span><span class="sxs-lookup"><span data-stu-id="3a47d-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a47d-129">![Exemplo a mostrar valores de campos mapeados para categorias](media/intelligence-categorymapping.png "Exemplo a mostrar valores de campos mapeados para categorias")</span><span class="sxs-lookup"><span data-stu-id="3a47d-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="3a47d-130">Selecione **Concluído** e a predição será processada.</span><span class="sxs-lookup"><span data-stu-id="3a47d-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="3a47d-131">O processamento irá demorar algum tempo, consoante o tamanho e a complexidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="3a47d-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="3a47d-132">Os resultados estarão disponíveis numa nova entidade baseada no **Nome da entidade de saída** da predição que criou.</span><span class="sxs-lookup"><span data-stu-id="3a47d-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="3a47d-133">Criar uma predição durante a criação de um segmento</span><span class="sxs-lookup"><span data-stu-id="3a47d-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="3a47d-134">A predição dos valores em falta para um atributo específico à escolha também é possível ao criar um segmento.</span><span class="sxs-lookup"><span data-stu-id="3a47d-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="3a47d-135">Especificamente, quando cria rapidamente um segmento baseado na entidade Cliente unificado ou na entidade Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="3a47d-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="3a47d-136">Como parte deste fluxo, irá escolher um atributo específico onde basear o segmento, como Satisfação do Cliente ou Montante de Compra.</span><span class="sxs-lookup"><span data-stu-id="3a47d-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="3a47d-137">Após a criação do segmento, o sistema irá sugerir um método para prever quaisquer valores em falta para este atributo.</span><span class="sxs-lookup"><span data-stu-id="3a47d-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="3a47d-138">Nas informações de audiência, aceda a **Segmentos** e selecione o mosaico **Perfis**. </span><span class="sxs-lookup"><span data-stu-id="3a47d-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="3a47d-139">Escolha um **Campo** onde criar um segmento e selecione um **Operador** e, em seguida selecione **Rever**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="3a47d-140">Forneça um **Nome** e um **Nome a apresentar** para o segmento.</span><span class="sxs-lookup"><span data-stu-id="3a47d-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="3a47d-141">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-141">Select **Save**.</span></span>

5. <span data-ttu-id="3a47d-142">Se o segmento que criar tiver dados incompletos no campo de origem, poderá optar por prever os valores em falta.</span><span class="sxs-lookup"><span data-stu-id="3a47d-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a47d-143">![Botão Predição](media/segments-predictoption.png "Botão Predição")</span><span class="sxs-lookup"><span data-stu-id="3a47d-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="3a47d-144">Forneça um **Nome a Apresentar** e um **Nome da entidade de saída** para obter os resultados da predição.</span><span class="sxs-lookup"><span data-stu-id="3a47d-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3a47d-145">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-145">Select **Done**.</span></span> <span data-ttu-id="3a47d-146">A sua predição será gerada em breve numa nova entidade com o nome fornecido para o **Nome da entidade de saída**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="3a47d-147">Ver uma predição</span><span class="sxs-lookup"><span data-stu-id="3a47d-147">View a prediction</span></span>

1. <span data-ttu-id="3a47d-148">Nas informações de audiência, vá a **Inteligência** > **Predições** > **As minhas predições**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3a47d-149">Selecione a predição que pretende rever.</span><span class="sxs-lookup"><span data-stu-id="3a47d-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="3a47d-150">Selecione as reticências na coluna **Ações** e escolha **Ver**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3a47d-151">Verá vários pontos de dados na vista da sua predição.</span><span class="sxs-lookup"><span data-stu-id="3a47d-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a47d-152">![Página Predições](media/intelligence-predictionsviewpage.png "Página Predições")</span><span class="sxs-lookup"><span data-stu-id="3a47d-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="3a47d-153">Os **valores previstos** mostram o mapeamento criado durante a fase de mapeamento do valor Campo para Categoria.</span><span class="sxs-lookup"><span data-stu-id="3a47d-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="3a47d-154">São valores no conjunto de dados que foram mapeados para uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="3a47d-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="3a47d-155">-**Principais influenciadores** são os fatores existentes no seu conjunto de dados com maior probabilidade de influenciar a confiança da predição do valor Campo que está a ser mapeado para uma categoria específica..</span><span class="sxs-lookup"><span data-stu-id="3a47d-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="3a47d-156">**Desempenho** indica a forma como as predições estão a ser efetuadas.</span><span class="sxs-lookup"><span data-stu-id="3a47d-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="3a47d-157">Selecione a ligação para saber mais.</span><span class="sxs-lookup"><span data-stu-id="3a47d-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="3a47d-158">**Pré-visualizar** mostra exemplos do conjunto de dados de saída da sua predição, bem como a probabilidade, ou nossa confiança, do valor previsto, em que 0 é incerteza e 1 é certo.</span><span class="sxs-lookup"><span data-stu-id="3a47d-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="3a47d-159">Atualizar uma predição</span><span class="sxs-lookup"><span data-stu-id="3a47d-159">Update a prediction</span></span>

1. <span data-ttu-id="3a47d-160">Nas informações de audiência, vá a **Inteligência** > **Predições** > **As minhas predições**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3a47d-161">Selecione a predição que pretende atualizar e selecione o ícone **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="3a47d-162">A predição será agendada para processamento.</span><span class="sxs-lookup"><span data-stu-id="3a47d-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="3a47d-163">Pode ver a hora da última atualização na coluna **Atualizado** da página **Predições**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="3a47d-164">Editar uma predição</span><span class="sxs-lookup"><span data-stu-id="3a47d-164">Edit a prediction</span></span>

<span data-ttu-id="3a47d-165">Depois de ter criado uma predição, pode personalizar o modelo no AI Builder para aumentar a eficácia do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="3a47d-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="3a47d-166">Nas informações de audiência, vá a **Inteligência** > **Predições** > **As minhas predições**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3a47d-167">Selecione a predição que pretende editar.</span><span class="sxs-lookup"><span data-stu-id="3a47d-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="3a47d-168">Selecione as reticências na coluna **Ações** e escolha **Ver**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3a47d-169">Selecione **Personalizar no AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="3a47d-170">Atualize o seu modelo no AI Builder.</span><span class="sxs-lookup"><span data-stu-id="3a47d-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="3a47d-171">[Saiba mais informações sobre como gerir os modelos no AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="3a47d-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="3a47d-172">A execução seguinte da sua predição utilizará o modelo atualizado que criou.</span><span class="sxs-lookup"><span data-stu-id="3a47d-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="3a47d-173">Os novos modelos criados no AI Builder não serão exibidos em informações de audiência, a menos que o modelo tenha sido criado a partir das experiências listadas acima.</span><span class="sxs-lookup"><span data-stu-id="3a47d-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="3a47d-174">Remover uma predição</span><span class="sxs-lookup"><span data-stu-id="3a47d-174">Remove a prediction</span></span>

1. <span data-ttu-id="3a47d-175">Nas informações de audiência, vá a **Inteligência** > **Predições** > **As minhas predições**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3a47d-176">Selecione a predição que pretende eliminar.</span><span class="sxs-lookup"><span data-stu-id="3a47d-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="3a47d-177">Selecione as reticências na coluna **Ações** e escolha **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="3a47d-178">Confirme a eliminação.</span><span class="sxs-lookup"><span data-stu-id="3a47d-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3a47d-179">Resolução de Problemas</span><span class="sxs-lookup"><span data-stu-id="3a47d-179">Troubleshooting</span></span>

<span data-ttu-id="3a47d-180">Se não conseguir concluir o processo de anexação do Common Data Service devido a um erro, poderá tentar concluir o processo manualmente.</span><span class="sxs-lookup"><span data-stu-id="3a47d-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="3a47d-181">Existem dois problemas conhecidos que podem ocorrer no processo de anexação:</span><span class="sxs-lookup"><span data-stu-id="3a47d-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="3a47d-182">A solução Suplemento Ficha de Cliente não está instalada.</span><span class="sxs-lookup"><span data-stu-id="3a47d-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="3a47d-183">Conclua as instruções para [instalar e configurar a solução](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="3a47d-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="3a47d-184">Não são concedidas permissões da aplicação.</span><span class="sxs-lookup"><span data-stu-id="3a47d-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="3a47d-185">Ir para o [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3a47d-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="3a47d-186">Selecionar **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="3a47d-187">Selecione as reticências junto do ambiente ao qual pretende adicionar a permissão e selecione **Definições**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="3a47d-188">Expanda **Utilizadores + permissões** e selecione **Utilizadores**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="3a47d-189">Selecione **+ Novo** e selecione **Utilizador**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="3a47d-190">Selecione **Utilizador da Aplicação** se ainda não estiver selecionado e introduza as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3a47d-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="3a47d-191">**Nome de Utilizador:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3a47d-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="3a47d-192">**ID da Aplicação:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="3a47d-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="3a47d-193">**Nome Próprio:** Cliente</span><span class="sxs-lookup"><span data-stu-id="3a47d-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="3a47d-194">**Apelido:** Informações</span><span class="sxs-lookup"><span data-stu-id="3a47d-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="3a47d-195">**E-mail Principal:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3a47d-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="3a47d-196">Selecione **Guardar e Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="3a47d-197">Selecione o utilizador que criou.</span><span class="sxs-lookup"><span data-stu-id="3a47d-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="3a47d-198">Selecione **Gerir Funções** na barra de menus superior.</span><span class="sxs-lookup"><span data-stu-id="3a47d-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="3a47d-199">Selecione **Administrador de Sistema** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a47d-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
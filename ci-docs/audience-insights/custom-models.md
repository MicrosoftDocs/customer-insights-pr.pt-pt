---
title: Modelos de aprendizagem automática personalizados | Documentos da Microsoft
description: Trabalhar com modelos personalizados do Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668917"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="9021e-103">Modelos de aprendizagem automática personalizados</span><span class="sxs-lookup"><span data-stu-id="9021e-103">Custom machine learning models</span></span>

<span data-ttu-id="9021e-104">**Informações** > **Modelos personalizados** permite-lhe gerir fluxos de trabalho baseados em modelos do Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="9021e-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="9021e-105">Os fluxos de trabalho ajudam-no a escolher os dados a partir dos quais pretende gerar conhecimentos e mapear os resultados para os seus dados unificados de clientes.</span><span class="sxs-lookup"><span data-stu-id="9021e-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="9021e-106">Para mais informações sobre a construção de modelos ML personalizados, ver [Usar modelos baseados no Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="9021e-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="9021e-107">Responsável IA</span><span class="sxs-lookup"><span data-stu-id="9021e-107">Responsible AI</span></span>

<span data-ttu-id="9021e-108">As previsões oferecem capacidades para criar melhores experiências para os clientes, melhorar as capacidades empresariais, e fluxos de receitas.</span><span class="sxs-lookup"><span data-stu-id="9021e-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="9021e-109">Recomendamos vivamente que equilibre o valor da sua previsão com o impacto que tem e os desvios que podem ser introduzidos de uma forma ética.</span><span class="sxs-lookup"><span data-stu-id="9021e-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="9021e-110">Saiba mais sobre como a Microsoft [está a tratar a IA Responsável](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="9021e-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="9021e-111">Também pode saber mais sobre [técnicas e processos para uma aprendizagem automática responsável](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) específica do Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="9021e-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9021e-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9021e-112">Prerequisites</span></span>

- <span data-ttu-id="9021e-113">Atualmente, esta funcionalidade suporta serviços web publicados através de [Machine Learning Studio (clássico)](https://studio.azureml.net) e [pipelines por lote do Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="9021e-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="9021e-114">Necessita de uma conta de armazenamento Azure Data Lake Gen2 associada à sua instância Azure Studio para utilizar esta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="9021e-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="9021e-115">Para mais informações, consulte [Criar uma conta de armazenamento do Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="9021e-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="9021e-116">Adicionar um novo fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="9021e-116">Add a new workflow</span></span>

1. <span data-ttu-id="9021e-117">Vá a **Informações** > **Modelos personalizados** e selecione **Novo fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="9021e-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="9021e-118">Forneça um nome reconhecível ao modelo personalizado no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="9021e-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9021e-119">![Captura de ecrã do painel de Novo fluxo de trabalho](media/new-workflowv2.png "Captura de ecrã do painel de Novo fluxo de trabalho")</span><span class="sxs-lookup"><span data-stu-id="9021e-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="9021e-120">Selecione a organização que contém o serviço Web no **Inquilino que contém o seu serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="9021e-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="9021e-121">Se a subscrição do Azure Machine Learning estiver num inquilino diferente do Customer Insights, selecione **Iniciar sessão** com as suas credenciais para a organização selecionada.</span><span class="sxs-lookup"><span data-stu-id="9021e-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="9021e-122">Selecione **Áreas de trabalho** associadas ao seu serviço web.</span><span class="sxs-lookup"><span data-stu-id="9021e-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="9021e-123">Há duas secções listadas, uma para Azure Machine Learning v1 (Machine Learning Studio (clássico)) e a Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="9021e-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="9021e-124">Se não tiver a certeza qual é a área de trabalho certa para o seu serviço web de Machine Learning Studio (clássico), selecione **Qualquer uma**.</span><span class="sxs-lookup"><span data-stu-id="9021e-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="9021e-125">Escolha o serviço web Machine Learning Studio (clássico) ou pipeline Azure Machine Learning no menu pendente **Serviço Web que contém o seu modelo**.</span><span class="sxs-lookup"><span data-stu-id="9021e-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="9021e-126">Em seguida, selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="9021e-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="9021e-127">Saiba mais sobre [publicar um serviço web em Machine Learning Studio (clássico)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="9021e-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="9021e-128">Saiba mais sobre [publicar um serviço web em Machine Learning Studio usando o designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou o [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="9021e-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="9021e-129">O seu pipeline deve ser publicado num [ponto final do pipeline](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="9021e-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="9021e-130">Para cada **Entrada do serviço Web**, selecione a **Entidade** correspondente a partir de insights da audiência e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="9021e-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9021e-131">![Configurar um fluxo de trabalho](media/intelligence-screen2-updated.png "Configurar um fluxo de trabalho")</span><span class="sxs-lookup"><span data-stu-id="9021e-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="9021e-132">No passo **Parâmetros de saída do modelo**, definir as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="9021e-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="9021e-133">Machine Learning Studio (clássico)</span><span class="sxs-lookup"><span data-stu-id="9021e-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="9021e-134">Introduza a saída do **nome da Entidade** para onde quer que as saídas dos serviços da web fluam.</span><span class="sxs-lookup"><span data-stu-id="9021e-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="9021e-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9021e-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="9021e-136">Introduza a saída do **nome da Entidade** para onde quer que as saídas do pipeline fluam.</span><span class="sxs-lookup"><span data-stu-id="9021e-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="9021e-137">Selecione o **Nome do parâmetro de armazenamento de dados de saída** do seu pipeline de lotes a partir da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9021e-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="9021e-138">Selecione o **Nome do parâmetro do caminho de dados de saída** do seu pipeline de lotes a partir da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9021e-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="9021e-139">![Painel de parâmetros de saída de modelo](media/intelligence-screen3-outputparameters.png "Painel de parâmetros de saída de modelo")</span><span class="sxs-lookup"><span data-stu-id="9021e-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="9021e-140">Selecione o atributo correspondente a partir da lista pendente do **ID do cliente nos resultados** que identifica os clientes e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9021e-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9021e-141">![Relacionar resultados com painel de dados do cliente](media/intelligence-screen4-relatetocustomer.png "Relacionar resultados com painel de dados do cliente")</span><span class="sxs-lookup"><span data-stu-id="9021e-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="9021e-142">Verá o ecrã **Fluxo de Trabalho Guardado** com detalhes sobre o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9021e-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="9021e-143">Se configurou um fluxo de trabalho para um pipeline de Azure Machine Learning, os insights da audiência serão anexados à área de trabalho que contém o pipeline.</span><span class="sxs-lookup"><span data-stu-id="9021e-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="9021e-144">Os insights da audiência terão um papel de **Contribuinte** na área de trabalho do Azure.</span><span class="sxs-lookup"><span data-stu-id="9021e-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="9021e-145">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="9021e-145">Select **Done**.</span></span>

1. <span data-ttu-id="9021e-146">Pode agora executar o fluxo de trabalho a partir da página **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="9021e-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="9021e-147">Editar um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="9021e-147">Edit a workflow</span></span>

1. <span data-ttu-id="9021e-148">Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** junto de um fluxo de trabalho que criou anteriormente e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9021e-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="9021e-149">Pode atualizar o nome reconhecível do seu fluxo de trabalho no campo **Nome a apresentar**, mas não pode alterar o serviço web configurado ou o pipeline.</span><span class="sxs-lookup"><span data-stu-id="9021e-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="9021e-150">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="9021e-150">Select **Next**.</span></span>

1. <span data-ttu-id="9021e-151">Para cada **Entrada do serviço Web**, pode atualizar a **Entidade** correspondente a partir de insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="9021e-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="9021e-152">Em seguida, selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="9021e-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="9021e-153">No passo **Parâmetros de saída do modelo**, definir as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="9021e-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="9021e-154">Machine Learning Studio (clássico)</span><span class="sxs-lookup"><span data-stu-id="9021e-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="9021e-155">Introduza a saída do **nome da Entidade** para onde quer que as saídas dos serviços da web fluam.</span><span class="sxs-lookup"><span data-stu-id="9021e-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="9021e-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9021e-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="9021e-157">Introduza a saída do **nome da Entidade** para onde quer que as saídas do pipeline fluam.</span><span class="sxs-lookup"><span data-stu-id="9021e-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="9021e-158">Selecione o **Nome do parâmetro de armazenamento de dados de saída** para o seu pipeline de teste.</span><span class="sxs-lookup"><span data-stu-id="9021e-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="9021e-159">Selecione o **Nome do parâmetro do caminho de saída** para o seu pipeline de teste.</span><span class="sxs-lookup"><span data-stu-id="9021e-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="9021e-160">Selecione o atributo correspondente a partir da lista pendente do **ID do cliente nos resultados** que identifica os clientes e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9021e-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="9021e-161">É necessário escolher um atributo da saída de inferência com valores semelhantes aos da coluna ID do Cliente da entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="9021e-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="9021e-162">Se não tiver tal coluna no seu conjunto de dados, escolha um atributo que identifique de forma única a linha.</span><span class="sxs-lookup"><span data-stu-id="9021e-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="9021e-163">Executar um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="9021e-163">Run a workflow</span></span>

1. <span data-ttu-id="9021e-164">Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** junto de um fluxo de trabalho que criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9021e-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="9021e-165">Selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9021e-165">Select **Run**.</span></span>

<span data-ttu-id="9021e-166">O seu fluxo de trabalho também é executado automaticamente com cada as atualização programada.</span><span class="sxs-lookup"><span data-stu-id="9021e-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="9021e-167">Saber mais sobre a [configuração de atualizações agendadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9021e-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="9021e-168">Eliminar um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="9021e-168">Delete a workflow</span></span>

1. <span data-ttu-id="9021e-169">Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** junto de um fluxo de trabalho que criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9021e-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="9021e-170">Selecione **Eliminar** e confirme a eliminação.</span><span class="sxs-lookup"><span data-stu-id="9021e-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="9021e-171">O fluxo de trabalho será eliminado.</span><span class="sxs-lookup"><span data-stu-id="9021e-171">Your workflow will be deleted.</span></span> <span data-ttu-id="9021e-172">A [entidade](entities.md) que foi criada quando criou o fluxo de trabalho persiste e pode ser visualizada na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="9021e-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

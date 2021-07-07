---
title: Ingerir dados através de um conector Power Query
description: Conectores para origens de dados com base no Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305905"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="a3dbf-103">Ligue-se a uma origem de dados do Power Query</span><span class="sxs-lookup"><span data-stu-id="a3dbf-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="a3dbf-104">O Power Query oferece um vasto conjunto de conectores para ingerir dados.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="a3dbf-105">A maioria destes conectores são suportados pelo Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="a3dbf-106">A adição de origens de dados com base em conectores Power Query geralmente segue os passos descritos na secção seguinte.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="a3dbf-107">No entanto, dependendo do conector que utiliza, são necessárias informações diferentes.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="a3dbf-108">Para obter mais informações, consulte a documentação sobre os conectores individuais na [referência do conector Power Query](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="a3dbf-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="a3dbf-109">Criar uma nova origem de dados</span><span class="sxs-lookup"><span data-stu-id="a3dbf-109">Create a new data source</span></span>

1. <span data-ttu-id="a3dbf-110">Em informações de audiência, aceda a **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="a3dbf-111">Selecione **Adicionar origem de dados**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="a3dbf-112">Escolha o método **Importação de dados** e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="a3dbf-113">Forneça um **Nome** para a origem de dados e selecione **Seguinte** para criar a origem de dados.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="a3dbf-114">Nomear diretrizes:</span><span class="sxs-lookup"><span data-stu-id="a3dbf-114">Name guidelines:</span></span> 
   - <span data-ttu-id="a3dbf-115">Comece com uma letra.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-115">Start with a letter.</span></span>
   - <span data-ttu-id="a3dbf-116">Utilize apenas letras e números.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-116">Use letters and numbers only.</span></span> <span data-ttu-id="a3dbf-117">Não são permitidos carateres especiais e espaços.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="a3dbf-118">Utilize entre 3 e 64 carateres.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="a3dbf-119">Escolha um dos [conectores disponíveis](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="a3dbf-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="a3dbf-120">Para este exemplo, selecionamos o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a3dbf-121">Introduza os detalhes requeridos nas **Definições de ligação** para o conector selecionado e selecione **Seguinte** para ver uma pré-visualização dos dados.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="a3dbf-122">Selecione **Transformar dados**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-122">Select **Transform data**.</span></span> <span data-ttu-id="a3dbf-123">Neste passo, vai adicionar entidades à sua origem de dados.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="a3dbf-124">As entidades são conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-124">Entities are datasets.</span></span> <span data-ttu-id="a3dbf-125">Se tiver uma base de dados que inclua vários conjuntos de dados, cada conjunto é a sua própria entidade.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="a3dbf-126">A caixa de diálogo **Power Query – Editar consultas** permite-lhe rever e refinar os dados.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="a3dbf-127">As entidades que os sistemas identificaram na sua origem de dados ligada aparecem no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3dbf-128">![Diálogo Editar consultas](media/data-manager-configure-edit-queries.png "Diálogo Editar consultas")</span><span class="sxs-lookup"><span data-stu-id="a3dbf-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="a3dbf-129">Também pode transformar os seus dados.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-129">You can also transform your data.</span></span> <span data-ttu-id="a3dbf-130">Selecione uma entidade para edição ou transformação.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="a3dbf-131">Utilize as opções na janela do Power Query para aplicar transformações.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="a3dbf-132">Cada transformação é listada em **Passos aplicados**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="a3dbf-133">O Power Query fornece inúmeras opções de transformação pré-criadas.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="a3dbf-134">Para obter mais informações, veja [Transformações do Power Query](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="a3dbf-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="a3dbf-135">Poderá adicionar entidades adicionar à sua origem de dados ao selecionar **Obter dados** na caixa de diálogo **Editar consultas**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="a3dbf-136">Estas transformações são altamente recomendadas:</span><span class="sxs-lookup"><span data-stu-id="a3dbf-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="a3dbf-137">Se estiver a ingerir dados a partir de um ficheiro CSV, a primeira linha contém frequentemente cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="a3dbf-138">Aceda a **Tabela de transformar** e selecione **Utilizar os cabeçalhos como primeira linha**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="a3dbf-139">Certifique-se de que o tipo de dados está definido de forma adequada.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="a3dbf-140">Selecione **Guardar** no final da janela do Power Query para guardar as transformações.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="a3dbf-141">Depois de guardar, encontrará a sua origem de dados em **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="a3dbf-142">Na página **Origens de dados**, vai notar que a nova origem de dados está em estado **A atualizar**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="a3dbf-143">Origens de dados do Power Query disponíveis</span><span class="sxs-lookup"><span data-stu-id="a3dbf-143">Available Power Query data sources</span></span>

<span data-ttu-id="a3dbf-144">Consulte a [referência do conector Power Query](/power-query/connectors/) para obter uma lista atualizada de conectores que pode selecionar para importar dados para o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="a3dbf-145">Os conectores com uma marca de verificação na coluna **Customer Insights (Fluxos de dados)** estão disponíveis para criar novas origens de dados com base no Power Query.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="a3dbf-146">Reveja a documentação de um conector específico para saber mais sobre os seus pré-requisitos, limitações e outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="a3dbf-147">Editar origens de dados do Power Query</span><span class="sxs-lookup"><span data-stu-id="a3dbf-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="a3dbf-148">Poderá não ser possível efetuar alterações às origens de dados que estão atualmente a ser utilizadas num dos processos da aplicação (*segmentação*, *corresponder* ou *intercalar*, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="a3dbf-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="a3dbf-149">A utilização da página **Definições** permite monitorizar o progresso de cada um dos processos ativos.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="a3dbf-150">Quando um processo é concluído, pode regressar à página **Origens de Dados** e efetuar as suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="a3dbf-151">Em informações de audiência, aceda a **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a3dbf-152">Selecione as reticências verticais junto da origem de dados que pretende alterar e selecione **Editar** no menu pendente.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3dbf-153">![Opção Editar](media/edit-option-data-sources.png "Opção Editar")</span><span class="sxs-lookup"><span data-stu-id="a3dbf-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="a3dbf-154">Aplique as suas alterações e transformações no diálogo **Power Query – Editar consultas** como descrito na secção [Criar uma nova origem de dados](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="a3dbf-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="a3dbf-155">Selecione **Guardar** no Power Query depois de completar as suas edições para guardar as suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a3dbf-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
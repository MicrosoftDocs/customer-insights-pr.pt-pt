---
title: Utilizar origens de dados para ingerir dados
description: Saiba como importar dados de várias origens.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887908"
---
# <a name="data-sources-overview"></a><span data-ttu-id="11e4c-103">Descrição geral das origens de dados</span><span class="sxs-lookup"><span data-stu-id="11e4c-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="11e4c-104">A capacidade de insights da audiência em Dynamics 365 Customer Insights liga-se a dados de um vasto conjunto de origens.</span><span class="sxs-lookup"><span data-stu-id="11e4c-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="11e4c-105">A ligação a um origem de dados é frequentemente referida como o processo de *ingestão de dados*.</span><span class="sxs-lookup"><span data-stu-id="11e4c-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="11e4c-106">Depois de ingerir os dados, pode [unificar](data-unification.md) e tomar medidas sobre os mesmos.</span><span class="sxs-lookup"><span data-stu-id="11e4c-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="11e4c-107">Adicionar uma origem de dados</span><span class="sxs-lookup"><span data-stu-id="11e4c-107">Add a data source</span></span>

<span data-ttu-id="11e4c-108">Consulte os artigos detalhados sobre como adicionar uma origem de dados, dependendo da opção que escolher.</span><span class="sxs-lookup"><span data-stu-id="11e4c-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="11e4c-109">Pode adicionar uma origem de dados de três formas principais:</span><span class="sxs-lookup"><span data-stu-id="11e4c-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="11e4c-110">Através de dezenas de conectores Power Query</span><span class="sxs-lookup"><span data-stu-id="11e4c-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="11e4c-111">A partir de uma pasta do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="11e4c-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="11e4c-112">A partir do seu próprio lake do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11e4c-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="11e4c-113">Adicionar dados de origens de dados no local</span><span class="sxs-lookup"><span data-stu-id="11e4c-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="11e4c-114">Ingerir dados de origens de dados no local em Audience Insights é suportado com base em fluxos de dados do Power Platform.</span><span class="sxs-lookup"><span data-stu-id="11e4c-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="11e4c-115">Os fluxos de dados podem ser ativados no Customer Insights [fornecendo o URL do ambiente Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) ao configurar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="11e4c-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="11e4c-116">Por predefinição, as origens de dados criadas após a associação de um ambiente Dataverse ao Customer Insights utilizarão [fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="11e4c-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="11e4c-117">Os fluxos de dados suportam conectividade no local utilizando os gateways de dados.</span><span class="sxs-lookup"><span data-stu-id="11e4c-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="11e4c-118">Remova e recrie origens de dados que existiam antes de um ambiente Dataverse ser associado a utilizar os gateways de dados no local.</span><span class="sxs-lookup"><span data-stu-id="11e4c-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="11e4c-119">Os gateways de dados de um ambiente Power BI ou Power Apps existente serão visíveis e poderá reutilizá-los no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11e4c-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="11e4c-120">A página de origens de dados mostra ligações para ir para o ambiente Power Platform onde pode ver e configurar gateways de dados no local.</span><span class="sxs-lookup"><span data-stu-id="11e4c-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Captura de ecrã da página de origens de dados a mostrar ligações que apontam para o ambiente Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="11e4c-122">Rever dados ingeridos</span><span class="sxs-lookup"><span data-stu-id="11e4c-122">Review ingested data</span></span>

<span data-ttu-id="11e4c-123">Verá o nome de cada origem de dados ingerido, o seu estado, e a última vez que os dados foram atualizados para essa origem.</span><span class="sxs-lookup"><span data-stu-id="11e4c-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="11e4c-124">Pode ordenar a lista de origens de dados por cada coluna.</span><span class="sxs-lookup"><span data-stu-id="11e4c-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11e4c-125">![Origem de dados adicionada](media/configure-data-datasource-added.png "Origem de dados adicionada")</span><span class="sxs-lookup"><span data-stu-id="11e4c-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="11e4c-126">Estado</span><span class="sxs-lookup"><span data-stu-id="11e4c-126">Status</span></span>  |<span data-ttu-id="11e4c-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="11e4c-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="11e4c-128">Êxito</span><span class="sxs-lookup"><span data-stu-id="11e4c-128">Successful</span></span>   |<span data-ttu-id="11e4c-129">A origem dos dados foi ingerida com sucesso se houver uma hora mencionada na coluna **Atualizada**.</span><span class="sxs-lookup"><span data-stu-id="11e4c-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="11e4c-130">Não iniciado</span><span class="sxs-lookup"><span data-stu-id="11e4c-130">Not started</span></span>   |<span data-ttu-id="11e4c-131">A origem dos dados ainda não tem dados ingeridos ou ainda está em modo de rascunho.</span><span class="sxs-lookup"><span data-stu-id="11e4c-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="11e4c-132">A atualizar</span><span class="sxs-lookup"><span data-stu-id="11e4c-132">Refreshing</span></span>    |<span data-ttu-id="11e4c-133">A ingestão de dados está em curso.</span><span class="sxs-lookup"><span data-stu-id="11e4c-133">Data ingestion is in progress.</span></span> <span data-ttu-id="11e4c-134">Poderá cancelar esta operação ao selecionar **Parar de atualizar** na coluna **Ações**.</span><span class="sxs-lookup"><span data-stu-id="11e4c-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="11e4c-135">Parar a atualização de um origem de dados irá revertê-lo para o último estado de atualização.</span><span class="sxs-lookup"><span data-stu-id="11e4c-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="11e4c-136">Falha</span><span class="sxs-lookup"><span data-stu-id="11e4c-136">Failed</span></span>     |<span data-ttu-id="11e4c-137">A ingestão de dados encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="11e4c-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="11e4c-138">Selecione o valor na coluna **Estado** de qualquer origem de dados para rever mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="11e4c-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="11e4c-139">No painel **Detalhes do progresso**, expanda **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="11e4c-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="11e4c-140">Selecione **Ver detalhes** para obter mais informações sobre o estado da atualização, incluindo detalhes de erro e atualizações do processo a jusante.</span><span class="sxs-lookup"><span data-stu-id="11e4c-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="11e4c-141">O carregamento dos dados pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="11e4c-141">Loading data can take some time.</span></span> <span data-ttu-id="11e4c-142">Após uma atualização bem-sucedida, os dados ingeridos podem ser revistos na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="11e4c-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="11e4c-143">Para mais informações, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="11e4c-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="11e4c-144">Atualizar uma origem de dados</span><span class="sxs-lookup"><span data-stu-id="11e4c-144">Refresh a data source</span></span>

<span data-ttu-id="11e4c-145">As origens de dados podem ser atualizadas com agendamento automático ou atualizadas manualmente a pedido.</span><span class="sxs-lookup"><span data-stu-id="11e4c-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="11e4c-146">Vá a **Admin** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações programadas de todas as suas origens de dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="11e4c-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="11e4c-147">Para atualizar uma origem de dados a pedido, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="11e4c-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="11e4c-148">Nas informações de audiência, vá a **Dados** > **Origens de dados**</span><span class="sxs-lookup"><span data-stu-id="11e4c-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="11e4c-149">Selecione a elipse vertical ao lado da origem dos dados que deseja atualizar e selecione **Atualizar** da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="11e4c-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="11e4c-150">A origem dos dados é agora ativada para uma atualização manual.</span><span class="sxs-lookup"><span data-stu-id="11e4c-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="11e4c-151">Atualizar uma origem de dados irá atualizar tanto o esquema da entidade como os dados para todas as entidades especificadas na origem de dados.</span><span class="sxs-lookup"><span data-stu-id="11e4c-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="11e4c-152">Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e a origem dos dados reverterá para o seu último estado de atualização.</span><span class="sxs-lookup"><span data-stu-id="11e4c-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="11e4c-153">Eliminar uma origem de dados</span><span class="sxs-lookup"><span data-stu-id="11e4c-153">Delete a data source</span></span>

1. <span data-ttu-id="11e4c-154">Em informações de audiência, aceda a **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="11e4c-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="11e4c-155">Selecione as reticências verticais junto à origem de dados que pretende remover e selecione **Eliminar** a partir do menu pendente.</span><span class="sxs-lookup"><span data-stu-id="11e4c-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="11e4c-156">Confirme a eliminação.</span><span class="sxs-lookup"><span data-stu-id="11e4c-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

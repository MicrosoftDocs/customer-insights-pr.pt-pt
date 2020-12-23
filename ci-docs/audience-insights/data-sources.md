---
title: Utilizar origens de dados para ingerir dados
description: Saiba como importar dados de várias origens.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643967"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="8727f-103">Descrição geral sobre origens de dados</span><span class="sxs-lookup"><span data-stu-id="8727f-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8727f-104">A capacidade de insights da audiência em Dynamics 365 Customer Insights liga-se a dados de um vasto conjunto de origens.</span><span class="sxs-lookup"><span data-stu-id="8727f-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="8727f-105">A ligação a um origem de dados é frequentemente referida como o processo de *ingestão de dados*.</span><span class="sxs-lookup"><span data-stu-id="8727f-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="8727f-106">Depois de ingerir os dados, pode [unificar](data-unification.md) e tomar medidas sobre os mesmos.</span><span class="sxs-lookup"><span data-stu-id="8727f-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="8727f-107">Adicionar uma origem de dados</span><span class="sxs-lookup"><span data-stu-id="8727f-107">Add a data source</span></span>

<span data-ttu-id="8727f-108">Consulte os artigos detalhados sobre como adicionar uma origem de dados, dependendo da opção que escolher.</span><span class="sxs-lookup"><span data-stu-id="8727f-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="8727f-109">Pode adicionar uma origem de dados de três formas principais:</span><span class="sxs-lookup"><span data-stu-id="8727f-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="8727f-110">Através de dezenas de conectores Power Query</span><span class="sxs-lookup"><span data-stu-id="8727f-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="8727f-111">A partir de uma pasta do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="8727f-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="8727f-112">A partir do seu próprio lake do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8727f-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="8727f-113">Ainda não é possível adicionar dados de origens de dados no local.</span><span class="sxs-lookup"><span data-stu-id="8727f-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="8727f-114">Rever dados ingeridos</span><span class="sxs-lookup"><span data-stu-id="8727f-114">Review ingested data</span></span>

<span data-ttu-id="8727f-115">Verá o nome de cada origem de dados ingerido, o seu estado, e a última vez que os dados foram atualizados para essa origem.</span><span class="sxs-lookup"><span data-stu-id="8727f-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="8727f-116">Pode ordenar a lista de origens de dados por cada coluna.</span><span class="sxs-lookup"><span data-stu-id="8727f-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8727f-117">![Origem de dados adicionada](media/configure-data-datasource-added.png "Origem de dados adicionada")</span><span class="sxs-lookup"><span data-stu-id="8727f-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="8727f-118">Estado</span><span class="sxs-lookup"><span data-stu-id="8727f-118">Status</span></span>  |<span data-ttu-id="8727f-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="8727f-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="8727f-120">Êxito</span><span class="sxs-lookup"><span data-stu-id="8727f-120">Successful</span></span>   |<span data-ttu-id="8727f-121">A origem dos dados foi ingerida com sucesso se houver uma hora mencionada na coluna **Atualizada**.</span><span class="sxs-lookup"><span data-stu-id="8727f-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="8727f-122">Não iniciado</span><span class="sxs-lookup"><span data-stu-id="8727f-122">Not started</span></span>   |<span data-ttu-id="8727f-123">A origem dos dados ainda não tem dados ingeridos ou ainda está em modo de rascunho.</span><span class="sxs-lookup"><span data-stu-id="8727f-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="8727f-124">A atualizar</span><span class="sxs-lookup"><span data-stu-id="8727f-124">Refreshing</span></span>    |<span data-ttu-id="8727f-125">A ingestão de dados está em curso.</span><span class="sxs-lookup"><span data-stu-id="8727f-125">Data ingestion is in progress.</span></span> <span data-ttu-id="8727f-126">Poderá cancelar esta operação ao selecionar **Parar de atualizar** na coluna **Ações**.</span><span class="sxs-lookup"><span data-stu-id="8727f-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="8727f-127">Parar a atualização de um origem de dados irá revertê-lo para o último estado de atualização.</span><span class="sxs-lookup"><span data-stu-id="8727f-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="8727f-128">Falha</span><span class="sxs-lookup"><span data-stu-id="8727f-128">Failed</span></span>     |<span data-ttu-id="8727f-129">A ingestão de dados encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="8727f-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="8727f-130">Selecione **Atualizar estado** para rever mais detalhes sobre o estado de atualização, incluindo detalhes de erro e atualizações do processo a jusante.</span><span class="sxs-lookup"><span data-stu-id="8727f-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="8727f-131">O carregamento dos dados pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="8727f-131">Loading data can take some time.</span></span> <span data-ttu-id="8727f-132">Após uma atualização bem-sucedida, os dados ingeridos podem ser revistos na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="8727f-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="8727f-133">Para mais informações, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="8727f-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="8727f-134">Atualizar uma origem de dados</span><span class="sxs-lookup"><span data-stu-id="8727f-134">Refresh a data source</span></span>

<span data-ttu-id="8727f-135">As origens de dados podem ser atualizadas com agendamento automático ou atualizadas manualmente a pedido.</span><span class="sxs-lookup"><span data-stu-id="8727f-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="8727f-136">Vá a **Admin** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações programadas de todas as suas origens de dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="8727f-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="8727f-137">Para atualizar uma origem de dados a pedido, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="8727f-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="8727f-138">Nas informações de audiência, vá a **Dados** > **Origens de dados**</span><span class="sxs-lookup"><span data-stu-id="8727f-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="8727f-139">Selecione a elipse vertical ao lado da origem dos dados que deseja atualizar e selecione **Atualizar** da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8727f-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="8727f-140">A origem dos dados é agora ativada para uma atualização manual.</span><span class="sxs-lookup"><span data-stu-id="8727f-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="8727f-141">A atualização de uma origem de dados atualizará tanto o esquema da entidade como os dados para todas as entidades especificadas na origem de dados.</span><span class="sxs-lookup"><span data-stu-id="8727f-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="8727f-142">Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e a origem dos dados reverterá para o seu último estado de atualização.</span><span class="sxs-lookup"><span data-stu-id="8727f-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="8727f-143">Eliminar uma origem de dados</span><span class="sxs-lookup"><span data-stu-id="8727f-143">Delete a data source</span></span>

1. <span data-ttu-id="8727f-144">Em informações de audiência, aceda a **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="8727f-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8727f-145">Selecione as reticências verticais junto à origem de dados que pretende remover e selecione **Eliminar** a partir do menu pendente.</span><span class="sxs-lookup"><span data-stu-id="8727f-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="8727f-146">Confirme a eliminação.</span><span class="sxs-lookup"><span data-stu-id="8727f-146">Confirm your deletion.</span></span>

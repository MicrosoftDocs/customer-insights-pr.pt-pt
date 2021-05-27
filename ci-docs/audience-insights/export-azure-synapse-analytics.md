---
title: Exportar dados do Customer Insights para a Análise do Azure Synapse
description: Aprenda a configurar a ligação e exportar para a Análise do Azure Synapse.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977391"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="c822c-103">Exportar dados para a Análise do Azure Synapse (Pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="c822c-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="c822c-104">O Azure Synapse é um serviço de análise que acelera o tempo para as informações através de armazéns de dados e sistemas de macrodados.</span><span class="sxs-lookup"><span data-stu-id="c822c-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="c822c-105">Pode ingerir e utilizar os seus dados do Customer Insights no [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="c822c-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c822c-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c822c-106">Prerequisites</span></span>

<span data-ttu-id="c822c-107">Os seguintes pré-requisitos têm de ser cumpridos para configurar a ligação do Customer Insights para o Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="c822c-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="c822c-108">Certifique-se de que define todas as **atribuições de funções**, conforme descrito.</span><span class="sxs-lookup"><span data-stu-id="c822c-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="c822c-109">Pré-requisitos no Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c822c-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="c822c-110">Tem uma função de **Administrador** nas informações de audiência.</span><span class="sxs-lookup"><span data-stu-id="c822c-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="c822c-111">Saiba mais sobre [definir permissões de utilizador em informações de audiência](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="c822c-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="c822c-112">No Azure:</span><span class="sxs-lookup"><span data-stu-id="c822c-112">In Azure:</span></span> 

- <span data-ttu-id="c822c-113">Uma subscrição ativa do Azure.</span><span class="sxs-lookup"><span data-stu-id="c822c-113">An active Azure subscription.</span></span>

- <span data-ttu-id="c822c-114">Se utilizar uma nova conta Azure Data Lake Storage Gen2, o *principal de serviço para informações de audiência* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="c822c-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="c822c-115">Saiba mais sobre [ligar a uma conta Azure Data Lake Storage Gen2 com o principal do serviço do Azure para informações de audiência](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c822c-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="c822c-116">O Data Lake Storage Gen2 **tem de ter** [espaço de nomes hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.</span><span class="sxs-lookup"><span data-stu-id="c822c-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="c822c-117">No grupo de recursos onde está localizada a área de trabalho do Azure Synapse, o *principal do serviço* e o *utilizador para as informações de audiência* precisam de ser atribuídas, pelo menos, as permissões de **Leitor**.</span><span class="sxs-lookup"><span data-stu-id="c822c-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="c822c-118">Para obter mais informações, consulte [Atribuir funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="c822c-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="c822c-119">O *utilizador* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="c822c-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="c822c-120">Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="c822c-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="c822c-121">A *[identidade gerida da área de trabalho do Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="c822c-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="c822c-122">Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="c822c-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="c822c-123">Na área de trabalho do Azure Synapse, o *principal do serviço para informações de audiência* precisa da função de **Administrador do Synapse** atribuída.</span><span class="sxs-lookup"><span data-stu-id="c822c-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="c822c-124">Para mais informações, consulte [Como configurar o controlo de acesso à sua área de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="c822c-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="c822c-125">Configure a ligação exporte para o Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="c822c-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="c822c-126">Configurar uma ligação</span><span class="sxs-lookup"><span data-stu-id="c822c-126">Configure a connection</span></span>

1. <span data-ttu-id="c822c-127">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="c822c-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c822c-128">Selecione **Adicionar ligação** e escolha a **Análise do Azure Synapse** para selecionar **Configurar** no mosaico **Análise do Azure Synapse** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="c822c-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="c822c-129">Forneça um nome reconhecível à ligação no campo Nome a apresentar.</span><span class="sxs-lookup"><span data-stu-id="c822c-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="c822c-130">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="c822c-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="c822c-131">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="c822c-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c822c-132">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="c822c-132">Choose who can use this connection.</span></span> <span data-ttu-id="c822c-133">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="c822c-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c822c-134">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c822c-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c822c-135">Selecione ou procure a subscrição em que pretende utilizar os dados do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c822c-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="c822c-136">Assim que uma subscrição for selecionada, também pode selecionar **Área de Trabalho**, **Conta de armazenamento** e **Contentor**.</span><span class="sxs-lookup"><span data-stu-id="c822c-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="c822c-137">Selecione **Guardar** para guardar a ligação.</span><span class="sxs-lookup"><span data-stu-id="c822c-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="c822c-138">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="c822c-138">Configure an export</span></span>

<span data-ttu-id="c822c-139">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="c822c-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c822c-140">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c822c-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c822c-141">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c822c-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c822c-142">Para criar um nova exportação, selecione **Adicionar exportação**.</span><span class="sxs-lookup"><span data-stu-id="c822c-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c822c-143">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção **Análise do Azure Synapse**.</span><span class="sxs-lookup"><span data-stu-id="c822c-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="c822c-144">Se não vir este nome de secção, não existem [ligações](connections.md) deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="c822c-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="c822c-145">Forneça um **Nome a apresentar** reconhecível para a sua exportação e um **Nome de base de dados**.</span><span class="sxs-lookup"><span data-stu-id="c822c-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="c822c-146">Selecione que entidades pretende exportar para a Análise do Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="c822c-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="c822c-147">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c822c-147">Select **Save**.</span></span>

<span data-ttu-id="c822c-148">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c822c-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c822c-149">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c822c-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c822c-150">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c822c-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="c822c-151">Atualizar uma exportação</span><span class="sxs-lookup"><span data-stu-id="c822c-151">Update an export</span></span>

1. <span data-ttu-id="c822c-152">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c822c-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c822c-153">Selecione **Editar** na exportação que quer atualizar.</span><span class="sxs-lookup"><span data-stu-id="c822c-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="c822c-154">**Adicione** ou **Remova** entidades da seleção.</span><span class="sxs-lookup"><span data-stu-id="c822c-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="c822c-155">Se as entidades forem removidas da seleção, não são eliminadas da base de dados da Análise do Synapse.</span><span class="sxs-lookup"><span data-stu-id="c822c-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="c822c-156">No entanto, futuras atualizações de dados não atualizarão as entidades removidas nessa base de dados.</span><span class="sxs-lookup"><span data-stu-id="c822c-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="c822c-157">**Alterar o Nome da Base de Dados** cria uma nova base de dados de Análise do Synapse.</span><span class="sxs-lookup"><span data-stu-id="c822c-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="c822c-158">A base de dados com o nome que foi configurado anteriormente não receberá quaisquer atualizações em futuras atualizações.</span><span class="sxs-lookup"><span data-stu-id="c822c-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>

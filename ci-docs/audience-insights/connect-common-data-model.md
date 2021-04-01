---
title: Ligue os dados Common Data Model a uma conta Azure Data Lake
description: Trabalhe com dados do Common Data Model utilizando Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596559"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="21e4b-103">Ligar a uma pasta do Common Data Model com uma conta Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="21e4b-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="21e4b-104">Este artigo fornece informações sobre como ingerir dados a partir de uma pasta Common Data Model utilizando a sua conta Gen2 Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="21e4b-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="21e4b-105">Considerações importantes</span><span class="sxs-lookup"><span data-stu-id="21e4b-105">Important considerations</span></span>

- <span data-ttu-id="21e4b-106">Os dados existentes no seu Azure Data Lake têm de seguir o padrão do Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="21e4b-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="21e4b-107">De momento, não há suporte para outros formatos.</span><span class="sxs-lookup"><span data-stu-id="21e4b-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="21e4b-108">A ingestão de dados suporta exclusivamente as contas de armazenamento do Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="21e4b-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="21e4b-109">Não pode usar as contas de armazenamento do Azure Data Lake Gen1 para ingerir dados.</span><span class="sxs-lookup"><span data-stu-id="21e4b-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="21e4b-110">Para autenticar com um principal de serviço da Azure, certifique-se de que está configurado no seu inquilino.</span><span class="sxs-lookup"><span data-stu-id="21e4b-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="21e4b-111">Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="21e4b-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="21e4b-112">O Azure Data Lake a que se quer conectar e do qual pretende ingerir dados tem de ser na mesma região do Azure que o ambiente Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21e4b-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="21e4b-113">As ligações a uma pasta Common Data Model a partir de um data lake numa região do Azure diferente não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="21e4b-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="21e4b-114">Para conhecer a região do Azure do ambiente, vá a **Admin** > **Sistema** > **Sobre** informações da audiência.</span><span class="sxs-lookup"><span data-stu-id="21e4b-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="21e4b-115">Os dados armazenados em serviços online podem ser armazenados numa localização diferente do local onde os dados são tratados ou armazenados em Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21e4b-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="21e4b-116"> Ao importar, ou ligar a, os dados armazenados em serviços online, como o , concorda que os dados podem ser transferidos para, e armazenados com o Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="21e4b-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="21e4b-117">Ligar a uma pasta do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="21e4b-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="21e4b-118">Em informações de audiência, aceda a **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="21e4b-119">Selecione **Adicionar origem de dados**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="21e4b-120">Selecione **Ligar a uma pasta Common Data Model**, introduza um **Nome** para a origem de dados e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="21e4b-121">Nomear diretrizes:</span><span class="sxs-lookup"><span data-stu-id="21e4b-121">Name guidelines:</span></span> 
   - <span data-ttu-id="21e4b-122">Comece com uma letra.</span><span class="sxs-lookup"><span data-stu-id="21e4b-122">Start with a letter.</span></span>
   - <span data-ttu-id="21e4b-123">Utilize apenas letras e números.</span><span class="sxs-lookup"><span data-stu-id="21e4b-123">Use letters and numbers only.</span></span> <span data-ttu-id="21e4b-124">Não são permitidos carateres especiais e espaços.</span><span class="sxs-lookup"><span data-stu-id="21e4b-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="21e4b-125">Utilize entre 3 e 64 carateres.</span><span class="sxs-lookup"><span data-stu-id="21e4b-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="21e4b-126">Pode escolher entre usar uma opção baseada em recursos e uma opção baseada em subscrição para autenticação.</span><span class="sxs-lookup"><span data-stu-id="21e4b-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="21e4b-127">Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="21e4b-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="21e4b-128">Introduza as informações do **Recipiente** e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="21e4b-129">![Caixa de diálogo para introduzir detalhes da nova ligação para o Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="21e4b-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="21e4b-130">Precisa de uma das seguintes funções, quer no recipiente, quer na conta de armazenamento acima referida, para poder ligar-se e criar uma origem de dados:</span><span class="sxs-lookup"><span data-stu-id="21e4b-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="21e4b-131">Leitor de Dados de Blobs de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="21e4b-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="21e4b-132">Proprietário de Dados de Blobs de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="21e4b-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="21e4b-133">Contribuidor de Dados de Blobs de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="21e4b-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="21e4b-134">No diálogo **Selecionar uma pasta Common Data Model**, selecione o ficheiro model.json ou manifest.json para importar dados e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="21e4b-135">Qualquer ficheiro model.json ou manifest.json associado a outra origem de dados no ambiente não aparecerá na lista.</span><span class="sxs-lookup"><span data-stu-id="21e4b-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="21e4b-136">Irá receber uma lista de entidades disponíveis no ficheiro model.json ou manifest.json selecionado.</span><span class="sxs-lookup"><span data-stu-id="21e4b-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="21e4b-137">Pode rever e selecionae da lista de entidades disponíveis e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="21e4b-138">Todas as entidades selecionadas serão ingeridas a partir da nova origem de dados.</span><span class="sxs-lookup"><span data-stu-id="21e4b-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="21e4b-139">![Caixa de diálogo que mostra uma lista de entidades a partir de um ficheiro model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="21e4b-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="21e4b-140">Indique as entidades de dados para as quais pretende ativar a criação de perfis de dados e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="21e4b-141">A criação de perfis de dados permite utilizar análise e outras capacidades.</span><span class="sxs-lookup"><span data-stu-id="21e4b-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="21e4b-142">Pode selecionar toda a entidade, o que seleciona todos os atributos da entidade, ou selecionar certos atributos à sua escolha.</span><span class="sxs-lookup"><span data-stu-id="21e4b-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="21e4b-143">Por defeito, nenhuma entidade está habilitada para a criação de perfis de dados.</span><span class="sxs-lookup"><span data-stu-id="21e4b-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="21e4b-144">![Caixa de diálogo que mostra a criação de perfis de dados](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="21e4b-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="21e4b-145">Depois de guardar as seleções, é aberta a página **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="21e4b-146">Deverá ver agora a ligação de pasta do Common Data Model como uma origem de dados.</span><span class="sxs-lookup"><span data-stu-id="21e4b-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="21e4b-147">Um ficheiro model.json ou manifest.json só pode associar-se a um origem de dados no mesmo ambiente.</span><span class="sxs-lookup"><span data-stu-id="21e4b-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="21e4b-148">No entanto, o mesmo ficheiro model.json ou manifest.json pode ser usado para origens de dados em vários ambientes.</span><span class="sxs-lookup"><span data-stu-id="21e4b-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="21e4b-149">Editar uma origem de dados do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="21e4b-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="21e4b-150">Pode atualizar a chave de acesso para a conta de armazenamento que contém a pasta Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="21e4b-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="21e4b-151">Também pode alterar o ficheiro model.json ou manifest.json.</span><span class="sxs-lookup"><span data-stu-id="21e4b-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="21e4b-152">Para ligar a um contentor diferente da conta de armazenamento ou alterar o nome da conta, tem de [criar uma nova ligação à origem de dados](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="21e4b-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="21e4b-153">Em informações de audiência, aceda a **Dados** > **Origens de dados**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="21e4b-154">Junto da origem de dados que pretende atualizar, selecione as reticências.</span><span class="sxs-lookup"><span data-stu-id="21e4b-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="21e4b-155">Selecione a opção **Editar** da lista.</span><span class="sxs-lookup"><span data-stu-id="21e4b-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="21e4b-156">Opcionalmente, atualize a **Chave de acesso** e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="21e4b-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Diálogo para editar e atualizar uma tecla de acesso para uma origem de dados existente](media/edit-access-key.png)

5. <span data-ttu-id="21e4b-158">Opcionalmente, pode atualizar a partir de uma ligação chave de conta a uma ligação baseada em recursos ou baseada em subscrição.</span><span class="sxs-lookup"><span data-stu-id="21e4b-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="21e4b-159">Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="21e4b-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="21e4b-160">Não é possível alterar as informações do **Recipiente** ao atualizar a ligação.</span><span class="sxs-lookup"><span data-stu-id="21e4b-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Caixa de diálogo para introduzir detalhes de ligação para o Azure Data Lake para uma conta de armazenamento existente](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="21e4b-162">Precisa de uma das seguintes funções, quer no recipiente, quer na conta de armazenamento acima referida, para poder ligar-se e criar uma origem de dados:</span><span class="sxs-lookup"><span data-stu-id="21e4b-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="21e4b-163">Leitor de Dados de Blobs de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="21e4b-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="21e4b-164">Proprietário de Dados de Blobs de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="21e4b-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="21e4b-165">Contribuidor de Dados de Blobs de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="21e4b-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="21e4b-166">Opcionalmente, escolha outro ficheiro model.json ou manifest.json com um conjunto diferente de entidades do recipiente.</span><span class="sxs-lookup"><span data-stu-id="21e4b-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="21e4b-167">Opcionalmente, pode selecionar entidades adicionais para ingerir.</span><span class="sxs-lookup"><span data-stu-id="21e4b-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="21e4b-168">Também pode remover quaisquer entidades já selecionadas se não houver dependências.</span><span class="sxs-lookup"><span data-stu-id="21e4b-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="21e4b-169">Se houver dependências do ficheiro model.json ou manifest.json existente e do conjunto de entidades, verá uma mensagem de erro e não poderá selecionar um ficheiro model.json ou manifest.json diferente.</span><span class="sxs-lookup"><span data-stu-id="21e4b-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="21e4b-170">Remova essas dependências antes de alterar o ficheiro model.json ou manifest.json ou criar uma nova origem de dados com o ficheiro model.json ou manifest.json que pretende utilizar para evitar a remoção das dependências.</span><span class="sxs-lookup"><span data-stu-id="21e4b-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="21e4b-171">Opcionalmente, pode selecionar atributos ou entidades adicionais para possibilitar a criação de perfis de dados ou desativar os já selecionados.</span><span class="sxs-lookup"><span data-stu-id="21e4b-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]
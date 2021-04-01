---
title: Criar e gerir ambientes
description: Saiba como se inscrever no serviço e como gerir ambientes.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598307"
---
# <a name="manage-environments"></a><span data-ttu-id="5559e-103">Gerir ambientes</span><span class="sxs-lookup"><span data-stu-id="5559e-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5559e-104">Este artigo explica como criar uma nova organização e como providenciar um ambiente.</span><span class="sxs-lookup"><span data-stu-id="5559e-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="5559e-105">Inscreva-se e crie uma organização</span><span class="sxs-lookup"><span data-stu-id="5559e-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="5559e-106">Aceder ao site [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="5559e-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="5559e-107">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="5559e-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="5559e-108">Escolha o cenário de inscrição preferencial e selecione a ligação correspondente.</span><span class="sxs-lookup"><span data-stu-id="5559e-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="5559e-109">Aceite os termos e condições e selecione **Continuar** para começar a criar a organização.</span><span class="sxs-lookup"><span data-stu-id="5559e-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="5559e-110">Após a criação do ambiente, será redirecionado para o [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="5559e-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="5559e-111">Use o ambiente de demonstração para explorar a aplicação ou crie um novo ambiente seguindo os passos na secção seguinte.</span><span class="sxs-lookup"><span data-stu-id="5559e-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="5559e-112">Depois de especificar as definições de ambiente, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="5559e-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="5559e-113">Será registado depois de o ambiente ter sido criado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="5559e-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="5559e-114">Criar um ambiente numa organização existente</span><span class="sxs-lookup"><span data-stu-id="5559e-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="5559e-115">Existem duas formas de criar um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="5559e-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="5559e-116">Pode especificar uma configuração totalmente nova ou pode copiar algumas definições de configuração a partir de um ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="5559e-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="5559e-117">Para criar um ambiente:</span><span class="sxs-lookup"><span data-stu-id="5559e-117">To create an environment:</span></span>

1. <span data-ttu-id="5559e-118">Selecione o seletor **Ambiente** no cabeçalho da aplicação.</span><span class="sxs-lookup"><span data-stu-id="5559e-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="5559e-119">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5559e-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5559e-120">![Definições de ambiente](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="5559e-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="5559e-121">No diálogo **Criar novo ambiente**, selecione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="5559e-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="5559e-122">Se pretender [copiar dados do ambiente atual](#additional-considerations-for-copy-configuration-preview), selecione **Copiar do ambiente atual**.</span><span class="sxs-lookup"><span data-stu-id="5559e-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="5559e-123">Verá uma lista de todos os ambientes disponíveis na sua organização de onde pode copiar dados.</span><span class="sxs-lookup"><span data-stu-id="5559e-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="5559e-124">Forneça os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="5559e-124">Provide the following details:</span></span>
   - <span data-ttu-id="5559e-125">**Nome**: O nome para este ambiente.</span><span class="sxs-lookup"><span data-stu-id="5559e-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="5559e-126">Este campo já está preenchido se copiou de um ambiente existente, mas pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="5559e-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="5559e-127">**Região**: a região na qual o serviço é implementado e hospedado.</span><span class="sxs-lookup"><span data-stu-id="5559e-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="5559e-128">**Tipo**: selecione se pretende criar um ambiente de Produção ou Sandbox.</span><span class="sxs-lookup"><span data-stu-id="5559e-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="5559e-129">Opcionalmente, pode selecionar **Definições avançadas**:</span><span class="sxs-lookup"><span data-stu-id="5559e-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="5559e-130">**Guardar todos os dados para**: Especifica onde pretende armazenar os dados de saída gerados a partir do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5559e-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="5559e-131">Terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerido pela equipa do Customer Insights) e **Azure Data Lake Storage Gen2** (o seu próprio Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="5559e-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="5559e-132">Por predefinição, a opção de armazenamento do Customer Insights está selecionada.</span><span class="sxs-lookup"><span data-stu-id="5559e-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5559e-133">Ao guardar dados no Azure Data Lake Storage, aceita que os dados serão transferidos e armazenados na localização geográfica adequada para essa apropriada para essa conta de armazenamento do Azure, que pode ser diferente daquela na qual os dados estão armazenados no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5559e-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="5559e-134">Saber mais no Centro de Fidedignidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5559e-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="5559e-135">Atualmente, as entidades incluídas são sempre armazenadas no data Lake gerido pelo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5559e-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="5559e-136">Apoiamos apenas contas de armazenamento Azure Data Lake Gen2 da mesma região Azure que selecionou ao criar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="5559e-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="5559e-137">Só oferecemos suporte a contas de armazenamento com o Espaço de Nome Hierárquico (HNS) do Azure Data Lake Gen2 ativadas.</span><span class="sxs-lookup"><span data-stu-id="5559e-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="5559e-138">Para a opção Azure Data Lake Storage Gen2, pode escolher entre uma opção baseada em recursos e uma opção baseada em subscrições para autenticação.</span><span class="sxs-lookup"><span data-stu-id="5559e-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="5559e-139">Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="5559e-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="5559e-140">O nome do **Recepiente** não pode ser alterado e será "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="5559e-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="5559e-141">Se pretender utilizar [predições](predictions.md) ou configurar a partilha de dados com aplicações e soluções baseadas no Microsoft Dataverse, forneça o URL do ambiente Microsoft Dataverse em **Configurar a partilha de dados com o Microsoft Dataverse e ativar capacidades adicionais**.</span><span class="sxs-lookup"><span data-stu-id="5559e-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="5559e-142">Selecione **Ativar partilha de dados** para partilhar dados de saída do Customer Insights com um Data Lake Gerido do Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5559e-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="5559e-143">A partilha de dados com o Data Lake Gerido do Microsoft Dataverse não é atualmente suportada quando guarda todos os dados para o seu próprio Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5559e-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="5559e-144">[Predição de valores em falta numa entidade](predictions.md) não é atualmente suportado quando ativa a partilha de dados com o Data Lake Gerido do Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5559e-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="5559e-145">![Opções de configuração para ativar a partilha de dados com o Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="5559e-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="5559e-146">Quando executa processos, tais como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento que especificou acima.</span><span class="sxs-lookup"><span data-stu-id="5559e-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="5559e-147">Os ficheiros de dados e os ficheiros model.json serão criados e adicionados às respetivas subpastas com base no processo que é executado.</span><span class="sxs-lookup"><span data-stu-id="5559e-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="5559e-148">Se criar vários ambientes de Customer Insights e optar por guardar as entidades de saída desses ambientes na sua conta de armazenamento, serão criadas pastas separadas para cada ambiente com ci_<environmentid> no recipiente.</span><span class="sxs-lookup"><span data-stu-id="5559e-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="5559e-149">Considerações adicionais para a configuração da cópia (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="5559e-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="5559e-150">As seguintes definições de configuração são copiadas:</span><span class="sxs-lookup"><span data-stu-id="5559e-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="5559e-151">Configurações de funcionalidades</span><span class="sxs-lookup"><span data-stu-id="5559e-151">Feature configurations</span></span>
- <span data-ttu-id="5559e-152">Origens de dados ingeridas/importadas</span><span class="sxs-lookup"><span data-stu-id="5559e-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="5559e-153">Configuração de unificação de dados (Mapa, Corresponder, Unir)</span><span class="sxs-lookup"><span data-stu-id="5559e-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="5559e-154">Segmentos</span><span class="sxs-lookup"><span data-stu-id="5559e-154">Segments</span></span>
- <span data-ttu-id="5559e-155">Medições</span><span class="sxs-lookup"><span data-stu-id="5559e-155">Measures</span></span>
- <span data-ttu-id="5559e-156">Relações</span><span class="sxs-lookup"><span data-stu-id="5559e-156">Relationships</span></span>
- <span data-ttu-id="5559e-157">Atividades</span><span class="sxs-lookup"><span data-stu-id="5559e-157">Activities</span></span>
- <span data-ttu-id="5559e-158">Índice de pesquisas e filtros</span><span class="sxs-lookup"><span data-stu-id="5559e-158">Search & filter Index</span></span>
- <span data-ttu-id="5559e-159">Destinos de exportação</span><span class="sxs-lookup"><span data-stu-id="5559e-159">Export destinations</span></span>
- <span data-ttu-id="5559e-160">Atualização agendada</span><span class="sxs-lookup"><span data-stu-id="5559e-160">Scheduled refresh</span></span>
- <span data-ttu-id="5559e-161">Melhoramentos</span><span class="sxs-lookup"><span data-stu-id="5559e-161">Enrichments</span></span>
- <span data-ttu-id="5559e-162">Gestão de modelos</span><span class="sxs-lookup"><span data-stu-id="5559e-162">Model management</span></span>
- <span data-ttu-id="5559e-163">Atribuições de funções</span><span class="sxs-lookup"><span data-stu-id="5559e-163">Role assignments</span></span>

<span data-ttu-id="5559e-164">As seguintes definições *não* são copiadas:</span><span class="sxs-lookup"><span data-stu-id="5559e-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="5559e-165">Perfis de cliente.</span><span class="sxs-lookup"><span data-stu-id="5559e-165">Customer profiles.</span></span>
- <span data-ttu-id="5559e-166">Credenciais da origem de dados.</span><span class="sxs-lookup"><span data-stu-id="5559e-166">Data source credentials.</span></span> <span data-ttu-id="5559e-167">Terá de fornecer as credenciais para cada origem de dados e atualizar manualmente as origens de dados.</span><span class="sxs-lookup"><span data-stu-id="5559e-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="5559e-168">Origens de dados da pasta modelo do Common Data Model e Lake gerido do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5559e-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="5559e-169">Terá de criar manualmente essas origens de dados com o mesmo nome que no ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="5559e-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="5559e-170">Quando copia um ambiente, verá uma mensagem de confirmação de que o novo ambiente foi criado.</span><span class="sxs-lookup"><span data-stu-id="5559e-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="5559e-171">Selecione **Ir para origens de dados** para ver a lista de origens de dados.</span><span class="sxs-lookup"><span data-stu-id="5559e-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="5559e-172">Todas as origens de dados apresentarão um estado de **Credenciais Obrigatórias**.</span><span class="sxs-lookup"><span data-stu-id="5559e-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="5559e-173">Edite as origens de dados e introduza as credenciais para as atualizar.</span><span class="sxs-lookup"><span data-stu-id="5559e-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5559e-174">![Origens de dados copiadas](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="5559e-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="5559e-175">Depois de atualizar as fontes de dados, aceda ao **Dados** > **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="5559e-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="5559e-176">Aqui encontrará definições do ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="5559e-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="5559e-177">Edite-as conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="5559e-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="5559e-178">Quando a unificação de dados estiver concluída, aceda a **Medidas** e **Segmentos** para atualizá-los também.</span><span class="sxs-lookup"><span data-stu-id="5559e-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="5559e-179">Editar um ambiente existente</span><span class="sxs-lookup"><span data-stu-id="5559e-179">Edit an existing environment</span></span>

<span data-ttu-id="5559e-180">Pode editar alguns dos detalhes de ambientes existentes.</span><span class="sxs-lookup"><span data-stu-id="5559e-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="5559e-181">Selecione o seletor **Ambiente** no cabeçalho da aplicação.</span><span class="sxs-lookup"><span data-stu-id="5559e-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="5559e-182">Selecione o ícone **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5559e-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="5559e-183">Na caixa **Editar ambiente** pode atualizar o **Nome a apresentar** do ambiente, mas não pode alterar a **Região** ou o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="5559e-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="5559e-184">Se um ambiente estiver configurado para armazenar dados no Azure Data Lake Storage Gen2, poderá atualizar a **Chave da conta**.</span><span class="sxs-lookup"><span data-stu-id="5559e-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="5559e-185">No entanto, não é possível alterar o **Nome da conta** ou do **Recipiente**.</span><span class="sxs-lookup"><span data-stu-id="5559e-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="5559e-186">Opcionalmente, pode atualizar a partir de uma ligação baseada em chave de conta para uma ligação baseada em recursos ou em subscrição.</span><span class="sxs-lookup"><span data-stu-id="5559e-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="5559e-187">Uma vez atualizado, não se pode voltar à chave de conta após a atualização.</span><span class="sxs-lookup"><span data-stu-id="5559e-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="5559e-188">Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="5559e-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="5559e-189">Não é possível alterar as informações do **Recipiente** ao atualizar a ligação.</span><span class="sxs-lookup"><span data-stu-id="5559e-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="5559e-190">Repor um ambiente existente</span><span class="sxs-lookup"><span data-stu-id="5559e-190">Reset an existing environment</span></span>

<span data-ttu-id="5559e-191">Como administrador, pode repor um ambiente para um estado vazio se quiser eliminar todas as configurações e remover os dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="5559e-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="5559e-192">Selecione o seletor **Ambiente** no cabeçalho da aplicação.</span><span class="sxs-lookup"><span data-stu-id="5559e-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="5559e-193">Selecione o ambiente que pretende repor e selecione as reticências **...**.</span><span class="sxs-lookup"><span data-stu-id="5559e-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="5559e-194">Escolha a opção **Repor**.</span><span class="sxs-lookup"><span data-stu-id="5559e-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="5559e-195">Para confirmar a eliminação, introduza o nome do ambiente e selecione **Repor**.</span><span class="sxs-lookup"><span data-stu-id="5559e-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="5559e-196">Eliminar um ambiente existente (disponível apenas para admins)</span><span class="sxs-lookup"><span data-stu-id="5559e-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="5559e-197">Como administrador, pode eliminar um ambiente que administra.</span><span class="sxs-lookup"><span data-stu-id="5559e-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="5559e-198">Selecione o seletor **Ambiente** no cabeçalho da aplicação.</span><span class="sxs-lookup"><span data-stu-id="5559e-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="5559e-199">Selecione o ambiente que pretende repor e selecione as reticências **...**.</span><span class="sxs-lookup"><span data-stu-id="5559e-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="5559e-200">Escolha a opção **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5559e-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="5559e-201">Para confirmar a eliminação, introduza o nome do ambiente e selecione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5559e-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
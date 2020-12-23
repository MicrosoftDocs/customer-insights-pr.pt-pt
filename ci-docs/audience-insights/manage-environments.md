---
title: Criar e gerir ambientes
description: Saiba como se inscrever no serviço e como gerir ambientes.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644147"
---
# <a name="manage-environments"></a><span data-ttu-id="34037-103">Gerir ambientes</span><span class="sxs-lookup"><span data-stu-id="34037-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="34037-104">Este artigo explica como criar uma nova organização e como providenciar um ambiente.</span><span class="sxs-lookup"><span data-stu-id="34037-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="34037-105">Inscreva-se e crie uma organização</span><span class="sxs-lookup"><span data-stu-id="34037-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="34037-106">Aceder ao site [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="34037-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="34037-107">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="34037-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="34037-108">Escolha o cenário de inscrição preferencial e selecione a ligação correspondente.</span><span class="sxs-lookup"><span data-stu-id="34037-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="34037-109">Aceite os termos e condições e selecione **Continuar** para começar a criar a organização.</span><span class="sxs-lookup"><span data-stu-id="34037-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="34037-110">Após a criação do ambiente, será redirecionado para o [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="34037-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="34037-111">Use o ambiente de demonstração para explorar a aplicação ou crie um novo ambiente seguindo os passos na secção seguinte.</span><span class="sxs-lookup"><span data-stu-id="34037-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="34037-112">Depois de especificar as definições de ambiente, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="34037-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="34037-113">Será registado depois de o ambiente ter sido criado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="34037-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="34037-114">Criar um ambiente numa organização existente</span><span class="sxs-lookup"><span data-stu-id="34037-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="34037-115">Existem duas formas de criar um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="34037-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="34037-116">Pode especificar uma configuração totalmente nova ou pode copiar algumas definições de configuração a partir de um ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="34037-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="34037-117">Para criar um ambiente:</span><span class="sxs-lookup"><span data-stu-id="34037-117">To create an environment:</span></span>

1. <span data-ttu-id="34037-118">Selecione o símbolo de **Definições** no cabeçalho da aplicação.</span><span class="sxs-lookup"><span data-stu-id="34037-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="34037-119">Selecione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="34037-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34037-120">![Definições de ambiente](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="34037-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="34037-121">No diálogo **Criar novo ambiente**, selecione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="34037-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="34037-122">Se pretender [copiar dados do ambiente atual](#additional-considerations-for-copy-configuration-preview), selecione **Copiar do ambiente atual**.</span><span class="sxs-lookup"><span data-stu-id="34037-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="34037-123">Verá uma lista de todos os ambientes disponíveis na sua organização de onde pode copiar dados.</span><span class="sxs-lookup"><span data-stu-id="34037-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="34037-124">Forneça os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="34037-124">Provide the following details:</span></span>
   - <span data-ttu-id="34037-125">**Nome**: O nome para este ambiente.</span><span class="sxs-lookup"><span data-stu-id="34037-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="34037-126">Este campo já está preenchido se copiou de um ambiente existente, mas pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="34037-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="34037-127">**Região**: a região na qual o serviço é implementado e hospedado.</span><span class="sxs-lookup"><span data-stu-id="34037-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="34037-128">**Tipo**: selecione se pretende criar um ambiente de Produção ou Sandbox.</span><span class="sxs-lookup"><span data-stu-id="34037-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="34037-129">Opcionalmente, pode selecionar **Definições avançadas**:</span><span class="sxs-lookup"><span data-stu-id="34037-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="34037-130">**Guardar todos os dados para**: Especifica onde pretende armazenar os dados de saída gerados a partir do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34037-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="34037-131">Terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerido pela equipa do Customer Insights) e **Azure Data Lake Storage Gen2** (o seu próprio Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="34037-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="34037-132">Por predefinição, a opção de armazenamento do Customer Insights está selecionada.</span><span class="sxs-lookup"><span data-stu-id="34037-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="34037-133">Ao guardar dados no Azure Data Lake Storage, aceita que os dados serão transferidos e armazenados na localização geográfica adequada para essa apropriada para essa conta de armazenamento do Azure, que pode ser diferente daquela na qual os dados estão armazenados no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34037-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="34037-134">Saber mais no Centro de Fidedignidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34037-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="34037-135">Atualmente, as entidades incluídas são sempre armazenadas no data Lake gerido pelo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34037-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="34037-136">Apoiamos apenas contas de armazenamento Azure Data Lake Gen2 da mesma região Azure que selecionou ao criar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="34037-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="34037-137">Só oferecemos suporte a contas de armazenamento com o Espaço de Nome Hierárquico (HNS) do Azure Data Lake Gen2 ativadas.</span><span class="sxs-lookup"><span data-stu-id="34037-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="34037-138">Para a opção Azure Data Lake Storage Gen2, pode escolher entre uma opção baseada em recursos e uma opção baseada em subscrições para autenticação.</span><span class="sxs-lookup"><span data-stu-id="34037-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="34037-139">Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="34037-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="34037-140">O nome do **Recepiente** não pode ser alterado e será "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="34037-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="34037-141">Se quiser usar [predições](predictions.md), introduza o URL da instância Common Data Service no campo **endereço do servidor** em **Usar predições**.</span><span class="sxs-lookup"><span data-stu-id="34037-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="34037-142">Quando executa processos, tais como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento que especificou acima.</span><span class="sxs-lookup"><span data-stu-id="34037-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="34037-143">Os ficheiros de dados e os ficheiros model.json serão criados e adicionados às respetivas subpastas com base no processo que é executado.</span><span class="sxs-lookup"><span data-stu-id="34037-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="34037-144">Se criar vários ambientes de Customer Insights e optar por guardar as entidades de saída desses ambientes na sua conta de armazenamento, serão criadas pastas separadas para cada ambiente com ci_<environmentid> no recipiente.</span><span class="sxs-lookup"><span data-stu-id="34037-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="34037-145">Considerações adicionais para a configuração da cópia (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="34037-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="34037-146">As seguintes definições de configuração são copiadas:</span><span class="sxs-lookup"><span data-stu-id="34037-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="34037-147">Configurações de funcionalidades</span><span class="sxs-lookup"><span data-stu-id="34037-147">Feature configurations</span></span>
- <span data-ttu-id="34037-148">Fontes de dados ingeridas/importadas</span><span class="sxs-lookup"><span data-stu-id="34037-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="34037-149">Configuração de unificação de dados (Mapa, Corresponder, Unir)</span><span class="sxs-lookup"><span data-stu-id="34037-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="34037-150">Segmentos</span><span class="sxs-lookup"><span data-stu-id="34037-150">Segments</span></span>
- <span data-ttu-id="34037-151">Medições</span><span class="sxs-lookup"><span data-stu-id="34037-151">Measures</span></span>
- <span data-ttu-id="34037-152">Relações</span><span class="sxs-lookup"><span data-stu-id="34037-152">Relationships</span></span>
- <span data-ttu-id="34037-153">Atividades</span><span class="sxs-lookup"><span data-stu-id="34037-153">Activities</span></span>
- <span data-ttu-id="34037-154">Índice de pesquisas e filtros</span><span class="sxs-lookup"><span data-stu-id="34037-154">Search & filter Index</span></span>
- <span data-ttu-id="34037-155">Destinos de exportação</span><span class="sxs-lookup"><span data-stu-id="34037-155">Export destinations</span></span>
- <span data-ttu-id="34037-156">Atualização agendada</span><span class="sxs-lookup"><span data-stu-id="34037-156">Scheduled refresh</span></span>
- <span data-ttu-id="34037-157">Melhoramentos</span><span class="sxs-lookup"><span data-stu-id="34037-157">Enrichments</span></span>
- <span data-ttu-id="34037-158">Gestão de modelos</span><span class="sxs-lookup"><span data-stu-id="34037-158">Model management</span></span>
- <span data-ttu-id="34037-159">Atribuições de funções</span><span class="sxs-lookup"><span data-stu-id="34037-159">Role assignments</span></span>

<span data-ttu-id="34037-160">As seguintes definições *não* são copiadas:</span><span class="sxs-lookup"><span data-stu-id="34037-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="34037-161">Perfis de cliente.</span><span class="sxs-lookup"><span data-stu-id="34037-161">Customer profiles.</span></span>
- <span data-ttu-id="34037-162">Credenciais da origem de dados.</span><span class="sxs-lookup"><span data-stu-id="34037-162">Data source credentials.</span></span> <span data-ttu-id="34037-163">Terá de fornecer as credenciais para cada origem de dados e atualizar manualmente as origens de dados.</span><span class="sxs-lookup"><span data-stu-id="34037-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="34037-164">Origens de dados da pasta modelo do Common Data Model e Lake gerido do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34037-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="34037-165">Terá de criar manualmente essas origens de dados com o mesmo nome que no ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="34037-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="34037-166">Quando copia um ambiente, verá uma mensagem de confirmação de que o novo ambiente foi criado.</span><span class="sxs-lookup"><span data-stu-id="34037-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="34037-167">Selecione **Ir para origens de dados** para ver a lista de origens de dados.</span><span class="sxs-lookup"><span data-stu-id="34037-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="34037-168">Todas as origens de dados apresentarão um estado de **Credenciais Obrigatórias**.</span><span class="sxs-lookup"><span data-stu-id="34037-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="34037-169">Edite as origens de dados e introduza as credenciais para as atualizar.</span><span class="sxs-lookup"><span data-stu-id="34037-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="34037-170">![Origens de dados copiadas](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="34037-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="34037-171">Depois de atualizar as fontes de dados, aceda ao **Dados** > **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="34037-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="34037-172">Aqui encontrará definições do ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="34037-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="34037-173">Edite-as conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="34037-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="34037-174">Quando a unificação de dados estiver concluída, aceda a **Medidas** e **Segmentos** para atualizá-los também.</span><span class="sxs-lookup"><span data-stu-id="34037-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="34037-175">Editar um ambiente existente</span><span class="sxs-lookup"><span data-stu-id="34037-175">Edit an existing environment</span></span>

<span data-ttu-id="34037-176">Pode editar alguns dos detalhes de ambientes existentes.</span><span class="sxs-lookup"><span data-stu-id="34037-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="34037-177">Aceda a **Administração** > **Sistema** > **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="34037-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="34037-178">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="34037-178">Select **Edit**.</span></span>

3. <span data-ttu-id="34037-179">Pode atualizar o **Nome a apresentar** do ambiente, mas não pode alterar a **Região** ou o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="34037-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="34037-180">Se um ambiente estiver configurado para armazenar dados no Azure Data Lake Storage Gen2, poderá atualizar a **Chave da conta**.</span><span class="sxs-lookup"><span data-stu-id="34037-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="34037-181">No entanto, não é possível alterar o **Nome da conta** ou do **Recipiente**.</span><span class="sxs-lookup"><span data-stu-id="34037-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="34037-182">Opcionalmente, pode atualizar a partir de uma ligação baseada em chave de conta para uma ligação baseada em recursos ou em subscrição.</span><span class="sxs-lookup"><span data-stu-id="34037-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="34037-183">Uma vez atualizado, não se pode voltar à chave de conta após a atualização.</span><span class="sxs-lookup"><span data-stu-id="34037-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="34037-184">Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="34037-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="34037-185">Não é possível alterar as informações do **Recipiente** ao atualizar a ligação.</span><span class="sxs-lookup"><span data-stu-id="34037-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="34037-186">Repor um ambiente existente</span><span class="sxs-lookup"><span data-stu-id="34037-186">Reset an existing environment</span></span>

<span data-ttu-id="34037-187">Pode repor um ambiente para um estado vazio se quiser apagar todas as configurações e remover os dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="34037-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="34037-188">Aceda a **Administração** > **Sistema** > **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="34037-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="34037-189">Selecione **Repor**.</span><span class="sxs-lookup"><span data-stu-id="34037-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="34037-190">Para confirmar a eliminação, introduza o nome do ambiente e selecione **Repor**.</span><span class="sxs-lookup"><span data-stu-id="34037-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="34037-191">Eliminar um ambiente existente</span><span class="sxs-lookup"><span data-stu-id="34037-191">Delete an existing environment</span></span>

1. <span data-ttu-id="34037-192">Aceda a **Administração** > **Sistema** > **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="34037-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="34037-193">Selecione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="34037-193">Select **Delete**.</span></span>

1. <span data-ttu-id="34037-194">Para confirmar a eliminação, introduza o nome do ambiente e selecione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="34037-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>

---
title: Ligue-se a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço
description: utilize um principal de serviço do Azure para informações sobre a audiência para ligar ao seu próprio data lake quando o ligar às informações sobre a audiência.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644102"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="1b47d-103">Ligue-se a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço do Azure para informações sobre a audiência</span><span class="sxs-lookup"><span data-stu-id="1b47d-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="1b47d-104">As ferramentas automatizadas que utilizam os serviços Azure devem ter sempre permissões restritas.</span><span class="sxs-lookup"><span data-stu-id="1b47d-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="1b47d-105">Em vez de ter as informações de início de sessão das aplicações como um utilizador totalmente privilegiado, o Azure oferece os principais de serviço.</span><span class="sxs-lookup"><span data-stu-id="1b47d-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="1b47d-106">Continuar a ler para aprender a ligar informações sobre a audiência com uma conta Gen2 Azure Data Lake Storage usando um principal de serviço Azure em vez de chaves de conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1b47d-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="1b47d-107">Pode utilizar o principal de serviço para [adicionar ou editar uma pasta Common Data Model como origem de dados](connect-common-data-model.md) de forma segura, ou [criar um ambiente novo ou atualizar um ambiente existente](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="1b47d-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="1b47d-108">Precisa de permissões de admin para a sua subscrição Azure para criar o principal de serviço.</span><span class="sxs-lookup"><span data-stu-id="1b47d-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="1b47d-109">Criar o principal do serviço Azure para informações sobre a audiência</span><span class="sxs-lookup"><span data-stu-id="1b47d-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="1b47d-110">Antes de criar um novo principal de serviço para as informações sobre a audiência, verifique se já existe na sua organização.</span><span class="sxs-lookup"><span data-stu-id="1b47d-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="1b47d-111">Procure um principal de serviço existente</span><span class="sxs-lookup"><span data-stu-id="1b47d-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="1b47d-112">Aceda ao [portal de administração do Azure](https://portal.azure.com) e inicie sessão na sua organização.</span><span class="sxs-lookup"><span data-stu-id="1b47d-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="1b47d-113">Selecione **Azure Active Directory** a partir dos serviços Azure.</span><span class="sxs-lookup"><span data-stu-id="1b47d-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="1b47d-114">Em **Gerir**, selecione **Aplicações empresariais**.</span><span class="sxs-lookup"><span data-stu-id="1b47d-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="1b47d-115">Procure o ID da aplicação da primeira parte das informações da audiência `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou o nome `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="1b47d-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="1b47d-116">Se encontrar um registo correspondente, significa que o principal de serviço para as informações da audiência existe.</span><span class="sxs-lookup"><span data-stu-id="1b47d-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="1b47d-117">Não necessita de o criar novamente.</span><span class="sxs-lookup"><span data-stu-id="1b47d-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de ecrã que mostra o principal do serviço existente.":::
   
6. <span data-ttu-id="1b47d-119">Se não surgirem resultados, crie um novo principal de serviço.</span><span class="sxs-lookup"><span data-stu-id="1b47d-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="1b47d-120">Criar um novo principal de serviço</span><span class="sxs-lookup"><span data-stu-id="1b47d-120">Create a new service principal</span></span>

1. <span data-ttu-id="1b47d-121">Instale a versão mais recente do **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="1b47d-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="1b47d-122">Para obter mais informações, consulte [Instalar Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="1b47d-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="1b47d-123">No seu PC, selecione a tecla Windows no seu teclado e procure o **Windows PowerShell** e **Execute como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="1b47d-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="1b47d-124">Na janela PowerShell que se abre, introduza `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="1b47d-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="1b47d-125">Crie o principal de serviço para informações de audiência com o Módulo PowerShell do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1b47d-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="1b47d-126">Na janela PowerShell, introduza `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="1b47d-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="1b47d-127">Substitua "a identificação do seu inquilino" pela identificação real do seu inquilino onde pretende criar o principal de serviço.</span><span class="sxs-lookup"><span data-stu-id="1b47d-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="1b47d-128">O parâmetro do nome do ambiente `AzureEnvironmentName` é opcional.</span><span class="sxs-lookup"><span data-stu-id="1b47d-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="1b47d-129">Introduzir `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="1b47d-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="1b47d-130">Este comando cria o principal de serviço para informações de audiência sobre o inquilino selecionado.</span><span class="sxs-lookup"><span data-stu-id="1b47d-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="1b47d-131">Conceda permissões ao principal de serviço para aceder à conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="1b47d-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="1b47d-132">Vá ao portal do Azure para conceder permissões ao principal do serviço para a conta de armazenamento que pretende utilizar nas informações de audiência.</span><span class="sxs-lookup"><span data-stu-id="1b47d-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="1b47d-133">Aceda ao [portal de administração do Azure](https://portal.azure.com) e inicie sessão na sua organização.</span><span class="sxs-lookup"><span data-stu-id="1b47d-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="1b47d-134">Abra a conta de armazenamento a que pretende que o principal do serviço tenha acesso para as informações de audiência.</span><span class="sxs-lookup"><span data-stu-id="1b47d-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="1b47d-135">Selecione o **Controlo de acesso (IAM)** a partir do painel de navegação e selecione **Adicionar** > **Adicionar atribuição de função**.</span><span class="sxs-lookup"><span data-stu-id="1b47d-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de ecrã que mostra o portal do Azure enquanto adiciona uma atribuição de função.":::
   
1. <span data-ttu-id="1b47d-137">No painel **Adicionar atribuição de funções**, define as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="1b47d-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="1b47d-138">Função: *Contribuidor de dados de blobs de armazenamento*</span><span class="sxs-lookup"><span data-stu-id="1b47d-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="1b47d-139">Atribuir acesso a: *Utilizador, grupo ou principal de serviço*</span><span class="sxs-lookup"><span data-stu-id="1b47d-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="1b47d-140">Selecione: *Dynamics 365 AI para Customer Insights* (o [principal de serviço que criou](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="1b47d-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="1b47d-141">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1b47d-141">Select **Save**.</span></span>

<span data-ttu-id="1b47d-142">Pode demorar até 15 minutos a propagar as alterações.</span><span class="sxs-lookup"><span data-stu-id="1b47d-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="1b47d-143">Introduza o ID do Recurso do Azure ou os detalhes da subscrição do Azure no anexo da conta de armazenamento para as informações de audiência.</span><span class="sxs-lookup"><span data-stu-id="1b47d-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="1b47d-144">Anexar uma conta de armazenamento do Azure Data Lake nas informações de audiência para [arquivar dados de saída](manage-environments.md) ou [usá-la como origem de dados](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="1b47d-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="1b47d-145">A escolha da opção Azure Data Lake permite-lhe escolher entre uma abordagem baseada em recursos ou baseada em subscrições.</span><span class="sxs-lookup"><span data-stu-id="1b47d-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="1b47d-146">Siga os passos abaixo para fornecer as informações necessárias sobre a abordagem selecionada.</span><span class="sxs-lookup"><span data-stu-id="1b47d-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="1b47d-147">Ligação da conta de armazenamento baseada em recursos</span><span class="sxs-lookup"><span data-stu-id="1b47d-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="1b47d-148">Aceda ao [portal de administração do Azure](https://portal.azure.com), inicie sessão na sua subscrição e abra a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1b47d-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="1b47d-149">Aceda a **Configurações** > **Propriedades** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="1b47d-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="1b47d-150">Copie o valor de ID do recurso da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1b47d-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie a ID do recurso da conta de armazenamento.":::

1. <span data-ttu-id="1b47d-152">Para informações de audiência, insira o ID do recurso no campo de recursos apresentado no ecrã de ligação da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1b47d-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduza as informações de ID do recurso da conta de armazenamento.":::   
   
1. <span data-ttu-id="1b47d-154">Continue com os passos restantes nas informações de audiência para anexar a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1b47d-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="1b47d-155">Ligação da conta de armazenamento baseada em subscrições</span><span class="sxs-lookup"><span data-stu-id="1b47d-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="1b47d-156">Aceda ao [portal de administração do Azure](https://portal.azure.com), inicie sessão na sua subscrição e abra a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1b47d-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="1b47d-157">Aceda a **Configurações** > **Propriedades** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="1b47d-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="1b47d-158">Reveja a **Subscrição**, **Grupo de recursos**, e o **Nome** da conta de armazenamento para se certificar de que seleciona os valores coretos nas informações de audiência.</span><span class="sxs-lookup"><span data-stu-id="1b47d-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="1b47d-159">Em informações de audiência, escolha os valores ou os campos correspondentes ao anexar a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1b47d-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Introduza as informações de ID do recurso da conta de armazenamento.":::
   
1. <span data-ttu-id="1b47d-161">Continue com os passos restantes nas informações de audiência para anexar a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1b47d-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

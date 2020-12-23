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
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Ligue-se a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço do Azure para informações sobre a audiência

As ferramentas automatizadas que utilizam os serviços Azure devem ter sempre permissões restritas. Em vez de ter as informações de início de sessão das aplicações como um utilizador totalmente privilegiado, o Azure oferece os principais de serviço. Continuar a ler para aprender a ligar informações sobre a audiência com uma conta Gen2 Azure Data Lake Storage usando um principal de serviço Azure em vez de chaves de conta de armazenamento. 

Pode utilizar o principal de serviço para [adicionar ou editar uma pasta Common Data Model como origem de dados](connect-common-data-model.md) de forma segura, ou [criar um ambiente novo ou atualizar um ambiente existente](manage-environments.md#create-an-environment-in-an-existing-organization).

Precisa de permissões de admin para a sua subscrição Azure para criar o principal de serviço.

## <a name="create-azure-service-principal-for-audience-insights"></a>Criar o principal do serviço Azure para informações sobre a audiência

Antes de criar um novo principal de serviço para as informações sobre a audiência, verifique se já existe na sua organização.

### <a name="look-for-an-existing-service-principal"></a>Procure um principal de serviço existente

1. Aceda ao [portal de administração do Azure](https://portal.azure.com) e inicie sessão na sua organização.

2. Selecione **Azure Active Directory** a partir dos serviços Azure.

3. Em **Gerir**, selecione **Aplicações empresariais**.

4. Procure o ID da aplicação da primeira parte das informações da audiência `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou o nome `Dynamics 365 AI for Customer Insights`.

5. Se encontrar um registo correspondente, significa que o principal de serviço para as informações da audiência existe. Não necessita de o criar novamente.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de ecrã que mostra o principal do serviço existente.":::
   
6. Se não surgirem resultados, crie um novo principal de serviço.

### <a name="create-a-new-service-principal"></a>Criar um novo principal de serviço

1. Instale a versão mais recente do **Azure Active Directory PowerShell for Graph**. Para obter mais informações, consulte [Instalar Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - No seu PC, selecione a tecla Windows no seu teclado e procure o **Windows PowerShell** e **Execute como Administrador**.
   
   - Na janela PowerShell que se abre, introduza `Install-Module AzureAD`.

2. Crie o principal de serviço para informações de audiência com o Módulo PowerShell do Azure AD.
   - Na janela PowerShell, introduza `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substitua "a identificação do seu inquilino" pela identificação real do seu inquilino onde pretende criar o principal de serviço. O parâmetro do nome do ambiente `AzureEnvironmentName` é opcional.
  
   - Introduzir `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando cria o principal de serviço para informações de audiência sobre o inquilino selecionado.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceda permissões ao principal de serviço para aceder à conta de armazenamento

Vá ao portal do Azure para conceder permissões ao principal do serviço para a conta de armazenamento que pretende utilizar nas informações de audiência.

1. Aceda ao [portal de administração do Azure](https://portal.azure.com) e inicie sessão na sua organização.

1. Abra a conta de armazenamento a que pretende que o principal do serviço tenha acesso para as informações de audiência.

1. Selecione o **Controlo de acesso (IAM)** a partir do painel de navegação e selecione **Adicionar** > **Adicionar atribuição de função**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de ecrã que mostra o portal do Azure enquanto adiciona uma atribuição de função.":::
   
1. No painel **Adicionar atribuição de funções**, define as seguintes propriedades:
   - Função: *Contribuidor de dados de blobs de armazenamento*
   - Atribuir acesso a: *Utilizador, grupo ou principal de serviço*
   - Selecione: *Dynamics 365 AI para Customer Insights* (o [principal de serviço que criou](#create-a-new-service-principal))

1.  Selecione **Guardar**.

Pode demorar até 15 minutos a propagar as alterações.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduza o ID do Recurso do Azure ou os detalhes da subscrição do Azure no anexo da conta de armazenamento para as informações de audiência.

Anexar uma conta de armazenamento do Azure Data Lake nas informações de audiência para [arquivar dados de saída](manage-environments.md) ou [usá-la como origem de dados](connect-common-data-service-lake.md). A escolha da opção Azure Data Lake permite-lhe escolher entre uma abordagem baseada em recursos ou baseada em subscrições.

Siga os passos abaixo para fornecer as informações necessárias sobre a abordagem selecionada.

### <a name="resounce-based-storage-account-connection"></a>Ligação da conta de armazenamento baseada em recursos

1. Aceda ao [portal de administração do Azure](https://portal.azure.com), inicie sessão na sua subscrição e abra a conta de armazenamento.

1. Aceda a **Configurações** > **Propriedades** no painel de navegação.

1. Copie o valor de ID do recurso da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie a ID do recurso da conta de armazenamento.":::

1. Para informações de audiência, insira o ID do recurso no campo de recursos apresentado no ecrã de ligação da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduza as informações de ID do recurso da conta de armazenamento.":::   
   
1. Continue com os passos restantes nas informações de audiência para anexar a conta de armazenamento.

### <a name="subscription-based-storage-account-connection"></a>Ligação da conta de armazenamento baseada em subscrições

1. Aceda ao [portal de administração do Azure](https://portal.azure.com), inicie sessão na sua subscrição e abra a conta de armazenamento.

1. Aceda a **Configurações** > **Propriedades** no painel de navegação.

1. Reveja a **Subscrição**, **Grupo de recursos**, e o **Nome** da conta de armazenamento para se certificar de que seleciona os valores coretos nas informações de audiência.

1. Em informações de audiência, escolha os valores ou os campos correspondentes ao anexar a conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Introduza as informações de ID do recurso da conta de armazenamento.":::
   
1. Continue com os passos restantes nas informações de audiência para anexar a conta de armazenamento.

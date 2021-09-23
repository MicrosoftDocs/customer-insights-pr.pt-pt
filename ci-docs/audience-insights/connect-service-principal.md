---
title: Ligar a uma conta do Azure Data Lake Storage utilizando um principal de serviço
description: Utilize um principal de serviço do Azure para ligar ao seu próprio data lake.
ms.date: 09/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b96c7f580b4067e059e00a9cdb4e872e9acd4a5c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483539"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ligar a uma conta do Azure Data Lake Storage utilizando um principal de serviço do Azure

As ferramentas automatizadas que utilizam os serviços Azure devem ter sempre permissões restritas. Em vez de ter as informações de início de sessão das aplicações como um utilizador totalmente privilegiado, o Azure oferece os principais de serviço. Continue a ler para aprender a ligar o Dynamics 365 Customer Insights a uma conta do Azure Data Lake Storage utilizando um principal de serviço do Azure, em vez de chaves de conta de armazenamento. 

Pode utilizar o principal de serviço para [adicionar ou editar uma pasta do Common Data Model como origem de dados](connect-common-data-model.md) ou [criar ou atualizar um ambiente](get-started-paid.md) de forma segura.

> [!IMPORTANT]
> - A conta Data Lake Storage que utilizará o principal de serviço tem de ter o [espaço de nome hierárquico ativado](/azure/storage/blobs/data-lake-storage-namespace).
> - Precisa de permissões de admin para a sua subscrição Azure para criar o principal de serviço.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Criar um principal de serviço do Azure para o Customer Insights

Antes de criar um novo principal de serviço para informações de audiência ou informações de cativação, verifique se já existe na sua organização.

### <a name="look-for-an-existing-service-principal"></a>Procure um principal de serviço existente

1. Aceda ao [portal de administração do Azure](https://portal.azure.com) e inicie sessão na sua organização.

2. A partir do **Serviços do Azure**, selecione **Azure Active Directory**.

3. Em **Gerir**, selecione **Aplicações empresariais**.

4. Procure pelo ID da aplicação da Microsoft:
   - Informações de audiência: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` com o nome `Dynamics 365 AI for Customer Insights`
   - Informações de cativação: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` com o nome `Dynamics 365 AI for Customer Insights engagement insights`

5. Se encontrar um registo correspondente, significa que o principal de serviço já existe. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de ecrã a mostrar um principal de serviço existente.":::
   
6. Se não surgirem resultados, crie um novo principal de serviço.

>[!NOTE]
>Para utilizar o potência total do Dynamics 365 Customer Insights, sugerimos que adicione ambas as aplicações ao principal de serviço.

### <a name="create-a-new-service-principal"></a>Criar um novo principal de serviço

1. Instalar a versão do PowerShell for Graph do Azure Active Directory. Para obter mais informações, vá a [Instalar o PowerShell for Graph do Azure Active Directory](/powershell/azure/active-directory/install-adv2).

   1. No seu PC, selecione a tecla Windows no seu teclado, procure por **Windows PowerShell** e selecione **Executar como administrador**.
   
   1. Na janela PowerShell que se abre, introduza `Install-Module AzureAD`.

2. Crie o principal de serviço para o Customer Insights com o módulo PowerShell do Azure AD.

   1. Na janela PowerShell, introduza `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substitua *[o ID do seu inquilino]* pela identificação real do seu inquilino onde pretende criar o principal de serviço. O parâmetro do nome do ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Introduzir `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando cria o principal de serviço para informações de audiência sobre o inquilino selecionado. 

   1. Introduzir `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Este comando cria o principal de serviço para informações de cativação no inquilino selecionado.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceda permissões ao principal de serviço para aceder à conta de armazenamento

Vá ao portal do Azure para conceder permissões ao principal do serviço para a conta de armazenamento que pretende utilizar nas informações de audiência.

1. Aceda ao [portal de administração do Azure](https://portal.azure.com) e inicie sessão na sua organização.

1. Abra a conta de armazenamento a que pretende que o principal do serviço tenha acesso para as informações de audiência.

1. No painel esquerdo, selecione **Controlo de Acesso (IAM)** e, em seguida, selecione **Adicionar** > **Adicionar atribuição de licenças**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de ecrã a mostrar o portal do Azure enquanto adiciona uma atribuição de funções.":::

1. No painel **Adicionar atribuição de funções**, defina as seguintes propriedades:
   - Função: **Contribuidor de dados de blobs de armazenamento**
   - Atribuir acesso a: **Utilizador, grupo ou principal de serviço**
   - Selecione: **Dynamics 365 AI for Customer Insights** e **Informações de cativação do Dynamics 365 AI for Customer Insights** (os dois [principais de serviço](#create-a-new-service-principal) que criou anteriormente neste procedimento)

1.  Selecione **Guardar**.

Pode demorar até 15 minutos a propagar as alterações.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduza o ID do recurso do Azure ou os detalhes da subscrição do Azure no anexo da conta de armazenamento para as informações de audiência

Pode anexar uma conta Data Lake Storage em informações de audiência para [armazenar dados de saída](manage-environments.md) ou [usá-lo como uma origem de dados](connect-common-data-service-lake.md). Esta opção permite-lhe escolher entre uma abordagem baseada em recursos ou baseada em subscrições. Dependendo da abordagem escolhida, siga o procedimento numa das seguintes secções.

### <a name="resource-based-storage-account-connection"></a>Ligação da conta de armazenamento baseada em recursos

1. Aceda ao [portal de administração do Azure](https://portal.azure.com), inicie sessão na sua subscrição e abra a conta de armazenamento.

1. No painel esquerdo, vá a **Definições** > **Propriedades**.

1. Copie o valor de ID do recurso da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie a ID do recurso da conta de armazenamento.":::

1. Para informações de audiência, insira o ID do recurso no campo de recursos apresentado no ecrã de ligação da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduza as informações de ID do recurso da conta de armazenamento.":::   

1. Continue com os passos restantes nas informações de audiência para anexar a conta de armazenamento.

### <a name="subscription-based-storage-account-connection"></a>Ligação da conta de armazenamento baseada em subscrições

1. Aceda ao [portal de administração do Azure](https://portal.azure.com), inicie sessão na sua subscrição e abra a conta de armazenamento.

1. No painel esquerdo, vá a **Definições** > **Propriedades**.

1. Reveja a **Subscrição**, **Grupo de recursos**, e o **Nome** da conta de armazenamento para se certificar de que seleciona os valores coretos nas informações de audiência.

1. Em informações de audiência, escolha os valores para os campos correspondentes quando anexar a conta de armazenamento.

1. Continue com os passos restantes nas informações de audiência para anexar a conta de armazenamento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Ligar a uma conta do Azure Data Lake Storage utilizando um principal de serviço do Azure
description: Utilize um principal de serviço do Azure para ligar ao seu próprio data lake.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081302"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ligar a uma conta do Azure Data Lake Storage utilizando um principal de serviço do Azure

Este artigo aborda a forma de estabelecer ligação ao Dynamics 365 Customer Insights com uma conta do Azure Data Lake Storage ao utilizar um principal de serviço do Azure, em vez das chaves de conta de armazenamento.

As ferramentas automatizadas que utilizam os serviços Azure devem ter sempre permissões restritas. Em vez de ter as informações de início de sessão das aplicações como um utilizador totalmente privilegiado, o Azure oferece os principais de serviço. Poderá utilizar os principais de serviço para [adicionar ou editar uma pasta do Common Data Model como uma origem de dados](connect-common-data-model.md) em segurança ou [criar ou atualizar um ambiente](create-environment.md).

> [!IMPORTANT]
>
> - A conta Data Lake Storage que utilizará o principal do serviço tem de ser Gen2 e de ter o [espaço de nomes hierárquico ativado](/azure/storage/blobs/data-lake-storage-namespace). As contas de armazenamento do Azure Data Lake Gen1 não são suportadas.
> - São necessárias permissões de admin para o seu inquilino do Azure para criar um principal de serviço.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Criar um principal de serviço do Azure para o Customer Insights

Antes de criar um novo principal de serviço para o Customer Insights, verifique se já existe na sua organização.

### <a name="look-for-an-existing-service-principal"></a>Procure um principal de serviço existente

1. Aceda ao [portal de administração do Azure](https://portal.azure.com) e inicie sessão na sua organização.

2. A partir do **Serviços do Azure**, selecione **Azure Active Directory**.

3. Em **Gerir**, selecione **Aplicação da Microsoft**.

4. Adicione um filtro ao **ID da Aplicação que inicie com** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou procure o nome `Dynamics 365 AI for Customer Insights`.

5. Se encontrar um registo correspondente, significa que o principal de serviço já existe.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de ecrã a mostrar um principal de serviço existente.":::

6. Se não forem obtidos resultados, poderá [criar um novo principal de serviço](#create-a-new-service-principal). Na maioria dos casos, já existe e só necessita de conceder permissões ao principal de serviço para aceder à conta de armazenamento.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceda permissões ao principal de serviço para aceder à conta de armazenamento

Vá ao portal do Azure para conceder permissões ao principal do serviço para a conta de armazenamento que pretende utilizar no Customer Insights. Uma das seguintes funções tem de ser atribuída à conta ou armazenamento ou contentor:

|Credencial|Requisitos |
|----------|------------|
|Utilizador com sessão iniciada atualmente|**Função**: Leitor de Dados de Blob de Armazenamento, Contribuidor de Blob de Armazenamento ou Proprietário de Blob de Armazenamento.<br>**Nível**: as permissões podem ser concedidas na conta de armazenamento ou no contentor.</br>|
|Principal de Serviço do Customer Insights -<br>Utilizar o Azure Data Lake Storage como uma origem de dados</br>|Opção 1<ul><li>**Função**: Leitor de Dados de Blob de Armazenamento, Contribuidor de Dados de Blob de Armazenamento ou Proprietário de Dados de Blob de Armazenamento.</li><li>**Nível**: as permissões devem ser concedidas na conta de armazenamento.</li></ul>Opção 2 *(sem partilhar o acesso do Principal de Serviço à conta de armazenamento)*<ul><li>**Função 1**: Leitor de Dados de Blob de Armazenamento, Contribuidor de Dados de Blob de Armazenamento ou Proprietário de Dados de Blob de Armazenamento.</li><li>**Nível**: as permissões devem ser concedidas no contentor.</li><li>**Função 2**: Atribuidor de Dados de Blob de Armazenamento.</li><li>**Nível**: as permissões devem ser concedidas na conta de armazenamento.</li></ul>|
|Principal de Serviço do Customer Insights - <br>Utilizar o Azure Data Lake Storage como uma saída ou um destino</br>|Opção 1<ul><li>**Função**: Contribuidor de Dados de Blob de Armazenamento ou Proprietário de Blob de Armazenamento.</li><li>**Nível**: as permissões devem ser concedidas na conta de armazenamento.</li></ul>Opção 2 *(sem partilhar o acesso do Principal de Serviço à conta de armazenamento)*<ul><li>**Função**: Contribuidor de Dados de Blob de Armazenamento ou Proprietário de Blob de Armazenamento.</li><li>**Nível**: as permissões devem ser concedidas no contentor.</li><li>**Função 2**: Atribuidor de Blob de Armazenamento.</li><li>**Nível**: as permissões devem ser concedidas na conta de armazenamento.</li></ul>|

1. Aceda ao [portal de administração do Azure](https://portal.azure.com) e inicie sessão na sua organização.

1. Abra a conta de armazenamento à que pretende que o principal do serviço do Customer Insights tenha acesso.

1. No painel esquerdo, selecione **Controlo de Acesso (IAM)** e, em seguida, selecione **Adicionar** > **Adicionar atribuição de licenças**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de ecrã a mostrar o portal do Azure enquanto adiciona uma atribuição de funções.":::

1. No painel **Adicionar atribuição de funções**, defina as seguintes propriedades:
   - Função: Leitor de Dados de Blob de Armazenamento, Contribuidor de Blob de Armazenamento ou Proprietário de Blob de Armazenamento com base em credenciais listadas acima.
   - Atribuir acesso a: **Utilizador, grupo ou principal de serviço**
   - Selecionar membros: **Dynamics 365 AI for Customer Insights** (o [principal do serviço](#create-a-new-service-principal) que procurou anteriormente neste procedimento)

1. Selecione **Rever + atribuir**.

Pode demorar até 15 minutos a propagar as alterações.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Introduzir o ID do recurso do Azure ou os detalhes da subscrição do Azure no anexo da conta de armazenamento para o Customer Insights

Pode anexar uma conta do Data Lake Storage no Customer Insights para [armazenar dados de saída](manage-environments.md) ou [utilizá-la como uma origem de dados](connect-dataverse-managed-lake.md). Esta opção permite-lhe escolher entre uma abordagem baseada em recursos ou baseada em subscrições. Dependendo da abordagem escolhida, siga o procedimento numa das seguintes secções.

### <a name="resource-based-storage-account-connection"></a>Ligação da conta de armazenamento baseada em recursos

1. Aceda ao [portal de administração do Azure](https://portal.azure.com), inicie sessão na sua subscrição e abra a conta de armazenamento.

1. No painel esquerdo, aceda a **Definições** > **Pontos finais**.

1. Copie o valor de ID do recurso da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie a ID do recurso da conta de armazenamento.":::

1. No Customer Insights, introduza o ID do recurso no campo de recursos apresentado no ecrã de ligação da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduza as informações de ID do recurso da conta de armazenamento.":::   

1. Continue com os passos restantes no Customer Insights para anexar a conta de armazenamento.

### <a name="subscription-based-storage-account-connection"></a>Ligação da conta de armazenamento baseada em subscrições

1. Aceda ao [portal de administração do Azure](https://portal.azure.com), inicie sessão na sua subscrição e abra a conta de armazenamento.

1. No painel esquerdo, vá a **Definições** > **Propriedades**.

1. Reveja a **Subscrição**, o **Grupo de recursos** e o **Nome** da conta de armazenamento para se certificar de que seleciona os valores corretos no Customer Insights.

1. No Customer Insights, escolha os valores para os campos correspondentes quando anexa a conta de armazenamento.

1. Continue com os passos restantes no Customer Insights para anexar a conta de armazenamento.

### <a name="create-a-new-service-principal"></a>Criar um novo principal de serviço

1. Instalar a versão do PowerShell for Graph do Azure Active Directory. Para obter mais informações, vá a [Instalar o PowerShell for Graph do Azure Active Directory](/powershell/azure/active-directory/install-adv2).

   1. No PC, prima a tecla Windows no teclado, pesquise por **Windows PowerShell** e selecione **Executar como administrador**.

   1. Na janela PowerShell que se abre, introduza `Install-Module AzureAD`.

2. Crie o principal de serviço para o Customer Insights com o módulo PowerShell do Azure AD.

   1. Na janela PowerShell, introduza `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Substitua *[o ID do seu Diretório]* pelo ID do Diretório real da sua subscrição do Azure onde pretende criar o principal do serviço. O parâmetro do nome do ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Introduzir `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando cria o principal do serviço para o Customer Insights na subscrição do Azure selecionada.

[!INCLUDE [footer-include](includes/footer-banner.md)]

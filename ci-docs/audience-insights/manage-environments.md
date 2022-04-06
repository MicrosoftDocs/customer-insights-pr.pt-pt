---
title: Criar e gerir ambientes
description: Saiba como se inscrever no serviço e como gerir ambientes.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492018"
---
# <a name="manage-environments"></a>Gerir ambientes

## <a name="switch-environments"></a>Mudar de ambientes

Selecione o controlo **Ambiente** no canto superior direito da página para mudar de ambiente.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de ecrã do controlo para mudar de ambiente.":::

Os administradores podem [criar](create-environment.md) e gerir ambientes.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Pode editar alguns dos detalhes de ambientes existentes.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação.

2.  Selecione o ícone **Editar**.

3. Na caixa **Editar ambiente**, pode atualizar as definições do ambiente.

Para obter mais informações sobre as definições do ambiente, consulte [Criar um novo ambiente](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Ligar ao Microsoft Dataverse
   
O passo **Microsoft Dataverse** permite-lhe ligar o Customer Insights ao ambiente do Dataverse. 

Forneça o seu próprio ambiente Microsoft Dataverse para partilhar dados (perfis e informações) com aplicações de negócio baseadas em Dataverse, como o Dynamics 365 Marketing ou aplicações orientadas por modelos no Power Apps.

Para utilizar [modelos de predição fornecidos com o programa](predictions-overview.md#out-of-box-models), configure a partilha de dados com o Dataverse. Ou pode ativar a ingestão de dados a partir de origens de dados no local, fornecendo o URL do ambiente do Microsoft Dataverse que a sua organização administra.

Permitir a partilha de dados com o Microsoft Dataverse selecionando a caixa de verificação de partilha de dados irá acionar uma atualização completa única das suas origens de dados e de todos os outros processos.

> [!IMPORTANT]
> 1. O Customer Insights e o Dataverse têm de estar na mesma região para permitir a partilha de dados.
> 1. Tem de ter uma função de administrador global no ambiente do Dataverse. Verifique se este [ambiente do Dataverse está associado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de segurança e certifique-se de que é adicionado a esses grupos de segurança.
> 1. Nenhum ambiente existente do Customer Insights está já associado a esse ambiente do Dataverse. Saiba como [remover uma ligação existente a um ambiente do Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opções de configuração para ativar a partilha de dados com o Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Ative a partilha de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage (Pré-visualização)

Se o seu ambiente estiver configurado para utilizar o seu próprio Azure Data Lake Storage para armazenar dados do Customer Insights, permitir a partilha de dados com o Microsoft Dataverse necessita de alguma configuração adicional.

1. Crie dois grupos de segurança na sua subscrição do Azure – um  grupo de segurança **Leitor** e um  grupo de segurança **Contribuidor** e defina o serviço Microsoft Dataverse como o proprietário para ambos os grupos de segurança.
2. Efetue a gestão da Lista de Controlo de Acesso (ACL) no contentor CustomerInsights na sua conta de armazenamento através destes grupos de segurança. Adicione o serviço Microsoft Dataverse e quaisquer aplicações empresariais baseadas no Dataverse, como o Dynamics 365 Marketing ao grupo de segurança **Leitor** com permissões **só de leitura**. Adicione *só* a aplicação Customer Insights ao grupo de segurança **Contribuidor** para conceder permissões de **leitura e escrita** para escrever perfis e informações.
   
#### <a name="prerequisites"></a>Pré-requisitos

Para executar os scripts do PowerShell é necessário importar os três módulos que se seguem. 

1. Instalar a versão mais recente do [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   1. No seu PC, selecione a tecla Windows no seu teclado, procure por **Windows PowerShell** e selecione **Executar como administrador**.
   1. Na janela PowerShell que se abre, introduza `Install-Module AzureAD`.
2. Importe três módulos.
    1. Na janela do PowerShell, introduza `Install-Module -Name Az.Accounts` e siga os passos. 
    1. Repita para `Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Passos de configuração

1. Transfira os dois scripts do PowerShell de que precisa para executar a partir do [repositório do GitHub](https://github.com/trin-msft/byol) do nosso engenheiro.
    1. `CreateSecurityGroups.ps1`
       - Necessita de ter permissões de *admin de inquilinos* para executar este script do PowerShell. 
       - Este script do PowerShell cria dois grupos de segurança na sua subscrição do Azure. Um para o grupo Leitor e outro para o grupo Contribuidor e tornará o serviço Microsoft Dataverse como proprietário para ambos estes grupos de segurança.
       - Execute este script do PowerShell no Windows PowerShell fornecendo o ID de subscrição do Azure que contém o seu Azure Data Lake Storage. Abra o script do PowerShell num editor para rever informações adicionais e a lógica implementada.
       - Guarde ambos os valores do ID do grupo de segurança gerados por este script porque vamos utilizá-los no script `ByolSetup.ps1`.
       
        > [!NOTE]
        > A criação de grupos de segurança pode ser desativada no seu inquilino. Nesse caso, seria necessária uma configuração manual e o seu admin do Azure AD teria de [permitir a criação de grupos de segurança](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Precisa de permissões de *Proprietário de Dados do Blob de Armazenamento* ao nível da conta de armazenamento/contentor para executar este script ou este script criará um para si. A sua atribuição de funções pode ser removida manualmente depois de executar o script com sucesso.
        - Este script do PowerShell adiciona o controlo de acesso baseado em funções (RBAC) necessário para o serviço Microsoft Dataverse e quaisquer aplicações empresariais baseadas no Dataverse. Também atualiza a Lista de Controlo de Acesso (ACL) no contentor CustomerInsights para os grupos de segurança criados com o script `CreateSecurityGroups.ps1`. O grupo Contribuidor terá permissão *rwx* e o grupo Leitores terá apenas permissão *r-x*.
        - Execute este script do PowerShell no Windows PowerShell fornecendo o ID de subscrição do Azure que contém o nome da sua conta de armazenamento do Azure Data Lake Storage, nome do grupo de recursos e os valores dos ID dos grupos de segurança Leitor e Contribuidor. Abra o script do PowerShell num editor para rever informações adicionais e a lógica implementada.
        - Copie a cadeia de saída depois de executar com sucesso o script. A cadeia de saída tem o seguinte aspeto: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Introduza a cadeia de saída copiada acima para o campo **Identificador de permissões** do passo de configuração do ambiente para o Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opções de configuração para permitir a partilha de dados a partir do seu próprio Azure Data Lake Storage com o Microsoft Dataverse.":::

O Customer Insights não suporta os seguintes cenários de partilha de dados:
- Se ativar a partilha de dados com o Dataverse, não poderá [criar valores previsíveis ou em falta numa entidade](predictions.md).
- Se permitir a partilha de dados com o Dataverse, não poderá ver quaisquer relatórios opcionais do PowerBI Embedded no seu ambiente do Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Remover uma ligação existente a um ambiente do Dataverse

Ao ligar a um ambiente do Dataverse, a mensagem de erro **Esta organização do CDS já está ligada a outra instância do Customer Insights** significa que o ambiente do Dataverse já é utilizado num ambiente do Customer Insights. Pode remover a ligação existente como um administrador global no ambiente do Dataverse. Pode levar duas horas para preencher as mudanças.

1. Ir para o [Power Apps](https://make.powerapps.com).
1. Selecione o ambiente do seletor de ambientes.
1. Vá para **Soluções**
1. Desinstale ou elimine a solução denominada **Suplemento de Cartões de Cliente do Dynamics 365 Customer Insights (Pré-visualização)**.

OR 

1. Abra o seu ambiente do Dataverse.
1. Aceda a **Definições Avançadas** > **Soluções**.
1. Desinstale a solução **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Como admin, pode optar por copiar a configuração de um ambiente existente quando cria um novo. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de ecrã das opções de definições nas definições do ambiente.":::

Verá uma lista de todos os ambientes disponíveis na sua organização de onde pode copiar dados.

As seguintes definições de configuração são copiadas:

- Origens de dados ingeridas/importadas
- Configuração de unificação de dados (Mapa, Corresponder, Unir)
- Segmentos
- Medições
- Relações
- Atividades
- Índice de pesquisas e filtros
- Destinos de exportação
- Atualização agendada
- Melhoramentos
- Gestão de modelos
- Atribuições de funções

## <a name="set-up-a-copied-environment"></a>Configurar um ambiente copiado

Quando copia a configuração do ambiente, os seguintes dados *não* são copiados:

- Perfis de cliente.
- Credenciais da origem de dados. Terá de fornecer as credenciais para cada origem de dados e atualizar manualmente as origens de dados.
- Origens de dados da pasta Common Data Model e data lake gerido do Dataverse. Terá de criar manualmente essas origens de dados com o mesmo nome que no ambiente de origem.
- Segredos de ligação que são utilizados para exportações e melhoramentos. Tem de voltar a autenticar as ligações e, em seguida, reativar melhoramentos e exportações. 

Quando copia um ambiente, verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para origens de dados** para ver a lista de origens de dados.

Todas as origens de dados apresentarão um estado de **Credenciais Obrigatórias**. Edite as origens de dados e introduza as credenciais para as atualizar.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de origens de dados que foram copiadas e precisam de autenticação.":::

Depois de atualizar as fontes de dados, aceda ao **Dados** > **Unificar**. Aqui encontrará definições do ambiente de origem. Edite-as conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade de cliente unificada.

Quando a unificação de dados estiver concluída, aceda a **Medidas** e **Segmentos** para atualizá-los também.

Antes de reativar exportações e melhoramentos, vá à **Admin** > **Ligações** para voltar a autenticar as ligações no seu novo ambiente.

## <a name="change-the-owner-of-an-environment"></a>Alterar o proprietário de um ambiente

Apesar de vários utilizadores poderem ter permissões de administrador no Customer Insights, apenas um utilizador é o proprietário de um ambiente. Por predefinição, é o administrador quem cria inicialmente um ambiente. Como administrador de um ambiente, pode atribuir a propriedade a outro utilizador com permissões de administrador.

1. Selecione o seletor **Ambiente** no cabeçalho da aplicação.

1. Selecione o ícone **Editar**.

1. Na caixa de **Editar ambiente**, vá para o passo **Informações básicas**.

1. No campo **Alterar proprietário do ambiente**, escolha o novo proprietário do ambiente.  

1. Selecione **Rever e concluir** e, em seguida, **Atualizar** para aplicar as alterações. 

## <a name="claim-ownership-of-an-environment"></a>Reclamar a propriedade de um ambiente

Se o proprietário de um ambiente sair da organização ou se a respetiva conta de utilizador for eliminada, o ambiente não terá proprietário. Um utilizador com permissões de administrador pode reclamar a propriedade e tornar-se o novo proprietário. Pode continuar a ser o proprietário do ambiente ou [alterar a propriedade para outro administrador](#change-the-owner-of-an-environment). 

Para reclamar a propriedade, selecione o botão **Assumir propriedade** que é apresentado no início de cada página no Customer Insights quando o proprietário original deixou a organização.

## <a name="reset-an-existing-environment"></a>Repor um ambiente existente

Como proprietário de um ambiente, pode repor um ambiente para um estado vazio se quiser eliminar todas as configurações e remover os dados ingeridos.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação. 

2.  Selecione o ambiente que pretende repor e selecione as reticências (**...**). 

3. Escolha a opção **Repor**. 

4.  Para confirmar a eliminação, introduza o nome do ambiente e selecione **Repor**.

## <a name="delete-an-existing-environment"></a>Eliminar um ambiente existente

Como proprietário de um ambiente, pode eliminar um ambiente que administra.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação.

2.  Selecione o ambiente que pretende repor e selecione as reticências (**...**). 

3. Escolha a opção **Eliminar**. 

4.  Para confirmar a eliminação, introduza o nome do ambiente e selecione **Eliminar**.

> [!NOTE]
> A eliminação de um ambiente não remove a associação a um ambiente do Dataverse. Saiba como [remover uma ligação existente a um ambiente do Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

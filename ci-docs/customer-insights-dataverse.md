---
title: Trabalhar com dados do Customer Insights no Microsoft Dataverse
description: Aprenda a ligar o Customer Insights e o Microsoft Dataverse e compreenda as entidades de saída que são exportadas para o Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011560"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabalhar com dados do Customer Insights no Microsoft Dataverse

O Customer Insights disponibiliza a opção para disponibilizar entidades de saída como [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Esta integração permite uma fácil partilha de dados e desenvolvimento personalizado através de uma abordagem de código baixo/sem código. As [entidades de saída](#output-entities) estão disponíveis como tabelas num ambiente do Dataverse. Pode utilizar os dados de qualquer outra aplicação com base em tabelas do Dataverse. Estas tabelas permitem cenários como fluxos de trabalho automatizados através do Power Automate ou a criação de aplicações com o Power Apps.

A ligação ao seu ambiente Dataverse também permite-lhe [ingerir dados de origens de dados no local utilizando fluxos de dados e gateways do Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Pré-requisitos

- Os ambientes do Customer Insights e do Dataverse têm de ser a hospedados na mesma região.
- Tem de ter uma função de administrador global no ambiente do Dataverse. Verifique se este [ambiente do Dataverse está associado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de segurança e certifique-se de que é adicionado a esses grupos de segurança.
- Nenhum outro ambiente do Customer Insights está já associado ao ambiente do Dataverse que pretende ligar. Saiba como [remover uma ligação existente a um ambiente do Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Um ambiente do Microsoft Dataverse só pode ligar a uma única conta de armazenamento. Só é aplicável se configurar o ambiente para [utilizar o seu Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Ligar um ambiente do Dataverse ao Customer Insights

O passo **Microsoft Dataverse** permite-lhe ligar o Customer Insights ao seu ambiente do Dataverse ao [criar um ambiente do Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="partilha de dados com Microsoft Dataverse ativado automaticamente para novos ambientes de rede.":::

Os administradores podem configurar o Customer Insights para ligar um ambiente do Dataverse existente. Ao fornecer o URL para o ambiente do Dataverse, está a anexar ao respetivo ambiente do Customer Insights.

Se não quiser utilizar um ambiente do Dataverse existente, o sistema cria um novo ambiente para os dados do Customer Insights no seu inquilino. [Os admins do Power Platform podem controlar quem pode criar ambientes](/power-platform/admin/control-environment-creation). Quando estiver a configurar um novo ambiente do Customer Insights e o admin tiver desativado a criação de ambientes do Dataverse para todas as pessoas, exceto admins, poderá não conseguir criar um novo ambiente.

**Ative a partilha de dados** com o Dataverse selecionando a caixa de verificação de partilha de dados.

Se estiver a utilizar a sua própria conta do Data Lake Storage, também necessita do **Identificador de permissões**. Para obter mais informações sobre como obter o identificador de permissões, reveja a secção que se segue.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Ative a partilha de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage (Pré-visualização)

Ativar a partilha de dados com o Microsoft Dataverse quando o ambiente [utiliza a sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md) requer alguma configuração adicional. O utilizador que configura o ambiente do Customer Insights tem de ter, pelo menos, permissões de **Leitor de Dados de Blobs de Armazenamento** no contentor *CustomerInsights* na conta do Azure Data Lake Storage.

1. Crie dois grupos de segurança na sua subscrição do Azure – um  grupo de segurança **Leitor** e um  grupo de segurança **Contribuidor** e defina o serviço Microsoft Dataverse como o proprietário para ambos os grupos de segurança.
2. Efetue a gestão da Lista de Controlo de Acesso (ACL) no contentor CustomerInsights na sua conta de armazenamento através destes grupos de segurança. Adicione o serviço Microsoft Dataverse e quaisquer aplicações empresariais baseadas no Dataverse, como o Dynamics 365 Marketing ao grupo de segurança **Leitor** com permissões **só de leitura**. Adicione *só* a aplicação Customer Insights ao grupo de segurança **Contribuidor** para conceder permissões de **leitura e escrita** para escrever perfis e informações.

### <a name="limitations"></a>Limitações

Existem duas limitações ao utilizar o Dataverse com a sua própria conta do Azure Data Lake Storage:

- Existe um mapeamento um-para-um entre uma organização do Dataverse e uma conta do Azure Data Lake Storage. Depois de uma organização Dataverse ser ligada a uma conta de armazenamento, não poderá ser ligada a outra conta de armazenamento. Esta limitação impede que um Dataverse não preencha várias contas de armazenamento.
- A partilha de dados não funcionará se for necessária uma configuração do Azure Private Link para aceder à sua conta Azure Data Lake Storage, porque está por detrás de uma firewall. Atualmente, o Dataverse não suporta a ligação a pontos finais privados através do Private Link.

### <a name="set-up-powershell"></a>Configurar o PowerShell

Para executar os scripts do PowerShell, primeiro é necessário configurar o PowerShell em conformidade.

1. Instalar a versão mais recente do [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   1. No seu PC, selecione a tecla Windows no seu teclado, procure por **Windows PowerShell** e selecione **Executar como administrador**.
   1. Na janela PowerShell que se abre, introduza `Install-Module AzureAD`.
2. Importe três módulos.
    1. Na janela do PowerShell, introduza `Install-Module -Name Az.Accounts` e siga os passos.
    1. Repita para `Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Passos de configuração

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
        - Copie a cadeia de saída depois de executar com sucesso o script. A cadeia de saída tem o seguinte aspeto: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Introduza a cadeia de saída copiada acima para o campo **Identificador de permissões** do passo de configuração do ambiente para o Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opções de configuração para permitir a partilha de dados a partir do seu próprio Azure Data Lake Storage com o Microsoft Dataverse.":::

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

Se a remoção da ligação falhar devido a dependências, precisa de remover as dependências também. Para obter mais informações, consulte [Remover dependências](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entidades de saída

Algumas entidades de saída do Customer Insights estão disponíveis como tabelas no Dataverse. As secções abaixo descrevem o esquema esperado destas tabelas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Melhoramento](#enrichment)
- [Predição](#prediction)
- [Associação a segmentos](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Esta tabela contém o perfil de cliente unificado do Customer Insights. O esquema para unified customer profile depende das entidades e atributos utilizados no processo de unificação de dados. Um esquema de perfil do cliente geralmente contém um subconjunto dos atributos da [definição do Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

A tabela AlternateKey contém chaves das entidades, as quais participaram no processo de unificação.

|Column  |Tipo  |Descrição  |
|---------|---------|---------|
|DataSourceName    |String         | Nome da origem de dados. Por exemplo: `datasource5`        |
|EntityName        | Cadeia (de carateres)        | Nome da entidade no Customer Insights. Por exemplo: `contact1`        |
|AlternateValue    |Cadeia (de carateres)         |ID Alternativo que é mapeado para o ID do cliente. Exemplo: `cntid_1078`         |
|KeyRing           | Texto multilinha        | Valor JSON  </br> Exemplo: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|ID do Cliente         | String        | ID do perfil de cliente unificado.         |
|AlternateKeyId     | GUID         |  GUID determinista de AlternateKey baseado em msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta tabela contém atividades de utilizadores que estão disponíveis no Customer Insights.

| Column            | Tipo        | Descrição                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| ID do Cliente        | String      | ID do Perfil do Cliente                                                                      |
| ActivityId        | String      | ID interno da atividade do cliente (chave primária)                                       |
| SourceEntityName  | String      | Nome da entidade fornecida com o programa                                                                |
| SourceActivityId  | String      | Chave primária da entidade fornecida com o programa                                                       |
| ActivityType      | String      | Tipo de atividade semântica ou nome de atividade personalizada                                        |
| ActivityTimeStamp | DATETIME    | Carimbo de Data/hora da Atividade                                                                      |
| Cargo             | String      | Título ou nome da atividade                                                               |
| Descrição       | String      | Descrição da atividade                                                                     |
| URL               | String      | Ligação a um URL externo específico à atividade                                         |
| SemanticData      | Cadeia JSON | Inclui uma lista de pares de valores de chave para campos de mapeamento semântico específicos para o tipo de atividade |
| RangeIndex        | String      | Carimbo de data/hora Unix utilizado para ordenar consultas de intervalo de eficácia e de intervalo de tempo |
| mydynci_unifiedactivityid   | GUID | ID interno da atividade do cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta tabela contém os dados de saída das medidas baseadas no atributo do cliente.

| Column             | Tipo             | Descrição                 |
|--------------------|------------------|-----------------------------|
| ID do Cliente         | String           | ID do perfil do cliente        |
| Medidas           | Cadeia JSON      | Inclui uma lista de pares de valores de chave para nome e valores de medida para determinado cliente | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID do perfil do cliente |


### <a name="enrichment"></a>Melhoramento

Esta tabela contém a saída do processo de enriquecimento.

| Column               | Tipo             |  Descrição                                          |
|----------------------|------------------|------------------------------------------------------|
| ID do Cliente           | String           | ID do perfil do cliente                                 |
| EnrichmentProvider   | String           | Nome do fornecedor para o enriquecimento                                  |
| EnrichmentType       | String           | Tipo de enriquecimento                                      |
| Valores               | Cadeia JSON      | Lista de atributos produzidos pelo processo de enriquecimento |
| msdynci_enrichmentid | GUID             | GUID determinista gerada a partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predição

Esta tabela contém a saída das predições do modelo.

| Column               | Tipo        | Descrição                                          |
|----------------------|-------------|------------------------------------------------------|
| ID do Cliente           | String      | ID do Perfil do Cliente                                  |
| ModelProvider        | String      | Nome do fornecedor do modelo                                      |
| Modelo                | String      | Nome do modelo                                                |
| Valores               | Cadeia JSON | Lista de atributos produzidos pelo modelo |
| msdynci_predictionid | GUID        | GUID determinista gerada a partir de msdynci_identifier | 
| msdynci_identifier   | Cadeia (de carateres)      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Associação a segmentos

Esta tabela contém informações de associação a segmentos dos perfis de cliente.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| ID do Cliente        | Cadeia (de carateres)       | ID do Perfil do Cliente        |
| SegmentProvider      | Cadeia (de carateres)       | Aplicação que publica os segmentos.      |
| SegmentMembershipType | Cadeia (de carateres)       | Tipo de cliente neste registo de associação a segmentos. Suporta vários tipos, tais como Cliente, Contacto ou Conta. Predefinição: Cliente  |
| Segmentos       | Cadeia JSON  | Lista de segmentos exclusivos dos quais os perfil de cliente é membro      |
| msdynci_identifier  | Cadeia (de carateres)   | Identificador exclusivo do registo de associação a segmentos. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista gerada a partir de `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->

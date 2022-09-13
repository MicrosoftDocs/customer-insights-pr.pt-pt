---
title: Trabalhar com dados do Customer Insights no Microsoft Dataverse
description: Aprenda a ligar o Customer Insights e o Microsoft Dataverse e compreenda as entidades de saída que são exportadas para o Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424323"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabalhar com dados do Customer Insights no Microsoft Dataverse

O Customer Insights oferece a opção de disponibilizar entidades de saída no [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Esta integração permite uma fácil partilha de dados e desenvolvimento personalizado através de uma abordagem de código baixo/sem código. As [entidades de saída](#output-entities) estão disponíveis como tabelas num ambiente do Dataverse. Pode utilizar os dados de qualquer outra aplicação com base em tabelas do Dataverse. Estas tabelas permitem cenários como fluxos de trabalho automatizados através do Power Automate ou a criação de aplicações com o Power Apps.

A ligação ao seu ambiente Dataverse também permite-lhe [ingerir dados de origens de dados no local utilizando fluxos de dados e gateways do Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Pré-requisitos

- Os ambientes do Customer Insights e do Dataverse têm de ser a hospedados na mesma região.
- Uma função de administrador global configurada no ambiente do Dataverse. Verifique se este [ambiente do Dataverse está associado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de segurança e certifique-se de que é adicionado a esses grupos de segurança.
- Nenhum outro ambiente do Customer Insights está associado ao ambiente do Dataverse que pretende ligar. Saiba como [remover uma ligação existente a um ambiente do Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Um ambiente Microsoft Dataverse ligado a uma única conta de armazenamento se configurar o ambiente para [utilizar o seu Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Elegibilidade da capacidade de armazenamento do Dataverse

Uma subscrição do Customer Insights dá-lhe uma capacidade adicional para a [capacidade de armazenamento do Dataverse](/power-platform/admin/capacity-storage) existente da organização. A capacidade adicionada depende do número de perfis que a sua subscrição utiliza.

**Exemplo:**

Partindo do princípio de que obtém 15 GB de armazenamento de bases de dados e 20 GB de armazenamento de ficheiros por 100.000 perfis de cliente. Se a sua subscrição incluir 300.000 perfis de clientes, a sua capacidade total de armazenamento é de 45 GB (3 x 15 GB) de armazenamento de ficheiros e de 60 GB (3 x 20 GB). Do mesmo modo, se tiver uma subscrição B2B com contas de 30K, a sua capacidade total de armazenamento é de 45 GB (3 x 15 GB) de armazenamento de bases de dados e de 60 GB de armazenamento de ficheiros (3 x 20 GB).

A capacidade de registo não é incremental e não está fixa para a sua organização.

Para mais informações sobre as elegibilidades de capacidade detalhada, consulte o [Guia de Licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Ligar um ambiente do Dataverse ao Customer Insights

O passo **Microsoft Dataverse** permite-lhe ligar o Customer Insights ao seu ambiente do Dataverse ao [criar um ambiente do Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="partilha de dados com Microsoft Dataverse ativado automaticamente para novos ambientes.":::

1. Forneça o URL do seu ambiente Dataverse ou deixe em branco para que seja criado um para si.

   > [!NOTE]
   > Depois de estabelecer a ligação entre o Customer Insights e o Dataverse, não altere o nome da organização para o ambiente do Dataverse. O nome da organização é utilizado no URL do Dataverse e um nome alterado quebra a ligação ao Customer Insights.

   Os admins do [Power Platform podem controlar quem pode criar novos ambientes Dataverse](/power-platform/admin/control-environment-creation). Se estiver a tentar configurar um novo ambiente do Customer Insights e não conseguir, o admin pode ter desativado a criação de ambientes do Dataverse para todas as pessoas, exceto admins.

1. Se estiver a utilizar a sua própria conta de Armazenamento Data Lake:
   1. Selecione **Ativar a partilha de dados** com o Dataverse.
   1. Introduza o **Identificador de permissões**. Para obter o identificador de permissão, [ative a partilha de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Ative a partilha de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage (pré-visualização)

Na [sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md), verifique se o utilizador de configuração do ambiente Customer Insights tem, pelo menos permissões **Leitor de dados do armazenamento de blobs** no contentor `customerinsights` na conta de armazenamento.

### <a name="limitations"></a>Limitações

- Existe apenas um mapeamento um-para-um entre uma organização do Dataverse e uma conta do Azure Data Lake Storage. Depois de uma organização Dataverse ser ligada a uma conta de armazenamento, não poderá ser ligada a outra conta de armazenamento. Esta limitação impede que o Dataverse preencha várias contas de armazenamento.
- A partilha de dados não funcionará se for necessária uma configuração do Azure Private Link para aceder à sua conta Azure Data Lake Storage, porque está por detrás de uma firewall. Atualmente, o Dataverse não suporta a ligação a pontos finais privados através do Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Configurar grupos de segurança no seu Azure Data Lake Storage

1. Crie dois grupos de segurança na sua subscrição do Azure – um  grupo de segurança **Leitor** e um  grupo de segurança **Contribuidor** e defina o serviço Microsoft Dataverse como o proprietário para ambos os grupos de segurança.

1. Efetue a gestão da Lista de Controlo de Acesso (ACL) no contentor `customerinsights` na sua conta de armazenamento através destes grupos de segurança.
   1. Adicione o serviço Microsoft Dataverse e quaisquer aplicações empresariais baseadas no Dataverse, como o Dynamics 365 Marketing ao grupo de segurança **Leitor** com permissões **só de leitura**.
   1. Adicione *só* a aplicação Customer Insights ao grupo de segurança **Contribuidor** para conceder permissões de **leitura e escrita** para escrever perfis e informações.

### <a name="set-up-powershell"></a>Configurar o PowerShell

Configurar o PowerShell para executar scripts de PowerShell.

1. Instalar a versão mais recente do [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   1. No seu PC, selecione a tecla Windows no seu teclado, procure por **Windows PowerShell** e selecione **Executar como administrador**.
   1. Na janela PowerShell que se abre, introduza `Install-Module AzureAD`.

1. Importe três módulos.
   1. Na janela do PowerShell, introduza `Install-Module -Name Az.Accounts` e siga os passos.
   1. Repita para `Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Executar scripts de PowerShell e obter o Identificador de Permissões

1. Transfira os dois scripts do PowerShell de que precisa para executar a partir do [repositório do GitHub](https://github.com/trin-msft/byol) do nosso engenheiro.
   - `CreateSecurityGroups.ps1`: necessita de permissões de administrador de inquilinos
   - `ByolSetup.ps1`: necessita de permissões Proprietário de Dados de Armazenamento de blobs ao nível da conta/contentor de armazenamento. Este script irá criar a permissão para si. A sua atribuição de funções pode ser removida manualmente depois de executar o script com sucesso.

1. Execute `CreateSecurityGroups.ps1` no PowerShell do Windows fornecendo o ID de subscrição do Azure que contém o seu Azure Data Lake Storage. Abra o script do PowerShell num editor para rever informações adicionais e a lógica implementada.

   Este script cria dois grupos de segurança na sua subscrição do Azure: um para o grupo de Leitores e outro para o grupo de Contribuidores. O serviço Microsoft Dataverse é o proprietário de ambos os grupos de segurança.

1. Guarde ambos os valores do ID do grupo de segurança gerados por este script para utilizar no script `ByolSetup.ps1`.

   > [!NOTE]
   > A criação de grupos de segurança pode ser desativada no seu inquilino. Nesse caso, seria necessária uma configuração manual e o seu admin do Azure AD teria de [permitir a criação de grupos de segurança](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Execute `ByolSetup.ps1` no PowerShell do Windows fornecendo o ID de subscrição do Azure que contém o seu Azure Data Lake Storage, nome da conta de armazenamento, nome do grupo de recursos e os valores dos ID dos grupos de segurança de Leitor e Contribuidor. Abra o script do PowerShell num editor para rever informações adicionais e a lógica implementada.

   Este script adiciona o controlo de acesso baseado em funções necessário para o serviço Microsoft Dataverse e quaisquer aplicações empresariais baseadas no Dataverse. Também atualiza a Lista de Controlo de Acesso (ACL) no contentor `customerinsights` para os grupos de segurança criados com o script `CreateSecurityGroups.ps1`. O grupo Contribuidor terá permissão *rwx* e o grupo Leitores terá apenas permissão *r-x*.

1. Copie a cadeia de saída que tem o seguinte aspeto: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Introduza a cadeia de saída copiada para o campo **Identificador de permissões** do passo de configuração do ambiente para o Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opções de configuração para permitir a partilha de dados a partir do seu próprio Azure Data Lake Storage com o Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Remover uma ligação existente a um ambiente do Dataverse

Ao ligar a um ambiente do Dataverse, a mensagem de erro **Esta organização do CDS já está ligada a outra instância do Customer Insights** significa que o ambiente do Dataverse já é utilizado num ambiente do Customer Insights. Pode remover a ligação existente como um administrador global no ambiente do Dataverse. Pode levar duas horas para preencher as mudanças.

1. Ir para o [Power Apps](https://make.powerapps.com).
1. Selecione o ambiente do seletor de ambientes.
1. Vá para **Soluções**.
1. Desinstale ou elimine a solução denominada **Suplemento de Cartões de Cliente do Dynamics 365 Customer Insights (Pré-visualização)**.

OR

1. Abra o seu ambiente do Dataverse.
1. Aceda a **Definições Avançadas** > **Soluções**.
1. Desinstale a solução **CustomerInsightsCustomerCard**.

Se a remoção da ligação falhar devido a dependências, precisa de remover as dependências também. Para obter mais informações, consulte [Remover dependências](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entidades de saída

Algumas entidades de saída do Customer Insights estão disponíveis como tabelas no Dataverse. As secções abaixo descrevem o esquema esperado destas tabelas.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Melhoramento](#enrichment)
- [Predição](#prediction)
- [Associação a segmentos](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Esta tabela contém o perfil de cliente unificado do Customer Insights. O esquema para unified customer profile depende das entidades e atributos utilizados no processo de unificação de dados. Um esquema de perfil do cliente geralmente contém um subconjunto dos atributos da [definição do Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Para o cenário B2B, o perfil de cliente contém contas unificadas e o esquema contém normalmente um subconjunto dos atributos da [Definição do Common Data Model de conta](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

Um ContactProfile contém informações unificadas sobre um contacto. Os contactos são [indivíduos que são mapeados a uma conta](data-unification-contacts.md) num cenário B2B.

| Column                       | Type                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | DateTime       |  Data de nascimento do contacto               |
|  City                 | Texto |  Cidade do endereço do contacto               |
|  ContactId            | Texto |  ID do perfil do contacto               |
|  ContactProfileId     | Identificador exclusivo   |  GUID para o contacto               |
|  CountryOrRegion      | Texto |  País/Região do endereço do contacto               |
|  ID do Cliente           | Texto |  ID da conta à qual o contacto está mapeado               |
|  EntityName           | Texto |  Entidade a partir da qual os dados são obtidos                |
|  FirstName            | Texto |  Nome próprio do contacto               |
|  Sexo               | Texto |  Sexo do contacto               |
|  Id                   | Texto |  GUID determinístico baseado no `Identifier`               |
|  Identificador           | Texto |  ID interno do perfil do contacto: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Texto |  Cargo do contacto               |
|  LastName             | Texto |  Apelido do contacto               |
|  PostalCode           | Texto |  Código postal do endereço do contacto               |
|  PrimaryEmail         | Texto |  Endereço de e-mail do contacto               |
|  PrimaryPhone         | Texto |  Número de telefone do contacto               |
|  StateOrProvince      | Texto |  Estado ou província do endereço do contacto               |
|  StreetAddress        | Texto |  Rua do endereço do contacto               |

### <a name="alternatekey"></a>AlternateKey

A tabela AlternateKey contém chaves das entidades, as quais participaram no processo de unificação.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |Texto         | Nome da origem de dados. Por exemplo: `datasource5`        |
|EntityName        | Texto        | Nome da entidade no Customer Insights. Por exemplo: `contact1`        |
|AlternateValue    |Texto         |ID Alternativo que é mapeado para o ID do cliente. Exemplo: `cntid_1078`         |
|KeyRing           | Texto        | Valor JSON  </br> Exemplo: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|ID do Cliente         | Texto        | ID do perfil de cliente unificado.         |
|AlternateKeyId     | Identificador exclusivo        |  GUID determinístico AlternateKey baseado no `Identifier`      |
|Identificador |   Texto      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta tabela contém atividades de utilizadores que estão disponíveis no Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| ID do Cliente        | Texto      | ID do perfil do cliente                                                                      |
| ActivityId        | Texto      | ID interno da atividade do cliente (chave primária)                                       |
| SourceEntityName  | Texto      | Nome da entidade fornecida com o programa                                                                |
| SourceActivityId  | Texto      | Chave primária da entidade fornecida com o programa                                                       |
| ActivityType      | Texto      | Tipo de atividade semântica ou nome de atividade personalizada                                        |
| ActivityTimeStamp | DateTime    | Carimbo de data/hora da Atividade                                                                      |
| Title             | Texto      | Título ou nome da atividade                                                               |
| Description       | Texto      | Descrição da atividade                                                                     |
| URL               | Texto      | Ligação a um URL externo específico à atividade                                         |
| SemanticData      | Texto | Inclui uma lista de pares de valores de chave para campos de mapeamento semântico específicos para o tipo de atividade |
| RangeIndex        | Texto      | Carimbo de data/hora Unix utilizado para ordenar consultas de intervalo de eficácia e de intervalo de tempo |
| UnifiedActivityId   | Identificador exclusivo | ID interno da atividade do cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta tabela contém os dados de saída das medidas baseadas no atributo do cliente.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| ID do Cliente         | Texto           | ID do perfil do cliente        |
| Medições           | Texto      | Inclui uma lista de pares de valores de chave para nome e valores de medida para determinado cliente |
| Identificador | Texto           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Identificador exclusivo     | ID do perfil do cliente |

### <a name="enrichment"></a>Melhoramento

Esta tabela contém a saída do processo de enriquecimento.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| ID do Cliente           | Texto           | ID do perfil do cliente                                 |
| EnrichmentProvider   | Texto           | Nome do fornecedor para o enriquecimento                                  |
| EnrichmentType       | Texto           | Tipo de enriquecimento                                      |
| Valores               | Texto      | Lista de atributos produzidos pelo processo de enriquecimento |
| EnrichmentId | Identificador exclusivo            | GUID determinista gerada a partir de `Identifier` |
| Identificador   | Texto           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Previsão

Esta tabela contém a saída das predições do modelo.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| ID do Cliente           | Texto      | ID do perfil do cliente                                  |
| ModelProvider        | Texto      | Nome do fornecedor do modelo                                      |
| Modelo                | Texto      | Nome do modelo                                                |
| Valores               | Texto | Lista de atributos produzidos pelo modelo |
| PredictionId | Identificador exclusivo       | GUID determinista gerada a partir de `Identifier` |
| Identificador   | Texto      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Associação a segmentos

Esta tabela contém informações de associação a segmentos dos perfis de cliente.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| ID do Cliente        | Texto       | ID do Perfil do Cliente        |
| SegmentProvider      | Texto       | Aplicação que publica os segmentos.      |
| SegmentMembershipType | Texto       | Tipo de cliente para este registo de associação a segmentos. Suporta vários tipos, tais como Cliente, Contacto ou Conta. Predefinição: Cliente  |
| Segmentos       | Texto  | Lista de segmentos exclusivos dos quais os perfil de cliente é membro      |
| Identificador  | Texto   | Identificador exclusivo do registo de associação a segmentos. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Identificador exclusivo      | GUID determinista gerada a partir de `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]

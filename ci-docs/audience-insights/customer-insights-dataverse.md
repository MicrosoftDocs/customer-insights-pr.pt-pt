---
title: Dados do Customer Insights no Microsoft Dataverse
description: Utilize entidades do Customer Insights como tabelas no Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547640"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabalhar com dados do Customer Insights no Microsoft Dataverse

O Customer Insights oferece a opção de disponibilizar entidades de saída no [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Esta integração permite uma fácil partilha de dados e desenvolvimento personalizado através de uma abordagem de código baixo/sem código. As [entidades de saída](#output-entities) estão disponíveis como tabelas num ambiente do Dataverse. Pode utilizar os dados de qualquer outra aplicação com base em tabelas do Dataverse. Estas tabelas permitem cenários como fluxos de trabalho automatizados através do Power Automate ou a criação de aplicações com o Power Apps. A implementação atual suporta principalmente procuras onde dados das entidades do Customer Insights disponíveis pode ser obtidos para um determinado ID de cliente.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Anexar um ambiente Dataverse ao Customer Insights

**Organização existente**

Os administradores podem configurar o Customer Insights para [utilizar um ambiente do Dataverse existente](create-environment.md) quando criam um ambiente do Customer Insights. Ao fornecer o URL ao ambiente do Dataverse, está ligado ao seu novo ambiente de informações de audiência. Os ambientes do Customer Insights e do Dataverse têm de ser a hospedados na mesma região. 

Se não quiser utilizar um ambiente do Dataverse existente, o sistema cria um novo ambiente para os dados do Customer Insights no seu inquilino. 

> [!NOTE]
> Se as suas organizações já usam o Dataverse no seu inquilino, é importante lembrar que a [criação do ambiente do Dataverse é controlada por um admin](/power-platform/admin/control-environment-creation). Por exemplo, se estiver a criar um novo ambiente de informações de audiência com a sua conta organizacional e o administrador tiver desativado a criação de ambientes do Dataverse experimentais para todos, exceto admins, não pode criar um novo ambiente experimental.
> 
> Os ambientes do Dataverse de avaliação criados no Customer Insights têm 3 GB de armazenamento que não contam para a capacidade global de direito do inquilino. As subscrições pagas têm direito Dataverse de 15 GB para base de dados e 20 GB para armazenamento de ficheiros.

**Nova organização**

Se criar uma nova organização ao configurar o Customer Insights, o sistema cria automaticamente um novo ambiente do Dataverse na sua organização por si.

## <a name="output-entities"></a>Entidades de saída

Algumas entidades de saída de informações de audiência estão disponíveis como tabelas no Dataverse. As secções abaixo descrevem o esquema esperado destas tabelas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Melhoramento](#enrichment)
- [Predição](#prediction)
- [Associação a segmentos](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Esta tabela contém o perfil de cliente unificado do Customer Insights. O esquema para um perfil de cliente unificado depende das entidades e atributos utilizados no processo de união. Um esquema de perfil do cliente geralmente contém um subconjunto dos atributos da [definição do Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

A tabela AlternateKey contém chaves das entidades, as quais participaram no processo de unificação.

|Column  |Tipo  |Descrição  |
|---------|---------|---------|
|DataSourceName    |String         | Nome da origem de dados. Por exemplo: `datasource5`        |
|EntityName        | String        | Nome da entidade nas informações de audiência. Por exemplo: `contact1`        |
|AlternateValue    |String         |ID Alternativo que é mapeado para o ID do cliente. Exemplo: `cntid_1078`         |
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

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| ID do Cliente        | Cadeia (de carateres)       | ID do Perfil do Cliente        |
| SegmentProvider      | Cadeia (de carateres)       | Aplicação que publica os segmentos. Predefinição: Informações de audiência         |
| SegmentMembershipType | Cadeia (de carateres)       | Tipo de cliente neste registo de associação a segmentos. Suporta vários tipos, tais como Cliente, Contacto ou Conta. Predefinição: Cliente  |
| Segmentos       | Cadeia JSON  | Lista de segmentos exclusivos dos quais os perfil de cliente é membro      |
| msdynci_identifier  | Cadeia (de carateres)   | Identificador exclusivo do registo de associação a segmentos. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista gerada a partir de `msdynci_identifier`          |

---
title: Dados do Customer Insights no Microsoft Dataverse
description: Utilize entidades do Customer Insights como tabelas no Microsoft Dataverse.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9855ff6908001dd18bc19a286fc56620d0a127e5
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645232"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabalhar com dados do Customer Insights no Microsoft Dataverse

O Customer Insights oferece a opção de disponibilizar entidades de saída no [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Esta integração permite uma fácil partilha de dados e desenvolvimento personalizado através de uma abordagem de código baixo/sem código. As entidades de saída estarão disponíveis como tabelas no Dataverse. Estas tabelas permitem cenários como [fluxos de trabalho automatizados através do Power Automate](/power-automate/getting-started), [aplicações condicionadas por modelo](/powerapps/maker/model-driven-apps/) e [aplicações de tela](/powerapps/maker/canvas-apps/) através do Power Apps. Pode utilizar os dados para qualquer outra aplicação que se baseie em tabelas do Dataverse. A implementação atual suporta principalmente as pesquisas onde os dados das entidades de informações de audiência disponíveis podem ser obtidos para um determinado ID de cliente.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Anexar um ambiente Dataverse ao Customer Insights

**Organizações com ambientes do Dataverse existentes**

As organizações que já utilizam o Dataverse podem [usar um dos seus ambientes do Dataverse existentes](create-environment.md) quando um administrador configurar informações de audiência. Ao fornecer o URL ao ambiente do Dataverse, está ligado ao seu novo ambiente de informações de audiência. Para garantir o melhor desempenho possível, os ambientes do Customer Insights e do Dataverse têm de estar alojados na mesma região.

**Nova organização**

Se criar uma nova organização ao configurar o Customer Insights, obterá automaticamente um novo ambiente do Dataverse.

> [!NOTE]
> Se as suas organizações já usam o Dataverse no seu inquilino, é importante lembrar que a [criação do ambiente do Dataverse é controlada por um admin](/power-platform/admin/control-environment-creation.md). Por exemplo, se estiver a criar um novo ambiente de informações de audiência com a sua conta organizacional e o administrador tiver desativado a criação de ambientes do Dataverse experimentais para todos, exceto admins, não pode criar um novo ambiente experimental.
> 
> Os ambientes do Dataverse de avaliação criados no Customer Insights têm 3 GB de armazenamento que não contam para a capacidade global de direito do inquilino. As subscrições pagas têm direito Dataverse de 15 GB para base de dados e 20 GB para armazenamento de ficheiros.

## <a name="output-entities"></a>Entidades de saída

Algumas entidades de saída de informações de audiência estão disponíveis como tabelas no Dataverse. As secções abaixo descrevem o esquema esperado destas tabelas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Melhoramento](#enrichment)
- [Predição](#prediction)


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
| msdynci_enrichmentid | GUID             | GUID determinista gerado a partir do msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predição

Esta tabela contém a saída das predições do modelo.

| Column               | Tipo        | Descrição                                          |
|----------------------|-------------|------------------------------------------------------|
| ID do Cliente           | String      | ID do Perfil do Cliente                                  |
| ModelProvider        | String      | Nome do fornecedor do modelo                                      |
| Modelo                | String      | Nome do modelo                                                |
| Valores               | Cadeia JSON | Lista de atributos produzidos pelo modelo |
| msdynci_predictionid | GUID        | GUID determinista gerado a partir do msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

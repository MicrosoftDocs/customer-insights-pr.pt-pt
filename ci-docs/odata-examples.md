---
title: Exemplos de OData para as APIs do Dynamics 365 Customer Insights
description: Exemplos utilizados normalmente para o Protocolo de Dados Abertos (OData) para consultar as APIs de Customer Insights para rever dados.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740045"
---
# <a name="odata-query-examples"></a>Exemplos de consultas de OData

O Protocolo de Dados Aberto (OData) é um protocolo de acesso a dados criado com protocolos base, como HTTP. Utiliza metodologias normalmente aceites como o REST para a Web. Existem vários tipos de bibliotecas e ferramentas que podem ser utilizadas para consumir serviços de OData.

Este artigo lista algumas consultas de exemplo pedidas com frequência para o ajudar a criar implementações próprias com base nas [APIs de Customer Insights](apis.md).

Tem de modificar as amostras de consulta para as fazer trabalhar nos ambientes de destino: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` onde {instanceId} está o GUID do ambiente de Customer Insights que pretende consultar. A [operação ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) permite-lhe encontrar a {InstanceId} a que tem acesso.
- {CID}: GUID de um registo de cliente unificado. Exemplo: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: identificador da chave primária de um registo de cliente numa origem de dados. Exemplo: `CNTID_1002`
- {DSname}: cadeia com o nome da entidade de um origem de dados que ingerida no Customer Insights. Exemplo: `Website_contacts`.
- {SegmentName}: cadeia com o nome da entidade de saída de um segmento em Customer Insights. Exemplo: `Male_under_40`.

## <a name="customer"></a>Cliente

A tabela seguinte contém um conjunto de consultas de amostra para a entidade *Cliente*.


|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|ID de cliente único     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Chave alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  As chaves alternativas persistem na entidade de cliente unificada       |
|Selecione   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Está presente em    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Chave Alternativa + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Pesquisar  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Devolve os 10 resultados principais de uma cadeia de pesquisa      |
|Associação a segmentos  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Devolve um número predefinido de linhas da entidade de segmentação.      |

## <a name="unified-activity"></a>Atividade unificada

A tabela seguinte contém um conjunto de consultas de exemplo para a entidade *UnifiedActivity*.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Atividade de CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Lista atividades de um perfil de cliente específico |
|Intervalo de tempo da atividade    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Atividades de um perfil de cliente num período de tempo       |
|Tipo de atividade    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Atividade por nome a apresentar     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Ordenação de atividades    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordenar atividades por ordem ascendente ou descendente       |
|Atividade expandida a partir da associação de segmentos  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Outros exemplos

A tabela seguinte contém um conjunto de consultas de amostra para outras entidades

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Medidas de CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Conteúdo melhorado de CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Melhoramento de interesses de CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Na cláusula + Expandir     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

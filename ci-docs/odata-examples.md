---
title: Exemplos de consultas de OData para APIs de Customer Insights
description: Exemplos utilizados normalmente para o Protocolo de Dados Abertos (OData) para consultar as APIs de Customer Insights para rever dados.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387216"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Exemplos de consultas de OData para APIs de Customer Insights

O Protocolo de Dados Aberto (OData) é um protocolo de acesso a dados criado com protocolos base, como HTTP. Utiliza metodologias normalmente aceites como o REST para a Web. Existem vários tipos de bibliotecas e ferramentas que podem ser utilizadas para consumir serviços de OData.

Para o ajudar a compilar as suas próprias implementações com base nas [API de Customer Insights](apis.md), reveja alguns inquéritos de exemplo frequentemente solicitados.

Modifique as amostras de consulta para as fazer funcionar nos ambientes de destino:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` onde {instanceId} está o GUID do ambiente de Customer Insights que pretende consultar. A [operação ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) permite-lhe encontrar a {InstanceId} a que tem acesso.
- {CID}: GUID de um registo de cliente unificado. Exemplo: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: identificador da chave primária de um registo de cliente numa origem de dados. Exemplo: `CNTID_1002`
- {DSname}: cadeia com o nome da entidade de um origem de dados que ingerida no Customer Insights. Exemplo: `Website_contacts`.
- {SegmentName}: cadeia com o nome da entidade de saída de um segmento em Customer Insights. Exemplo: `Male_under_40`.

## <a name="customer"></a>Cliente

Consultas de amostra para a entidade *Cliente*.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|ID de cliente único     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Chave alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  As chaves alternativas persistem na entidade de cliente unificada       |
|Selecione   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Está presente em    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Chave Alternativa + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Pesquisar  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Devolve os 10 resultados principais de uma cadeia de pesquisa      |
|Associação a segmentos  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Devolve um número predefinido de linhas da entidade de segmentação.      |
|Associação a segmentos para um cliente | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Devolve o perfil de cliente se for membro de um determinado segmento     |

## <a name="unified-activity"></a>Atividade unificada

Consultas de amostra para a entidade *UnifiedActivity*.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Atividade de CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Lista atividades de um perfil de cliente específico |
|Intervalo de tempo da atividade    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Atividades de um perfil de cliente num período de tempo       |
|Tipo de atividade    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Atividade por nome a apresentar     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Ordenação de atividades    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordenar atividades por ordem ascendente ou descendente       |
|Atividade expandida a partir da associação de segmentos  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Outros exemplos

Consultas de exemplo para outras entidades.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Medidas de CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Conteúdo melhorado de CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Melhoramento de interesses de CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Na cláusula + Expandir     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Consultas OData não suportadas

As consultas que se seguem não são suportadas pelo Customer Insights:

- `$filter` em entidades de origem ingeridas. Só pode executar consultas $filter em entidades de sistema criadas pelo Customer Insights.
- `$expand` a partir de uma consulta `$search`. Exemplo: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` a partir de `$select` se apenas um subconjunto de atributos estiver selecionado. Exemplo: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` melhorou afinidades de marca e de interesse para um determinado cliente. Exemplo: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Consulte entidades de saída do modelo de predição através de chave alternativa. Exemplo: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`

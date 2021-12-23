---
title: Auditar o Dynamics 365 Customer Insights com o Azure Monitor
description: Saiba como enviar registos para o Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920840"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Registar o reencaminhamento no Dynamics 365 Customer Insights com o Azure Monitor (Pré-visualização)

O Dynamics 365 Customer Insights fornece uma integração direta com o Azure Monitor. Os registos de recursos do Azure Monitor permitem monitorizar e enviar registos para o [Armazenamento do Azure](https://azure.microsoft.com/services/storage/), o [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) ou transmiti-los para [Hubs de Eventos do Azure](https://azure.microsoft.com/services/event-hubs/).

O Customer Insights envia os seguintes registos de eventos:

- **Eventos de Auditoria**
  - **APIEvent**: permite o controlo de alterações feito através da IU do Dynamics 365 Customer Insights.
- **Eventos Operacionais**
  - **WorkflowEvent**: o Fluxo de Trabalho permite um para configurar as [Origens de Dados](data-sources.md), [unificar](data-unification.md) e [melhorar](enrichment-hub.md) e finalmente [exportar](export-destinations.md) dados para outros sistemas. Todos estes passos podem ser feitas individualmente (por exemplo, acionar uma única exportação) ou orquestrados (por exemplo, a atualização de dados a partir de origens de dados que acionam o processo de unificação que irá solicitar melhoramentos adicionais e, depois de concluído, exportar os dados para outro sistema). Para mais detalhes, consulte o [Esquema WorkflowEvent](#workflow-event-schema).
  - **APIEvent**: todas as chamadas à API para a instância de clientes para o Dynamics 365 Customer Insights. Para mais detalhes, consulte o [Esquema APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Configurar as definições de diagnóstico

### <a name="prerequisites"></a>Pré-requisitos

Para configurar os diagnósticos no Customer Insights, têm de ser cumpridos os seguintes pré-requisitos:

- Tem uma [Subscrição do Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) ativa.
- Tem permissões de [Administrador](permissions.md#administrator) no Customer Insights.
- Tem a função **Contribuinte** e **Administrador de Acesso ao Utilizador** no recurso de destino no Azure. O recurso pode ser uma conta de Armazenamento do Azure, um Hub de Eventos do Azure ou uma área de trabalho do Azure Log Analytics. Para obter mais informações, consulte [Adicionar ou remova atribuições de funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).
- Os [Requisitos de destino](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) para o Armazenamento do Azure, o Hub de Eventos do Azure ou o Azure Log Analytics são cumpridos.
- Tem pelo menos a função **Leitor** no grupo de recursos ao qual o recurso pertence.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configurar o diagnóstico com o Azure Monitor

1. No Customer Insights, selecione **Sistema** > **Diagnóstico** para ver os destinos de diagnóstico configurados nesta instância.

1. Selecione **Adicionar destino**.

   > [!div class="mx-imgBorder"]
   > ![Ligação ao diagnóstico](media/diagnostics-pane.png "Ligação ao diagnóstico")

1. Forneça um nome no campo **Nome do destino do diagnóstico**.

1. Escolha o **Inquilino** da subscrição do Azure com o recurso de destino e selecione **Iniciar sessão**.

1. Selecione o **Tipo de recurso** (Conta de armazenamento, Hub de Eventos ou análise de registos).

1. Selecione a **Subscrição** para o recurso de destino.

1. Selecione o **Grupo de recursos** para o recurso de destino.

1. Selecione o **Recurso**.

1. Confirme a declaração de **Privacidade e conformidade de dados**.

1. Selecione **Ligar ao sistema** para ligar ao recurso de destino. Os registos começam a aparecer no destino após 15 minutos se a API estiver a ser utilizada e gerar eventos.

### <a name="remove-a-destination"></a>Remover um destino

1. Vá para **Sistema** > **Diagnóstico**.

1. Selecione o destino de diagnóstico na lista.

1. Na coluna **Ações**, selecione o ícone **Eliminar**.

1. Confirme a eliminação para parar o reencaminhamento de registos. O recurso na subscrição do Azure não será eliminado. Pode selecionar a ligação na coluna **Ações** para abrir o portal do Azure para o recurso selecionado e eliminá-lo lá.

## <a name="log-categories-and-event-schemas"></a>Categorias de registo e esquemas de eventos

Atualmente, os [eventos da API](apis.md) e os eventos de fluxo de trabalho são suportados e são aplicáveis as seguintes categorias e esquemas.
O esquema de registo segue o [esquema comum do Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorias

O Customer Insights fornece duas categorias:

- **Eventos de auditoria**: [eventos da API](#api-event-schema) para monitorizar as alterações à configuração no serviço. As operações `POST|PUT|DELETE|PATCH` entram nesta categoria.
- **Eventos operacionais**: [eventos da API](#api-event-schema) ou [eventos de fluxo de trabalho](#workflow-event-schema) gerados enquanto utiliza o serviço.  Por exemplo, os pedidos `GET` ou os eventos de execução de um fluxo de trabalho.

## <a name="configuration-on-the-destination-resource"></a>Configuração no recurso de destino

Com base na sua escolha no tipo de recurso, aplicar-se-ão automaticamente os seguintes passos:

### <a name="storage-account"></a>Storage account

O principal de serviço do Customer Insights obtém a permissão **Contribuidor de Conta de Armazenamento** no recurso selecionado e cria dois contentores no espaço de nomes selecionado:

- `insight-logs-audit` contendo **eventos de auditoria**
- `insight-logs-operational` contendo **eventos operacionais**

### <a name="event-hub"></a>Hub de Eventos

O principal de serviço do Customer Insights obtém a permissão **Proprietário de Dados de Hubs de Eventos do Azure** no recurso e criará dois Hubs de Eventos no espaço de nomes selecionado:

- `insight-logs-audit` contendo **eventos de auditoria**
- `insight-logs-operational` contendo **eventos operacionais**

### <a name="log-analytics"></a>Log Analytics

O principal de serviço do Customer Insights obtém a permissão **Contribuidor de Análise de Registos** no recurso. Os registos estarão disponíveis em **Registos** > **Tabelas** > **Gestão de Registos** na área de trabalho Análise de Registos selecionada. Expanda a solução **Gestão de Registos** e localize as tabelas `CIEventsAudit` e `CIEventsOperational`.

- `CIEventsAudit` contendo **eventos de auditoria**
- `CIEventsOperational` contendo **eventos operacionais**

Na janela **Consultas**, expanda a solução **Auditar** e localize as consultas de exemplo fornecidas ao procurar `CIEvents`.

## <a name="event-schemas"></a>Esquemas de eventos

Os eventos de API e os eventos de fluxo de trabalho têm uma estrutura comum e detalhes onde diferem, consulte [Esquema do evento da API](#api-event-schema) ou [esquema do evento de fluxo de trabalho](#workflow-event-schema).

### <a name="api-event-schema"></a>Esquema do evento da API

| Campo             | DataType  | Obrigatório/Opcional | Description       | Exemplo        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Carimbo de Data/Hora | Necessária          | Carimbo de data/hora do evento (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | Cadeia (de carateres)    | Necessária          | ResourceId da instância que emitiu o evento         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | Cadeia (de carateres)    | Necessária          | Nome da operação representada por este evento.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | Cadeia (de carateres)    | Necessária          | Registar categoria do evento. `Operational` ou `Audit`. Todos os pedidos POST/PUT/PATCH/DELETE HTTP são etiquetados com `Audit`, tudo o resto com `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | Cadeia (de carateres)    | Necessária          | Estado do evento. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | Cadeia (de carateres)    | Opcional          | Estado do resultado do evento. Se a operação corresponder a uma chamada à API REST, é o código de estado HTTP.        | `200`             |
| `durationMs`      | Longo      | Opcional          | Duração da operação em milissegundos.     | `133`     |
| `callerIpAddress` | Cadeia (de carateres)    | Opcional          | Endereço IP do chamador, se a operação corresponder a uma chamada à API com origem num endereço IP disponível publicamente.                                                 | `144.318.99.233`         |
| `identity`        | Cadeia (de carateres)    | Opcional          | Objeto JSON que descreve a identidade do utilizador ou da aplicação que executou a operação.       | Consulte a secção [Identidade](#identity-schema).     |  |
| `properties`      | Cadeia (de carateres)    | Opcional          | Objeto JSON com mais propriedades para a categoria de eventos específica.      | Consulte a secção [Propriedades](#api-properties-schema).    |
| `level`           | Cadeia (de carateres)    | Necessária          | Nível de gravidade do evento.    | `Informational`, `Warning`, `Error` ou `Critical`.           |
| `uri`             | Cadeia (de carateres)    | Opcional          | URI do pedido absoluto.    |               |

#### <a name="identity-schema"></a>Esquema de identidade

O objeto JSON `identity` tem a seguinte estrutura

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Campo                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Função atribuída ao utilizador ou à aplicação. Para mais informações, consulte [permissões de utilizador](permissions.md).                                     |
| `Authorization.RequiredRoles` | Funções necessárias para executar a operação. A função `Admin` tem permissão para executar todas as operações.                                                    |
| `Claims`                      | Afirmações do JWT (Tokens Web JSON) do utilizador ou da aplicação. As propriedades das afirmações variam consoante a organização e a configuração do Azure Active Directory. |

#### <a name="api-properties-schema"></a>Esquema de propriedades da API

Os [Eventos da API](apis.md) têm as seguintes propriedades.

| Campo                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sempre `ApiEvent`, que marca o evento de registo como um evento da API.                                                                 |
| `properties.userAgent`       | Agente do browser que envia o pedido ou `unknown`.                                                                        |
| `properties.method`          | Método HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Caminho relativo do pedido.                                                                                          |
| `properties.origin`          | URI que indica a origem de uma obtenção ou `unknown`.                                                                  |
| `properties.operationStatus` | `Success` para o código de Estado HTTP < 400 <br> `ClientError` para o código de Estado HTTP < 500 <br> `Error` para o Estado HTTP >= 500 |
| `properties.tenantId`        | ID da Organização                                                                                                        |
| `properties.tenantName`      | Nome da organização.                                                                                              |
| `properties.callerObjectId`  | ObjectId do Azure Active Directory do chamador.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Esquema do evento do fluxo de trabalho

O fluxo de trabalho contém vários passos. [Ingerir origens de dados](data-sources.md), [unificar](data-unification.md), [melhorar](enrichment-hub.md) e [exportar](export-destinations.md) dados. Todos esses passos podem ser executados individualmente ou orquestrados com os seguintes processos. 

#### <a name="operation-types"></a>Tipos de operação

| OperationType     | Agrupar                                     |
| ----------------- | ----------------------------------------- |
| Ingestão         | [Origens de dados](data-sources.md)           |
| DataPreparation   | [Origens de dados](data-sources.md)           |
| Mapa               | [Unificação de dados](data-unification.md)   |
| Match             | [Unificação de dados](data-unification.md)   |
| Unir             | [Unificação de dados](data-unification.md)   |
| ProfileStore      | [Perfis de cliente](customer-profiles.md) |
| Pesquisar            | [Perfis de cliente](customer-profiles.md) |
| Atividade          | [Atividades](activities.md)                  |
| AttributeMeasures | [Segmentos e Medidas](segments.md)      |
| EntityMeasures    | [Segmentos e Medidas](segments.md)      |
| Medições          | [Segmentos e Medidas](segments.md)      |
| Segmentação      | [Segmentos e Medidas](segments.md)      |
| Melhoramento        | [Melhoramento](enrichment-hub.md)                                          |
| Informações      | [Predições](predictions-overview.md)                                          |
| AiBuilder         | [Predições](predictions-overview.md)                                          |
| Informações          | [Predições](predictions-overview.md)                                          |
| Export            | [Exportações](export-destinations.md)                                          |
| ModelManagement   | [Predições](custom-models.md)                                           |
| Relação      | [Unificação de dados](relationships.md)                                           |

#### <a name="field-description"></a>Descrição do campo

| Campo           | DataType  | Obrigatório/Opcional | Description                                                                                                                                                   | Exemplo                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Carimbo de Data/Hora | Necessária          | Carimbo de data/hora do evento (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | Cadeia (de carateres)    | Necessária          | ResourceId da instância que emitiu o evento.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | Cadeia (de carateres)    | Necessária          | Nome da operação representada por este evento. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Consulte [Tipos de Operação](#operation-types) para referência. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | Cadeia (de carateres)    | Necessária          | Registar categoria do evento. Sempre `Operational` para eventos de Fluxo de Trabalho                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | Cadeia (de carateres)    | Necessária          | Estado do evento. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Longo      | Opcional          | Duração da operação em milissegundos.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | Cadeia (de carateres)    | Opcional          | Objeto JSON com mais propriedades para a categoria de eventos específica.                                                                                        | Consulte a subsecção [Propriedades de Fluxo de Trabalho](#workflow-properties-schema)                                                                                                       |
| `level`         | Cadeia (de carateres)    | Necessária          | Nível de gravidade do evento.                                                                                                                                  | `Informational`, `Warning` ou `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Esquema de propriedades de fluxo de trabalho

Os eventos de fluxo de trabalho têm as seguintes propriedades.

| Campo              | Fluxo de trabalho | Tarefa | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Sim      | Sim  | Sempre `WorkflowEvent`, que marca o evento como um evento de fluxo de trabalho.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Sim      | Sim  | Identificador da regra de fluxo de trabalho. Todos os eventos de fluxo de trabalho e tarefas na execução do fluxo de trabalho têm o mesmo `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Sim      | Sim  | Identificador da operação, consulte [Tipos de operação].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Sim      | No   | Apenas fluxo de trabalho. Número de tarefas que o fluxo de trabalho aciona.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Sim      | No   | Opcional. Apenas eventos do fluxo de trabalho. O [objectId do utilizador](/azure/marketplace/find-tenant-object-id#find-user-object-id) do Azure Active Directory que acionou o fluxo de trabalho, consulte também `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Sim      | No   | Atualização `full` ou `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Sim      | No   | `OnDemand` ou `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Sim      | No   | `Running` ou `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Sim      | Sim  | Carimbo de Data/Hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Sim      | Sim  | Carimbo de Data/Hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Sim      | Sim  | Carimbo de Data/Hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Sim      | Sim  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Sim  | - Para OperationType = `Export`, o identificar é o guid da configuração de exportação. <br> - Para OperationType = `Enrichment`, é o guid do melhoramento <br> - Para OperationType `Measures` e `Segmentation`, o identificar é o nome da entidade. |
| `properties.friendlyName`                    | No       | Sim  | Nome amigável da exportação ou da entidade que é processada.                                                                                                                                                                                           |
| `properties.error`                           | No       | Sim  | Opcional. Mensagem de erro com mais detalhes.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Sim  | Opcional. Apenas para OperationType `Export`. Identifica o tipo de exportação. Para mais informações, consulte [descrição geral dos destinos de exportação](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Sim  | Opcional. Apenas para OperationType `Export`. Contém uma lista de entidades configuradas na exportação.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Sim  | Opcional. Apenas para OperationType `Export`. Mensagem detalhada para a exportação.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Sim  | Opcional. Apenas para OperationType `Segmentation`. Indica o número total de membros que o segmento tem.                                                                                                                                                    |

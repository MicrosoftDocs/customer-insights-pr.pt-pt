---
title: Ingestão de dados em tempo real (pré-visualização)
description: Informações gerais sobre as capacidades em tempo real no Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2652e0868f5cc514ab6df9c150a9183cf95ae589
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246122"
---
# <a name="real-time-data-ingestion-preview"></a>Ingestão de dados em tempo real (pré-visualização)

A funcionalidade em tempo quase real permite ver, em poucos segundos, as interações mais recentes dos seus clientes com os seus produtos ou serviços.

[Atualizações programadas](schedule-refresh.md) incluem um grande número de registos e várias operações complexas. Primeiro, os dados são extraídos da origem de dados. Em seguida, os dados são unificados e, em seguida, melhorados com informações adicionais. Cada execução deste processo pode demorar desde minutos a horas.

A funcionalidade em tempo real fornece dados imediatamente para consumo, até a subsequente atualização programada extrair estes dados da origem de dados.

As atualizações em tempo real têm uma hora de expiração após a qual deixam de substituir o valor da origem de dados:

- As atualizações do perfil serão mantidas durante quatro horas
- As atividades serão mantidas durante 30 dias

Estes valores são os parâmetros de chamada à API que pode alterar. Visam assegurar que os seus dados de origem permanecem a sua origem da verdade. Se quiser que as atualizações em tempo real sejam incluídas por mais tempo, é necessário adicioná-las a uma origem de dados para que sejam extraídas durante a próxima atualização programada.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Atualização em tempo real dos campos do perfil de cliente unificado

Os perfis atualizados serão mostrados na visualização do cartão do cliente, ou qualquer outra visualização, dentro de alguns segundos.

Como as operações em tempo real ocorrem depois de a unificação de dados ter acontecido, só são aplicáveis aos perfis de cliente unificado. Consequentemente, as alterações ao perfil em tempo real não irão atualizar as medidas, a associação a segmentos ou os melhoramentos.

### <a name="limitations"></a>Limitações

- Os perfis de cliente podem ser atualizados, mas não criados ou eliminados.
- A exportação de atualizações em tempo real para sistemas externos, como o Power BI, não é possível de momento.

## <a name="real-time-creation-of-activities"></a>Criação de atividades em tempo real

A API em tempo real permite-lhe publicar uma nova atividade a partir do seu sistema de origem (um registo de origem individual) para um perfil de cliente unificado. A nova atividade estará disponível como uma atividade unificada na linha cronológica do perfil desse cliente unificado em poucos segundos. Pode ver a cronologia na visualização do cartão de cliente ou qualquer outra integração da cronologia que tenha configurado.

> [!NOTE]
>
> - As atividades são imutáveis. Não são alteradas depois de serem criadas.
> - Atualmente, os segmentos e as medidas não serão atualizados com base na nova atividade.
> - As atividades adicionadas apenas através da API em tempo real não fazem parte das exportações e não serão mostradas no PowerBI.

Há duas formas de ligação ao API em tempo real:

- [indiretamente](#connect-via-the-dynamics-365-customer-insights-connector), através do conector do [Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [diretamente](#connect-directly-to-the-real-time-api), com código

Ambas as formas partilham os seguintes pré-requisitos:

- Um ambiente de Customer Insights
- Perfis de cliente unificados
- Atividades configuradas e executadas
- Permissões de Contribuidor ou Administrador para autenticar a sua conta

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Ligar através do conector do Dynamics 365 Customer Insights

A API em tempo real pode ingerir os dados a partir de um conector do Power Platform dedicado, o conector do [Dynamics 365 Customer Insights](/connectors/customerinsights/), sem a necessidade de escrever e implementar qualquer código.    
O conector pode executar as mesmas ações em tempo real que a API. Necessita de uma licença válida para os conectores premium. Para mais informações, consulte [FAQ sobre o licenciamento do Power Apps e do Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps e/ou Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Para obter detalhes sobre como criar fluxos, consulte a [documentação do Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Ligar directamente à API em tempo real

Pode utilizar as capacidades em tempo real construindo o seu próprio pipeline e ligando-se diretamente ao API em tempo real.    
Poderá publicar uma atividade no formato do seu sistema de origem ou no formato UnifiedActivity. Obtenha o formato ao efetuar uma chamada à API para /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Detalhes desta API, incluindo parâmetros e respostas, podem ser encontrados na secção **EntityData** na [Referência de APIs de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Para mais informações, consulte [Trabalhar com APIs de Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Compreenda a sua utilização em tempo real com telemetria

Obtenha uma visão geral do volume de pedidos para o API em tempo real e informações sobre questões que o sistema possa encontrar. Pode [aceder à telemetria em tempo real](system.md#view-api-usage). 


[!INCLUDE [footer-include](includes/footer-banner.md)]

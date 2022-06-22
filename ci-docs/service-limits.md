---
title: Limites do serviço no Customer Insights
description: Compreenda os limites e restrições no serviço SaaS do Customer Insights.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940682"
---
# <a name="service-limits-in-customer-insights"></a>Limites do serviço no Customer Insights

Este artigo descreve os limites incorporados no serviço Customer Insights, que foram concebidos para assegurar a fiabilidade e estabilidade do serviço. Quaisquer pedidos de alterações podem ser efetuados através do [Fórum de ideias](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Area  | Limites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas e previsões | 300  | O número total de [segmentos](segments.md), [medidas](measures.md) e [previsões](predictions.md) combinados não pode ultrapassar os 300.  |
| Relações | 20 níveis de profundidade em relações nos caminhos de entidades. | Ao criar [segmentos](segments.md) ou [medidas](measures.md) utilizando a interface de construtor, os caminhos de entidades podem ter até 20 saltos de relações entre a entidade inicial e a entidade de destino.  |

## <a name="fair-scheduling-of-jobs"></a>Agendamento de tarefas justo

O Customer Insights é um serviço SaaS que utiliza recursos do Azure partilhados. Os clientes tendem a ter cargas de trabalho de intensidade variável e em agendas diferentes. Para assegurar um acesso justo aos recursos subjacentes, nós certificamo-nos de que os processos do sistema são executados por ordem justa. Exemplos de processos do sistema são tarefas relacionadas com a unificação de dados, a atualização de segmento ou o cálculo de medidas. O agendamento justo protege-o de fazer fila para recursos se houver um pico de tarefas pedidas. Ao mesmo tempo, o Customer Insights não garante que todas as tarefas que colocar em fila sejam processadas em paralelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]

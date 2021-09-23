---
title: Limites de serviço no Dynamics 365 Customer Insights
description: Compreender limites e restrições.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483697"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limites do serviço nas capacidades do Customer Insights

Este artigo descreve os limites incorporados no serviço Customer Insights, que foram concebidos para assegurar a fiabilidade e estabilidade do serviço. Quaisquer pedidos de alterações podem ser efetuados através do [Fórum de ideias](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Informações de Audiência

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limites de serviço da capacidade de informações de audiência do Dynamics 365 Customer Insights

| Área  | Limites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos e medidas | 100 segmentos ou medidas. | O número total de [segmentos](audience-insights/segments.md) ativos e [medidas](audience-insights/measures.md) combinadas não pode exceder 100.  |
| Relações | 20 níveis de profundidade em relações nos caminhos de entidades. | Ao criar [segmentos](audience-insights/segments.md) ou [medidas](audience-insights/measures.md) utilizando a interface de construtor, os caminhos de entidades podem ter até 20 saltos de relações entre a entidade inicial e a entidade de destino.  |


## <a name="engagement-insights"></a>Informações de cativação

### <a name="workspace-and-event-quotas"></a>Quotas de área de trabalho e de eventos

As informações de cativação são uma aplicação altamente escalável que pode suportar milhões de eventos por segundo. Durante a pré-visualização pública, os eventos têm um limiar de volume. Há também um limite para o número de áreas de trabalho numa organização.

### <a name="engagement-insights-limits"></a>Limites das informações de cativação

- Volume máximo de eventos por área de trabalho = 100 eventos por segundo

- Número máximo de áreas de trabalho por organização = 100

Quando os eventos excedem o limiar, pode levar à perda de dados em relatórios baseados nesses eventos. Pode [contactar o suporte](https://go.microsoft.com/fwlink/?linkid=2145734) para solicitar um aumento de volume antes de ultrapassar os limites. Trabalharemos consigo para determinar a sua necessidade de um aumento de volume e apoiar o seu pedido.


[!INCLUDE[footer-include](includes/footer-banner.md)]
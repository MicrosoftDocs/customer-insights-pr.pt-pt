---
title: Limites de serviço
description: Compreender limites e restrições.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034878"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limites de serviço da capacidade de informações de audiência do Dynamics 365 Customer Insights

Este artigo descreve os limites incorporados no serviço Customer Insights, que foram concebidos para assegurar a fiabilidade e estabilidade do serviço. Quaisquer pedidos de alterações podem ser efetuados através do [Fórum de ideias](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Área  | Limites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos e medidas | 100 segmentos ou medidas. | O número total de [segmentos](segments.md) ativos e [medidas](measures.md) combinadas não pode exceder 100.  |
| Relações | 20 níveis de profundidade em relações nos caminhos de entidades. | Ao criar [segmentos](segments.md) ou [medidas](measures.md) utilizando a interface de construtor, os caminhos de entidades podem ter até 20 saltos de relações entre a entidade inicial e a entidade de destino.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
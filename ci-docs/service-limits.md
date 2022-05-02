---
title: Limites de serviço no Dynamics 365 Customer Insights
description: Compreender limites e restrições.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641776"
---
# <a name="service-limits-in-customer-insights"></a>Limites do serviço no Customer Insights

Este artigo descreve os limites incorporados no serviço Customer Insights, que foram concebidos para assegurar a fiabilidade e estabilidade do serviço. Quaisquer pedidos de alterações podem ser efetuados através do [Fórum de ideias](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Area  | Limites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas e previsões | 300  | O número total de [segmentos](segments.md), [medidas](measures.md) e [previsões](predictions.md) combinados não pode ultrapassar os 300.  |
| Relações | 20 níveis de profundidade em relações nos caminhos de entidades. | Ao criar [segmentos](segments.md) ou [medidas](measures.md) utilizando a interface de construtor, os caminhos de entidades podem ter até 20 saltos de relações entre a entidade inicial e a entidade de destino.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]

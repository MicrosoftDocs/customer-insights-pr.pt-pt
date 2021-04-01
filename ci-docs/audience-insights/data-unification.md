---
title: Unificação de dados
description: Obtenha mais informações sobre como unificar os dados ingeridos.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597893"
---
# <a name="data-unification-overview"></a>Descrição geral da unificação de dados

Após [definir as origens dos dados](data-sources.md), é possível unificar os dados. A unificação dos dados inclui três passos: **Mapear**, **Corresponder** e **Intercalar**.

O processo de unificação de dados permite unificar origens de dados anteriormente dispersos num único conjunto de dados principal que fornece uma vista unificada dos seus clientes. As fases de Unificação são obrigatórias e executadas pela seguinte ordem:

1. [Mapa](map-entities.md)
2. [Corresponder](match-entities.md)
3. [Intercalar](merge-entities.md)

Depois de concluir a unificação dos dados, pode

- [configurar as relações entre entidades](relationships.md) para criar segmentos sofisticados
- [enriquecer os dados](enrichment-hub.md) para obter uma gama mais vasta de informações sobre os seus clientes
- [definir atividades](activities.md) a partir de alguns dos atributos ingeridos


[!INCLUDE[footer-include](../includes/footer-banner.md)]
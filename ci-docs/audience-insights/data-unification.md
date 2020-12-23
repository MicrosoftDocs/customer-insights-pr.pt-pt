---
title: Unificação de dados
description: Obtenha mais informações sobre como unificar os dados ingeridos.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406613"
---
# <a name="data-unification"></a>Unificação de dados

Após [definir as origens dos dados](data-sources.md), é possível unificar os dados. A unificação dos dados inclui três passos: **Mapear**, **Corresponder** e **Intercalar**.

O processo de unificação de dados permite unificar origens de dados anteriormente dispersos num único conjunto de dados principal que fornece uma vista unificada dos seus clientes. As fases de Unificação são obrigatórias e executadas pela seguinte ordem:

1. [Mapa](map-entities.md)
2. [Corresponder](match-entities.md)
3. [Intercalar](merge-entities.md)

Depois de concluir a unificação dos dados, pode

- [configurar as relações entre entidades](relationships.md) para criar segmentos sofisticados
- [enriquecer os dados](enrichment-hub.md) para obter uma gama mais vasta de informações sobre os seus clientes
- [definir atividades](activities.md) a partir de alguns dos atributos ingeridos

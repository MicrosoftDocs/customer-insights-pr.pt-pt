---
title: Criar uma vista unificada dos seus clientes
description: Passe pelo processo de unificação de dados com os seus dados para criar um único conjunto de dados principal de perfis de clientes.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-unify
ms.openlocfilehash: 694bfd0e407975af64ca0971a73fe4c3f5ba5a23
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648085"
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
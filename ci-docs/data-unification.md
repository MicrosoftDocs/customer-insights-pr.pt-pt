---
title: Criar uma vista unificada dos seus clientes
description: Passe pelo processo de unificação de dados com os seus dados para criar um único conjunto de dados de unified customer profiles.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755748"
---
# <a name="data-unification-overview"></a>Descrição geral da unificação de dados

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Após [definir as origens dos dados](data-sources.md), é possível unificar os dados. A unificação de dados permite-lhe unificar origens de dados separadas num único conjunto de dados que fornece uma vista unificada desses dados. Para consumidores individuais (B-to-C) em que os dados estão centrados em torno de indivíduos, a unificação fornece uma vista unificada dos seus clientes. Para contas empresariais (B-to-B) em que os dados estão centrados em torno de contas, a unificação fornece uma vista unificada das suas contas.

Os dados podem ser unificados numa única entidade ou em várias entidades. A unificação é realizada na seguinte ordem:

1. [Campos de origem](map-entities.md) (anteriormente denominado Mapa): no passo dos campos de origem, selecione as entidades e os campos a incluir no processo de unificação. Mapeie os campos para um tipo de semântica comum que descreva a finalidade do campo.

1. [Registos duplicados](remove-duplicates.md) (anteriormente pertencentes à Correspondência): no passo de registos duplicados, opcionalmente, defina regras para remover registos de clientes duplicados de cada entidade.

1. [Condições de correspondência](match-entities.md) (anteriormente denominada Correspondência): no passo de condições de correspondência, defina regras que estabelecerem a correspondência entre os registos dos clientes e as entidades. Quando um cliente é encontrado em duas ou mais entidades, é criado um único registo consolidado com todas as colunas e dados de cada entidade.

1. [Campos de cliente unificados](merge-entities.md) (anteriormente denominado União): no passo de campos de cliente unificados, determine que campos de origem devem ser incluídos, excluídos ou unidos num unified customer profile.  

1. [Reveja](review-unification.md) e crie o perfil unificado.

Depois de concluir a unificação dos dados, pode:

- [Configurar as relações entre entidades](relationships.md) para criar segmentos sofisticados.
- [Enriquecer os dados](enrichment-hub.md) para obter uma gama mais vasta de informações sobre os seus clientes.
- [Definir atividades](activities.md) a partir de alguns dos atributos ingeridos.
- [Criar medidas](measures.md) para compreender melhor o comportamento dos clientes e o desempenho do negócio.

[!INCLUDE [footer-include](includes/footer-banner.md)]

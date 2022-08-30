---
title: Criar uma vista unificada dos seus clientes
description: Passe pelo processo de unificação de dados com os seus dados para criar um único conjunto de dados principal de conta ou perfis de clientes.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304441"
---
# <a name="data-unification-overview"></a>Descrição geral da unificação de dados

Após [definir as origens dos dados](data-sources.md), é possível unificar os dados. A unificação de dados permite-lhe unificar origens de dados separadas num único conjunto de dados que fornece uma vista unificada desses dados.

Para consumidores individuais (B-to-C) em que os dados estão centrados em torno de indivíduos, a unificação fornece uma vista unificada dos seus clientes. Para contas empresariais (B-to-B) em que os dados estão centrados em torno de contas, a unificação fornece uma vista unificada das suas contas. [A unificação de contactos (pré-visualização)](data-unification-contacts.md) permite que os contactos dessas contas sejam unificados separadamente e associados às contas.

Os dados podem ser unificados numa única entidade ou em várias entidades.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

O processo de unificação mapeia dados de clientes a partir das suas origens de dados, remove duplicados, faz a correspondência de dados em todas as entidades e cria um perfil unificado. A unificação é realizada na seguinte ordem:

1. [Campos de origem](map-entities.md) (anteriormente denominado Mapa): no passo dos campos de origem, selecione as entidades e os campos a incluir no processo de unificação. Mapeie os campos para um tipo de semântica comum que descreva a finalidade do campo.

1. [Registos duplicados](remove-duplicates.md) (anteriormente pertencentes à Correspondência): no passo de registos duplicados, opcionalmente, defina regras para remover registos de clientes duplicados de cada entidade.

1. [Condições de correspondência](match-entities.md) (anteriormente denominada Correspondência): no passo de condições de correspondência, defina regras que estabelecerem a correspondência entre os registos dos clientes e as entidades. Quando um cliente é encontrado em duas ou mais entidades, é criado um único registo consolidado com todas as colunas e dados de cada entidade.

1. [Campos de cliente unificados](merge-entities.md) (anteriormente denominado União): no passo de campos de cliente unificados, determine que campos de origem devem ser incluídos, excluídos ou unidos num unified customer profile.  

1. [Reveja](review-unification.md) e crie o perfil unificado.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

O processo de unificação mapeia dados de conta a partir das suas origens de dados, remove duplicados, faz a correspondência de dados em todas as entidades e cria um perfil unificado. A unificação é realizada na seguinte ordem:

1. [Campos de origem](map-entities.md) (anteriormente denominados Mapa): no passo dos campos de origem, selecione as entidades e os campos a incluir no processo de unificação de conta. Mapeie os campos para um tipo de semântica comum que descreva a finalidade do campo.

1. [Registos duplicados](remove-duplicates.md) (anteriormente pertencentes à Correspondência): no passo de registos duplicados, defina opcionalmente regras para remover registos de conta duplicados de cada entidade.

1. [Condições de correspondência](match-entities.md) (anteriormente denominado Correspondência): no passo de condições de correspondência, defina regras que correspondem aos registos de conta e entidades. Quando uma conta é encontrada em duas ou mais entidades, é criado um único registo consolidado com todas as colunas e dados de cada entidade.

1. [Campos de cliente unificados](merge-entities.md) (anteriormente denominado União): no passo de campos de cliente unificados, determine que campos de origem devem ser incluídos, excluídos ou unidos num unified customer profile.  

1. [Reveja](review-unification.md) e crie o perfil unificado.

Depois de unificar contas empresariais, pode, opcionalmente, [unificar contactos (pré-visualização)](data-unification-contacts.md) dessas contas e ligar os contactos unificados às contas unificadas.

---

Depois de concluir a unificação de dados, pode opcionalmente:

- [Configurar as relações entre entidades](relationships.md) para criar segmentos sofisticados.
- [Enriquecer os dados](enrichment-hub.md) para obter uma gama mais vasta de informações sobre os seus clientes.
- [Definir atividades](activities.md) a partir de alguns dos atributos ingeridos.
- [Criar medidas](measures.md) para compreender melhor o comportamento dos clientes e o desempenho do negócio.

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Introdução ao Dynamics 365 Customer Insights
description: Uma descrição geral do Customer Insights ajuda os recursos a começar rapidamente.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304625"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Introdução ao Dynamics 365 Customer Insights

O Customer Insights pode ajudá-lo a criar uma compreensão mais profunda dos seus clientes. Ligar dados de várias origens transacionais, comportamentais e de observação para criar uma vista de 360 graus de um cliente. Utilize estes conhecimentos para conduzir experiências e processos centrados nos clientes. Unificar e compreender os dados dos clientes e aproveitá-los para informações e ações inteligentes.

## <a name="step-1-create-an-environment"></a>Passo 1: Criar um ambiente

Primeiro, crie um ambiente em que trabalhar. Se a sua organização já tiver comprado uma licença, consulte [Criar um ambiente](create-environment.md). Para iniciar uma versão de avaliação para o Customer Insights, consulte [Configurar um ambiente de avaliação](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Passo 2: Explorar o Customer Insights

Da primeira vez que iniciar sessão no Customer Insights, configure definições e explore o produto.

1. [inicie sessão no Customer Insights](https://home.ci.ai.dynamics.com) utilizando a sua conta de utilizador do Microsoft Azure Active Directory (AAD).

1. Altere o ambiente para ver dados de demonstração e [explorar o Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Passo 3: Ingerir, unificar e configurar relações para os seus dados

Os perfis unificados são a base para obter informações e tomar medidas sobre os dados. Traga dados de várias origens e execute o processo de unificação de dados para combinar perfis unificados. Especifique relações entre as entidades ingeridas e utilize funcionalidades de melhoramento para adicionar informações aos perfis.

1. Ingerir dados criando origens de dados a partir de várias opções. Escolha, entre [Azure Data Lake Storage, incluindo o Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) ou [conectores do Power Query](connect-power-query.md).

1. Execute o [processo de unificação de dados](data-unification.md) identificando os [campos de origem](map-entities.md), removendo [duplicados](remove-duplicates.md), [condições de correspondência](match-entities.md) e [campos não unificados](merge-entities.md).

1. Familiarize-se com as [entidades que o sistema cria](entities.md) e crie [relações entre as entidades ingeridas](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Passo 4: Melhorar perfis unificados com predições, atividades e medidas

Com os perfis unificados configurados, melhore os seus dados e aumente ainda mais as informações que fornecem.

1. Escolha entre uma biblioteca em expansão de fornecedores de melhoramento para [melhorar os dados dos seus clientes](enrichment-hub.md).

1. Utilize [modelos de origem](predictions-overview.md) para prever a probabilidade de abandono ou receitas esperadas.

1. [Configure atividades](activities.md) com base em dados ingeridos e visualize interações com os seus clientes numa linha cronológica.

1. [Crie medidas](measures.md) para medir os seus objetivos de negócio e KPIs.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Passo 5: Criar segmentos e ativar dados através de várias opções de exportação

Agora que os dados estão completos e contêm uma ampla variedade de informações sobre os seus clientes, procure formas de agir sobre esses dados.

1. [Crie segmentos](segments.md), subconjuntos da sua base de clientes, para garantir que as suas ações são relevantes para os clientes visados.

1. Navegue pelo catálogo em expansão das [opções de exportação](export-destinations.md) onde pode utilizar os dados do cliente. Por exemplo, pode utilizar dados para gerir promoções e contactar com marketing digital.

1. Reveja as opções de integração, por exemplo, para outras aplicações Dynamics 365 com o [Suplemento de Cartão de Clientes](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]

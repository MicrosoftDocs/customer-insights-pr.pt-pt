---
title: Começar com contas profissionais como audiência alvo principal
description: Mais informações sobre começar com contas profissionais como audiência alvo principal Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ac5ae950a44f7f32e3cb9fdc0ffad05b78fddef0
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673701"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Trabalhar com contas empresariais nas informações de audiência

A capacidade de informações de audiência no Dynamics 365 Customer Insights permite configurar o seu ambiente para diferentes audiências alvo principais: consumidores individuais (B2C) e contas empresariais (B2B). Nos cenários B2C, os dados centram-se nos indivíduos. No B2B, as audiências alvo principais são as contas - organizações ou empresas - e os contactos. Este artigo ajuda-o a começar com um ambiente para contas empresariais. Lista as diferenças para as áreas de funcionalidades em informações de audiência, dependendo do foco do seu ambiente. Para obter mais informações sobre as diferenças, reveja os documentos das áreas de funcionalidades. 

## <a name="create-an-environment-for-business-accounts"></a>Criar um ambiente para contas empresariais

Os administradores podem [criar um ambiente numa organização existente](create-environment.md). Um passo no processo de criação de um novo ambiente pede aos administradores a audiência alvo principal do ambiente. No caso de ser a configuração inicial de informações de audiência após a compra de uma licença, uma experiência guiada ajuda na criação do primeiro ambiente.

Em seguida, pode [ingerir dados](data-sources.md) para contas empresariais e contactos relacionados como origens de dados de todas as origens suportadas.

Após a unificação dos dados, [especifique as hierarquias de contas](relationships.md#set-up-account-hierarchies) como parte da configuração da relação. Também pode [configurar mapeamentos semânticos](semantic-mappings.md) para ligar entidades de contacto e conta. 

## <a name="switch-between-primary-target-audience"></a>Mudar entre a audiência alvo principal

Se a sua organização mantiver ambientes para clientes individuais e contas empresariais, pode utilizar o comutador no painel esquerdo para escolher a audiência alvo principal.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Comutador para alterar a audiência alvo principal entre clientes individuais e contas empresariais.":::

## <a name="supported-feature-areas"></a>Áreas de funcionalidades suportadas

- [Atividades](activities.md): suporte para contas e contactos relacionados para criar atividades e mostrá-las numa linha cronológica.
- [Relações](relationships.md): o assistente de atividades ajuda a criar relações entre as entidades para que a vista de conta possa mostrar todas as atividades a partir dos contactos. Os contactos podem ser agregados para ver a vista de contacto e as hierarquias podem ser utilizadas para agregações de atividades de contas.
- [Medidas](measures.md): suporta as medidas criadas a partir do construtor de medidas com um único cálculo. Uma definição opcional permite o rollup de subcontas ao criar medidas.
- [Segmentos](segments.md): suporta segmentos que são criados do zero com o construtor de segmentos. Os novos operadores permitem incorporar a hierarquia de contas ao criar segmentos.
- [Ingestão de dados](data-sources.md): todas as funcionalidades nesta área são as mesmas para as contas empresariais e os clientes individuais.
- [Unificação de dados](data-unification.md): todas as funcionalidades nesta área são as mesmas para as contas empresariais e os clientes individuais.
- [Melhoramento](enrichment-hub.md): alguns tipos de melhoramento estão disponíveis apenas para cenários de clientes individuais, enquanto outros estão exclusivamente disponíveis para contas empresariais.
- [Predições e modelos fornecidos com o programa](predictions-overview.md): a predição de abandono transacional contém passos adicionais para as contas empresariais. Outras predições só estão disponíveis para clientes individuais.
- [Ativação e exportação](export-destinations.md): as exportações estão disponíveis para contas empresariais e clientes individuais. Algumas exportações requerem que a configuração adicional e as informações de contacto projetadas nos segmentos subjacentes sejam válidas para contas empresariais.
- [Definições de sistema](system.md) e [gestão de utilizadores](permissions.md): todas as funcionalidades nesta área são as mesmas para as contas empresariais e os clientes individuais.


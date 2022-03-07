---
title: Começar com capacidade de informações de cativação
description: Uma visão geral dos recursos de ajuda para começar rapidamente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225612"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Começar com capacidade de informações de cativação Dynamics 365 Customer Insights (pré-visualização pública)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A capacidade de informações de cativação permite-lhe recolher e medir o comportamento do cliente no seu website. Integra-se com capacidade de informações de audiência para que possa ver análises comportamentais ricas em tempo real ao lado de relatórios de perfil do cliente. Os links deste artigo ajudam-no a definir e configurar rapidamente o seu ambiente.

## <a name="step-1-review-prerequisites"></a>Passo 1: rever os pré-requisitos

Em primeiro lugar, deve ter uma conta de utilizador ativa do Microsoft Azure Active Directory (AAD). Em seguida, leia os seguintes artigos antes de configurar uma área de trabalho de informações de cativação.

- Rever e concordar com os [Termos do serviço](terms-of-service.md) da Microsoft.  
- Leia o artigo [Gerir cookies e consentimento do utilizador](user-consent-storage.md). Em seguida, avalie se precisa de atualizar a notificação de consentimento do utilizador. Se anteriormente não tiver cookies "não essenciais", provavelmente terá de atualizar a sua política do site.
- Reveja o [glossário](glossary.md) para uma rápida introdução aos termos e conceitos chave.

## <a name="step-2-explore-engagement-insights"></a>Passo 2: Explorar informações de cativação

A primeira vez que visitar as informações de cativação, pode configurar definições, rever políticas e explorar a capacidade.

1. Inicie sessão no [portal de capacidade de informações de cativação](https://home.ci.ai.dynamics.com/app/engagement-insights) utilizando a sua conta de utilizador do Microsoft AAD (escolar ou profissional).

1. Selecione a sua região e marque a caixa se optar ativamente por receber atualizações e ofertas por e-mail.

1. Reveja os **Termos de utilização** das informações de cativação (pré-visualização) e **Declaração de privacidade** e, em seguida, selecione **Explorar a demonstração** para aceitar estas definições.

1. Explore o produto utilizando um conjunto de dados de amostra.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Passo 3: configurar uma área de trabalho e criar relatórios

Uma área de trabalho é onde pode ver a atividade do utilizador em tempo real e armazenar e gerir relatórios. Adicione código ao seu website para começar a recolher *eventos*, os dados de atividade que chegam dos utilizadores.

1. [Criar uma área de trabalho](create-workspace.md) e adicionar membros.

1. Adicione o código ao seu [site](instrument-website.md) ou à sua [aplicação móvel](developer-resources.md#capture-events-from-mobile-apps) para ver a atividade de utilizadores que chegam à sua área de trabalho.

1. Veja um [relatório em tempo real](view-reports.md) que mostra utilizadores ativos por browser, dispositivo, sistema operativo, localização e idioma. Também pode criar [relatórios personalizados](custom-reports.md) para criar as suas próprias visualizações.

1. Crie [dimensões](dimensions.md) para ordenar os visitantes por utilizadores novos e retornados, [métricas](metrics.md) para ajudar a compreender melhor o comportamento do utilizador, e [segmentos](segments.md) para identificar subconjuntos de visitantes com base em características ou interações do site.
    
## <a name="step-4-export-data-to-other-channels"></a>Passo 4: Dados de exportação para outros canais

Pode criar *eventos refinados* (uma vista virtual) dos seus dados de análise web. Em seguida, filtre e exporte os dados para Azure Data Lake Storage. Pode ingerir os dados exportados como uma origem de dados.

1. [Criar eventos refinados](refined-events.md) para exportação.

1. [Exporte os dados](export-events.md) para o Azure Data Lake Storage.

1. [Crie uma ligação entre as informações de audiência e as informações de cativação](integrate-audience-insights-engagement-insights.md) para partilhar dados entre as duas capacidades.

1. [Reconheça eventos Web de utilizadores anteriormente autenticados](unknown-to-known.md) com a funcionalidade **desconhecido para conhecido**.

1. Saiba como [eliminar e exportar dados de eventos contendo informações pessoais](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Passo 5: criar e gerir relatórios de funil

Um relatório de funil recolhe informações sobre os passos que ocorrem durante um percurso do cliente através do seu site ou aplicação móvel. Além de criar relatórios de perfil fornecidos com o programa e relatórios personalizados, pode criar um relatório de funil para identificar os caminhos que os seus clientes tomam antes de fazerem uma compra. 

1. [Crie um relatório de funil](funnel-reports.md) para informar as decisões e identificar áreas para otimização e melhorias de processos.

1. Crie relatórios de funil intercanal, assim que tenha instrumentado a sua aplicação móvel com informações de cativação [SDK do Android](get-started-android.md) ou [SDK do iOS](get-started-ios.md).

1. Utilize [informações de funil](funnel-reports.md#funnel-insights) para obter informações mais aprofundadas do comportamento do cliente sobre os passos no seu relatório de funil.
 
## <a name="step-6-stay-connected"></a>Passo 6: Mantenha-se ligado

Agradecemos a sua participação ativa e consideramos todos os comentários relevantes no desenvolvimento de versões futuras. Partilhe o seu comentário e comunique as questões por um destes canais:
- [Comunidade](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Enviar comentários](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Pedir suporte](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

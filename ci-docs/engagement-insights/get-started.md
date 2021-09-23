---
title: Começar com capacidade de informações de cativação
description: Uma visão geral dos recursos de ajuda para começar rapidamente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494608"
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

1. Reveja os **Termos de utilização das informações de cativação (pré-visualização)** e **Declaração de privacidade** e, em seguida, selecione **Explorar a demonstração** para aceitar estas definições.

1. Explore o produto utilizando um conjunto de dados de amostra.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Passo 3: Crie uma área de trabalho e adicione código ao seu website

Uma área de trabalho é onde pode ver a atividade do utilizador em tempo real e armazenar e gerir relatórios. Adicione código ao seu website para começar a recolher *eventos*, os dados de atividade que chegam dos utilizadores.

1. [Criar uma área de trabalho](create-workspace.md) e adicionar membros.

1. [Adicione código ao seu site](instrument-website.md) ou [aplicação móvel](developer-resources.md#capture-events-from-mobile-apps) para ver a atividade de utilizadores que chegam à sua área de trabalho.

1. Veja um [relatório em tempo real](view-reports.md) que mostra utilizadores ativos por browser, dispositivo, sistema operativo, localização e idioma. Também pode criar [relatórios personalizados](custom-reports.md) para criar as suas próprias visualizações.
    
## <a name="step-4-export-data-to-other-channels"></a>Passo 4: Dados de exportação para outros canais

Pode criar *eventos refinados* (uma vista virtual) dos seus dados de análise web. Em seguida, filtre e exporte os dados para Azure Data Lake Storage. Pode ingerir os dados exportados como uma origem de dados. Para mais informações, consulte [Criar uma ligação entre as informações de audiência e as informações de cativação](integrate-audience-insights-engagement-insights.md).

1. [Criar eventos refinados](refined-events.md) para exportação.

1. [Exporte os dados](export-events.md) para o Data Lake Storage.

1. [Crie uma ligação entre as informações de audiência e as informações de cativação](integrate-audience-insights-engagement-insights.md) para partilhar dados entre as duas capacidades.

1. Saiba como [eliminar e exportar dados de eventos contendo informações pessoais](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Passo 5: Mantenha-se ligado

Agradecemos a sua participação ativa e consideramos todos os comentários relevantes no desenvolvimento de versões futuras. Partilhe o seu comentário e comunique as questões por um destes canais:
- [Comunidade](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Enviar comentários](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Pedir suporte](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Começar com capacidade de informações de cativação
description: Uma visão geral dos recursos de ajuda para começar rapidamente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405372"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Começar com capacidade de informações de cativação Dynamics 365 Customer Insights (pré-visualização pública)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A capacidade de informações de cativação permite-lhe recolher e medir o comportamento do cliente no seu website. Integra-se com capacidade de informações de audiência para que possa ver análises comportamentais ricas em tempo real ao lado de relatórios de perfil do cliente. Os links deste artigo ajudam-no a definir e configurar rapidamente o seu ambiente.

## <a name="step-1-review-prerequisites"></a>Passo 1: rever os pré-requisitos

Em primeiro lugar, deve ter uma conta de utilizador ativa de Microsoft Azure Active Directory. Em seguida, leia os seguintes artigos antes de configurar uma área de trabalho de informações de cativação.

- Rever e concordar com os [Termos do Serviço](terms-of-service.md) da Microsoft.  
- Leia o artigo [Gerir cookies e consentimento do utilizador](user-consent-storage.md). Depois de rever este artigo, avalie se precisa atualizar a notificação de consentimento do utilizador. Se anteriormente não tiver cookies "não essenciais", provavelmente terá de atualizar a sua política do site.
- Reveja o [glossário](glossary.md) para uma rápida introdução aos termos e conceitos chave.

## <a name="step-2-explore-engagement-insights"></a>Passo 2: Explorar informações de cativação

A primeira vez que visitar informações de cativação pode configurar definições, rever políticas e explorar o produto.

1. Inicie sessão no [portal de capacidade de informações de cativação](https://pi.dynamics.com) utilizando a sua conta de utilizador Microsoft Azure Active Directory. (Pode ser a sua escola ou conta profissional.)

1. Selecione a sua região e use a caixa de verificação para indicar se deseja optar por receber atualizações e ofertas via e-mail.

1. Reveja os **Termos de utilização de informações de cativação (pré-visualização)** e a **Declaração de Privacidade** e, em seguida, selecione **Explorar a demonstração** para os aceitar.

1. Explore o produto utilizando um conjunto de dados de amostra.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Passo 3: Crie uma área de trabalho e adicione código ao seu website

A área de trabalho é onde pode ver a atividade do utilizador em tempo real, e armazenar e gerir relatórios. Adicione código ao seu website para começar a recolher *eventos*, os dados de atividade que chegam dos utilizadores.

1. [Criar uma área de trabalho](create-workspace.md) e adicionar membros.

1. [Adicione código ao seu site](instrument-website.md) ou [aplicação móvel](developer-resources.md#capture-events-from-mobile-apps) para ver a atividade de utilizadores que chegam à sua área de trabalho.

1. Veja um [relatório em tempo real](view-reports.md) mostrando utilizadores ativos por navegador, dispositivo, sistema operativo, localização e idioma. Também pode criar [relatórios personalizados](custom-reports.md) para criar as suas próprias visualizações.
    
## <a name="step-4-export-data-to-other-channels"></a>Passo 4: Dados de exportação para outros canais

Pode criar *eventos refinados* (uma vista virtual) dos seus dados de análise web. Em seguida, filtre e exporte os dados para Azure Data Lake Storage. Pode ingerir os dados exportados como uma origem de dados. Para mais informações, consulte [Criar uma ligação entre as informações de audiência e as informações de cativação](integrate-audience-insights-engagement-insights.md).

1. [Criar eventos refinados](refined-events.md) para exportação.

1. [Exporte os dados](export-events.md) para o Data Lake Storage.

1. Saiba como [eliminar e exportar dados de eventos contendo informações pessoais](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Passo 5: Mantenha-se ligado

Agradecemos a sua participação ativa e planeamos considerar todos os comentários relevantes no desenvolvimento de lançamentos futuros. Partilhe o seu comentário e comunique as questões por um destes canais:
- [Comunidade](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Enviar comentários](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Pedir suporte](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

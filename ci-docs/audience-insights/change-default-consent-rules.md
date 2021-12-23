---
title: Gerir regras de consentimento predefinidas em segmentos
description: Com a capacidade de gestão de consentimentos, pode desativar ou alterar as regras de consentimento predefinidas se as substituições estiverem ativadas.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884184"
---
# <a name="disable-or-change-default-consent-rules"></a>Desativar ou alterar regras de consentimento predefinidas

Se as suas organizações utilizarem a [capacidade de gestão de consentimentos](../consent-management/overview.md) combinada com informações de audiência, os [administradores podem impor regras de consentimento](activate-consent.md) para os segmentos. 

Com as regras de consentimento aplicadas na área do segmento, cada segmento informa sobre o estado de verificação de consentimento e regras. Se forem permitidas substituições, as regras de consentimento predefinidas são desligadas para segmentos específicos. Cada criador de um segmento pode adicionar mais regras de consentimento para além das regras predefinidas a um segmento. 

## <a name="for-administrators"></a>Para administradores

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Construtor de segmentos com opções de regra de consentimento.":::

**Para desativar as regras de consentimento predefinidas:**

1. Na notificação **Regras de consentimento**, selecione **Ver detalhes**. 

1. Defina o comutador **Regras de consentimento predefinidas** para **Desativado**.

**Para adicionar mais regras de consentimento:**

1. Na notificação **Regras de consentimento**, selecione **Ver detalhes**. 

1. Selecione **Adicionar regras de consentimento** e escolha uma regra de consentimento a partir do menu pendente **Selecionar tipo de dados de consentimento**.

1. Selecione **Guardar** para aplicar a nova regra no segmento.

## <a name="for-contributors"></a>Para os contribuidores

Para criar um segmento sem regras de consentimento impostas, tem de trabalhar com o seu administrador para desativá-las no seu segmento. No entanto, poderá adicionar as suas próprias regras de consentimento aos segmentos dos quais é proprietário e gere.

É um processo de três passos: 
1. [Crie o segmento](segments.md) nas informações da audiência e guarde-o. 

1. Partilhe o nome do segmento com o seu administrador e solicite que [ative as substituições para o seu segmento](activate-consent.md). 

1. Abra os seus segmentos novamente. Na notificação **Regras de consentimento**, selecione **Ver detalhes** e adicione as regras de consentimento que pretende aplicar. Em seguida, **Guardar** e **Executar** o seu segmento.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 

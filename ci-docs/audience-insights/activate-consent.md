---
title: Ativar regras de consentimento para segmentos
description: Siga estes passos para ligar os dados de consentimento e ativar verificações de consentimento em informações de audiência. Um administrador também pode desativar as verificações de consentimento.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790790"
---
# <a name="activate-consent-rules"></a>Ativar regras de consentimento

O [Centro de Consentimento (pré-visualização)](../consent-management/overview.md) ajuda-o a harmonizar os dados de consentimento a partir de várias origens. Utilize a entidade *Consentimento* unificada para aplicar as verificações de consentimento predefinidas. Após a importação de dados de consentimento para o Centro de Consentimento e a configuração das regras para os dados de consentimento importados, a entidade *Consentimento* é automaticamente sincronizada com as informações de audiência.

## <a name="enable-consent-checks"></a>Ativar verificações de consentimento

Com os dados de consentimento importados para o Centro de Consentimento (pré-visualização) e as regras configuradas, pode ativar as verificações de consentimento. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Separador de consentimento nas definições de informações de audiência com os dados de consentimento ativados.":::

1. Nos insights de audiência, vá a **Admin** > **Sistema**.

1. Selecione o separador **Consentimento (pré-visualização)**.

1. Na secção **Ativar verificações de consentimento**, defina o comutador para **Ativado** para todas as áreas que pretende ativar.

1. Selecione a caixa de verificação **Permitir substituição das regras de consentimento predefinidas** para remover as verificações de consentimento predefinidas executadas num determinado segmento. 

1. No menu pendente, selecione onde pretende permitir substituições.     

1. Na secção **Associar consentimento a perfis de clientes**, escolha o atributo que é utilizado como um identificador para ligar os dados de consentimento aos dados do cliente. Será provável que seja um número de telefone ou um endereço de e-mail. 

1. Selecione **Guardar** para aplicar as definições.

## <a name="disable-consent-checks"></a>Desativar verificações de consentimento

Para parar de usar os dados de consentimento em informações de audiência, um administrador tem de atualizar as definições do sistema em conformidade.

1. Nos insights de audiência, vá a **Admin** > **Sistema**.

1. Selecione o separador **Consentimento (pré-visualização)**.

1. Na secção **Ativar verificações de consentimento**, defina o comutador para **Desativado**.

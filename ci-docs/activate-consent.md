---
title: Ativar regras de consentimento para segmentos
description: Siga estes passos para ligar os dados de consentimento e ativar verificações de consentimento no Dynamics 365 Customer Insights. Um administrador também pode desativar as verificações de consentimento.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646642"
---
# <a name="activate-consent-rules"></a>Ativar regras de consentimento

O [Centro de Consentimento (pré-visualização)](consent-management/overview.md) ajuda-o a harmonizar os dados de consentimento a partir de várias origens. Utilize a entidade *Consentimento* unificada para aplicar as verificações de consentimento predefinidas. Após a importação de dados de consentimento para o Centro de Consentimento e a configuração das regras para os dados, a entidade *Consentimento* é automaticamente sincronizada com o Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Ativar verificações de consentimento

Com os dados de consentimento importados para o Centro de Consentimento (pré-visualização) e as regras configuradas, pode ativar as verificações de consentimento. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Separador de consentimento nas definições do Customer Insights com os dados de consentimento ativados.":::

1. No Customer Insights, aceda a **Admin** > **Sistema**.

1. Selecione o separador **Consentimento (pré-visualização)**.

1. Na secção **Ativar verificações de consentimento**, defina o comutador para **Ativado** para todas as áreas que pretende ativar.

1. Selecione a caixa de verificação **Permitir substituição das regras de consentimento predefinidas** para remover as verificações de consentimento predefinidas executadas num determinado segmento. 

1. No menu pendente, selecione onde pretende permitir substituições.     

1. Na secção **Associar consentimento a perfis de clientes**, escolha o atributo que é utilizado como um identificador para ligar os dados de consentimento aos dados do cliente. Será provável que seja um número de telefone ou um endereço de e-mail. 

1. Selecione **Guardar** para aplicar as definições.

## <a name="disable-consent-checks"></a>Desativar verificações de consentimento

Para parar de usar os dados de consentimento no Customer Insights, um admin tem de atualizar as definições do sistema em conformidade.

1. No Customer Insights, aceda a **Admin** > **Sistema**.

1. Selecione o separador **Consentimento (pré-visualização)**.

1. Na secção **Ativar verificações de consentimento**, defina o comutador para **Desativado**.

> [!TIP]
> Para deixar de utilizar a capacidade de gestão do consentimento, consulte [Definições de sistema no Centro de Consentimento (pré-visualização)](consent-management/system-settings.md).

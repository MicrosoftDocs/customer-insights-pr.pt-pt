---
title: Conectores do Power Automate (pré-visualização) | Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196132"
---
# <a name="power-automate-connector-preview"></a>Conector do Power Automate (pré-visualização)

Acione eventos específicos para ocorrerem automaticamente quando os seus dados forem alterados e faça a gestão de fluxos mais complexos diretamente no [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitações conhecidas

- Um máximo de 100 chamadas por cada 60 segundos. Utilize o [parâmetro $skip](/connectors/customerinsights/#get-items-from-an-entity) para chamar o ponto final de API várias vezes.

## <a name="power-automate-triggers"></a>Acionadores do Power Automate

Utilize acionadores para criar fluxos de cloud e automatizar tarefas repetitivas, tais como notificações ou ações mais avançadas. Utilize acionadores quando:

- Uma origem de dados falhar.
- Uma atualização de origem de dados for concluída com êxito.
- Um limiar é ultrapassado num segmento. O acionador limita-se a passar acima do limiar.
- Um limiar é ultrapassado numa medida empresarial. Apenas as medidas de negócio sem uma dimensão são suportadas. O acionador limita-se a passar acima do limiar.
- É concluída uma atualização agendada completa. Este acionador não funciona para as atualizações iniciadas manualmente.
- Uma atualização do processo de unificação é concluída.

[Configure os seus acionadores no Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Ações do Power Automate

O conector do Power Automate fornece outras ações que não os acionadores disponíveis. Para mais informações, consulte o [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Criar um fluxo do Power Automate

1. Aceda a **Admin** > **Ligações**.

1. No mosaico **Power Automate**, selecione **Configurar**.

1. O Conector Customer Insights (pré-visualização) no Power Automate abre-se. **Inicie sessão** no Power Automate.

1. Escolha um dos acionadores disponíveis e adicione mais passos ao seu novo fluxo. Para obter mais informações, consulte [Criar um fluxo de cloud no Power Automate](/power-automate/get-started-logic-flow).

Exemplos de como utilizar fluxos: 
- Publique uma mensagem num canal do Microsoft Teams se uma atualização de origem de dados falhar. 
- Envie um e-mail aos proprietários de dados quando um limiar de um segmento é ultrapassado.

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Conector do Power Automate| Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 409792bc3f12fca451ef038e3300758bdf9ecf3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647219"
---
# <a name="power-automate-connector-preview"></a>Conector do Power Automate (pré-visualização)

Acione eventos específicos para ocorrerem automaticamente quando os seus dados forem alterados e faça a gestão de fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitações conhecidas

- Pode fazer um máximo de 100 chamadas por cada 60 segundos. Pode chamar o ponto final de API várias vezes ao utilizar o parâmetro $skip. [Saiba mais sobre o parâmetro $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Acionadores do Power Automate

Utilize acionadores para criar fluxos de cloud e automatizar tarefas repetitivas, tais como notificações ou ações mais avançadas. 

- É acionado quando uma atualização de origem de dados falha. 
- É acionado quando uma atualização de origem de dados é bem sucedida.
- É acionado quando um limiar é ultrapassado num segmento. O acionador limita-se a passar acima do limiar.
- É acionado quando um limiar é ultrapassado numa medida empresarial. Apenas as medidas de negócio sem uma dimensão são suportadas. O acionador limita-se a passar acima do limiar.
- Acionar quando uma atualização completa de ( origens de dados, segmentos, medidas, ...) é completada.
- Acionar quando uma atualização do processo de unificação (mapa, correspondência, união) estiver concluída.

[Configure os seus acionadores no Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Ações do Power Automate

O conector do Power Automate fornece outras ações que não os acionadores disponíveis. Para mais informações, consulte o [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Criar um fluxo do Power Automate

1. Aceda a **Administrador** > **Destinos de exportação**.

1. No mosaico **Power Automate**, selecione **Configurar**.

1. O Conector Customer Insights (pré-visualização) no Power Automate abre-se. **Inicie sessão** no Power Automate.

1. Escolha um dos acionadores disponíveis e adicione mais passos ao seu novo fluxo. Para obter mais informações, consulte [Criar um fluxo de cloud no Power Automate](/power-automate/get-started-logic-flow).

Exemplos de como utilizar fluxos: 
- Publique uma mensagem num canal do Microsoft Teams se uma atualização de origem de dados falhar. 
- Envie um e-mail aos proprietários de dados quando um limiar de um segmento é ultrapassado.



[!INCLUDE [footer-include](includes/footer-banner.md)]

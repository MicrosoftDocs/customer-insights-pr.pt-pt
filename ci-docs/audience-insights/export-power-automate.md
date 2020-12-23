---
title: Conector do Power Automate| Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406605"
---
# <a name="power-automate-connector-preview"></a>Conector do Power Automate (pré-visualização)

Acione eventos específicos para ocorrerem automaticamente quando os seus dados forem alterados e faça a gestão de fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Acionadores do Power Automate

Pode utilizar uma variedade de acionadores que lhe permitem criar fluxos para automatizar tarefas repetitivas, tais como notificações ou ações mais avançadas. 

- É acionado quando uma atualização de origem de dados falha. 
- É acionado quando uma atualização de origem de dados é bem sucedida.
- É acionado quando um limiar é ultrapassado num segmento. O acionador limita-se a passar acima do limiar.
- É acionado quando um limiar é ultrapassado numa medida empresarial. O acionador limita-se a passar acima do limiar.
- Acionar quando uma atualização completa de ( origens de dados, segmentos, medidas,...) é completada.
- Acionar quando uma atualização do processo de unificação (mapa, correspondência, união) estiver concluída.

[Configure os seus acionadores no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Ações do Power Automate
O conector do Power Automate fornece outras ações que não os acionadores disponíveis. Para mais informações, consulte o [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Criar um fluxo Power Automate nos insights de audiência

1. Nos insights de audiência, vá a **Admin** > **Sistema**.

1. Na página **Sistema**, selecione o separador **Estado**.

1. Na secção **Origens de Dados**, selecione **Fluxos** e selecione **Criar um fluxo** a partir da lista pendente.
   > [!div class="mx-imgBorder"]
   > ![Conector do Power Automate a mostrar a ação Criar um Fluxo](media/power-automate-connector-create-flow.png "Conector do Power Automate a mostrar a ação Criar um Fluxo")

1. No Power Automate, selecione um dos acionadores disponíveis para criar o seu fluxo preferencial. Se estiver a criar o seu primeiro fluxo, terá de efetuar inicialmente a autenticação do conector do Power Automate.

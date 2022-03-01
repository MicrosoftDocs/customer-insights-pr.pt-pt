---
title: Exportar dados do Customer Insights para o Autopilot
description: Aprenda a configurar a ligação ao Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269252"
---
# <a name="connector-for-autopilot-preview"></a>Conector para o Autopilot (pré-visualização)

Exportar segmentos de perfis unificados de clientes para o Autopilot e utilizá-los para marketing de e-mail no Autopilot. 

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta do Autopilot](https://www.autopilothq.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="connect-to-autopilot"></a>Ligar ao Autopilot

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Sob **Autopilot**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Painel de configuração para a ligação ao Autopilot.":::

1. Introduza a sua **Chave de API do Autopilot** [Chave de API do Autopilot](https://autopilot.docs.apiary.io/#).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Autopilot.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Seguinte** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. Repita os mesmos passos para outros campos opcionais, tais como **Nome próprio**, **Apelido**.

1. Selecione os segmentos que quer exportar. **Recomendamos que não exporte mais de 100.000 perfis de clientes no total** para o Autopilot. 

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 100.000 perfis no total para o Autopilot.
- A exportação para o Autopilot está limitada a segmentos.
- Exportar até 100.000 perfis para o Autopilot pode demorar até algumas horas para ser concluído. 
- O número de perfis que pode exportar para o Autopilot é dependente e limitado no seu contrato com o Autopilot.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Autopilot, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados a seu pedido, mas você é responsável por garantir que o Autopilot cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
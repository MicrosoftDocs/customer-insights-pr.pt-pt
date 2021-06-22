---
title: Exportar dados do Customer Insights para o LinkedIn Ads
description: Aprenda a configurar a ligação e exportar para o LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124536"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segmentos para o LinkedIn Ads (pré-visualização)

Segmentos de exportação de perfis de clientes unificados para o LinkedIn Ads para criar Matched Audiences. Utilize as Matched Audiences para direcionamento de empresa e direcionamento de contactos.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta do LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e credenciais correspondentes de administrador.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis de clientes nos segmentos exportados contêm um campo com um endereço de e-mail.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 100 mil perfis por exportação para o LinkedIn Ads.
- A exportação para o LinkedIn Ads limita-se a segmentos.
- Exportar até 100 mil perfis para o LinkedIn Ads pode levar até 10 minutos a ser concluído. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Configure a ligação para o LinkedIn Ads

1. No Audience Insights, vá a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **LinkedIn Ads** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição é administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça o seu [ID da Conta do LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação à Campaign Monitor.

1. Selecione **Autenticar com o LinkedIn** e forneça as suas credenciais de admin para o LinkedIn Campaign Manager.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar uma exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção LinkedIn Ads. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Escolha se pretende exportar dados para [direcionamento de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou [direcionamento de empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) no LinkedIn. 

1. Na secção **Correspondência de dados**, selecione o campo no seu perfil de cliente unificado que representa o endereço de e-mail de um cliente. É obrigatório exportar segmentos para o LinkedIn Ads.

1. Selecione os segmentos que quer exportar. As Matched Audiences no LinkedIn Campaign Manager serão automaticamente criadas com o nome dos segmentos que selecionou para exportar. Cada segmento resultará num Matched Audience separada. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o LinkedIn Ads, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que o LinkedIn Ads cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para parar a utilização desta funcionalidade.

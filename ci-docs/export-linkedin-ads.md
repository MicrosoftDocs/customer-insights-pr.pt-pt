---
title: Exportar segmentos para o LinkedIn Ads (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304717"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segmentos para o LinkedIn Ads (pré-visualização)

Segmentos de exportação de perfis de clientes unificados para o LinkedIn Ads para criar Matched Audiences. Utilize as Matched Audiences para direcionamento de empresa e direcionamento de contactos.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e as credenciais de administrador correspondentes.
- Um [ID de conta do LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmentos configurados](segments.md) no Customer Insights.
- Os segmentos exportados necessitam, pelo menos, de um campo específico, dependendo se escolhe a [focalização de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou a [focalização de empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) no LinkedIn. Os campos possíveis são listados no passo **Correspondência de dados** ao [configurar a exportação](#configure-an-export).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 100.000 perfis de cliente por exportação para o LinkedIn Ads, o que pode demorar até 10 minutos a concluir.
- Apenas segmentos. Um segmento tem de conter pelo menos 300 perfis exclusivos.

## <a name="set-up-connection-to-linkedin-ads"></a>Configurar ligação ao LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **LinkedIn Ads**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça o seu ID de Conta do LinkedIn Campaign Manager.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Autenticar com o LinkedIn** e forneça as suas credenciais de admin para o LinkedIn Campaign Manager.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção LinkedIn Ads. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Escolha se pretende exportar dados para [direcionamento de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou [direcionamento de empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) no LinkedIn.

1. Na secção **Correspondência de dados**, para filtrar por contacto, selecione, pelo menos, um campo que represente o endereço de e-mail de um cliente, o ID do Apple Ad, o ID do Google Ad, o ID de Utilizador do Google ou o nome próprio e o apelido. Se escolher a filtragem por empresa, selecione, pelo menos, um campo que represente um nome da empresa, um domínio de e-mail, o URL da página do LinkedIn, o símbolo de Stock ou o site.

1. Opcionalmente, adicione campos para definir ainda mais a sua exportação. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar. As Matched Audiences no LinkedIn Campaign Manager serão automaticamente criadas com o nome dos segmentos que selecionou para exportar. Cada segmento resultará num Matched Audience separada.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

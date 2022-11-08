---
title: Exportar segmentos para o Klaviyo (pré-visualização)
description: Aprenda a configurar a ligação e a exportar para o Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724646"
---
# <a name="export-segments-to-klaviyo-preview"></a>Exportar segmentos para o Klaviyo (pré-visualização)

Exporte segmentos de perfis de clientes unificados para o Klaviyo e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Klaviyo](https://www.klaviyo.com/) e as credenciais de administrador correspondentes.
- Uma [chave de API do Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- Um [ID de lista do Klaviyo](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- A ligação privada, em combinação com o Traga o seu próprio armazenamento (BYOS) não é suportada.
- Até 1 milhão de perfis de cliente por exportação para o Klaviyo, o que pode demorar até 20 minutos a concluir. O número de perfis de clientes que pode exportar para o Klaviyo depende do seu contrato com o Klaviyo.
- Apenas segmentos.

## <a name="set-up-connection-to-klaviyo"></a>Configurar a ligação para o Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Klaviyo**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça a sua chave de API Klaviyo para continuar a iniciar sessão.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Autenticar com Klaviyo** e forneça as suas credenciais de admin para Klaviyo.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação à exportação**, escolha uma ligação a partir da secção Klaviyo. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Introduza o seu **ID de Lista Klaviyo**.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

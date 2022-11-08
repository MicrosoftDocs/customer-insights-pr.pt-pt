---
title: Exportar segmentos para o Iterable (pré-visualização)
description: Saiba como configurar a ligação e exportar para o Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724618"
---
# <a name="export-segments-to-iterable-preview"></a>Exportar segmentos para o Iterable (pré-visualização)

Exporte segmentos do unified customer profiles para o Iterable e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Iterable](https://iterable.com/) e credenciais de administrador correspondentes.
- Uma [Chave de API do Iterable](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- A ligação privada, em combinação com o Traga o seu próprio armazenamento (BYOS) não é suportada.
- Até 1 milhão de perfis de cliente para o Iterable, que pode demorar até 30 minutos a concluir. O número de perfis de cliente que pode exportar para o Iterable depende do seu contrato com o Iterable.
- Apenas segmentos.

## <a name="set-up-connection-to-iterable"></a>Configure a ligação ao Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Iterable**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça a sua chave de API do Iterable para continuar a iniciar sessão.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação na secção Iterable. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. A lista criada no Iterable receberá exatamente o mesmo nome que o seu nome de segmento no Dynamics 365 Customer Insights.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

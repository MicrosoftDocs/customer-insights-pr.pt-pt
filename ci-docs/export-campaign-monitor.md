---
title: Exportar segmentos para o Monitor de Campanha (pré-visualização)
description: Aprenda a configurar a ligação e exportar para a Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196316"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segmentos para o Monitor de Campanha (pré-visualização)

Exporte segmentos de perfis de clientes unificados para a Campaign Monitor e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Campaign Monitor](https://www.campaignmonitor.com/) e credenciais de administrador correspondentes.
- Um [ID de Lista do Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Uma [Chave de API gerada](https://www.campaignmonitor.com/api/getting-started/) a partir de **Definições de Conta** no Campaign Monitor para obter o ID de lista de API.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente por exportação para a Campaign Monitor, que pode demorar até 20 minutos a concluir. O número de perfis de cliente que pode exportar para o Campaign Monitor depende do seu contrato com o Campaign Monitor.
- Apenas segmentos.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar ligação aa Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Campaign Monitor**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação à Campaign Monitor.

1. Selecione **Autenticar com a Campaign Monitor** e forneça as suas credenciais de admin para a Campaign Monitor.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Para criar um nova exportação, selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Campaign Monitor. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Introduza o seu **ID de Lista do Campaign Monitor**.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. É obrigatório exportar segmentos para a Campaign Monitor.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

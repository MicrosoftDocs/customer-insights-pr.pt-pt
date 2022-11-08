---
title: Exportar segmentos para o Google Ads (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725092"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos para o Google Ads (pré-visualização)

Exporte segmentos de perfis de clientes unificados para uma lista de audiência do Google Ads e utilizá-los para anunciar no Google Search, Gmail, YouTube e Google Display Network.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.
- Um [ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344).
- Os requisitos da [Política do Customer Match](https://support.google.com/adspolicy/answer/6299717) são cumpridos.
- Os requisitos dos [tamanhos da lista de remarketing](https://support.google.com/google-ads/answer/7558048) são cumpridos.
- [Segmentos configurados](segments.md).
- Unified customer profiles nos segmentos exportados contém campos que representam um endereço de e-mail, telefone, ID de anunciante móvel, ID de utilizador de terceiros ou endereço.

## <a name="known-limitations"></a>Limitações conhecidas

- A ligação privada, em combinação com o Traga o seu próprio armazenamento (BYOS) não é suportada.
- Exporte até de 1 milhão de perfis de clientes por exportação para o Google Ads, que pode demorar até 30 minutos a concluir dadas as limitações do lado do fornecedor.
- Apenas segmentos.
- A correspondência no Google Ads pode demorar até 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar ligação ao Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Google Ads**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o seu ID de cliente do Google Ads.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Autenticar com o Google Ads** e forneça as suas credenciais do Google Ads.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Google Ads. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Escolha se deve utilizar um audiência existente ou criar uma nova:
   - Para atualizar um audiência Google Ads existente, introduza o seu [ID de audiência do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns)
   - Para criar uma nova audiência, deixe o campo ID de Audiência da Google em branco. O Customer Insights irá criar automaticamente uma nova audiência na sua conta Google Ads e utilizaremos o nome do segmento exportado.

1. Na secção **Correspondência de dados**, selecione um ou mais campos de dados para exportar e selecione o campo que representa os campos de dados correspondentes no Customer Insights.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

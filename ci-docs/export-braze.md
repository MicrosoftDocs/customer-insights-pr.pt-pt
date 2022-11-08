---
title: Exportar segmentos para o Braze (pré-visualização)
description: Saiba como configurar a ligação e exportar para o Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725230"
---
# <a name="export-segments-to-braze-preview"></a>Exportar segmentos para o Braze (pré-visualização)

Exporte segmentos do unified customer profiles para o Braze e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Braze](https://www.braze.com/) e credenciais de administrador correspondentes.
- Uma [Chave de API da Braze](https://www.braze.com/docs/api/basics/)
- O seu [Ponto final REST do Braze](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segmentos configurados](segments.md) no Customer Insights.
- Unified customer profiles nos segmentos exportados contém um campo que representa um endereço de e-mail e um ID de cliente do Braze.

## <a name="known-limitations"></a>Limitações conhecidas

- A ligação privada, em combinação com o Traga o seu próprio armazenamento (BYOS) não é suportada.
- Até 1 milhão de perfis de cliente para o Braze, que pode demorar até 40 minutos a concluir. O número de perfis de cliente que pode exportar para o Braze depende do seu contrato com o Braze.
- Apenas segmentos.
- O Azure Private Link não é suportado para a exportação do Braze.

## <a name="set-up-connection-to-braze"></a>Configure a ligação ao Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Braze**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça a sua chave de API do Braze para continuar a iniciar sessão.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação na secção Braze. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza o seu ponto final REST no campo **Nome do anfitrião** no seguinte formato: `rest.iad-03.braze.com`.

1. Introduza um nome para a exportação.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. No campo **ID do cliente**, selecione o campo que representa o ID Braze do cliente. Os segmentos no Braze serão criados com o mesmo nome de segmento que no Dynamics 365 Customer Insights. Pode escolher mais campos opcionais para corresponder dados.

1. Selecione as entidades ou segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

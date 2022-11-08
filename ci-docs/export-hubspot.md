---
title: Exportar dados do Customer Insights para o HubSpot
description: Aprenda a configurar a ligação e a exportar para o HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725368"
---
# <a name="export-segments-to-hubspot-preview"></a>Exportar segmentos para o HubSpot (pré-visualização)

Exporte segmentos de perfis de clientes unificados para o HubSpot e utilize-os para marketing de e-mail.

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

- Uma [conta HubSpot](https://www.hubspot.com/) e as correspondentes credenciais de administrador.
- [Chave de API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) do HubSpot.
- [Segmentos configurados](segments.md) no Customer Insights.

## <a name="known-limitations"></a>Limitações conhecidas

- A ligação privada, em combinação com o Traga o seu próprio armazenamento (BYOS) não é suportada.
- Até 100,000 perfis de clientes por exportação para o HubSpot, o que pode demorar até 15 minutos a concluir. O número de perfis de clientes que pode exportar para o HubSpot está dependente e limitado no seu contrato com o HubSpot.
- Apenas segmentos.

## <a name="set-up-connection-to-hubspot"></a>Configure a ligação para a HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **HubSpot** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza as suas credencias do HubSpot quando pedido.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação ao HubSpot.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Para criar um nova exportação, selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção HubSpot. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. Repita os mesmos passos para outros campos opcionais.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Exportar segmentos para o Google Ads (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081646"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos para o Google Ads (pré-visualização)

Exporte segmentos de perfis de clientes unificados para uma lista de audiência do Google Ads e utilizá-los para anunciar no Google Search, Gmail, YouTube e Google Display Network. 


## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

-   Tem uma [conta Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.
-   Cumpre os requisitos da [Política de Correspondência de Clientes](https://support.google.com/adspolicy/answer/6299717).
-   Cumpre os requisitos dos [tamanhos da lista de remarketing](https://support.google.com/google-ads/answer/7558048).
-   Tem [segmentos configurados](segments.md).
-   Unified customer profiles nos segmentos exportados contém campos que representam um endereço de e-mail, telefone, ID de anunciante móvel, ID de utilizador de terceiros ou endereço.

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação para o Google Ads é limitada a segmentos.
- Os segmentos de exportação com um total de 1 milhão de perfis de clientes podem levar até 30 minutos devido a limitações do lado do fornecedor. 
- A correspondência no Google Ads pode demorar até 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar ligação ao Google Ads

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Google Ads** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Autenticar com o Google Ads** e forneça as suas credenciais do Google Ads.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação. 

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Google Ads. Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.

1. Se quiser criar uma nova audiência, deixe o campo ID de Audiência da Google em branco. Iremos criar automaticamente uma nova audiência na sua conta Google Ads e utilizaremos o nome do segmento exportado. Se pretender atualizar um audiência Google Ads existente, introduza o seu [ID de audiência do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Na secção **Correspondência de dados**, selecione um ou mais campos de dados para exportar e selecione o campo que representa os campos de dados correspondentes no Customer Insights.

1. Selecione os segmentos que quer exportar. 

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). 

Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Google Ads, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Google Ads cumprem quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]

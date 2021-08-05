---
title: Exportar dados Customer Insights para o Google Ads
description: Aprenda a configurar a ligação e exportar para o Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c16967bf8ea1fd02b3f991d7b7d3715a71fa8681
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604291"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos para o Google Ads (pré-visualização)

Exporte segmentos de perfis de clientes unificados para uma lista de audiência do Google Ads e utilizá-los para anunciar no Google Search, Gmail, YouTube e Google Display Network. 

## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

-   Tem uma [conta Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.
-   Tem um [token de Programador do Google Ads aprovado](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Cumpre os requisitos da [Política de Correspondência de Clientes](https://support.google.com/adspolicy/answer/6299717).
-   Cumpre os requisitos dos [tamanhos da lista de remarketing](https://support.google.com/google-ads/answer/7558048).
-   Existem audiências no Google Ads e os IDs correspondentes. Para mais informações, consulte [audiências do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Tem [segmentos configurados](segments.md).
-   Os perfis unificados dos clientes nos segmentos exportados contêm campos que representam um endereço de e-mail, nome próprio e apelido.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportar para o Google Ads.
- A exportação para o Google Ads é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 5 minutos devido a limitações do lado do fornecedor. 
- A correspondência no Google Ads pode demorar até 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar ligação ao Google Ads

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Google Ads** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduza a sua **[token de programador aprovado do Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Autenticar com o Google Ads** e forneça as suas credenciais do Google Ads.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação. 

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Google Ads. Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.

1. Introduza a sua **[ID de audiência do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e selecione **Ligar** para iniciar a ligação ao Google Ads.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para o Google Ads.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). 

Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Google Ads, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Google Ads cumprem quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

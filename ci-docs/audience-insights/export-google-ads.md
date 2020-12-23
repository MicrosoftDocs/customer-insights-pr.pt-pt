---
title: Exportar dados Customer Insights para o Google Ads
description: Saiba como configurar a ligação a Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568484"
---
# <a name="connector-for-google-ads-preview"></a>Ligação para Google Ads (pré-visualização)

Exportar segmentos de perfis unificados de clientes para a lista de audiências do Google Ads e utilizá-los para fazer publicidade na Pesquisa Google, Gmail, YouTube, e Google Display Network. 

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.
-   Existem audiências no Google Ads e os IDs correspondentes. Para mais informações, consulte [audiências do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Tem [segmentos configurados](segments.md)
-   Os perfis unificados dos clientes nos segmentos exportados contêm campos que representam um endereço de correio eletrónico, nome e apelido

## <a name="connect-to-google-ads"></a>Ligar ao Google Ads

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Em **Google Ads**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.

1. Introduza a sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduza a sua **[token de programador aprovado do Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Introduza a sua **[ID de audiência do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e selecione **Ligar** para iniciar a ligação ao Google Ads.

1. Selecione **Autenticar com o Google Ads** e forneça as suas credenciais do Google Ads.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Exportar captura de ecrã para ligação ao Google Ads":::

1. Selecione **Seguinte** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. Repita os mesmos passos para os campos **nome próprio** e **apelido**.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para o Google Ads.

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab). No Google Ads, pode agora encontrar os seus segmentos nas [audiências do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportar para o Google Ads.
- A exportação para o Google Ads é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 5 minutos devido a limitações do lado do fornecedor. 
- A correspondência no Google Ads pode demorar até 48 horas.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Google Ads, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Google Ads cumprem quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

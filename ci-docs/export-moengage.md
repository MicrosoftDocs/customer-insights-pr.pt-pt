---
title: Exportar segmentos para o MoEngage
description: Saiba como configurar a ligação e exportar para o MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725280"
---
# <a name="export-segments-to-moengage-preview"></a>Exportar segmentos para o MoEngage (pré-visualização)

Exportar segmentos de perfis unificados de clientes para o MoEngage e utilizá-los para marketing de e-mail no MoEngage.

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

- [Conta MoEngage](https://www.moengage.com/) e as credenciais de administrador correspondentes.
- Chave de API do MoEngage em Definições > API no MoEngage.
- [Segmentos configurados](segments.md) no Customer Insights.

## <a name="known-limitations"></a>Limitações conhecidas

- A ligação privada, em combinação com o Traga o seu próprio armazenamento (BYOS) não é suportada.
- Até 100.000 perfis de cliente por exportação para o MoEngage, o que pode demorar até 15 minutos. O número de perfis de clientes que pode exportar para o MoEngage depende do seu contrato com o MoEngage.
- Apenas segmentos.

## <a name="set-up-connection-to-moengage"></a>Configurar ligação ao MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **MoEngage** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o seu [ID de API de Dados do MoEngage e chave de API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação ao MoEngage.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Para criar um nova exportação, selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção MoEngage. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. Repita os mesmos passos para outros campos opcionais.

1. Selecione os segmentos que quer exportar. Vamos criar um ou mais segmentos com o mesmo nome que os segmentos selecionados no MoEngage em **Segmentos** > **Personalizados**.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

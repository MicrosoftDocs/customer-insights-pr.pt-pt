---
title: Exportar segmentos para o Snapchat (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195396"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segmentos para o Snapchat (pré-visualização)

Exporte segmentos de perfis de clientes unificados para o Snapchat e utilize-os para publicidade.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Snapchat Business](https://business.snapchat.com/), uma [conta Snapchat Ads](https://ads.snapchat.com/) e credenciais de administrador correspondentes. Tem, pelo menos, de ser membro de uma Conta de Organização e de um Gestor de Dados de uma Conta de Publicidade específica.
- Pelo menos uma audiência no Gestor de Audiências do Snapchat do tipo SAM (Correspondência de Audiências de Encaixe).
- O [ID de Segmento/Audiência do Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). O ID da audiência pode ser encontrado no URL depois de selecionar a audiência no Gestor de Audiências do Snapchat.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente, que pode demorar até 15 minutos a concluir.
- Apenas segmentos.

## <a name="set-up-connection-to-snapchat"></a>Configurar ligação ao Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Snapchat**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Autenticar com o Snapchat** e forneça as suas credenciais de admin para o Snapchat.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Snapchat. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Introduza o **ID De Segmento/Audiência do Snapchat**.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

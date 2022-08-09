---
title: Exportar segmentos para o Microsoft Advertising (pré-visualização)
description: Aprenda a configurar a ligação e exportar para para o Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196546"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segmentos para o Microsoft Advertising (pré-visualização)

Exporte segmentos do Customer Insights para o Microsoft Advertising para criar audiências de Correspondência de Clientes. Utilize estas audiências para as suas campanhas publicitárias.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Microsoft Advertising](https://ads.microsoft.com/) e credenciais de administrador correspondentes.
- ID de Conta e ID de Cliente do Microsoft Advertising. Encontre o ID de Cliente (`cid`) e o ID da Conta (`aid`) nos parâmetros do URL quando estiver registado no Microsoft Advertising.
- Os termos de utilização do Customer Match são aceites.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 500.000 perfis de cliente por exportação para o Microsoft Advertising, o que pode demorar até 10 minutos.
- Apenas segmentos.

## <a name="set-up-connection-to-microsoft-advertising"></a>Configurar ligação ao Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Microsoft Advertising**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. A predefinição é administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **ID do Cliente do Microsoft Advertising**.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Autenticar com o Microsoft Advertising** e forneça as suas credenciais de admin para o Microsoft Advertising.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Microsoft Advertising. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Selecione os segmentos a exportar. As audiências de Correspondência de Clientes no Microsoft Advertising são automaticamente criadas com o nome dos segmentos selecionados para exportação. Cada segmento resultará num audiência de Correspondência de Clientes separada.

1. Introduza o seu **ID de Cliente e ID da Conta do Microsoft Advertising**.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo com o endereço de e-mail de um cliente.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Exportar segmentos para o Autopilot (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724771"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportar segmentos para o Autopilot (pré-visualização)

Exportar segmentos de perfis unificados de clientes para o Autopilot e utilizá-los para marketing de e-mail no Autopilot.

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

- Uma [conta do Autopilot](https://www.autopilothq.com/) e credenciais de administrador correspondentes.
- Uma [chave de API do Autopilot](https://autopilot.docs.apiary.io/#)
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- A ligação privada, em combinação com o Traga o seu próprio armazenamento (BYOS) não é suportada.
- Até 100.000 perfis de cliente para exportar para o Autopilot, que pode demorar até algumas horas a concluir. O número de perfis de cliente que pode exportar para o Autopilot depende do seu contrato com o Autopilot.
- Apenas segmentos.

## <a name="set-up-connection-to-autopilot"></a>Configure a ligação para o Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Autopilot**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a sua chave de API do Autopilot.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Autopilot. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente.

1. Opcionalmente, exporte outros campos, tais como **Nome próprio** e **Apelido**.

1. Selecione os segmentos que pretende exportar ao aderir às limitações conhecidas.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Executar uma amostra web SDK
description: Aprenda a personalizar e executar uma amostra web SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225345"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Executar a amostra web SDK para obter a capacidade de informações de cativação de Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A biblioteca SDK da web de informações de cativação é uma biblioteca JavaScript com código de amostra que pode usar no seu site.

## <a name="prerequisites"></a>Pré-requisitos

- Instalar [Visual Studio Código](https://code.visualstudio.com/).
- [Instale a extensão do Servidor Dinâmico](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) em Código Visual Studio e familiarize-se com a forma de executar o Servidor Dinâmico.
- Deve ter uma [área de trabalho de informações de cativação](create-workspace.md).

## <a name="run-sample"></a>Executar amostra

1. [Transferir a amostra web SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descomprimir o ficheiro comprimido `ei_websdk_sample.zip`.

1. Abra a pasta descomprimida em código Visual Studio.

1. Vá para o portal de informações de cativação para a sua área de trabalho. Selecione **Administrador** > **Área de trabalho** e, em seguida, **Guia de instalação**. Siga a primeira opção e selecione **Copiar código** para copiar o fragmento de código de JavaScript.

1. No ficheiro `ei_websdk_sample.html`, cole o fragmento de código que acabou de copiar nesta linha:

   - <-- COLAR O FRAGMENTO DE CÓDIGO DE JAVASCRIPT DO PORTAL DE INFORMAÇÕES DE CATIVAÇÃO AQUI ABAIXO DESTA LINHA -->

1. Abra o ficheiro `ei_websdk_sample.html` utilizando o Servidor Dinâmico em código Visual Studio selecionando **Passar a Live** a partir da barra de estado.

1. Ao abrir a página, deve ser enviado automaticamente um evento de visualização. Clicar em qualquer um dos botões da página enviará eventos de ação. O botão **Monitorizar eventos** também enviará eventos personalizados. A seleção do botão **Passar a Bing** enviará um evento de ação antes de navegar para o site Bing.

1. Veja os eventos que fluem quando navega para a sua área de trabalho. Esta área de trabalho está associada à chave de ingestão inserida no Passo 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

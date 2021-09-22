---
title: Executar uma amostra web SDK
description: Aprenda a personalizar e executar uma amostra web SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036617"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Executar a amostra web SDK para obter a capacidade de informações de cativação de Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A biblioteca SDK da web de informações de cativação é uma biblioteca JavaScript com código de amostra que pode usar no seu site.

## <a name="prerequisites"></a>Pré-requisitos

- Instalar [Visual Studio Código](https://code.visualstudio.com/).
- [Instale a extensão do Servidor Dinâmico](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) em Código Visual Studio e familiarize-se com a forma de executar o Servidor Dinâmico.
- Deve ter a [chave de ingestão](instrument-website.md).

## <a name="run-sample"></a>Executar amostra

1. [Transferir a amostra web SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descomprimir o ficheiro comprimido `ei_websdk_sample.zip`.

1. Abra a pasta descomprimida em código Visual Studio.

1. No ficheiro `ei_websdk_sample.html`, substitua a cadeia "INGESTION_KEY" pela tecla de ingestão do portal de capacidade de informações de cativação e a cadeia "NAME" pelo nome global em que pretende que o SDK seja instantâneo. Certifique-se de que substitui todas as ocorrências.

1. Abra o ficheiro `ei_websdk_sample.html` utilizando o Servidor Dinâmico em código Visual Studio selecionando **Passar a Live** a partir da barra de estado.

1. Ao abrir a página, deve ser enviado automaticamente um evento de visualização. Clicar em qualquer um dos botões da página enviará eventos de ação. O botão **Monitorizar eventos** também enviará eventos personalizados. A seleção do botão **Passar a Bing** enviará um evento de ação antes de navegar para o site Bing.

1. Veja os eventos que fluem quando navega para a sua área de trabalho. Esta área de trabalho está associada à chave de ingestão inserida no Passo 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
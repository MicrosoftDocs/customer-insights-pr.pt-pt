---
title: Executar o exemplo de SDK iOS
description: Projeto de exemplo para conhecer a SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232856"
---
# <a name="run-the-ios-sdk-sample"></a>Executar o exemplo de SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este projeto iOS de exemplo ajuda-o a entender como a SDK funciona numa aplicação. Não tem de escrever código. Basta adicionar a sua chave de ingestão e poderá ver eventos na sua área de trabalho imediatamente.

## <a name="prerequisites"></a>Pré-requisitos

- [Xcode versão 9+](https://developer.apple.com/xcode/downloads/)
- [Chave de ingestão](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Transferir o exemplo de SDK iOS

1. [Transferir o exemplo de SDK iOS de informações de cativação](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Descomprimir o ficheiro comprimido `ei-ios-sample.zip`.
1. Abra o projeto de aplicação de exemplo no Xcode.
1. No ficheiro `EIConfig.plist`, substitua a cadeia `“YOUR-INGESTION-KEY”` no campo `ingestionKey` pela chave de ingestão da área de trabalho de informações de cativação sob o do **Admin** > **Área de trabalho** > **Guia de instalação**.
1. Selecione **Executar** para iniciar o projeto de exemplo.
1. Veja os eventos na sua área de trabalho.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

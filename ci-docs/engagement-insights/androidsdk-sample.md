---
title: Exemplo de SDK Android
description: Projeto de exemplo para conhecer a SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229932"
---
# <a name="run-the-android-sdk-sample"></a>Executar o exemplo de SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este projeto Android de exemplo ajuda-o a entender como a SDK funciona numa aplicação. Não tem de escrever código. Basta adicionar a sua chave de ingestão e poderá ver eventos na sua área de trabalho imediatamente.

## <a name="prerequisites"></a>Pré-requisitos

- [Android Studio](https://developer.android.com/studio)
- [Chave de ingestão](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Transferir o exemplo de SDK Android

1. [Transferir o exemplo de SDK Android de informações de cativação](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Descomprimir o ficheiro comprimido `ei-android-sample.zip`.
1. Abra a pasta deszipada no Android Studio.
1. No ficheiro `AndroidManifest.xml`, substitua a cadeia `"Your-Ingestion-Key"` com a chave de ingestão da área de trabalho de informações de cativação sob o do **Admin** > **Área de trabalho** > **Guia de instalação**. 

   > [!NOTE]
   > Não precisa de substituir a secção `${applicationId}`. É preenchido automaticamente.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Selecione **Executar** para iniciar o projeto de exemplo.
1. Veja os eventos na sua área de trabalho.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

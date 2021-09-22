---
title: Exemplo de SDK Android
description: Projeto de exemplo para conhecer a SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035840"
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

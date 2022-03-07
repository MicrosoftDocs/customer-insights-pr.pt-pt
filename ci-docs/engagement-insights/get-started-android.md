---
title: Começar a trabalhar com a SDK Android
description: Aprenda a personalizar e a executar a SDK Android
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226183"
---
# <a name="get-started-with-the-android-sdk"></a>Começar a trabalhar com a SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este tutorial orienta-o ao longo do processo de instrumentalização da sua aplicação Android com uma SDK das informações de cativação do Dynamics 365 Customer Insights. Começará a ver eventos no seu portal em cinco minutos ou mais cedo.

## <a name="configuration-options"></a>Opções de configuração
As seguintes opções de configuração podem ser passadas para a SDK:

- **ingestionKey**: a chave de ingestão é utilizada para enviar eventos para a sua área de trabalho.

## <a name="prerequisites"></a>Pré-requisitos

- Android Studio

- Nível mínimo da API Android: 16 (Jelly Bean)

- Uma chave de ingestão (consulte abaixo as instruções sobre como a obter)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar a SDK na aplicação
Inicie o processo selecionando uma área de trabalho onde trabalhar, selecionando a plataforma móvel Android e transferindo a SDK Android.

- Utilize o comutador da área de trabalho no painel de navegação esquerdo para selecionar a sua área de trabalho.

- Se não tiver uma área de trabalho existente, selecione **Nova Área de Trabalho** e siga os passos para criar uma [nova área de trabalho](create-workspace.md).

- Depois de criar uma área de trabalho, aceda a **Admin** > **Área de Trabalho** e, em seguida, selecione **Guia de instalação**.

## <a name="configure-the-sdk"></a>Configure a SDK

Uma vez transferida a SDK, pode trabalhar com ela no Android Studio para ativar e definir eventos. Existem duas formas de o fazer:
### <a name="option-1-use-jitpack-recommended"></a>Opção 1: utilizar o JitPack (recomendado)
1. Adicione o repositório JitPack à sua raiz `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Adicione a dependência:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Opção 2: utilizar a ligação de transferência
1. Transfira a [SDK Android de informações de cativação](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) e coloque o ficheiro `eiandroidsdk-debug.aar` na pasta `libs`.

1. Abra o ficheiro `build.gradle` de nível de projeto e adicione os seguintes fragmentos:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>Ativar a instrumentalização automática

1. Adicione permissão para rede e Internet no seu ficheiro `AndroidManifest.xml` localizado na pasta `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Configure a configuração da SDK de informações de cativação através do seu ficheiro `AndroidManifest.xml`.

1. Copie o fragmento XML do **Guia de instalação**. `Your-Ingestion-Key` deve ser preenchido automaticamente.

   > [!NOTE]
   > Não precisa de substituir a secção `${applicationId}`. É preenchido automaticamente.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Ative ou desative a captura automática de eventos `View` definindo o campo `autoCapture` acima como `true` ou `false`. 

   >[!NOTE]
   >Os eventos `Action` precisam de ser adicionados manualmente.

1. (Opcional) Outras configurações incluem a definição do URL do recoletor de ponto final. Podem ser adicionados sob os metadados da chave de ingestão no `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Implementar eventos personalizados

Depois de inicializar a SDK, pode trabalhar com eventos e respetivas propriedades no ambiente `MainActivity`.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Definir propriedade para todos os eventos (opcional)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Os seguintes tipos são suportados para propriedades de eventos de contexto:
- String
- Data
- Duplo
- Longo
- Boolean
- UUID

### <a name="track-an-event"></a>Monitorizar um evento

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Definir os detalhes de utilizador para o seu evento (opcional)

O SDK permite definir informações do utilizador que podem ser enviadas em cada evento. Pode especificar as informações de utilizador chamando a API `setUser(user: User)` no nível do `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

A classe de dados `User` contém as seguintes propriedades de cadeia:

- **localId**: Identificação local do utilizador.
- **authId**: O ID de utilizador autenticado.
- **authType**: o tipo de autenticação utilizado para obter o ID de utilizador autenticado.
- **name**: O nome do utilizador.
- **email**: O endereço de e-mail do utilizador.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

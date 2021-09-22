---
title: Começar a trabalhar com a SDK iOS
description: Aprenda a personalizar e a executar a SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036887"
---
# <a name="get-started-with-the-ios-sdk"></a>Começar a trabalhar com a SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este tutorial orienta-o ao longo da instrumentalização da sua aplicação iOS com uma SDK de informações de cativação do Dynamics 365 Customer Insights. Começará a ver eventos no seu portal em cinco minutos ou mais cedo.

## <a name="configuration-options"></a>Opções de configuração

As seguintes opções de configuração podem ser passadas para a SDK através do ficheiro `EIConfig.plist` fornecido:

- **ingestionKey**: a chave de ingestão utilizada para enviar eventos para o seu projeto.
- **autocollectAction**: um valor booleano para ativar ou desativar a instrumentalização automática do evento da ação.
- **autocollectView**: um valor booleano para ativar ou desativar a instrumentalização automática do evento da vista.
- **endpointUrl**: o URL de ponto final para onde os eventos serão direcionados.

## <a name="prerequisites"></a>Pré-requisitos

- Xcode versão 9+
- iOS versão 8.2+
- Uma chave de ingestão (consulte as instruções abaixo para a obter)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar a SDK na aplicação

Inicie o processo selecionando uma área de trabalho onde trabalhar, selecionando a plataforma móvel iOS e transferindo a SDK.

- Utilize o comutador da área de trabalho no painel de navegação esquerdo para selecionar a sua área de trabalho.

- Se não tiver uma área de trabalho existente, selecione **Nova Área de Trabalho** e siga os passos para criar uma [nova área de trabalho](create-workspace.md).

## <a name="configure-the-sdk"></a>Configure a SDK

Uma vez transferida a SDK, pode trabalhar com ela no Xcode para ativar e definir eventos.

1. Depois de criar uma área de trabalho, aceda a **Admin** > **Área de Trabalho** e, em seguida, selecione **Guia de instalação**.

1. Transfira a [SDK iOS de informações de cativação](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) e coloque o ficheiro `EIObjC.xcframework` na pasta `Frameworks`.

1. Se não existir uma pasta `Frameworks`, crie uma na pasta do projeto.

## <a name="enable-auto-instrumentation"></a>Ativar a instrumentalização automática
 
Pode ativar facilmente a instrumentalização automática sem codificação. Quando o projeto for executado, irá monitorizar automaticamente os eventos `view` e `action` utilizando a chave de ingestão configurada. 

1. Atualize e inclua o ficheiro `EIConfig.plist` fornecido na pasta do diretório do projeto para os seguintes campos:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = SIM
    - autocollectAction = SIM

2. Em seguida, adicione o ficheiro `EIConfig.plist` ao seu projeto no Xcode. 



Para desativar a instrumentalização automática, atualize os campos seguintes no ficheiro `EIConfig.plist` incluído na pasta do diretório do projeto. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementar eventos personalizados

1. Abra o seu projeto no Xcode e navegue para as definições **Gerais**. 
1. Adicione o `EIObjC.xcframework` ao projeto sob a secção "Arquiteturas, Bibliotecas e Conteúdo Incorporado".

1. Importe o ficheiro de cabeçalho da arquitetura em AppDelegate.m com o fragmento seguinte:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicialize a SDK de informações de cativação a partir da aplicação: didFinishLaunchingWithOptions.
1. Copie o fragmento XML do **Guia de instalação**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Monitorizar um evento:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Defina os detalhes de utilizador para o seu evento

O SDK permite definir informações do utilizador que podem ser enviadas em cada evento. Pode especificar as informações de utilizador chamando a API `setUser:(nonnull EIUser *)user` na SDK.

Especificar os dados de utilizador no nível do `Analytics` significa que todas as telemetrias terão estas informações. No entanto, se especificar ao nível do evento chamando a API `setUser:(nonnull EIUser *)user` no objeto EIEvent, apenas esse evento específico conterá as informações.

A classe de dados `EIUser` contém as seguintes propriedades NSString:

- **localId**: Identificação local do utilizador.
- **authId**: O ID de utilizador autenticado.
- **authType**: O tipo de autenticação utilizado para obter o ID de utilizador autenticado.
- **name**: O nome do utilizador.
- **email**: O endereço de e-mail do utilizador.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

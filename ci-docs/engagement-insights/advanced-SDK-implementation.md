---
title: Cenários web SDK avançados
description: Cenários avançados a ter em conta ao instrumentar o seu website com um SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558716"
---
# <a name="advanced-web-sdk-instrumentation"></a>Instrumentação SDK web avançada

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo guia-o através de cenários avançados a ter em conta ao [instrumentar o seu website](instrument-website.md) com uma capacidade de informações de envolvimento SDK Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Definição de dados do utilizador para o seu evento

O SDK permite definir informações do utilizador que podem ser enviadas em cada evento. Pode especificar os dados do utilizador numa propriedade chamada `user` (os dados esperados para esta propriedade são o objeto `IUser`), semelhante a `src`, `name` e `cfg` na configuração fragmento de código.

O objeto `IUser` contém as seguintes propriedades de cadeias:

- **localId**: Identificação local do utilizador.
- **authId**: O ID de utilizador autenticado.
- **authType**: O tipo de autenticação utilizado para obter o ID de utilizador autenticado.
- **name**: O nome do utilizador.
- **email**: O endereço de e-mail do utilizador.

O exemplo a seguir mostra um fragmento de código a enviar informações do utilizador. Quando vir funções precedidas por um símbolo * de asterisco, substitua a função pela sua implementação personalizada:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Também pode especificar informações de utilizador chamando a API `setUser(user: IUser)`. A telemetria enviada após chamar a API `setUser` contém as informações do utilizador.

## <a name="adding-custom-properties-for-each-event"></a>Adicionar propriedades personalizadas para cada evento

O SDK permite especificar propriedades personalizadas que podem ser enviadas em cada evento. Pode especificar as propriedades personalizadas como um objeto que contém pares chave-valor (o valor pode ser do tipo `string | number | boolean`). Pode adicionar o objeto numa propriedade chamada `props`, semelhante a `src`, `name` e `cfg` na configuração do fragmento de código.

O exemplo a seguir mostra um fragmento de código a enviar propriedades personalizadas.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Também pode especificar propriedades personalizadas individualmente chamando a API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>A enviar eventos personalizados

Pode utilizar o SDK para enviar eventos personalizados. Deve especificar um nome para o evento e propriedades a enviar com o evento.

O exemplo a seguir mostra um fragmento de código a detetar um evento personalizado. O "NAME" é o valor da chave `name` na configuração de fragmento. É também o nome variável no objeto da janela onde o SDK está carregado.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Reconhecer eventos Web de visitantes previamente autenticados com desconhecido para conhecido
description: A funcionalidade de desconhecido para conhecido permite-lhe associar eventos num site a visitantes que autenticaram anteriormente.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036797"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Reconhecer eventos Web de visitantes previamente autenticados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A funcionalidade **desconhecido para conhecido** na capacidade de informações de cativação permite associar eventos num site a visitantes que autenticaram anteriormente. Se a funcionalidade estiver desativada, os visitantes que autenticaram durante uma visita anterior e depois saíram não são identificados se não voltarem a autenticar quando voltarem. 

Por exemplo, uma pessoa visitou um site na semana passada, iniciou sessão na sua conta de utilizador no site e navegou no catálogo de produtos. A pessoa regressa na semana seguinte para ver mais produtos sem iniciar sessão na sua conta. O proprietário do site que usa a funcionalidade **desconhecido para conhecido** saberia que a mesma pessoa tinha regressado e o que tinha feito no site. Isto permite informações e análises mais precisas das atividades do site.

## <a name="enable-unknown-to-known"></a>Ativar desconhecido para conhecido

Necessita de ser um [admin da área de trabalho](user-roles.md) para ativar esta funcionalidade. 

1. Nas informações de cativação, vá a **Admin** > **Área de Trabalho**. 
2. Selecione o separador **Definições**.
3. Na secção **Desconhecido para conhecido**, defina o comutador como **Ativado**.

![Ativar desconhecido para conhecido](media/U2Ktoggle.png "Ativar desconhecido para conhecido")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Adicionar código JavaScript ao fragmento de monitorização do site

Um site pode capturar **user authId** com o seguinte exemplo JavaScript usando a [SDK Web de informações de cativação](advanced-SDK-implementation.md). Para que a funcionalidade **desconhecido para conhecido** funcione, é necessário capturar authId *e* ativar o userMapping:True no seu fragmento JavaScript como no exemplo abaixo.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]

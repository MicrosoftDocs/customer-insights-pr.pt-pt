---
title: Gerir cookies e consentimento do utilizador para armazenar dados de utilizador no Dynamics 365 Customer Insights
description: Entender como os cookies e o consentimento do utilizador são usados para identificar visitantes do site.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558885"
---
# <a name="manage-cookies-and-user-consent"></a>Gerir cookies e consentimentos de utilizadores

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A capacidade de informações de cativação do Dynamics 365 Customer Insights usa cookies e chaves (`localStorage`) para identificar visitantes do site.

Os cookies são pequenos ficheiros que armazenam bits de informação sobre as interações de um utilizador com o site. São armazenados em navegadores web. Quando os utilizadores visitam um site para o qual os seus utilizadores armazenaram cookies, o navegador envia essa informação para o servidor, que devolve informações exclusivas do utilizador. Esta é a tecnologia que permite, por exemplo, um carrinho de compras online manter itens selecionados no mesmo que um utilizador saia do site.

## <a name="user-consent"></a>Consentimento do utilizador

O [Regulamento Geral de Proteção de Dados (RGPD)](/dynamics365/get-started/gdpr/) é um regulamento da União Europeia (UE) que determina a forma como as organizações devem lidar com a privacidade e segurança dos seus utilizadores. Os cookies muitas vezes armazenam ou recolhem "dados pessoais", como um identificador online, que é coberto pelo RGPD. Se o seu negócio empregar e/ou vender a pessoas com dados da UE, o RGPD afeta-o. [Saiba mais sobre como a Microsoft o pode ajudar a cumprir o RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Para permitir que as informações de cativação SDK armazenem cookies ou outras informações sensíveis, deve especificar se os seus utilizadores consentiram. Isto ocorre na inicialização do SDK definindo um campo `userConsent` na configuração.

Se indicar que não existe consentimento do utilizador, o SDK não armazenará quaisquer dados e não enviará eventos que possam ser usados para rastrear o comportamento do utilizador. Quaisquer dados previamente armazenados serão eliminados do navegador.

Se não for especificado nenhum valor de consentimento do utilizador, o SDK assumirá que o utilizador consentiu. Isto significa que se você (como nosso cliente) não especificar um valor para o consentimento do utilizador no SDK, os dados serão recolhidos. No entanto, se especificar que o valor para o consentimento do utilizador tem de ser "verdadeiro", os dados não serão recolhidos se um utilizador recusar ou não fornecer consentimento explícito.

Abaixo está um fragmento de código para inicializar o SDK Web com o consentimento do utilizador:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Armazenamento de dados do visitante na capacidade de informações de cativação

### <a name="cookies"></a>Cookies

- _msei
    - Armazena o ID de utilizador anónimo. Este cookie é definido no domínio do cliente e expira em 365 dias.

### <a name="local-storage"></a>Armazenamento local

A capacidade de informações de cativação também utiliza chaves (`localStorage`) para monitorizar dados não confidenciais. Estes dados são totalmente armazenados no próprio navegador, sem tráfego enviado para ou a partir dos seus servidores.

- *EISession.Id*
    - Armazena informações sobre a sessão de utilizador em curso, como o ID da sessão, quando começou e quando expira.
- *EISession.Previous*
    - Armazena o URL da página previamente visitada na sessão atual.

As chaves no armazenamento local não expiram automaticamente e serão repostas durante a próxima sessão SDK.

## <a name="deleting-cookies"></a>Eliminação de cookies

Os seus clientes podem eliminar manualmente os cookies e as chaves de armazenamento locais a qualquer momento através das definições dos seus navegadores.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

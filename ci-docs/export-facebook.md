---
title: Exportar segmentos para o Facebook Ads Manager (pré-visualização) (contém vídeo)
description: Aprenda a configurar a ligação e exportar para o Gestor de Anúncios do Facebook.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195028"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportar segmentos para o Facebook Ads Manager (pré-visualização)

Exportar segmentos de perfis de cliente unificados para o Gestor de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Pré-requisitos

- Uma [Conta Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclui uma [Conta Empresarial do Facebook](https://business.facebook.com/).
- Privilégios de administrador na [Conta Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 10 milhões de perfis de cliente por exportação para o Facebook Ads Manager, o que pode demorar até 90 minutos.
- Apenas segmentos.
- Tipo de *lista de clientes* do Facebook apenas em [audiências personalizadas](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > Em alguns casos, poderá ver audiências personalizadas de diferentes tipos na lista pendente. Se selecionar um tipo diferente diferente de *lista de clientes*, a exportação falha.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurar ligação ao Gestor de Anúncios do Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Gestor de Anúncios do Facebook**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. [Permitir que os contribuidores utilizem a ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autenticar com os Anúncios do Facebook:

   1. Selecione **Continuar com o Facebook** para iniciar sessão na sua conta Facebook Ads.

   1. Permitir a permissão **ads_management** após autenticação com o Facebook.

   1. Selecione a **Conta de Anúncios do Facebook** com que pretende trabalhar.

   1. Selecione uma **Audiência personalizada existente** na lista pendente ou crie uma **Nova audiência personalizada**.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Gestor de Anúncios do Facebook Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. No campo **Ligar dados**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o Gestor de Anúncios do Facebook.

1. Mapeie os atributos correspondentes da entidade de cliente unificada para o identificador-chave selecionado.
   > [!TIP]
   > As melhores hipóteses para que uma correspondência ocorra é se selecionar **E-mail** como identificador de chave. A adição de identificadores adicionais pode melhorar a correspondência.

1. Selecione **Adicionar atributo** para mapear mais atributos para enviar para o Gestor de Anúncios do Facebook. Atributos do Gestor de Anúncios do Facebook estão a mapear para os seguintes nomes amigáveis de utilizador: **NP** = **Nome Próprio**, **AP** = **Apelido**, **PI** = **Primeira Inicial**, **TELEFONE** = **Telefone**, **SEX** = **Sexo**, **DN** = **Data de nascimento**, **EST** = **Estado**, **CD** = **Cidade**, **CP** = **Código postal**, **PAÍS** = **País / Região**

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

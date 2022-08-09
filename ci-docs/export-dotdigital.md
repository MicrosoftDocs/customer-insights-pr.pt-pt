---
title: Exportar segmentos para a DotDigital (pré-visualização)
description: Aprenda a configurar a ligação e exportar para a DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196086"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segmentos para a DotDigital (pré-visualização)

Exportar segmentos de perfis unificados de clientes para a DotDigital e utilizá-los em campanhas, marketing por e-mail, e construir segmentos de clientes com a DotDigital.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta DotDigital](https://dotdigital.com/) e um [utilizador da API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Um ID DotDigital de um livro de endereços [novo](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) ou existente em DotDigital. A ID pode ser encontrada no URL ao selecionar e abrir um livro de endereços.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até de 1 milhão de perfis de clientes por exportação para o DotDigital, que pode demorar até três horas a concluir dadas as limitações do lado do fornecedor. O número de perfis de cliente que pode exportar para o DotDigital depende do seu contrato com o DotDigital.
- Apenas segmentos.

## <a name="set-up-connection-to-dotdigital"></a>Configurar ligação à DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **DotDigital**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o seu **nome de utilizador e a palavra-passe da API do DotDigital**.

1. Introduza o seu **ID de livro de endereços DotDigital**.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção DotDigital. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente.

1. Opcionalmente, exporte **Nome próprio**, **Apelido**, **Nome completo**, **Sexo** e **Código portal**.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Na DotDigital, encontre os seus segmentos nos [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]

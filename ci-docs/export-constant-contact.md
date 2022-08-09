---
title: Exportar segmentos para o Constant Contact (pré-visualização)
description: Aprenda a configurar a ligação e exportar para a Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196500"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportar segmentos para o Constant Contact (pré-visualização)

Exporte segmentos de perfis de clientes unificados para a Constant Contact e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Constant Contact](https://www.constantcontact.com/account-home) e as credenciais de administrador correspondentes.
- Um [ID de Lista do Constant Contact](https://app.constantcontact.com/pages/contacts/ui#lists). Abra uma lista na Constant Contact para encontrar o ID da lista no URL.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente por exportação para o Constant Contact, que pode demorar até uma hora a concluir. O número de perfis de cliente que pode exportar para o Constant Contact depende do seu contrato com o Constant Contact.
- Apenas segmentos.

## <a name="set-up-connection-to-constant-contact"></a>Configurar uma ligação à Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Constant Contact**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Autenticar com Contacto Constante** e forneça as suas credenciais de admin para Contacto Constante.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Constant Contact. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Introduza o seu **ID de Lista do Constant Contact**.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente.

1. Opcionalmente, exporte o **Nome próprio** e o **Apelido** como campos adicionais para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Exportar segmentos para a Sendinblue (pré-visualização)
description: Aprenda a configurar a ligação e a exportar para a Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724908"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportar segmentos para a Sendinblue (pré-visualização)

Exporte segmentos de perfis de clientes unificados para gerar campanhas, fornecer marketing por e-mail e utilizar grupos de clientes específicos com a Sendinblue.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Sendinblue](https://www.sendinblue.com/) e credenciais de administrador correspondentes.
- Uma [Chave de API do SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Listas existentes no Sendinblue e os IDs correspondentes.
- [Segmentos configurados](segments.md).
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- A ligação privada, em combinação com o Traga o seu próprio armazenamento (BYOS) não é suportada.
- Até 1 milhão de perfis de cliente por exportação para o Sendinblue, o que pode demorar até 90 minutos a concluir. O número de perfis de clientes que pode exportar para o Sendinblue depende do seu contrato com o Sendinblue.
- Apenas segmentos.

## <a name="set-up-connection-to-sendinblue"></a>Configurar ligação à Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Sendinblue**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a **chave de API do SendinBlue**.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação à exportação**, escolha uma ligação a partir da secção Sendinblue. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Introduza o **ID de lista Sendinblue**.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente.

1. Opcionalmente, exporte **Nome próprio**, **Apelido** e **Telefone** para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

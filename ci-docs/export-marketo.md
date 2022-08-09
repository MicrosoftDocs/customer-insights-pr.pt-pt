---
title: Exportar segmentos para a Marketo (pré-visualização)
description: Aprenda a configurar a ligação e exportar para a Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195258"
---
# <a name="export-segments-to-marketo-preview"></a>Exportar segmentos para a Marketo (pré-visualização)

Exportar segmentos de perfis unificados de clientes para gerar campanhas, fornecer marketing por e-mail e utilizar grupos específicos de clientes com Marketo.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.
- Um [ID de cliente da Marketo, Segredo de cliente e Nome do Anfitrião do Ponto Final REST](https://developers.marketo.com/rest-api/authentication/).
- [Listas existentes no Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) e os IDs correspondentes.
- [Segmentos configurados](segments.md).
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente por exportação para o Marketo, o que pode demorar até 3 horas. O número de perfis de cliente que pode exportar para o Marketo depende do seu contrato com o Marketo.
- Apenas segmentos.

## <a name="set-up-connection-to-marketo"></a>Configure a ligação para a Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Marketo**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o seu **ID de cliente do Marketo, Segredo do cliente e Nome do Anfitrião do Ponto Final REST**. O Nome do Anfitrião do Ponto Final REST é apenas o nome de anfitrião, sem https://. Exemplo: xyz-abc-123.mktorest.com.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Marketo. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Introduza o seu **ID de lista do Marketo**. O ID da lista é um valor puramente numérico. Por exemplo, se o seu ID de lista do Marketo for ST12345A7, remova o caráter antes e depois dos numerais e introduza *12345*.

1. Na secção **Correspondência de dados**, selecione, pelo menos, um campo que represente o endereço de e-mail de um cliente ou o ID de Marketo de um cliente.

1. Opcionalmente, exporte **Nome próprio**, **Apelido**, **Localidade**, **Estado** e **País/Região** para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Na Marketo, encontre os seus segmentos nas [listas do Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]

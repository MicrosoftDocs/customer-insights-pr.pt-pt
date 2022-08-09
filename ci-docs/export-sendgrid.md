---
title: Exportar segmentos para o SendGrid (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197006"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segmentos para o SendGrid (pré-visualização)

Exportar segmentos de perfis unificados de clientes para listas de contactos do SendGrid e utilizá-los para campanhas e marketing de e-mail no SendGrid.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do SendGrid](https://sendgrid.com/) e credenciais de administrador correspondentes.
- [Listas de contactos existentes no SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) e os IDs correspondentes.
- Uma [chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 100.000 perfis de cliente no total para o SendGrid, que pode demorar até algumas horas a concluir. O número de perfis de cliente que pode exportar para o SendGrid depende do seu contrato com o SendGrid.
- Apenas segmentos.

## <a name="set-up-connection-to-sendgrid"></a>Configurar ligação ao SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **SendGrid**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a sua **chave de API do SendGrid**.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção SendGrid. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Insira o seu **ID de lista do SendGrid**.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente.

1. Opcionalmente, selecione campos como **Nome próprio**, **Apelido**, **País/Região**, **Estado**, **Localidade** e **Código Postal**.

1. Selecione os segmentos que pretende exportar aderindo às limitações conhecidas.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

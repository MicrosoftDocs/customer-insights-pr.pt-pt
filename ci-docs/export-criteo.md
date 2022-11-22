---
title: Exportar segmentos para o Criteo (pré-visualização)
description: Saiba como configurar a ligação e exportar para o Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760040"
---
# <a name="export-segments-to-criteo-preview"></a>Exportar segmentos para o Criteo (pré-visualização)

Exporte segmentos de perfis de cliente unificados para gerar campanhas, fornecer marketing por e-mail e utilizar grupos de clientes específicos com o Criteo.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Criteo Dynamics Retargeting](https://www.criteo.com/login/) e as credenciais de administrador correspondentes.
- [Segmentos configurados](segments.md).
- Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente por exportação para o Criteo, o que pode demorar até 30 minutos a concluir. O número de perfis de cliente que pode exportar para o Criteo depende do seu contrato com o Criteo.
- Apenas segmentos.

## <a name="set-up-connection-to-criteo"></a>Configure a ligação ao Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Criteo**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Ligar** para inicializar a ligação.

1. Selecione **Autenticar com o Criteo** e forneça o nome de utilizador e as credenciais de administrador para o Criteo.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação na secção Criteo. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

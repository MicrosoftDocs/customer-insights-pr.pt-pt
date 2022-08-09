---
title: Equipas bot para o Dynamics 365 Customer Insights (pré-visualização)
description: Procure perfis unificados de clientes no Microsoft Teams com a ajuda de um bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195856"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Equipas bot para o Dynamics 365 Customer Insights (pré-visualização)

Ligar com o Microsoft Teams para deixar um bot procurar perfis unificados de clientes nos canais Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot do Teams que mostra um registo de cliente":::

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos uma [origem de dados adicionada](data-sources.md).
- O [processo de unificação](data-unification.md) está concluído.
- Os campos são adicionados ao [índice de pesquisa e filtro](search-filter-index.md).
- O Customer Insights e o Teams estão na mesma organização.
- O seu ambiente tem a audiência alvo principal definida para clientes individuais. As contas empresariais não são suportadas.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configure o bot

1. Aceda a **Admin** > **Ligações**.
1. No mosaico do Microsoft Teams, selecione **Configurar**.
1. É redireccionado para a área **Aplicações** no Teams. Também pode abrir o Teams e selecionar **Aplicações** no canto inferior esquerdo ou [obtê-las da AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) diretamente.
1. Procure por **Customer Insights** e selecione a aplicação.
1. Selecione **Adicionar**.
1. Inicie sessão no to Customer Insights no Teams. É apresentada uma mensagem de boas-vindas.

## <a name="things-you-can-do-with-the-bot"></a>Coisas que pode fazer com o bot

O bot fornece capacidades de pesquisa para perfis de cliente unificados.

- Introduza **pesquisa** seguida por um nome, endereço de e-mail ou qualquer outro campo no perfil de cliente unificado que seja adicionado ao índice de pesquisa e filtro.

  Obterá um cartão com até 15 campos do perfil de cliente resultante. Várias correspondências devolvem uma lista de resultados onde pode selecionar um perfil. Para procurar uma correspondência exata, adicione o termo de pesquisa entre aspas.

- Se a sua organização mantém vários ambientes de Customer Insights na mesma organização, introduza **switchinstance** para escolher o ambiente a que quer ligar o bot.

- Introduza **ajuda** para ver uma lista dos comandos disponíveis para o bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]
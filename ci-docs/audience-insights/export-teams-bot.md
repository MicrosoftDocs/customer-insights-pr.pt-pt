---
title: Bot para o Microsoft Teams
description: Procure perfis unificados de clientes no Microsoft Teams com a ajuda de um bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032496"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Equipas bot para o Dynamics 365 Customer Insights (pré-visualização)

Ligar com o Microsoft Teams para deixar um bot procurar perfis unificados de clientes nos canais Teams.

> [!div class="mx-imgBorder"]
> ![Bot do Teams que mostra um registo de cliente.](media/teams-bot.png "Bot do Teams que mostra um registo de cliente")

## <a name="prerequisites"></a>Pré-requisitos

Para preparar e configurar o bot, os pré-requisitos seguintes têm de ser satisfeitos:

- Existe pelo menos uma [origem de dados adicionada](data-sources.md).
- O [processo de unificação](data-unification.md) está concluído.
- Os campos são adicionados ao [índice de pesquisa e filtro](search-filter-index.md).
- O Customer Insights e o Teams estão na mesma organização.

## <a name="configure-the-bot"></a>Configure o bot

1. Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.
1. No mosaico do Microsoft Teams, selecione **Configurar**.
1. É redireccionado para a área **Aplicações** no Teams. Também pode abrir o Teams e selecionar **Aplicações** no canto inferior esquerdo ou [obtê-las da AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) diretamente.
1. Procure por **Customer Insights** e selecione a aplicação.
1. Selecione **Adicionar**.
1. Depois de iniciar sessão no Customer Insights no Teams, verá uma mensagem de boas-vindas e poderá começar a trabalhar.

## <a name="things-you-can-do-with-the-bot"></a>Coisas que pode fazer com o bot

O bot fornece capacidades de pesquisa para perfis de cliente unificados.

- Introduza **pesquisa** seguida por um nome, endereço de e-mail ou qualquer outro campo no perfil de cliente unificado que seja adicionado ao índice de pesquisa e filtro.

  Obterá um cartão com até 15 campos do perfil de cliente resultante. Várias correspondências devolvem uma lista de resultados onde pode selecionar um perfil. Pode adicionar o termo de pesquisa entre aspas para procurar uma correspondência exata.

- Se a sua organização mantém vários ambientes de Customer Insights na mesma organização, pode entrar **switchinstance** para escolher o ambiente a que quer ligar o bot.

- Introduza **ajuda** para ver uma lista dos comandos disponíveis para o bot.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
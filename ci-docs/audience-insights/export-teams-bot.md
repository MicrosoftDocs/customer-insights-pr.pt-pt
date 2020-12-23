---
title: Bot para o Microsoft Teams
description: Procure perfis unificados de clientes no Microsoft Teams com a ajuda de um bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406638"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="c1c82-103">Equipas bot para o Dynamics 365 Customer Insights (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="c1c82-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="c1c82-104">Ligar com o Microsoft Teams para deixar um bot procurar perfis unificados de clientes nos canais Teams.</span><span class="sxs-lookup"><span data-stu-id="c1c82-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c1c82-105">![Bot do Teams que mostra um registo de cliente](media/teams-bot.png "Bot do Teams que mostra um registo de cliente")</span><span class="sxs-lookup"><span data-stu-id="c1c82-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c1c82-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c1c82-106">Prerequisites</span></span>

<span data-ttu-id="c1c82-107">Para preparar e configurar o bot, os pré-requisitos seguintes têm de ser satisfeitos:</span><span class="sxs-lookup"><span data-stu-id="c1c82-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c1c82-108">Existe pelo menos uma [origem de dados adicionada](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="c1c82-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="c1c82-109">O [processo de unificação](data-unification.md) está concluído.</span><span class="sxs-lookup"><span data-stu-id="c1c82-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="c1c82-110">Os campos são adicionados ao [índice de pesquisa e filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="c1c82-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="c1c82-111">O Customer Insights e o Teams estão na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="c1c82-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="c1c82-112">Configure o bot</span><span class="sxs-lookup"><span data-stu-id="c1c82-112">Configure the bot</span></span>

1. <span data-ttu-id="c1c82-113">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="c1c82-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="c1c82-114">No mosaico do Microsoft Teams, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="c1c82-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="c1c82-115">É redireccionado para a área **Aplicações** no Teams.</span><span class="sxs-lookup"><span data-stu-id="c1c82-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="c1c82-116">Também pode abrir o Teams e selecionar **Aplicações** no canto inferior esquerdo ou [obtê-las da AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) diretamente.</span><span class="sxs-lookup"><span data-stu-id="c1c82-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="c1c82-117">Procure por **Customer Insights** e selecione a aplicação.</span><span class="sxs-lookup"><span data-stu-id="c1c82-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="c1c82-118">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c1c82-118">Select **Add**.</span></span>
1. <span data-ttu-id="c1c82-119">Depois de iniciar sessão no Customer Insights no Teams, verá uma mensagem de boas-vindas e poderá começar a trabalhar.</span><span class="sxs-lookup"><span data-stu-id="c1c82-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="c1c82-120">Coisas que pode fazer com o bot</span><span class="sxs-lookup"><span data-stu-id="c1c82-120">Things you can do with the bot</span></span>

<span data-ttu-id="c1c82-121">O bot fornece capacidades de pesquisa para perfis de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="c1c82-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="c1c82-122">Introduza **pesquisa** seguida por um nome, endereço de e-mail ou qualquer outro campo no perfil de cliente unificado que seja adicionado ao índice de pesquisa e filtro.</span><span class="sxs-lookup"><span data-stu-id="c1c82-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="c1c82-123">Obterá um cartão com até 15 campos do perfil de cliente resultante.</span><span class="sxs-lookup"><span data-stu-id="c1c82-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="c1c82-124">Várias correspondências devolvem uma lista de resultados onde pode selecionar um perfil.</span><span class="sxs-lookup"><span data-stu-id="c1c82-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="c1c82-125">Pode adicionar o termo de pesquisa entre aspas para procurar uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="c1c82-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="c1c82-126">Se a sua organização mantém vários ambientes de Customer Insights na mesma organização, pode entrar **switchinstance** para escolher o ambiente a que quer ligar o bot.</span><span class="sxs-lookup"><span data-stu-id="c1c82-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="c1c82-127">Introduza **ajuda** para ver uma lista dos comandos disponíveis para o bot.</span><span class="sxs-lookup"><span data-stu-id="c1c82-127">Enter **help** to see a list of available commands for the bot.</span></span>  

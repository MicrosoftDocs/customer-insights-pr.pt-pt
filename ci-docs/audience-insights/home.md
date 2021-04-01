---
title: Página inicial em insights da audiência
description: Comece a explorar a aplicação na página inicial.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597249"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="36d75-103">Criar um novo ambiente</span><span class="sxs-lookup"><span data-stu-id="36d75-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="36d75-104">Criar um ambiente de avaliação</span><span class="sxs-lookup"><span data-stu-id="36d75-104">Create a trial environment</span></span>

<span data-ttu-id="36d75-105">Pode inscrever-se para uma avaliação na [página de inscrição da avaliação](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span><span class="sxs-lookup"><span data-stu-id="36d75-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="36d75-106">As versões expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="36d75-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="36d75-107">Escolha a opção **Inscrever para uma avaliação gratuita** e **Inscrever agora**.</span><span class="sxs-lookup"><span data-stu-id="36d75-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="36d75-108">Forneça o seu endereço de e-mail escolar ou profissional, conte-nos um pouco mais sobre si mesmo e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="36d75-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Caixa de diálogo para se inscrever numa instância de avaliação":::

1. <span data-ttu-id="36d75-110">Forneça um **Nome** para o seu novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="36d75-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="36d75-111">Selecione o tipo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="36d75-111">Select the trial type.</span></span>

1. <span data-ttu-id="36d75-112">Escolha a **Região** para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="36d75-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="36d75-113">Opcionalmente, para administradores de uma organização do Dynamics 365: Selecione **Definições avançadas** e forneça o URL da sua organização para usar funcionalidades de predição como o abandono de clientes.</span><span class="sxs-lookup"><span data-stu-id="36d75-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="36d75-114">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="36d75-114">Select **Create**.</span></span> 

<span data-ttu-id="36d75-115">Depois do ambiente ter sido criado, verá o ambiente de **Demonstração** que lhe permite explorar a aplicações com dados fictícios.</span><span class="sxs-lookup"><span data-stu-id="36d75-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="36d75-116">Pode alterar os dados de exemplo para corresponderem ao seu setor.</span><span class="sxs-lookup"><span data-stu-id="36d75-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="36d75-117">Selecione o ícone **Definições** no cabeçalho e selecione **Definições de Demonstração**.</span><span class="sxs-lookup"><span data-stu-id="36d75-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="36d75-118">Além disso, pode alterar o tema visual.</span><span class="sxs-lookup"><span data-stu-id="36d75-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="36d75-119">[Muda para o ambiente](#switch-environments) que criou durante o processo de inscrição para trabalhar com os seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="36d75-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="36d75-120">Criar um novo ambiente de produção ou de sandbox</span><span class="sxs-lookup"><span data-stu-id="36d75-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="36d75-121">No seu ambiente, selecione o seletor **Ambientes** no cabeçalho da aplicação e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="36d75-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="36d75-122">Siga os passos como se [criasse um ambiente de avaliação](#create-a-trial-environment).</span><span class="sxs-lookup"><span data-stu-id="36d75-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="36d75-123">Por predefinição, os dados são armazenados no data lake gerido pelo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="36d75-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="36d75-124">Obtém uma opção adicional ao selecionar **Definições avançadas** para armazenar os seus dados no seu próprio Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="36d75-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="36d75-125">Forneça o nome da sua conta e a chave da sua conta para estabelecer uma ligação ao seu Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="36d75-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="36d75-126">Ao guardar dados no seu Azure Data Lake Storage, aceita que os dados serão transferidos e armazenados na localização geográfica adequada para essa apropriada para essa conta de armazenamento do Azure, que pode ser diferente daquela na qual os dados estão armazenados no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="36d75-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="36d75-127">Saber mais no Centro de Fidedignidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36d75-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="36d75-128">Explorar a home page</span><span class="sxs-lookup"><span data-stu-id="36d75-128">Explore the home page</span></span>

<span data-ttu-id="36d75-129">Pode [aceder a informações da audiência a partir do Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) no URL seguinte: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="36d75-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="36d75-130">A página **Home Page** mostra uma descrição geral de segmentos, medidas e dados de melhoramento (se configurados) depois de completar as fases [mapear](map-entities.md), [corresponder](match-entities.md) e [unir](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="36d75-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="36d75-131">![Informações na Home page](media/home-page-insights.png "Informações na Home page")</span><span class="sxs-lookup"><span data-stu-id="36d75-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="36d75-132">Em **Segmentos recentes** vê grupos de clientes baseados em atributos demográficos, comportamentais ou transacionais que definiu.</span><span class="sxs-lookup"><span data-stu-id="36d75-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="36d75-133">[Criar segmentos](segments.md) ajuda-o a agrupar a sua base de clientes e a direcionar melhor as suas atividades empresariais.</span><span class="sxs-lookup"><span data-stu-id="36d75-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="36d75-134">As **medidas recentes** mostram mosaicos com [indicadores chave de desempenho (KPIs)](measures.md) que definiu.</span><span class="sxs-lookup"><span data-stu-id="36d75-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="36d75-135">Por exemplo, a probabilidade média de um cliente de abandonar ou a média de gastos online por cliente.</span><span class="sxs-lookup"><span data-stu-id="36d75-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="36d75-136">A secção **Enriquecimentos recentes** lista os resultados das execuções de enriquecimento que foram concluídas recentemente.</span><span class="sxs-lookup"><span data-stu-id="36d75-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="36d75-137">Os [melhoramentos](enrichment-hub.md) adicionam informações sobre a sua base de clientes.</span><span class="sxs-lookup"><span data-stu-id="36d75-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="36d75-138">Por exemplo, compreendendo os interesses e marcas para os quais têm afinidade.</span><span class="sxs-lookup"><span data-stu-id="36d75-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="36d75-139">Mudar de ambientes</span><span class="sxs-lookup"><span data-stu-id="36d75-139">Switch environments</span></span>

<span data-ttu-id="36d75-140">Selecione o controlo **Ambiente** no canto superior direito da página para mudar de ambiente.</span><span class="sxs-lookup"><span data-stu-id="36d75-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="36d75-141">![Mudar de ambiente](media/home-page-environment-switcher.png "Mudar de ambiente")</span><span class="sxs-lookup"><span data-stu-id="36d75-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="36d75-142">Os administradores podem criar e gerir [vários ambientes](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="36d75-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="36d75-143">Manter mais do que um ambiente pode ser útil se, por exemplo, a sua organização operar internacionalmente e precisar de segregar dados e informações de diferentes maneiras.</span><span class="sxs-lookup"><span data-stu-id="36d75-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="36d75-144">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="36d75-144">Next step</span></span>

<span data-ttu-id="36d75-145">Para ver as suas próprias informações na home page, primeiro terá de [adicionar origens de dados](data-sources.md) e [unificar](data-unification.md) os seus dados para compilar perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="36d75-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
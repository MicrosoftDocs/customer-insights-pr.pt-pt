---
title: Conector do Power BI
description: Saiba como utilizar o conector do Dynamics 365 Customer Insights no Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477102"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="f98ba-103">Conector para Power BI (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="f98ba-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="f98ba-104">Crie visualizações para os seus dados com o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="f98ba-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="f98ba-105">Gere informações adicionais e crie relatórios com os seus dados de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="f98ba-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f98ba-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f98ba-106">Prerequisites</span></span>

- <span data-ttu-id="f98ba-107">Tem perfis unificados de clientes.</span><span class="sxs-lookup"><span data-stu-id="f98ba-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="f98ba-108">A versão mais recente do [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalada no seu computador.</span><span class="sxs-lookup"><span data-stu-id="f98ba-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="f98ba-109">[Mais informações sobre o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="f98ba-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="f98ba-110">Configurar o conector para Power BI</span><span class="sxs-lookup"><span data-stu-id="f98ba-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="f98ba-111">No Power BI Desktop, selecione **Ficheiro** > **Obter Dados**.</span><span class="sxs-lookup"><span data-stu-id="f98ba-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="f98ba-112">Selecione **Ver mais** e procure **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="f98ba-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="f98ba-113">Selecione **Ligar**.</span><span class="sxs-lookup"><span data-stu-id="f98ba-113">Select **Connect**.</span></span>

1. <span data-ttu-id="f98ba-114">**Inicie sessão** com a mesma conta organizacional utilizada para o Customer Insights e selecione **Ligar**.</span><span class="sxs-lookup"><span data-stu-id="f98ba-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f98ba-115">A conta que indica neste passo é usada para recolher dados do Customer Insights e não precisa de ser a mesma em que está a iniciar sessão no Power BI.</span><span class="sxs-lookup"><span data-stu-id="f98ba-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="f98ba-116">Para reiniciar a conta que é utilizada para a recolha de dados, abra o Power BI e vá a **Ficheiro** > **Opções** > **Definições** > **Definições de origem de dados**.</span><span class="sxs-lookup"><span data-stu-id="f98ba-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="f98ba-117">Na lista de origens de dados, selecione **Iniciar sessão no Dynamics 365 Customer Insights** e selecione **Limpar permissões**.</span><span class="sxs-lookup"><span data-stu-id="f98ba-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="f98ba-118">Na caixa de diálogo **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="f98ba-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="f98ba-119">vê a lista de todos os ambientes a que tem acesso.</span><span class="sxs-lookup"><span data-stu-id="f98ba-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="f98ba-120">Expandir um ambiente e abrir qualquer uma das pastas (entidades, medidas, segmentos, melhoramentos).</span><span class="sxs-lookup"><span data-stu-id="f98ba-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="f98ba-121">Por exemplo, abra a pasta **Entidades**, para ver todas as entidades que pode importar.</span><span class="sxs-lookup"><span data-stu-id="f98ba-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="f98ba-122">![Navegador do Conetor do Power BI](media/power-bi-navigator.png "Navegador do Conetor do Power BI")</span><span class="sxs-lookup"><span data-stu-id="f98ba-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="f98ba-123">Selecione as caixas de verificação junto às entidades que pretende incluir e **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="f98ba-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="f98ba-124">Pode selecionar várias entidades de vários ambientes.</span><span class="sxs-lookup"><span data-stu-id="f98ba-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="f98ba-125">Verá uma caixa de diálogo de carregamento enquanto as suas entidades estão a ser carregadas.</span><span class="sxs-lookup"><span data-stu-id="f98ba-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="f98ba-126">Depois de todas as suas entidades selecionadas terem carregado, pode utilizar as capacidades do Power BI para visualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="f98ba-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="f98ba-127">Conjuntos de dados de grandes dimensões</span><span class="sxs-lookup"><span data-stu-id="f98ba-127">Large data sets</span></span>

<span data-ttu-id="f98ba-128">O conector Customer Insights para o Power BI foi concebido para trabalhar com conjuntos de dados que contenham até 1 milhão de perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="f98ba-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="f98ba-129">Importar conjuntos de dados maiores pode funcionar, mas leva muito tempo.</span><span class="sxs-lookup"><span data-stu-id="f98ba-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="f98ba-130">Além disso, o processo pode exceder o tempo limite devido a limitações do Power BI.</span><span class="sxs-lookup"><span data-stu-id="f98ba-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="f98ba-131">Para obter mais informações, consulte [Power BI : Recomendações para conjuntos de dados de grandes dimensões](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="f98ba-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="f98ba-132">Trabalhar como um subconjunto de dados</span><span class="sxs-lookup"><span data-stu-id="f98ba-132">Work with a subset of data</span></span>

<span data-ttu-id="f98ba-133">Considere trabalhar com um subconjunto dos seus dados.</span><span class="sxs-lookup"><span data-stu-id="f98ba-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="f98ba-134">Por exemplo, pode criar [segmentos](segments.md) em vez de exportar todos os registos de clientes para o Power BI.</span><span class="sxs-lookup"><span data-stu-id="f98ba-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f98ba-135">Resolução de Problemas</span><span class="sxs-lookup"><span data-stu-id="f98ba-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="f98ba-136">O ambiente do Customer Insights não aparece no Power BI</span><span class="sxs-lookup"><span data-stu-id="f98ba-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="f98ba-137">Ambientes que tenham mais do que uma [relação](relationships.md) definida entre duas entidades idênticas nas informações da audiência não estarão disponíveis no conector do Power BI.</span><span class="sxs-lookup"><span data-stu-id="f98ba-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="f98ba-138">Pode identificar e remover as relações duplicadas.</span><span class="sxs-lookup"><span data-stu-id="f98ba-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="f98ba-139">Nas informações da audiência, vá a **Dados** > **Relações** no ambiente em falta no Power BI.</span><span class="sxs-lookup"><span data-stu-id="f98ba-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="f98ba-140">Identificar relações duplicadas:</span><span class="sxs-lookup"><span data-stu-id="f98ba-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="f98ba-141">Verifique se há mais de uma relação definida entre as mesmas duas entidades.</span><span class="sxs-lookup"><span data-stu-id="f98ba-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="f98ba-142">Verifique se existe uma relação criada entre duas entidades que estão ambas incluídas no processo de unificação.</span><span class="sxs-lookup"><span data-stu-id="f98ba-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="f98ba-143">Existe uma relação implícita definida entre todas as entidades incluídas no processo de unificação.</span><span class="sxs-lookup"><span data-stu-id="f98ba-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="f98ba-144">Remova quaisquer relações duplicadas identificadas.</span><span class="sxs-lookup"><span data-stu-id="f98ba-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="f98ba-145">Após a remoção das relações duplicadas, tente configurar novamente o conector do Power BI.</span><span class="sxs-lookup"><span data-stu-id="f98ba-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="f98ba-146">O ambiente deve estar agora disponível.</span><span class="sxs-lookup"><span data-stu-id="f98ba-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]


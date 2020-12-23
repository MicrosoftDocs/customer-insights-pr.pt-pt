---
title: Conector do Power BI
description: Saiba como utilizar o conector do Dynamics 365 Customer Insights no Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406610"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="c774c-103">Conector para Power BI (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="c774c-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="c774c-104">Crie visualizações para os seus dados com o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="c774c-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="c774c-105">Gere informações adicionais e crie relatórios com os seus dados de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="c774c-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c774c-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c774c-106">Prerequisites</span></span>

- <span data-ttu-id="c774c-107">Tem perfis unificados de clientes.</span><span class="sxs-lookup"><span data-stu-id="c774c-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="c774c-108">A versão mais recente do [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalada no seu computador.</span><span class="sxs-lookup"><span data-stu-id="c774c-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="c774c-109">[Mais informações sobre o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="c774c-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="c774c-110">Configurar o conector para Power BI</span><span class="sxs-lookup"><span data-stu-id="c774c-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="c774c-111">No Power BI Desktop, selecione **Ficheiro** > **Obter Dados**.</span><span class="sxs-lookup"><span data-stu-id="c774c-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="c774c-112">Selecione **Ver mais** e procure **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="c774c-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="c774c-113">Selecione o resultado e selecione **Ligar**.</span><span class="sxs-lookup"><span data-stu-id="c774c-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="c774c-114">**Inicie sessão** com a mesma conta organizacional utilizada para o Customer Insights e selecione **Ligar**.</span><span class="sxs-lookup"><span data-stu-id="c774c-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c774c-115">A conta que indica neste passo é usada para recolher dados do Customer Insights e não precisa de ser a mesma em que está a iniciar sessão no Power BI.</span><span class="sxs-lookup"><span data-stu-id="c774c-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="c774c-116">Para reiniciar a conta que é utilizada para a recolha de dados, abra o Power BI e vá a **Ficheiro** > **Opções** > **Definições** > **Definições de origem de dados**.</span><span class="sxs-lookup"><span data-stu-id="c774c-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="c774c-117">Na lista de origens de dados, selecione **Iniciar sessão no Dynamics 365 Customer Insights** e selecione **Limpar permissões**.</span><span class="sxs-lookup"><span data-stu-id="c774c-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="c774c-118">Na caixa de diálogo **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="c774c-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="c774c-119">vê a lista de todos os ambientes a que tem acesso.</span><span class="sxs-lookup"><span data-stu-id="c774c-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="c774c-120">Expandir um ambiente e abrir qualquer uma das pastas (entidades, medidas, segmentos, melhoramentos).</span><span class="sxs-lookup"><span data-stu-id="c774c-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="c774c-121">Por exemplo, abra a pasta **Entidades**, para ver todas as entidades que pode importar.</span><span class="sxs-lookup"><span data-stu-id="c774c-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="c774c-122">![Navegador do Conetor do Power BI](media/power-bi-navigator.png "Navegador do Conetor do Power BI")</span><span class="sxs-lookup"><span data-stu-id="c774c-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="c774c-123">Selecione as caixas de verificação junto às entidades que pretende incluir e **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="c774c-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="c774c-124">Pode selecionar várias entidades de vários ambientes.</span><span class="sxs-lookup"><span data-stu-id="c774c-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="c774c-125">Verá uma caixa de diálogo de carregamento enquanto as suas entidades estão a ser carregadas.</span><span class="sxs-lookup"><span data-stu-id="c774c-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="c774c-126">Depois de todas as suas entidades selecionadas terem carregado, pode utilizar as capacidades do Power BI para visualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="c774c-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="c774c-127">Conjuntos de dados de grandes dimensões</span><span class="sxs-lookup"><span data-stu-id="c774c-127">Large data sets</span></span>

<span data-ttu-id="c774c-128">O conector Customer Insights para o Power BI foi concebido para trabalhar com conjuntos de dados que contenham até 1 milhão de perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="c774c-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="c774c-129">Importar conjuntos de dados maiores pode funcionar, mas leva muito tempo.</span><span class="sxs-lookup"><span data-stu-id="c774c-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="c774c-130">Além disso, o processo pode exceder o tempo limite devido a limitações do Power BI.</span><span class="sxs-lookup"><span data-stu-id="c774c-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="c774c-131">Para obter mais informações, consulte [Power BI : Recomendações para conjuntos de dados de grandes dimensões](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="c774c-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="c774c-132">Trabalhar como um subconjunto de dados</span><span class="sxs-lookup"><span data-stu-id="c774c-132">Work with a subset of data</span></span>

<span data-ttu-id="c774c-133">Considere trabalhar com um subconjunto dos seus dados.</span><span class="sxs-lookup"><span data-stu-id="c774c-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="c774c-134">Por exemplo, pode criar [segmentos](segments.md) em vez de exportar todos os registos de clientes para o Power BI.</span><span class="sxs-lookup"><span data-stu-id="c774c-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

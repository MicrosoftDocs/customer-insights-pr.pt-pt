---
title: Atualização incremental para origens de dados baseados em Power Query
description: Atualizar dados novos e atualizados para grandes origens de dados baseadas no Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406640"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="0e596-103">Atualização incremental para origens de dados baseadas no Power Query</span><span class="sxs-lookup"><span data-stu-id="0e596-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="0e596-104">A atualização incremental para origens de dados fornece as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="0e596-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="0e596-105">**Atualizações mais rápidas** – apenas os dados alterados são atualizados.</span><span class="sxs-lookup"><span data-stu-id="0e596-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="0e596-106">Por exemplo, poderá atualizar apenas os últimos cinco dias de um conjunto de dados histórico.</span><span class="sxs-lookup"><span data-stu-id="0e596-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="0e596-107">**Maior fiabilidade** – com atualizações menores, não é necessário manter ligações com sistemas de origem voláteis por tanto tempo, reduzindo o risco de problemas de ligação.</span><span class="sxs-lookup"><span data-stu-id="0e596-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="0e596-108">**Consumo de recursos reduzida** – a atualização de apenas um subconjunto de dados proporciona uma utilização mais eficiente dos recursos informáticos e reduz a pegada ambiental.</span><span class="sxs-lookup"><span data-stu-id="0e596-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="0e596-109">Configurar atualização incremental</span><span class="sxs-lookup"><span data-stu-id="0e596-109">Configure incremental refresh</span></span>

<span data-ttu-id="0e596-110">Os insights da audiência permitem uma atualização incremental para origens de dados importados através do Power Query que suportam a ingestão incremental.</span><span class="sxs-lookup"><span data-stu-id="0e596-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="0e596-111">Por exemplo, bases de dados SQL do Azure com campos de data e hora, que indicam quando os registos de dados foram atualizados pela última vez.</span><span class="sxs-lookup"><span data-stu-id="0e596-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="0e596-112">[Criar uma nova origem de dados baseado no Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0e596-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="0e596-113">Forneça um nome para a origem de dados.</span><span class="sxs-lookup"><span data-stu-id="0e596-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="0e596-114">Selecione uma origem de dados que suporte a atualização incremental, tal como a base de dados SQL do Azure.</span><span class="sxs-lookup"><span data-stu-id="0e596-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="0e596-115">Selecione as entidades ou tabelas a ingerir.</span><span class="sxs-lookup"><span data-stu-id="0e596-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="0e596-116">Conclua os passos de transformação e selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="0e596-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="0e596-117">Na caixa de diálogo **Configurar atualização incremental**, selecione **Configurar** para abrir as **Definições de atualização incremental**.</span><span class="sxs-lookup"><span data-stu-id="0e596-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="0e596-118">Se selecionar **Ignorar**, a origem de dados irá atualizar todo o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="0e596-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="0e596-119">Também pode aplicar a atualização incremental mais tarde editando uma origem de dados existente.</span><span class="sxs-lookup"><span data-stu-id="0e596-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="0e596-120">Nas **Definições de atualização incremental**, irá configurar a atualização incremental para todas as entidades que tiver selecionado ao criar a origem de dados.</span><span class="sxs-lookup"><span data-stu-id="0e596-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e596-121">![Configurar entidades numa origem de dados para atualização incremental](media/incremental-refresh-settings.png "Configurar entidades numa origem de dados para atualização incremental")</span><span class="sxs-lookup"><span data-stu-id="0e596-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="0e596-122">Selecione uma entidade e forneça os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="0e596-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="0e596-123">**Definir a chave primária**: selecione uma chave primária para a entidade ou tabela.</span><span class="sxs-lookup"><span data-stu-id="0e596-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="0e596-124">**Definir o campo "última atualização"**: este campo só irá apresentar atributos do tipo data ou hora.</span><span class="sxs-lookup"><span data-stu-id="0e596-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="0e596-125">Selecione um atributo que indique quando os registos foram atualizados pela última vez.</span><span class="sxs-lookup"><span data-stu-id="0e596-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="0e596-126">Será usado para identificar os registos que se enquadram no intervalo de tempo de atualização incremental.</span><span class="sxs-lookup"><span data-stu-id="0e596-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="0e596-127">**Pesquisar atualizações a cada**: especifique o intervalo de tempo pretendido da atualização incremental.</span><span class="sxs-lookup"><span data-stu-id="0e596-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="0e596-128">Selecione **Guardar** para concluir a criação do origem de dados.</span><span class="sxs-lookup"><span data-stu-id="0e596-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="0e596-129">A atualização de dados inicial será uma atualização completa.</span><span class="sxs-lookup"><span data-stu-id="0e596-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="0e596-130">Posteriormente, a atualização de dados incremental acontece conforme configurado no passo anterior.</span><span class="sxs-lookup"><span data-stu-id="0e596-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>

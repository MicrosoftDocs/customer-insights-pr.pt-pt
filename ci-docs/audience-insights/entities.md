---
title: Entidades e conjuntos de dados
description: Ver dados na página Entidades.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596421"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="07ebb-103">Entidades em insight da audiência</span><span class="sxs-lookup"><span data-stu-id="07ebb-103">Entities in audience insights</span></span>

<span data-ttu-id="07ebb-104">Depois de [configurar as suas origens de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="07ebb-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="07ebb-105">As entidades são consideradas conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="07ebb-105">Entities are considered datasets.</span></span> <span data-ttu-id="07ebb-106">Múltiplas capacidades de Dynamics 365 Customer Insights são construídas em torno destas entidades.</span><span class="sxs-lookup"><span data-stu-id="07ebb-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="07ebb-107">A sua análise aprofundada poderá ajudar a validar a saída dessas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="07ebb-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="07ebb-108">A página **Entidades** lista as entidades e inclui várias colunas:</span><span class="sxs-lookup"><span data-stu-id="07ebb-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="07ebb-109">**Nome**: o nome da sua entidade de dados.</span><span class="sxs-lookup"><span data-stu-id="07ebb-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="07ebb-110">Se for apresentado um símbolo de aviso junto a um nome de entidade, significa que os dados dessa entidade não foram carregados com êxito.</span><span class="sxs-lookup"><span data-stu-id="07ebb-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="07ebb-111">**Origem**: o tipo de origem de dados que ingeriu a entidade</span><span class="sxs-lookup"><span data-stu-id="07ebb-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="07ebb-112">**Criado por**: nome da pessoa que criou a entidade</span><span class="sxs-lookup"><span data-stu-id="07ebb-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="07ebb-113">**Criado**: data e hora da criação da entidade</span><span class="sxs-lookup"><span data-stu-id="07ebb-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="07ebb-114">**Atualizado por**: nome da pessoa que atualizou a entidade</span><span class="sxs-lookup"><span data-stu-id="07ebb-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="07ebb-115">**Última atualização**: data e hora da última atualização da entidade</span><span class="sxs-lookup"><span data-stu-id="07ebb-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="07ebb-116">**Última atualização**: data e hora da última atualização de dados</span><span class="sxs-lookup"><span data-stu-id="07ebb-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="07ebb-117">Explorar os dados de uma entidade específica</span><span class="sxs-lookup"><span data-stu-id="07ebb-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="07ebb-118">Selecione uma entidade para explorar os diferentes campos e registos incluídos nessa entidade.</span><span class="sxs-lookup"><span data-stu-id="07ebb-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="07ebb-119">![Selecionar uma entidade](media/data-manager-entities-data.png "Selecionar uma entidade")</span><span class="sxs-lookup"><span data-stu-id="07ebb-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="07ebb-120">O separador **Dados** é selecionado por predefinição e mostra uma tabela a listar os detalhes sobre os registos individuais da entidade.</span><span class="sxs-lookup"><span data-stu-id="07ebb-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="07ebb-121">![Tabela de campos](media/data-manager-entities-fields.PNG "Tabela de campos")</span><span class="sxs-lookup"><span data-stu-id="07ebb-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="07ebb-122">O separador **Campos** mostra uma tabela para rever os detalhes da entidade selecionada, como os nomes dos campos, os tipos de dados e os tipos.</span><span class="sxs-lookup"><span data-stu-id="07ebb-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="07ebb-123">A coluna **Tipo** mostra os tipos associados do Common Data Model, que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos utilizadores.</span><span class="sxs-lookup"><span data-stu-id="07ebb-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="07ebb-124">Estes são tipos semânticos que podem ser diferentes dos tipos de dados dos atributos. Por exemplo, o campo *E-mail* abaixo tem um tipo de dados *Texto*, mas o respetivo tipo (semântico) de Common Data Model pode ser *E-mail* ou *Endereço de E-mail*.</span><span class="sxs-lookup"><span data-stu-id="07ebb-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="07ebb-125">Ambas as tabelas mostram apenas um exemplo dos dados da sua entidade.</span><span class="sxs-lookup"><span data-stu-id="07ebb-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="07ebb-126">Para ver o conjunto de dados completo, vá para a página **Origens de dados**, selecione uma entidade, selecione **Editar** e, em seguida, veja os dados desta entidade com o editor do Power Query, tal como explicado em [Origens de dados](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="07ebb-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="07ebb-127">Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características importantes dos dados, tais como os valores nulos, os valores em falta, os valores exclusivos, as contagens e as distribuições, conforme aplicável aos seus dados.</span><span class="sxs-lookup"><span data-stu-id="07ebb-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="07ebb-128">Selecione o ícone de gráfico para ver o resumo dos dados.</span><span class="sxs-lookup"><span data-stu-id="07ebb-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="07ebb-129">![Símbolo de resumo](media/data-manager-entities-summary.png "Tabela de resumo de dados")</span><span class="sxs-lookup"><span data-stu-id="07ebb-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="07ebb-130">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="07ebb-130">Next step</span></span>

<span data-ttu-id="07ebb-131">Consulte o tópico [Unificar](data-unification.md) para saber mais sobre como *mapear*, *corresponder* e *intercalar* os dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="07ebb-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
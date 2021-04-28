---
title: Segmentos baseados na saída de predição
description: Crie segmentos baseados na entidade de saída de um modelo de predição.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741443"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="1b710-103">Criar um segmento baseado num modelo predição (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="1b710-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="1b710-104">Por vezes, os resultados de predições aplicam-se apenas a um subconjunto dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="1b710-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="1b710-105">Aumente a personalização das recomendações através da criação de segmentos a partir de resultados de modelos de predição.</span><span class="sxs-lookup"><span data-stu-id="1b710-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="1b710-106">Por exemplo, pode querer apresentar recomendações específicas aos clientes que preferem um determinado tipo de serviço.</span><span class="sxs-lookup"><span data-stu-id="1b710-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1b710-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1b710-107">Prerequisites</span></span>

- <span data-ttu-id="1b710-108">Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1b710-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="1b710-109">Um modelo recomendação de produtos, de abandono transacional, de abandono de subscrições ou de valor vitalício do cliente configurados no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1b710-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="1b710-110">Reveja os requisitos para configurar os diferentes modelos:</span><span class="sxs-lookup"><span data-stu-id="1b710-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="1b710-111">Modelo de recomendação de produtos</span><span class="sxs-lookup"><span data-stu-id="1b710-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="1b710-112">Modelo de abandono de subscrições</span><span class="sxs-lookup"><span data-stu-id="1b710-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="1b710-113">Modelo de abandono transacional</span><span class="sxs-lookup"><span data-stu-id="1b710-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="1b710-114">Modelo de valor vitalício do cliente</span><span class="sxs-lookup"><span data-stu-id="1b710-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="1b710-115">Criar um segmento de clientes com base em predições</span><span class="sxs-lookup"><span data-stu-id="1b710-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="1b710-116">Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.</span><span class="sxs-lookup"><span data-stu-id="1b710-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="1b710-117">Selecione as reticências verticais junto ao modelo que pretende rever e selecione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="1b710-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="1b710-118">Na página de resultados, selecione **Criar segmento**.</span><span class="sxs-lookup"><span data-stu-id="1b710-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="1b710-119">Para mais informações sobre a página de resultados, reveja o artigo sobre o modelo.</span><span class="sxs-lookup"><span data-stu-id="1b710-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de ecrã da página de resultados de predição com a ação Criar segmento realçada.":::

1. <span data-ttu-id="1b710-121">Crie um novo segmento baseado na entidade de saída do modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1b710-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="1b710-122">Para obter mais informações, veja [Criar e gerir segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1b710-122">For more information, see [Create and manage segments](segments.md).</span></span>
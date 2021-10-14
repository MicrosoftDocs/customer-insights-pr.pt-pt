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
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036433"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Criar um segmento baseado num modelo predição (pré-visualização)

Por vezes, os resultados de predições aplicam-se apenas a um subconjunto dos seus clientes. Aumente a personalização das recomendações através da criação de segmentos a partir de resultados de modelos de predição. Por exemplo, pode querer apresentar recomendações específicas aos clientes que preferem um determinado tipo de serviço. 

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.

- Um modelo recomendação de produtos, de abandono transacional, de abandono de subscrições ou de valor vitalício do cliente configurados no Customer Insights. Reveja os requisitos para configurar os diferentes modelos:

  - [Modelo de recomendação de produtos](predict-product-recommendation.md)
  - [Modelo de abandono de subscrições](predict-subscription-churn.md)
  - [Modelo de abandono transacional](predict-transactional-churn.md)
  - [Modelo de valor vitalício do cliente](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Criar um segmento de clientes com base em predições

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione as reticências verticais junto ao modelo que pretende rever e selecione **Ver**.

1. Na página de resultados, selecione **Criar segmento**. Para mais informações sobre a página de resultados, reveja o artigo sobre o modelo.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de ecrã da página de resultados de predição com a ação Criar segmento realçada.":::

1. Crie um novo segmento baseado na entidade de saída do modelo selecionado. Para obter mais informações, veja [Criar e gerir segmentos](segments.md).
---
title: Criar um segmento baseado num modelo de predição
description: Crie segmentos baseados na entidade de saída de um modelo de predição.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: d67594f2467c1a0fde84b1ba0bd1afa4025e7b71
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081377"
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
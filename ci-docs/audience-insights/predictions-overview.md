---
title: Descrição geral sobre cenários de predição suportados
description: Cenários de predição e opções abrangidas pela aplicação Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095739"
---
# <a name="predictions-overview"></a><span data-ttu-id="bf2a5-103">Descrição geral das predições</span><span class="sxs-lookup"><span data-stu-id="bf2a5-103">Predictions overview</span></span>

<span data-ttu-id="bf2a5-104">O Dynamics 365 Customer Insights vem com uma variedade de opções que tiram proveito da IA e aprendizagem automática para prever dados.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="bf2a5-105">Modelos fornecidos com o programa</span><span class="sxs-lookup"><span data-stu-id="bf2a5-105">Out-of-box models</span></span>

<span data-ttu-id="bf2a5-106">A maneira mais fácil de começar com a previsão de dados são os modelos predefinidos, muitas vezes referidos como modelos fornecidos com o programa.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="bf2a5-107">Só requerem certos dados e estrutura para gerar informações rapidamente.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="bf2a5-108">Atualmente, estão disponíveis os seguintes modelos:</span><span class="sxs-lookup"><span data-stu-id="bf2a5-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="bf2a5-109">[Valor vitalício do cliente](predict-customer-lifetime-value.md): prevê a receita potencial de um cliente ao longo de toda a interação com um negócio.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="bf2a5-110">[Recomendação do produto](predict-product-recommendation.md): sugere conjuntos de recomendações preditivas do produto com base no comportamento de compra e clientes com padrões de compra semelhantes.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="bf2a5-111">[Abandono de subscrições](predict-subscription-churn.md): prevê se um cliente está em risco por ter deixado de utilizar os produtos ou serviços de subscrição da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="bf2a5-112">[Abandono transacional](predict-transactional-churn.md): prevê se um cliente deixará de comprar os seus produtos ou serviços num determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="bf2a5-113">Integração do Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bf2a5-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="bf2a5-114">Se uma organização já utiliza cenários aprendizagem automática baseados em experiências do Azure Machine Learning, a funcionalidade de modelos personalizados no Customer Insights ajuda a interligá-los.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="bf2a5-115">Crie fluxos de trabalho que o ajudem a escolher os dados de que pretende gerar informações e mapeie os resultados para os seus perfis de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="bf2a5-116">Para mais informações, consulte [Modelos personalizados de aprendizagem automática](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="bf2a5-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="bf2a5-117">Predição do AI Builder</span><span class="sxs-lookup"><span data-stu-id="bf2a5-117">AI Builder prediction</span></span>

<span data-ttu-id="bf2a5-118">Por vezes, os conjuntos de dados estão incompletos e alguns valores estão em falta.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="bf2a5-119">O Customer Insights pode ajudar a prever valores em falta para a entidade e segmentos do Cliente.</span><span class="sxs-lookup"><span data-stu-id="bf2a5-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="bf2a5-120">Para mais informações, consulte [Completar os seus dados parciais com predições](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="bf2a5-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>

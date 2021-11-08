---
title: Descrição geral sobre cenários de predição suportados
description: Cenários de predição e opções abrangidas pela aplicação Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 63e22bf9a457ea43c65132643681cffb295ae7e5
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673976"
---
# <a name="predictions-overview"></a>Descrição geral das predições

O Dynamics 365 Customer Insights vem com uma variedade de opções que tiram proveito da IA e aprendizagem automática para prever dados. 

## <a name="out-of-box-models"></a>Modelos fornecidos com o programa

A maneira mais fácil de começar com a previsão de dados são os modelos predefinidos, muitas vezes referidos como modelos fornecidos com o programa. Só requerem certos dados e estrutura para gerar informações rapidamente. Atualmente, estão disponíveis os seguintes modelos: 

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- [Valor vitalício do cliente](predict-customer-lifetime-value.md): prevê a receita potencial de um cliente ao longo de toda a interação com um negócio.
- [Recomendação do produto](predict-product-recommendation.md): sugere conjuntos de recomendações preditivas do produto com base no comportamento de compra e clientes com padrões de compra semelhantes.
- [Abandono de subscrições](predict-subscription-churn.md): prevê se um cliente está em risco por ter deixado de utilizar os produtos ou serviços de subscrição da sua empresa.
- [Abandono transacional](predict-transactional-churn.md): prevê se um cliente deixará de comprar os seus produtos ou serviços num determinado período de tempo.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- [Abandono transacional](predict-transactional-churn.md): prevê se um cliente deixará de comprar os seus produtos ou serviços num determinado período de tempo.

---


## <a name="azure-machine-learning-integration"></a>Integração do Azure Machine Learning

Se uma organização já utiliza cenários aprendizagem automática baseados em experiências do Azure Machine Learning, a funcionalidade de modelos personalizados no Customer Insights ajuda a interligá-los. Crie fluxos de trabalho que o ajudem a escolher os dados de que pretende gerar informações e mapeie os resultados para os seus perfis de clientes unificados. Para mais informações, consulte [Modelos personalizados de aprendizagem automática](custom-models.md).

## <a name="ai-builder-prediction"></a>Predição do AI Builder

Por vezes, os conjuntos de dados estão incompletos e alguns valores estão em falta. O Customer Insights pode ajudar a prever valores em falta para a entidade e segmentos do Cliente. Para mais informações, consulte [Completar os seus dados parciais com predições](predictions.md).

---
title: Guia de exemplos de predição de recomendações de produtos
description: Utilize este guia de exemplos para experimentar o modelo de predição de recomendações de produtos de origem.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610158"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guia de exemplos de predição de recomendações de produtos

Este guia acompanha-o através de um exemplo de ponto a ponto da predição de recomendações de produtos utilizando dados de amostra. Recomendamos-lhe que esta predição [num ambiente novo](manage-environments.md).

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz máquinas de café, bem como café de alta qualidade. Vendem os produtos através do seu site Contoso Coffee. O objetivo é compreender quais os produtos que devem recomendar aos seus clientes recorrentes. Saber quais os clientes mais **propensos a comprar**, pode ajudá-los a economizar esforços de marketing, focando-se em itens específicos.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Reveja os artigos [sobre a ingestão de dados](data-sources.md) e [ligar a uma origem de dados do Power Query](connect-power-query.md). As seguintes informações pressupõem que está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados de clientes a partir da plataforma eCommerce

1. Crie uma origem de dados do Power Query com o nome **eCommerce** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce: https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados para **eCommerceContacts**.

1. **Guardar** a origem dos dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**. Escolha novamente o conetor **Texto/CSV**.

1. Introduza o URL para dados de compras online https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel lateral, mude o nome da sua origem de dados para **eCommercePurchases**.

1. **Guardar** a origem dos dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados de clientes a partir do esquema de fidelidade

1. Crie uma origem de dados com o nome **LoyaltyScheme** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para clientes fidelizados https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados para **loyCustomers**.

1. **Guardar** a origem dos dados.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Reveja o artigo [sobre unificação de dados](data-unification.md). As seguintes informações pressupõem que está familiarizado com a unificação de dados em geral.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tarefa 3 – Criar atividade do histórico de transações

Reveja o artigo [sobre atividades do cliente](activities.md). As seguintes informações pressupõem que está familiarizado com a criação de atividades em geral.

1. Crie uma atividade denominada **eCommercePurchases** com a entidade *eCommercePurchases:eCommerce* e a respetiva chave primária, **PurchaseId**.

1. Crie uma relação entre *eCommercePurchases:eCommerce* e *eCommerceContacts:eCommerce* com o **ContactID** como a chave externa para ligar as duas entidades.

1. Selecione **TotalPrice** para **EventActivity** e **PurchasedOn** para **TimeStamp**.

1. Selecione **SalesOrderLine** para o **Tipo de Atividade** e mapeie semanticamente os dados de atividade.

1. Execute a atividade.

## <a name="task-4---configure-product-recommendation-prediction"></a>Tarefa 4 – Configurar a predição de recomendações de produtos

Com os perfis de clientes unificados em vigor e a atividade criada, execute a predição de recomendações de produtos.

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** no mosaico **Recomendações de produtos (pré-visualização)**.

1. Selecione **Introdução**.

1. Nomeie o modelo **Predição do Modelo de Recomendações de Produtos OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Selecione **Seguinte**.

1. Definir preferências de modelo:
   - **Número de produtos**: **5** para definir quantos produtos pretende recomendar aos seus clientes.
   - **Repetir compras esperadas**: **Sim** para incluir produtos comprados anteriormente na recomendação.
   - **Janela Relembrar:** **365 dias** para definir quão atrás o modelo irá procurar antes de recomendar um produto novamente.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferências de modelo para o modelo de recomendação de produtos.":::

1. Selecione **Seguinte**.

1. No passo **Adicionar histórico de compras**, selecione **Adicionar dados**.

1. Selecione **SalesOrderLine** e a entidade eCommercePurchases e selecione **Seguinte**. Os dados obrigatórios são preenchidos automaticamente a partir da atividade. Selecione **Guardar** e, em seguida, **Seguinte**.

1. Ignore os passos **Adicionar informações de produtos** e **Filtros de produtos** porque não temos dados de informações de produtos.

1. No passo **Atualizações de dados**, selecione **Mensal** para a agenda do modelo.

1. Selecione **Seguinte**.

1. Depois de rever todos os detalhes, selecione **Guardar e Executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5 - Rever resultados do modelo e explicações

Deixe o modelo completar a formação e a pontuação dos dados. Reveja as [explicações do modelo de recomendações de produtos](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tarefa 6 – Criar um segmento de produtos muito comprados

A execução do modelo cria uma nova entidade, que é listada em **Dados** > **Entidades**. Pode criar um novo segmento com base na entidade criada pelo modelo.

1. Na página de resultados, selecione **Criar segmento**.

1. Crie uma regra utilizando a entidade **OOBProductRecommendationModelPrediction** e defina o segmento:
   - **Campo**: ProductID
   - **Valor**: selecione os três principais IDs do produto

1. Selecione **Guardar** e **Execute** o segmento.

Agora, tem um segmento atualizado dinamicamente que identifica os clientes que poderão estar interessados em comprar os cinco produtos mais recomendados. Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

> [!TIP]
> Também pode criar um segmento para um modelo de predição a partir da página **Segmentos** selecionando **Novo** e escolhendo **Criar a partir** > **Inteligência**. Para mais informações, consulte [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Guia de exemplos de predição de recomendações de produtos
description: Utilize este guia de exemplos para experimentar o modelo de predição de recomendações de produtos de origem.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762700"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guia de exemplos de predição de recomendações de produtos

Iremos acompanhá-lo do princípio ao fim num exemplo de predição de recomendações de produtos usando os dados de exemplo fornecidos abaixo.

## <a name="scenario"></a>Cenário

Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que vendem através do seu site Contoso Coffee. O objetivo é compreender quais os produtos que devem recomendar aos seus clientes recorrentes. Saber quais os clientes mais **propensos a comprar**, pode ajudá-los a economizar esforços de marketing, focando-se em itens específicos.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.
- Recomendamos-lhe que implemente as seguintes etapas [num ambiente novo](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Reveja os artigos [sobre a ingestão de dados](data-sources.md) e a [importação de origens de dados utilizando especificamente conectores do Power Query](connect-power-query.md). A seguinte informação pressupõe que está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados de clientes a partir da plataforma eCommerce

1. Criar uma origem de dados com o nome **eCommerce**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo "Nome" no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**

1. **Guardar** a origem dos dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**. Escolha novamente o conetor **Texto/CSV**.

1. Introduza o URL para dados de **Compras online** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel lateral, mude o nome da sua origem de dados de **Consulta** para **eCommercePurchases**.

1. **Guardar** a origem dos dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados de clientes a partir do esquema de fidelidade

1. Criar uma origem de dados com o nome **LoyaltyScheme**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **loyCustomers**.

1. **Guardar** a origem dos dados.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tarefa 3 – Configurar a predição de recomendações de produtos

Com os unified customer profiles criados, podemos agora executar a previsão de recomendação de produto.

1. Vá à **Inteligência** > **Predição**, escolha **Recomendação do produto**.

1. Selecione **Introdução**.

1. Nomeie o modelo **Predição do Modelo de Recomendações de Produtos OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Definir três condições para o modelo:

   - **Número de produtos**: defina este valor para **5**. Esta definição define quantos produtos pretende recomendar aos seus clientes.

   - **Repetir compras esperadas**: selecione **Sim** para indicar que pretende incluir produtos na recomendação que os seus clientes já compraram anteriormente.

   - **Janela de recuo:** selecione, pelo menos, **365 dias**. Esta definição define o período passado que o modelo irá observar a atividade do cliente para a utilizar como entrada para as respetivas recomendações.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferências de modelo para o modelo de recomendação de produtos.":::

1. No passo **Adicionar dados necessários**, selecione **Adicionar dados**.

1. No painel **Adicionar dados**, escolha **SalesOrderLine** como entidade do histórico de compra. Neste momento, é provável que ainda não tenha sido configurada. Abra a ligação no painel para criar a atividade com os seguintes passos:
   1. Introduza um **Nome de atividade** e escolha *eCommercePurchases:eCommerce* como **Entidade de atividade**. A **Chave primária** é *PurchaseId*.
   1. Defina e escolha o nome da relação para a *entidade eCommerceContacts:eCommerce* e escolha **ContactId** como chave externa.
   1. Para a unificação de Atividade, defina a **Atividade de evento** como *TotalPrice* e o carimbo de data/hora como *PurchasedOn*. Pode especificar mais campos conforme descrito nas [atividades do Cliente](activities.md).
   1. Para **Tipo de atividade**, escolha *SalesOrderLine*. Mapeie os campos de atividade seguintes:
      - ID da linha de encomenda: PurchaseId
      - ID da encomenda: PurchaseId
      - Data da encomenda: PurchasedOn
      - ID do Produto: ProductId
      - Montante: TotalPrice
   1. Reveja e finalize a atividade antes de voltar à configuração do modelo.

1. Novamente no passo **Selecionar atividades**, escolha a atividade recém-criada na secção **Atividades**. Selecione **Seguinte** e o mapeamento de atributos já está preenchido. Selecione **Guardar**.

1. Neste guia de exemplo, ignoramos os conjuntos **Adicionar informações sobre produtos** e **Filtros de produtos** porque não temos dados sobre informações de produtos.

1. No passo **Atualizações de dados**, configure a agenda do modelo.

   O modelo precisa de treinar regularmente para aprender novos padrões quando há novos dados ingeridos. Para este exemplo, selecione **Mensalmente**.

1. Depois de rever todos os detalhes, selecione **Guardar e Executar**. A primeira vez que executar o modelo irá demorar alguns minutos.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Rever resultados do modelo e explicações

Deixe o modelo completar a formação e a pontuação dos dados. Pode agora rever as explicações do modelo de recomendação de produtos. Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tarefa 5 – Criar um segmento de produtos muito comprados

A execução do modelo de produção cria uma nova entidade que se pode ver em **Dados** > **Entidades**.

Pode criar um novo segmento com base na entidade criada pelo modelo.

1. Aceda a **Segmentos**. Selecione **Novo** e escolha **Criar a partir de inteligência**.

   ![Criar um segmento com a saída do modelo.](media/segment-intelligence.png)

1. Selecione o ponto final **OOBProductProductRecommendationModelPrediction** e defina o segmento:

   - Campo: ProductID
   - Valor: selecione os três principais IDs do produto

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Criar um segmento a partir dos resultados do modelo.":::

Agora, tem um segmento atualizado dinamicamente que identifica os clientes que poderão estar interessados em comprar os três produtos mais recomendados.

Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

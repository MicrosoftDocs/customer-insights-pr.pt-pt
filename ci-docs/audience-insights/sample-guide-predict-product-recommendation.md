---
title: Guia de exemplos de predição de recomendações de produtos
description: Utilize este guia de exemplos para experimentar o modelo de predição de recomendações de produtos de origem.
ms.date: 02/10/2021
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
ms.openlocfilehash: 8ba54cfd466049c8df99c15f34626ab1914234f1
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354661"
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

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

5. No campo "Nome" no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**

6. **Guardar** a origem dos dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**. Escolha novamente o conetor **Texto/CSV**.

1. Introduza o URL para dados de **Compras online** https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel lateral, mude o nome da sua origem de dados de **Consulta** para **eCommercePurchases**.

1. **Guardar** a origem dos dados.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados de clientes a partir do esquema de fidelidade

1. Criar uma origem de dados com o nome **LoyaltyScheme**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **loyCustomers**.

1. **Guardar** a origem dos dados.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Depois de ingerir os dados, iniciamos agora o processo de unificação de dados para criar um perfil de cliente unificado. Para mais informações, consulte [Unificação de dados](data-unification.md).

### <a name="map"></a>Mapear

1. Depois de ingerir os dados, mapear os contactos desde os dados de eCommerce e Fidelidade até aos tipos de dados comuns. Aceder a **Dados** > **Unificar** > **Mapear**.

2. Selecionar as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.

   ![unificar as origens de dados do comércio eletrónico e da fidelidade.](media/unify-ecommerce-loyalty.png)

3. Selecionar **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.

   ![Unificar LoyaltyId como a chave primária.](media/unify-loyaltyid.png)

### <a name="match"></a>Corresponder

1. Aceda ao separador **Corresponder** e selecione **Definir encomenda**.

2. Na lista pendente **Primário**, escolha **eCommerceContacts : eCommerce** como a origem primária e inclua todos os registos.

3. Na lista pendente **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registos.

   ![Unificar corresponder comércio eletrónico e fidelidade.](media/unify-match-order.png)

4. Selecione **Criar uma nova regra**

5. Adicione a sua primeira condição usando FullName.

   - Para eCommerceContacts, selecione **FullName** na lista pendente.
   - Para loyCustomers, selecione **FullName** na lista pendente.
   - Selecione a lista pendente **Normalizar** e escolha **Tipo (Telefone, Nome, Morada, ...)**.
   - Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.

6. Introduzir o nome **FullName, Email** para a nova regra.

   - Acrescentar uma segunda condição para o endereço de correio eletrónico, selecionando **Adicionar condição**
   - Para a entidade eCommerceContacts, escolha **E-mail** na lista pendente.
   - Para a entidade loyCustomers, escolha **E-mail** na lista pendente.
   - Deixar em branco Normalizar.
   - Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.

   ![Unificar a regra de correspondência para nome e e-mail.](media/unify-match-rule.png)

7. Selecione **Guardar** e **Executar**.

### <a name="merge"></a>Unir

1. Aceda ao separador **Intercalar**.

1. No **ContactId** para a entidade **loyCustomers**, alterar o nome a apresentar para **ContactIdLOYALTY** para o diferenciar das outras IDs ingeridas.

   ![renomear contactid a partir de loyalty id.](media/unify-merge-contactid.png)

1. Selecione **Guardar** e **Executar** para iniciar o processo de intercalar.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tarefa 3 – Configurar a predição de recomendações de produtos

Com os perfis unificados de clientes em vigor, podemos agora executar a predição de abandono da subscrição.

1. Vá à **Inteligência** > **Predição**, escolha **Recomendação do produto**.

1. Selecione **Introdução**.

1. Nomeie o modelo **Predição do Modelo de Recomendações de Produtos OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Definir três condições para o modelo:

   - **Número de produtos**: defina este valor para **5**. Esta definição define quantos produtos pretende recomendar aos seus clientes.

   - **Repetir compras esperadas**: selecione **Sim** para indicar que pretende incluir produtos na recomendação que os seus clientes já compraram anteriormente.

   - **Janela de recuo:** selecione, pelo menos, **365 dias**. Esta definição define o período passado que o modelo irá observar a atividade do cliente para a utilizar como entrada para as respetivas recomendações.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferências de modelo para o modelo de recomendação de produtos.":::

1. Selecione **Dados obrigatórios** e selecione **Adicionar dados** para o histórico de compras.

1. Adicionar a entidade **eCommercePurchases : eCommerce** e mapear os campos desde o comércio eletrónico até aos campos correspondentes exigidos pelo modelo.

1. Junte a entidade **eCommercePurchases : eCommerce** com **eCommerceContacts : eCommerce**.

   ![Junte-se às entidade de eCommerce.](media/model-purchase-join.png)

1. Selecione **Seguinte** para definir o agendar do modelo.

   O modelo precisa de treinar regularmente para aprender novos padrões quando há novos dados ingeridos. Para este exemplo, selecione **Mensalmente**.

1. Depois de rever todos os detalhes, selecione **Guardar e Executar**.


## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Rever resultados do modelo e explicações

Deixe o modelo completar a formação e a pontuação dos dados. Pode agora rever as explicações do modelo de recomendação de produtos. Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tarefa 5 – Criar um segmento de produtos muito comprados

A execução do modelo de produção cria uma nova entidade que se pode ver em **Dados** > **Entidades**.

Pode criar um novo segmento com base na entidade criada pelo modelo.

1. Aceda a **Segmentos**. Selecione **Novo** e escolha **Criar a partir de** > **Inteligência**.

   ![Criar um segmento com a saída do modelo.](media/segment-intelligence.png)

1. Selecione o ponto final **OOBProductProductRecommendationModelPrediction** e defina o segmento:

   - Campo: ProductID
   - Operador: Valor
   - Valor: selecione os três principais IDs do produto

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Criar um segmento a partir dos resultados do modelo.":::

Tem agora um segmento que é atualizado dinamicamente que identifica os clientes que estão mais dispostos a comprar os três produtos mais recomendados 

Para obter mais informações, veja [Criar e gerir segmentos](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

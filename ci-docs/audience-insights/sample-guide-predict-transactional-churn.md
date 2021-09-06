---
title: Guia de predição de abandono transacional
description: Utilize este guia de amostra para experimentar o modelo de predição de abandono transacional.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 19befa17524aba4543f0d8a5f5f7d6f5a88b2322f1264b88fa0b31641610592a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029459"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>Guia de amostra de predição de abandono transacional (pré-visualização)

Este guia irá guiá-lo através de um exemplo da predição de abandono transacional no Customer Insights, utilizando os dados fornecidos abaixo Todos os dados utilizados neste guia não são dados reais de clientes e fazem parte do conjunto de dados da Contoso encontrados no ambiente de *Demonstração* da sua Subscrição do Customer Insights.

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que vende através do seu site Contoso Coffee. O seu objetivo é saber quais os clientes que normalmente adquirem os seus produtos regularmente deixarão de ser clientes ativos nos próximos 60 dias. Saber qual dos seus clientes os pode **abandonar** pode ajudá-los a poupar esforços de marketing, concentrando-se em mantê-los.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.
- Recomendamos-lhe que implemente as seguintes etapas [num ambiente novo](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Rever os artigos [sobre ingestão de dados](data-sources.md) e [importar origens de dados utilizando conectores Power Query](connect-power-query.md) especificamente. A seguinte informação pressupõe que está familiarizado com a ingestão de dados em geral. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados de clientes a partir da plataforma eCommerce

1. Criar uma origem de dados com o nome **eCommerce**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**

1. Guardar a origem dos dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**. Escolha novamente o conetor **Texto/CSV**.

1. Introduza o URL para dados de **Compras online** https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda
   
1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommercePurchases**.

1. Guardar a origem dos dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados de clientes a partir do esquema de fidelidade

1. Criar uma origem de dados com o nome **LoyaltyScheme**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **loyCustomers**.

1. Guardar a origem dos dados.


## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Depois de ingerirmos os dados, iniciamos agora o processo **Mapear, Corresponder, Intercalar** para criar um perfil de cliente unificado. Para mais informações, consulte [Unificação de dados](data-unification.md).

### <a name="map"></a>Mapear

1. Depois de ingerir os dados, mapear os contactos desde os dados de eCommerce e Fidelidade até aos tipos de dados comuns. Aceder a **Dados** > **Unificar** > **Mapear**.

1. Selecionar as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar as origens de dados do comércio eletrónico e da fidelidade.":::

1. Selecionar **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificar LoyaltyId como a chave primária.":::

### <a name="match"></a>Corresponder

1. Aceda ao separador **Corresponder** e selecione **Definir encomenda**.

1. Na lista pendente **Primário**, escolha **eCommerceContacts : eCommerce** como a origem primária e inclua todos os registos.

1. Na lista pendente **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registos.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificar corresponder comércio eletrónico e fidelidade.":::

1. Selecione **Criar uma nova regra**

1. Adicione a sua primeira condição usando FullName.

   * Para eCommerceContacts, selecione **FullName** na lista pendente.
   * Para loyCustomers, selecione **FullName** na lista pendente.
   * Selecione a lista pendente **Normalizar** e escolha **Tipo (Telefone, Nome, Morada, ...)**.
   * Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.

1. Introduzir o nome **FullName, Email** para a nova regra.

   * Acrescentar uma segunda condição para o endereço de correio eletrónico, selecionando **Adicionar condição**
   * Para a entidade eCommerceContacts, escolha **E-mail** na lista pendente.
   * Para a entidade loyCustomers, escolha **E-mail** na lista pendente. 
   * Deixar em branco Normalizar. 
   * Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificar a regra de correspondência para nome e e-mail.":::

7. Selecione **Guardar** e **Executar**.

### <a name="merge"></a>Unir

1. Aceda ao separador **Intercalar**.

1. No **ContactId** para a entidade **loyCustomers**, alterar o nome a apresentar para **ContactIdLOYALTY** para o diferenciar das outras IDs ingeridas.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid a partir de loyalty id.":::

1. Selecione **Guardar** e **Executar** para iniciar o processo de intercalar.



## <a name="task-3---configure-transaction-churn-prediction"></a>Tarefa 3 - Configurar a predição de abandono da transação

Com os perfis unificados de clientes em vigor, podemos agora executar a predição de abandono da subscrição. Para passos detalhados, ver o artigo [Predição de abandono da subscrição (pré-visualização)](predict-subscription-churn.md). 

1. Vá a **Inteligência** > **Descobrir** e selecione para utilizar o **Modelo de abandono do cliente**.

1. Selecione a opção **Transacional** e selecione **Iniciar**.

1. Dê um nome ao modelo **Predição de abandono de transação por comércio eletrónico OOB** e a entidade de saída **OOBeCommerceChurnPrediction**.

1. Definir duas condições para o modelo de abandono:

   * **Janela de predição**: **pelo menos 60** dias. Esta definição estabelece até que ponto queremos prever o abandono dos clientes no futuro.

   * **Definição de abandono**: **pelo menos 60** dias. A duração sem compras após a qual um cliente é considerado em abandono.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecionar as alavancas do modelo Janela de Predição e Definição de Abandono.":::

1. Selecione **Histórico de Compras (obrigatório)** e selecione **Adicionar dados** para o histórico de compras.

1. Adicionar a entidade **eCommercePurchases : eCommerce** e mapear os campos desde o comércio eletrónico até aos campos correspondentes exigidos pelo modelo.

1. Junte a entidade **eCommercePurchases : eCommerce** com **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Junte-se às entidade de eCommerce.":::

1. Selecione **Seguinte** para definir o agendar do modelo.

   O modelo precisa de treinar regularmente para aprender novos padrões quando há novos dados ingeridos. Para este exemplo, selecione **Mensalmente**.

1. Depois de rever todos os detalhes, selecione **Guardar e Executar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Rever resultados do modelo e explicações

Deixe o modelo completar a formação e a pontuação dos dados. Pode agora rever as explicações do modelo de abandono da subscrição. Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 5 - Criar um segmento de clientes de alto risco de abandono

A execução do modelo de produção cria uma nova entidade que se pode ver em **Dados** > **Entidades**.   

Pode criar um novo segmento com base na entidade criada pelo modelo.

1.  Aceda a **Segmentos**. Selecione **Novo** e escolha **Criar a partir de** > **Inteligência**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Criar um segmento com a saída do modelo.":::

1. Selecione o ponto final **OOBSubscriptionChurnPrediction** e defina o segmento: 
   - Campo: ChurnScore
   - Operador: maior do que
   - Valor: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar um segmento de abandono de subscrição.":::

Tem agora um segmento dinamicamente atualizado que identifica clientes com alto risco de abandono para este negócio de subscrições.

Para obter mais informações, veja [Criar e gerir segmentos](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

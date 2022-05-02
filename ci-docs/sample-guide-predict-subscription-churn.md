---
title: Guia de predição de abandono da subscrição
description: Utilize este guia de amostra para experimentar o modelo de predição de abandono de subscrição.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2aea6c62421b308705899e4f8af64f64bfcb2d3d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647099"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guia de predição de abandono da subscrição

Iremos acompanhá-lo através de um exemplo de predição de abandono de subscrição usando os dados de amostra fornecidos abaixo. 

## <a name="scenario"></a>Cenário

Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que vendem através do seu site Contoso Coffee. Iniciaram recentemente um negócio de subscrições para que os seus clientes pudessem tomar café com regularidade. O seu objetivo é compreender, quais os clientes subscritores que poderão cancelar a sua subscrição nos próximos meses. Saber qual dos seus clientes os pode **abandonar** pode ajudá-los a poupar esforços de marketing, concentrando-se em mantê-los.

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

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**

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

### <a name="ingest-subscription-information"></a>Ingerir informações de subscrição

1. Criar uma origem de dados com o nome **SubscriptionHistory**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **SubscriptioID**: Número inteiro
   - **SubscriptionAmount**: Moeda
   - **SubscriptionEndDate**: Data/Hora
   - **SubscriptionStartDate**: Data/Hora
   - **TransactionDate**: Data/Hora
   - **IsRecurring**: Verdadeiro/Falso
   - **Is_auto_renew**: Verdadeiro/Falso
   - **RecurringFrequencyInMonths**: Número inteiro

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **SubscriptionHistory**.

1. Guardar a origem dos dados.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dados de clientes a partir de avaliações de websites

1. Criar uma origem de dados com o nome **Website**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasswebsite.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **ReviewRating**: Número inteiro
   - **ReviewDate**: Data

1. No campo "Nome" no painel da direita, altere o nome da sua origem de dados de **Consulta** para **webReview**.

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


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tarefa 3 - Configurar a predição de abandono da subscrição

Com os perfis unificados de clientes em vigor, podemos agora executar a predição de abandono da subscrição. Para obter passos detalhados, consulte o artigo [Predição de abandono de subscrições](predict-subscription-churn.md). 

1. Vá a **Inteligência** > **Descobrir** e selecione para utilizar o **Modelo de abandono do cliente**.

1. Selecione a opção **Subscrição** e selecione **Iniciar**.

1. Dê um nome ao modelo **Predição de abandono de subscrição OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.

1. Definir duas condições para o modelo de abandono:

   * **Dias desde o fim da subscrição**: **pelo menos 60** dias. Se um cliente não renovar a subscrição neste período após o fim da sua subscrição, considera-se um abandono. 

   * **Definição de abandono**: **pelo menos 93** dias. A duração que o modelo prevê quais os clientes que poderão abandonar. Quanto mais longe olhar no futuro, menos precisos serão os resultados.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecionar as alavancas do modelo Janela de Predição e Definição de Abandono.":::

1. Selecione **Adicionar dados necessários** e selecione **Adicionar dados** para o histórico de subscrições.

1. Adicionar a entidade **Subscrição : SubscriptionHistory** e mapear os campos desde o comércio eletrónico até aos campos correspondentes exigidos pelo modelo.

1. Junte-se à entidade **Subscrição: SubscriptionHistory** com **eCommerceContacts : eCommerce**, dê um nome à relação **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Junte-se às entidade de eCommerce.":::

1. Em Atividades de Cliente, adicionar a entidade **webReviews : Website** e mapear os campos desde webReviews até aos campos correspondentes exigidos pelo modelo. 
   - Chave primária: ReviewId
   - Carimbo de Data/Hora: ReviewDate
   - Evento: ReviewRating

1. Configurar uma atividade para avaliações de website. Selecione a atividade **Avaliar** e junte a entidade **webReviews : Website** com **eCommerceContacts : eCommerce**.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
---
title: Guia de predição de abandono da subscrição
description: Utilize este guia de amostra para experimentar o modelo de predição de abandono de subscrição.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610020"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guia de predição de abandono da subscrição

Este guia irá guiá-lo através de um exemplo de ponto a ponto da predição de abandono de subscrições utilizando dados de amostra. Recomendamos-lhe que esta predição [num ambiente novo](manage-environments.md).

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz máquinas de café, bem como café de alta qualidade. Vendem os produtos através do seu site Contoso Coffee. Iniciaram recentemente um negócio de subscrições para que os seus clientes pudessem tomar café com regularidade. O seu objetivo é compreender, quais os clientes subscritores que poderão cancelar a sua subscrição nos próximos meses. Saber quais dos seus clientes é **provável que abandonem**, pode ajudá-los a poupar esforços de marketing, concentrando-se em mantê-los.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Reveja os artigos [sobre a ingestão de dados](data-sources.md) e [ligar a uma origem de dados do Power Query](connect-power-query.md). As seguintes informações pressupõem que está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados de clientes a partir da plataforma eCommerce

1. Crie uma origem de dados do Power Query com o nome **eCommerce** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados para **eCommerceContacts**

1. Guardar a origem dos dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados de clientes a partir do esquema de fidelidade

1. Crie uma origem de dados com o nome **LoyaltyScheme** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para clientes fidelizados https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados para **loyCustomers**.

1. Guardar a origem dos dados.

### <a name="ingest-subscription-information"></a>Ingerir informações de subscrição

1. Crie uma origem de dados com o nome **SubscriptionHistory** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para subscrições https://aka.ms/ciadchurnsubscriptionhistory.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **SubscriptioID**: Número inteiro
   - **SubscriptionAmount**: Moeda
   - **SubscriptionEndDate**: Data/Hora
   - **SubscriptionStartDate**: Data/Hora
   - **TransactionDate**: Data/Hora
   - **IsRecurring**: Verdadeiro/Falso
   - **Is_auto_renew**: Verdadeiro/Falso
   - **RecurringFrequencyInMonths**: Número inteiro

1. No campo **Nome** no painel direito, mude o nome da sua origem de dados para **SubscriptionHistory**.

1. Guardar a origem dos dados.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dados de clientes a partir de avaliações de websites

1. Crie uma origem de dados com o nome **Website** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para as críticas ao site https://aka.ms/ciadclasswebsite.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **ReviewRating**: Número inteiro
   - **ReviewDate**: Data

1. No campo **Nome** no painel direito, mude o nome da sua origem de dados para **webReviews**.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Reveja o artigo [sobre unificação de dados](data-unification.md). As seguintes informações pressupõem que está familiarizado com a unificação de dados em geral.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tarefa 3 – Criar atividade do histórico de transações

Reveja o artigo [sobre atividades do cliente](activities.md). As seguintes informações pressupõem que está familiarizado com a criação de atividades em geral.

1. Crie uma atividade denominada **SubscriptionHistory** com a entidade *Subscription* e a respetiva chave primária, **CustomerId**.

1. Crie uma relação entre *SubscriptionHistory:Subscription* e *eCommerceContacts:eCommerce* com o **CustomerID** como a chave externa para ligar as duas entidades.

1. Selecione **SubscriptionType** para **EventActivity** e **SubscriptionEndDate** para **TimeStamp**.

1. Selecione **Subscrição** para o **Tipo de Atividade** e mapeie semanticamente os dados de atividade.

1. Execute a atividade.

1. Adicione outra atividade e mapeie os respetivos nomes dos campos para os campos correspondentes:
   - Entidade de atividade do cliente: Reviews:Website
   - Chave primária: Website.Reviews.ReviewId
   - Carimbo de data/hora: Website.Reviews.ReviewDate
   - Evento (nome da atividade): Website.Reviews.ActivityTypeDisplay
   - Detalhes (montante ou valor): Website.Reviews.ReviewRating

1. Execute a atividade.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tarefa 4 - Configurar a predição de abandono da subscrição

Com os perfis unificados de clientes em vigor e a atividade criada, podemos agora executar a predição de abandono de subscrições. Para obter passos detalhados, consulte [Predição de abandono de subscrições](predict-subscription-churn.md).

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** no mosaico **Modelo de abandono de clientes**.

1. Selecione **Subscrição** para o tipo de abandono e, em seguida, **Começar**.

1. Dê um nome ao modelo **Predição de abandono de subscrição OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.

1. Definir preferências de modelo:
   - **Dias desde que a subscrição terminou**: **60** dias para indicar que um cliente é considerado como abandonado se não renovar a subscrição neste período após a subscrição ter terminado.
   - **Dias para olhar no futuro para prever o abandono**: **93** dias, que é a duração que o modelo prevê que clientes possam abandonar. Quanto mais longe olhar no futuro, menos precisos serão os resultados.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecionar as preferências do modelo e a definição de abandono.":::

1. Selecione **Seguinte**.

1. No passo **Dados Exigidos**, selecione **Adicionar dados** para fornecer o histórico de subscrições.

1. Selecione **Subscrição** e a entidade SubscriptionHistory e selecione **Seguinte**. Os dados obrigatórios são preenchidos automaticamente a partir da atividade. Selecione **Guardar**.

1. Sob Atividades do Cliente, selecione **Adicionar dados**.

1. Para este exemplo, adicione a atividade de revisão Web.

1. Selecione **Seguinte**.

1. No passo **Atualizações de dados**, selecione **Mensal** para a agenda do modelo.

1. Depois de rever todos os detalhes, selecione **Guardar e Executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5 - Rever resultados do modelo e explicações

Deixe o modelo completar a formação e a pontuação dos dados. Reveja as explicações do modelo de abandono de subscrições. Para obter mais informações, consulte [Ver resultados de predição](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 6 - Criar um segmento de clientes de alto risco de abandono

A execução do modelo cria uma nova entidade, que é listada em **Dados** > **Entidades**. Pode criar um novo segmento com base na entidade criada pelo modelo.

1. Na página de resultados, selecione **Criar segmento**.

1. Crie uma regra utilizando a entidade **OOBSubscriptionChurnPrediction** e defina o segmento:
   - **Campo**: ChurnScore
   - **Operador**: maior do que
   - **Valor**: 0,6

1. Selecione **Guardar** e **Execute** o segmento.

Tem agora um segmento dinamicamente atualizado que identifica clientes com alto risco de abandono para este negócio de subscrições. Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

> [!TIP]
> Também pode criar um segmento para um modelo de predição a partir da página **Segmentos** selecionando **Novo** e escolhendo **Criar a partir** > **Inteligência**. Para mais informações, consulte [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

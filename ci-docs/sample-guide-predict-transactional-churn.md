---
title: Guia de predição de abandono transacional
description: Utilize este guia de amostra para experimentar o modelo de predição de abandono transacional.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741333"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guia de predição de abandono transacional

Este guia irá guiá-lo através de um exemplo da predição de abandono transacional no Customer Insights, utilizando os dados fornecidos abaixo Todos os dados utilizados neste guia não são dados reais do cliente e fazem parte do conjunto de dados Contoso que se encontram no ambiente de *Demonstração* na sua subscrição do Customer Insights.

## <a name="scenario"></a>Cenário

Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que vendem através do seu site Contoso Coffee. O seu objetivo é saber quais os clientes que normalmente adquirem os seus produtos regularmente deixarão de ser clientes ativos nos próximos 60 dias. Saber qual dos seus clientes os pode **abandonar** pode ajudá-los a poupar esforços de marketing, concentrando-se em mantê-los.

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

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Tarefa 3 - Configurar a predição de abandono da transação

Com os unified customer profiles criados, podemos agora executar a previsão de abandono da transação. Para obter passos detalhados, consulte o artigo [Previsão de abandono de transações](predict-transactional-churn.md). 

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

Deixe o modelo completar a formação e a pontuação dos dados. Pode agora rever as explicações do modelo de abandono. Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 5 - Criar um segmento de clientes de alto risco de abandono

A execução do modelo de produção cria uma nova entidade que se pode ver em **Dados** > **Entidades**.   

Pode criar um novo segmento com base na entidade criada pelo modelo.

1.  Aceda a **Segmentos**. Selecione **Novo** e escolha **Criar a partir de** > **Inteligência**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Criar um segmento com a saída do modelo.":::

1. Selecione o ponto final **OOBeCommerceChurnPrediction** e defina o segmento: 
   - Campo: ChurnScore
   - Operador: maior do que
   - Valor: 0,6

Agora, tem um segmento atualizado dinamicamente que identifica clientes com elevado risco de abandono.

Para obter mais informações, veja [Criar e gerir segmentos](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]

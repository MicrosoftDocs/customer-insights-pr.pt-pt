---
title: Guia de predição de abandono transacional
description: Utilize este guia de amostra para experimentar o modelo de predição de abandono transacional.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609698"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guia de predição de abandono transacional

Este guia irá guiá-lo através de um exemplo de ponto a ponto da predição de abandono transacional utilizando dados de amostra. Recomendamos-lhe que esta predição [num ambiente novo](manage-environments.md).

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz máquinas de café, bem como café de alta qualidade. Vendem os produtos através do seu site Contoso Coffee. O seu objetivo é saber quais os clientes que normalmente adquirem os seus produtos regularmente deixarão de ser clientes ativos nos próximos 60 dias. Saber qual dos seus clientes os pode **abandonar** pode ajudá-los a poupar esforços de marketing, concentrando-se em mantê-los.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões do contribuinte](permissions.md).

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Reveja os artigos [sobre a ingestão de dados](data-sources.md) e [ligar a uma origem de dados do Power Query](connect-power-query.md). As seguintes informações pressupõem que está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados de clientes a partir da plataforma eCommerce

1. Crie uma origem de dados com o nome **eCommerce** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados para **eCommerceContacts**

1. Guardar a origem dos dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**. Escolha novamente o conetor **Texto/CSV**.

1. Introduza o URL para dados de compras online https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados para **eCommercePurchases**.

1. Guardar a origem dos dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados de clientes a partir do esquema de fidelidade

1. Crie uma origem de dados com o nome **LoyaltyScheme** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel da direita, altere o nome da sua origem de dados para **loyCustomers**.

1. Guardar a origem dos dados.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Tarefa 4 - Configurar a predição de abandono da transação

Com os perfis unificados de cliente criados e a atividade, podemos executar a predição de abandono de transações.

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** em **Modelo de abandono de clientes**.

1. Selecione **Transacional** para o tipo de abandono e, em seguida, **Começar**.

1. Dê um nome ao modelo **Predição de abandono de transação por comércio eletrónico OOB** e a entidade de saída **OOBeCommerceChurnPrediction**.

1. Selecione **Seguinte**.

1. Definir preferências de modelo:

   - **Janela de predição**: **60** dias para definir até que ponto queremos prever o abandono dos clientes no futuro.

   - **Definição de abandono**: **60** dias para indicar a duração sem compras após a qual um cliente é considerado em abandono.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecionar as preferências do modelo Janela de Predição e Definição de Abandono.":::

1. Selecione **Seguinte**.

1. Selecione **Histórico de Compras (obrigatório)** e selecione **Adicionar dados** para o histórico de compras.

1. Selecione **SalesOrderLine** e a entidade eCommercePurchases e selecione **Seguinte**. Os dados obrigatórios são preenchidos automaticamente a partir da atividade. Selecione **Guardar** e, em seguida, **Seguinte**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Junte-se às entidade de eCommerce.":::

1. Ignore o passo **Dados adicionais (opcional)**.

1. No passo **Atualizações de dados**, selecione **Mensal** para a agenda do modelo.

1. Depois de rever todos os detalhes, selecione **Guardar e Executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5 - Rever resultados do modelo e explicações

Deixe o modelo completar a formação e a pontuação dos dados. Reveja as explicações do modelo de abandono. Para obter mais informações, consulte [Ver resultados de predição](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 6 - Criar um segmento de clientes de alto risco de abandono

A execução do modelo de produção cria uma nova entidade, que é listada em **Dados** > **Entidades**. Pode criar um novo segmento com base na entidade criada pelo modelo.

1. Na página de resultados, selecione **Criar segmento**.

1. Crie uma regra utilizando a entidade **OOBeCommerceChurnPrediction** e defina o segmento:
   - **Campo**: ChurnScore
   - **Operador**: maior do que
   - **Valor**: 0,6

1. Selecione **Guardar** e **Execute** o segmento.

Agora, tem um segmento atualizado dinamicamente que identifica clientes com elevado risco de abandono. Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

> [!TIP]
> Também pode criar um segmento para um modelo de predição a partir da página **Segmentos** selecionando **Novo** e escolhendo **Criar a partir** > **Inteligência**. Para mais informações, consulte [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

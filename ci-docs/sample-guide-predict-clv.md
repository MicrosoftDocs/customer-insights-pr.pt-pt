---
title: Guia de exemplo de predição de valor vitalício do cliente (CLV)
description: Utilize este guia de exemplo para experimentar o modelo de predição de valor vitalício do cliente.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609652"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guia de exemplo de predição de valor vitalício do cliente (CLV)

Este guia orienta-o através de exemplo de ponto a ponto da predição de Valor vitalício do cliente (CLV) no Customer Insights utilizando dados de amostra. Recomendamos-lhe que esta predição [num ambiente novo](manage-environments.md).

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz máquinas de café, bem como café de alta qualidade. Vendem os produtos através do seu site Contoso Coffee. A empresa quer entender o valor (receita) que os seus clientes podem gerar nos próximos 12 meses. Conhecer o valor esperado dos seus clientes nos próximos 12 meses irá ajudá-los a orientar os seus esforços de marketing para clientes de valor elevado.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões do contribuinte](permissions.md).

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

1. **Guardar** a origem dos dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**. Escolha novamente o conetor **Texto/CSV**.

1. Introduza o URL para dados de **Compras online** https://aka.ms/ciadclassonline.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dados de clientes a partir de avaliações de websites

1. Crie uma origem de dados com o nome **Website** e selecione o conetor **Texto/CSV**.

1. Introduza o URL para as críticas ao site https://aka.ms/CI-ILT/WebReviews.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **ReviewRating**: número Decimal
   - **ReviewDate**: Data

1. No campo **Nome** no painel direito, mude o nome da sua origem de dados para **Críticas**.

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

1. Adicione outra atividade e mapeie os respetivos nomes dos campos para os campos correspondentes:
   - **Entidade de atividade**: Reviews:Website
   - **Chave primária**: ReviewId
   - **Carimbo de data/hora**: ReviewDate
   - **Atividade de evento**: ActivityTypeDisplay
   - **Detalhe adicional**: ReviewRating
   - **Tipo de atividade**: Review

1. Execute a atividade.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tarefa 4 – Configurar a predição de valor vitalício do cliente

Com os perfis de clientes unificados em vigor e a atividade criada, execute a predição de valor vitalício do cliente (CLV). Para passos detalhados, consulte [predição do Valor Vitalício do Cliente](predict-customer-lifetime-value.md).

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** no mosaico **Valor vitalício do cliente**.

1. Selecione **Introdução**.

1. Nomeie o modelo **Predição de CLV de eCommerce OOB** e a entidade de saída  **OOBeCommerceCLVPrediction**.

1. Definir preferências de modelo:
   - **Período de tempo da predição**: **12 meses ou 1 ano** para definir até onde pretende prever o CLV.
   - **Clientes ativos**: **Permite que o modelo calcule o intervalo de compras**, o qual é intervalo de tempo em que um cliente deve ter tido pelo menos uma transação a considerar ativa.
   - **Clientes de alto valor**: defina manualmente clientes de alto valor como **principais 30% de clientes ativos**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Passo de preferências na experiência guiada para o modelo CLV.":::

1. Selecione **Seguinte**.

1. No passo **Dados Exigidos**, selecione **Adicionar dados** para fornecer os dados do histórico de transações.

    :::image type="content" source="media/clv-model-required.png" alt-text="Adicionar passo de dados obrigatórios na experiência guiada para o modelo CLV.":::

1. Selecione **SalesOrderLine** e a entidade eCommercePurchases e selecione **Seguinte**. Os dados obrigatórios são preenchidos automaticamente a partir da atividade. Selecione **Guardar** e, em seguida, **Seguinte**.

1. O passo **Dados adicionais (opcional)** permite-lhe adicionar mais dados de atividade do cliente para obter mais informações para interações com o cliente. Para este exemplo, selecione **Adicionar dados** e adicione a atividade de revisão Web.

1. Selecione **Seguinte**.

1. No passo **Atualizações de dados**, selecione **Mensal** para a agenda do modelo.

1. Selecione **Seguinte**.

1. Depois de rever todos os detalhes, selecione **Guardar e Executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5 - Rever resultados do modelo e explicações

Deixe o modelo completar a formação e a pontuação dos dados. Reveja as [resultados do modelo e explicações do CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tarefa 6 – Criar um segmento de clientes de valor elevado

A execução do modelo cria uma nova entidade, que é listada em **Dados** > **Entidades**. Pode criar um novo segmento de cliente baseado na entidade criada pelo modelo.

1. Na página de resultados, selecione **Criar segmento**.

1. Crie uma regra utilizando a entidade **OOBeCommerceCLVPrediction** e defina o segmento:
   - **Campo**: CLVScore
   - **Operador**: maior do que
   - **Valor**: 1500

1. Selecione **Guardar** e **Execute** o segmento.

Tem agora um segmento que identifica clientes que se prevê gerarem mais de 1500$ de receitas nos próximos 12 meses. Este segmento é atualizado dinamicamente se mais dados forem ingeridos. Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

> [!TIP]
> Também pode criar um segmento para um modelo de predição a partir da página **Segmentos** selecionando **Novo** e escolhendo **Criar a partir** > **Inteligência**. Para mais informações, consulte [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

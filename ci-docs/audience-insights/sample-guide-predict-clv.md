---
title: Guia de exemplo de predição de valor vitalício do cliente
description: Utilize este guia de exemplo para experimentar o modelo de predição de valor vitalício do cliente.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 705e159f348e876f8a2a0ad3481608c6dd380df3dd74d7e5dba9dd3bebe25e52
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029505"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guia de exemplo de predição de valor vitalício do cliente (CLV)

Este guia irá orientá-lo através de exemplo de ponta a ponta da Predição de valor vitalício do cliente (CLV) no Customer Insights utilizando dados de exemplo.

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade. Vendem os produtos através do seu site Contoso Coffee. A empresa quer entender o valor (receita) que os seus clientes podem gerar nos próximos 12 meses. Conhecer o valor esperado dos seus clientes nos próximos 12 meses irá ajudá-los a orientar os seus esforços de marketing para clientes de valor elevado.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuidor](permissions.md) em informações de audiência.
- Recomendamos-lhe que implemente as seguintes etapas [num ambiente novo](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Reveja os artigos [sobre a ingestão de dados](data-sources.md) e a [importar origens de dados utilizando conectores do Power Query](connect-power-query.md). A seguinte informação pressupõe que está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados de clientes a partir da plataforma eCommerce

1. Criar uma origem de dados com o nome **eCommerce**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo "Nome" no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**

1. **Guardar** a origem dos dados.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dados de clientes a partir de avaliações de websites

1. Criar uma origem de dados com o nome **Website**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.

1. Introduza o URL para contactos de eCommerce https://aka.ms/CI-ILT/WebReviews.

1. Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.

1. Atualizar o tipo de dados para as colunas listadas abaixo:

   - **ReviewRating**: número Decimal
   - **ReviewDate**: Data

1. No campo "Nome" no painel direito, mude o nome da sua origem de dados de **Consulta** para **Revisão**.

1. **Guardar** a origem dos dados.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Depois de ingerir os dados, iniciamos agora o processo de unificação de dados para criar um perfil de cliente unificado. Para mais informações, consulte [Unificação de dados](data-unification.md).

### <a name="map"></a>Mapear

1. Depois de ingerir os dados, mapear os contactos desde os dados de eCommerce e Fidelidade até aos tipos de dados comuns. Aceder a **Dados** > **Unificar** > **Mapear**.

1. Selecionar as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**. Em seguida, selecione **Aplicar**.

   ![unificar as origens de dados do comércio eletrónico e da fidelidade.](media/unify-ecommerce-loyalty.png)

1. Selecionar **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.

   ![Unificar LoyaltyId como a chave primária.](media/unify-loyaltyid.png)

1. Selecione **Guardar**.

### <a name="match"></a>Corresponder

1. Aceda ao separador **Corresponder** e selecione **Definir encomenda**.

1. Na lista pendente **Primário**, escolha **eCommerceContacts : eCommerce** como a origem primária e inclua todos os registos.

1. Na lista pendente **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registos.

   ![Unificar corresponder comércio eletrónico e fidelidade.](media/unify-match-order.png)

1. Selecione **Adicionar regra**

1. Adicione a sua primeira condição usando FullName.

   - Para eCommerceContacts, selecione **FullName** na lista pendente.
   - Para loyCustomers, selecione **FullName** na lista pendente.
   - Selecione a lista pendente **Normalizar** e escolha **Tipo (Telefone, Nome, Endereço, ...)**.
   - Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.

1. Introduzir o nome **FullName, Email** para a nova regra.

   - Acrescentar uma segunda condição para o endereço de correio eletrónico, selecionando **Adicionar condição**
   - Para a entidade eCommerceContacts, escolha **E-mail** na lista pendente.
   - Para a entidade loyCustomers, escolha **E-mail** na lista pendente.
   - Deixar em branco Normalizar.
   - Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.

   ![Unificar a regra de correspondência para nome e e-mail.](media/unify-match-rule.png)

1. Selecione **Concluído**.

1. Selecione **Guardar** e **Executar**.

### <a name="merge"></a>Intercalar

1. Aceda ao separador **Intercalar**.

1. No **ContactId** para a entidade **loyCustomers**, alterar o nome a apresentar para **ContactIdLOYALTY** para o diferenciar das outras IDs ingeridas.

   ![renomear contactid a partir de loyalty id.](media/unify-merge-contactid.png)

1. Selecione **Guardar** e **Executar processos de união e a jusante**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tarefa 3 – Configurar a predição de valor vitalício do cliente

Com os perfis de clientes unificados no lugar, podemos agora executar a predição de valor vitalício do cliente. Para passos detalhados, consulte [Predição de Valor Vitalício do Cliente (pré-visualização)](predict-customer-lifetime-value.md).

1. Aceda a **Inteligência**  > **Predições** e selecione o **Modelo de valor vitalício do cliente**.

1. Veja as informações no painel lateral e selecione **Começar**.

1. Nomeie o modelo **Predição de CLV de eCommerce OOB** e a entidade de saída **OOBeCommerceCLVPrediction**.

1. Defina preferências de modelo para o modelo CLV:
   - **Período de tempo da predição**: **12 meses ou 1 ano**. Esta definição define até onde no futuro pretende prever o valor vitalício do cliente.
   - **Clientes ativos**: especifique o que clientes ativos significam para o seu negócio. Defina o intervalo de tempo histórico em que um cliente tem de ter tido, pelo menos, uma transação para ser considerado ativo. O modelo apenas irá prever o CLV para clientes ativos. Escolha entre deixar o modelo calcular o período de tempo com base em dados de transações históricos ou fornecer um intervalo de tempo específico. Neste guia de exemplo, **deixámos o modelo calcular o intervalo de compra**, que é a opção predefinida.
   - **Clientes de valor elevado**: defina clientes de valor elevado como um percentil de clientes que mais pagam. O modelo utiliza esta entrada para fornecer resultados que se adequam à sua definição de negócio de clientes de valor elevado. Pode escolher deixar o modelo definir os clientes de valor elevado. Utiliza uma regra heurística que deriva o percentil. Também pode definir clientes de valor elevado como um percentil de clientes que mais pagam futuros. Neste guia de exemplo, definimos manualmente clientes de valor elevado como **30%** dos clientes que pagam ativos e selecionamos **Seguinte**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Passo de preferências na experiência guiada para o modelo CLV.":::

1. No passo **Dados Exigidos**, selecione **Adicionar dados** para fornecer os dados do histórico de transações.

1. Adicione e entidade **eCommercePurchases : eCommerce** e mapeie os atributos que são exigidos pelo modelo:
   - ID da Transação: eCommerce.eCommercePurchases.PurchaseId
   - Data da transação: eCommerce.eCommercePurchases.PurchasedOn
   - Montante da transação: eCommerce.eCommercePurchases.TotalPrice
   - ID do Produto: eCommerce.eCommercePurchases.ProductId

1. Selecione **Seguinte**.

1. Configure a relação entre a entidade **eCommercePurchases : eCommerce** e **eCommerceContacts : eCommerce**.

1. O passo **Dados adicionais (opcional)** permite-lhe adicionar mais dados de atividade do cliente. Estes dados podem ajudar a obter mais informações sobre as interações do cliente com o seu negócio, o que pode contribuir para o CLV. Adicionar interações chave do cliente, como o histórico de registos Web, registos de suporte ao cliente ou recompensas do programa pode melhorar a precisão das predições. Selecione **Adicionar dados** para incluir mais dados de atividade do cliente.

1. Adicione a entidade de atividade do cliente e mapeie os respetivos nomes dos campos para os campos correspondentes exigidos pelo modelo:
   - Entidade de atividade do cliente: Reviews:Website
   - Chave primária: Website.Reviews.ReviewId
   - Carimbo de data/hora: Website.Reviews.ReviewDate
   - Evento (nome da atividade): Website.Reviews.ActivityTypeDisplay
   - Detalhes (montante ou valor): Website.Reviews.ReviewRating

1. Selecione **Seguinte** e configure a atividade e a relação entre os dados de transação e os dados do cliente:  
   - Tipo de atividade: escolha um existente
   - Etiqueta de atividade: Review
   - Etiqueta correspondente: Website.Reviews.UserId
   - Entidade de cliente: eCommerceContacts:eCommerce
   - Relação: WebsiteReviews

1. Selecione **Seguinte** para definir o agendar do modelo.

   O modelo precisa de treinar regularmente para aprender novos padrões quando há novos dados ingeridos. Para este exemplo, escolha **Mensalmente**.

1. Depois de rever todos os detalhes, selecione **Guardar e Executar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Rever resultados do modelo e explicações

Deixe o modelo completar a formação e a pontuação dos dados. Em seguida, pode rever os resultados e explicações do modelo CLV. Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tarefa 5 – Criar um segmento de clientes de valor elevado

A execução do modelo cria uma nova entidade, que é listada em **Dados** > **Entidades**. Pode criar um novo segmento de cliente baseado na entidade criada pelo modelo.

1. Aceda a **Segmentos**. 

1. Selecione **Novo** e escolha **Criar a partir de** > **Inteligência**.

   ![Criar um segmento com a saída do modelo.](media/segment-intelligence.png)

1. Selecione a entidade **OOBeCommerceCLVPrediction** e defina o segmento:
  - Campo: CLVScore
  - Operador: maior do que
  - Valor: 1500

1. Selecione **Rever** e **Guarde** o segmento.

Tem agora um segmento que identifica clientes que se prevê gerarem mais de 1500$ de receitas nos próximos 12 meses. Este segmento é atualizado dinamicamente se mais dados forem ingeridos.

Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

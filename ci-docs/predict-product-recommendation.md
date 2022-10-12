---
title: Prever recomendações de produtos
description: Preveja que produtos um cliente é provável que compre ou com os quais interaja.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610296"
---
# <a name="predict-product-recommendations"></a>Prever recomendações de produtos

O modelo de recomendação de produtos cria conjuntos de recomendações de produtos preditivas. As recomendações baseiam-se em comportamentos de compra anteriores e clientes com padrões de compra semelhantes. Este modelo destina-se a consumidores individuais (B-para-C).

Tem de ter conhecimento do negócio sobre os diferentes tipos de produtos para o seu negócio e como os seus clientes interagem com eles. Suportamos a recomendação de produtos que tenham sido previamente comprados pelos seus clientes ou recomendações para novos produtos.

As recomendações de produto podem estar sujeitas às leis e regulamentos locais e às expetativas dos clientes, o que o modelo não foi criado para ter especificamente em conta. Portanto, **tem de rever as recomendações antes de as entregar aos seus clientes** para garantir que está em conformidade com quaisquer leis ou regulamentos aplicáveis e expetativas de clientes para o que possa recomendar.

A saída deste modelo fornece recomendações com base no ID do produto. O seu mecanismo de entrega tem de mapear os IDs de produto previstos para o conteúdo apropriado para que os seus clientes tenham em conta a localização, conteúdo de imagem e outros conteúdos ou comportamentos específicos do negócio.

> [!TIP]
> Experimente a predição de produtos recomendados utilizando dados de amostra: [Guia de amostra de predição de recomendações de produtos](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [permissões de Contribuidor](permissions.md)
- Pelo menos, 100 clientes, de preferência mais de 10.000 clientes.
- Identificador de Cliente: um identificador exclusivo para combinar transações com um cliente individual
- Pelo menos, um ano de dados transacionais, de preferência de dois a três anos para incluir alguma sazonalidade. Idealmente, pelo menos, três ou mais transações por ID de Cliente. O histórico de transações tem de incluir:
  - **ID da Transação**: identificador exclusivo de uma compra ou transação.
  - **Data da transação**: data da compra ou transação.
  - **Valor da transação:** valor numérico da compra ou transação.
  - **ID exclusivo do produto:**: ID do produto ou serviço comprado se os seus dados estiverem a um nível de item de linha.
  - **Compra ou devolução**: um campo booleano true/false onde *true* identifica que uma transação foi uma devolução. Se os dados de Compra ou Devolução não forem fornecidos no modelo e o **Valor da transação** for negativo, inferimos uma devolução.
- Uma entidade de dados do catálogo de produtos a utilizar como um filtro de produto.

> [!NOTE]
> - O modelo necessita do histórico de transações dos clientes, em que a transação é quaisquer dados que descrevam uma interação utilizador-produto. Por exemplo, comprar um produto, ter uma aula ou assistir a um evento.
> - Apenas uma entidade de histórico de transações pode ser configurada. Se existirem várias entidades de compra, combine-as no Power Query antes da ingestão de dados.
> - Se a encomenda e os detalhes da encomenda forem entidades diferentes, una-as antes de usar no modelo. O modelo não funciona apenas com um ID de encomenda ou ID de recibo numa entidade.

## <a name="create-a-product-recommendation-prediction"></a>Criar uma predição de recomendação de produtos

Selecione **Guardar rascunho** a qualquer momento para guardar a predição como rascunho. A predição de rascunho é apresentada no separador **A minhas predições**.

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** no mosaico **Recomendações de produtos (pré-visualização)**.

1. Selecione **Introdução**.

1. **Nomeie este modelo** e o **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Seguinte**.

### <a name="define-product-recommendation-preferences"></a>Definir as preferências de recomendações de produtos

1. Defina o **Número de produtos** a recomendar a um cliente. Este valor depende de como o seu método de entrega preenche os dados.

1. Escolha se pretende incluir produtos que os clientes compraram anteriormente no campo **Compras repetidas esperadas**.

1. Defina **Janela Relembrar** com o período de tempo que o modelo considera antes de recomendar o produto ao utilizador novamente. Por exemplo, indica que um cliente compra um portátil de dois em dois anos. O modelo olha para o histórico de compras dos últimos dois anos e, se encontrar um item, o item é filtrado das recomendações.

1. Selecione **Seguinte**

### <a name="add-purchase-history"></a>Adicionar histórico de compras

1. Selecione **Adicionar dados** para **Histórico de transações do cliente**.

1. Selecione o tipo de atividade semântica **SalesOrderLine** que contém as informações de histórico de transações ou de compra necessárias. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos de atividade foram mapeados semanticamente quando a atividade foi criada, escolha os atributos ou a entidade específicos em que gostaria que o cálculo se focasse. Se o mapeamento semântico não ocorrer, selecione **Editar** e mapeie os dados.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Painel lateral a mostrar a escolha de atividades específicas sob o tipo semântico.":::

1. Selecione **Seguinte** e reveja os atributos necessários para este modelo.

1. Selecione **Guardar**.

1. Selecione **Seguinte**.

### <a name="add-product-information-and-filters"></a>Adicionar informações de produtos e filtros

Por vezes, apenas determinados produtos são benéficos ou adequados para o tipo de predição que cria. Utilize filtros de produtos para identificar um subconjunto de produtos com características específicas a recomendar aos seus clientes. O modelo utilizará todos os produtos disponíveis para aprender padrões, mas utilizará apenas os produtos correspondentes ao filtro do produto na sua saída.

1. Adicione a entidade do catálogo de produtos que contém as informações para cada produto. Mapeie as informações necessárias e selecione **Guardar**.

1. Selecione **Seguinte**.

1. Selecione **Filtros de produto**:

   - **Sem filtros**: utilize todos os produtos na predição de recomendação de produtos.

   - **Definir filtros específicos de produtos**: utilize produtos específicos na predição de recomendação de produtos. No painel **Atributos do catálogo de produtos**, selecione os atributos da entidade do catálogo de produtos que pretende incluir no filtro.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Painel lateral a mostrar atribuído na entidade do catálogo de produtos para selecionar para filtros de produtos.":::

1. Escolha se deseja que o filtro de produtos use conectores **and** ou **or** para combinar logicamente a sua seleção de atributos do catálogo de produtos.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Configuração de exemplo de filtros de produtos combinada com conectores lógicos AND.":::

1. Selecione **Seguinte**.

### <a name="set-update-schedule"></a>Definir agenda de atualização

1. Escolha uma frequência para reeducar o modelo. Esta definição é importante para atualizar a precisão das previsões à medida que novos dados são ingeridos para o Customer Insights. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Rever e executar a configuração do modelo

O passo **Rever e executar** mostra um resumo da configuração e fornece uma oportunidade de efetuar alterações antes de criar a predição.

1. Selecione **Editar** em qualquer um dos passos para rever e efetuar quaisquer alterações.

1. Se estiver satisfeito com as suas seleções, selecione **Guardar e executar** para começar a executar o modelo. Selecionar **Concluído**. O separador **As minhas predições** é apresentado enquanto a predição está a ser criada. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver resultados da predição

1. Aceda a **Inteligência** > **Predições**.

1. No separador **As minhas predições**, selecione a predição que pretende ver.

Existem cinco secções primárias de dados dentro da página de resultados.

- **Desempenho do modelo:** as notas A, B e C indicam o desempenho da predição e podem ajudá-lo a tomar a decisão de utilizar os resultados armazenados na entidade de saída.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Imagem do resultado do desempenho do modelo com a nota A.":::

  Os níveis são determinados com base nas seguintes regras:
  - **A** quando a métrica "Êxito @ K" é, pelo menos, 10% maior que a linha de base.
  - **B** quando a métrica "Êxito @ K" é de 0% a 10% maior que a linha de base.
  - **C** quando a métrica "Êxito @ K" é menor que a linha de base.
  - **Linha de base**: os produtos mais recomendados pela contagem de compras entre todos os clientes + as regras aprendidas identificadas pelo modelo = um conjunto de recomendações para os clientes. As predições são então comparadas com os produtos principais, como calculado pelo número de clientes que tinham comprado o produto. Se um cliente tiver, pelo menos, um produto nos seus produtos recomendados que também foi visto nos principais produtos comprados, são considerados uma parte da linha de base. Por exemplo, se 10 destes clientes tivessem um produto recomendado comprado de 100 clientes totais, a linha de base seria 10%.
  - **Êxito @ K**: são criadas recomendações para todos os clientes e comparadas com o conjunto de validação do período de tempo de transações. Por exemplo, num período de 12 meses, o mês 12 é reservado como um conjunto de validação de dados. Se o modelo prevê, pelo menos, uma coisa que compraria no mês 12 com base no que aprendeu com os 11 meses anteriores, o cliente aumentaria a métrica "Sucesso @ K".

- **Produtos mais sugeridos (com contagem):** os cinco principais produtos que foram previstos para os seus clientes.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafo que mostra os principais 5 produtos mais recomendados.":::

- **Principais fatores de recomendação:** o modelo utiliza o histórico de transações dos clientes para fazer recomendações de produtos. Aprende padrões com base em compras anteriores e encontra semelhanças entre clientes e produtos. Estas semelhanças são então utilizadas para gerar recomendações de produtos.
  Os fatores que se seguem podem influenciar uma recomendação de produtos gerada pelo modelo.
  - **Transações anteriores**: um produto recomendado baseou-se em padrões de compra anteriores. Por exemplo, o modelo pode recomendar um *Surface Arc Mouse* se alguém comprou recentemente um *Surface Book 3* e uma *Caneta para Surface*. O modelo aprendeu que, historicamente, muitos clientes tinham comprado um *Surface Arc Mouse* depois de comprarem um *Surface Book 3* e uma *Caneta para Surface*.
  - **Semelhança de clientes**: um produto recomendado foi historicamente comprado por outros clientes que apresentam padrões de compra semelhantes. Por exemplo, John foi recomendado o *Auscultadores Surface 2* porque Lara e Brad compraram recentemente *Auscultadores Surface 2*. O modelo acredita que John é semelhante a Lara e a Brad porque historicamente têm padrões de compra semelhantes.
  - **Semelhança de produtos**: um produto recomendado é semelhante a outros produtos que o cliente comprou anteriormente. O modelo considera que dois produtos são semelhantes se forem comprados juntos ou por clientes semelhantes. Por exemplo, alguém obtém uma recomendação para uma *Unidade de Armazenamento USB* porque comprou anteriormente um *Adaptador USB-C para USB* e o modelo acredita que a *Unidade de Armazenamento USB* é semelhante a *Adaptador USB-C para USB* com base em padrões históricos de compra.

  Cada recomendação de produtos é influenciada por um ou mais destes fatores. A percentagem de recomendações em que cada fator influenciador desempenhou um papel é visualizada num gráfico. No exemplo seguinte, 100% das recomendações foram influenciadas por transações passadas, 60% pela semelhança de clientes e 22% pela semelhança de produtos. Paire sobre as barras no gráfico para ver a percentagem exata onde os fatores influenciadores contribuíram.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Principais fatores de recomendação aprendidos pelo modelo para gerar recomendações de produtos.":::

- **Estatísticas de dados**: uma descrição geral do número de transações, clientes e produtos considerados pelo modelo. Baseia-se nos dados de entrada que foram usados para aprender padrões e gerar recomendações de produtos.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Estatísticas de dados em torno de dados de entrada utilizados pelo modelo para aprender padrões.":::
  
  O modelo utiliza todos os dados disponíveis para aprender padrões. Portanto, se utilizar a filtragem de produtos na configuração do modelo, esta secção mostra o número total de produtos que o modelo analisou para aprender padrões, o que pode diferir do número de produtos que correspondem aos critérios de filtragem definidos. A filtragem aplica-se às saídas geradas pelo modelo.

- **Recomendações de produtos de amostra:** uma amostra de recomendações que o modelo acredita serem suscetíveis de serem adquiridas pelo cliente. Se for adicionado um catálogo de produtos, os IDs de produtos são substituídos por nomes de produtos.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Lista que mostra sugestões de alta confiança para um conjunto selecionado de clientes individuais.":::

> [!NOTE]
> Na entidade de saída para este modelo, a *Classificação* mostra a medida quantitativa da recomendação. O modelo recomenda produtos com uma pontuação mais elevada sobre produtos com uma pontuação mais baixa. Para ver a classificação, aceda a **Dados** > **Entidades** e veja o separador de dados para a entidade de saída que definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]

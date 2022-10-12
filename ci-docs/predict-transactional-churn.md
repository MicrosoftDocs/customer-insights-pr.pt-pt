---
title: Predição de abandono de transações (contém vídeo)
description: Preveja se um cliente está em risco por ter deixado de comprar os seus produtos ou serviços.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610526"
---
# <a name="predict-transaction-churn"></a>Prever abandono de transações

A previsão de abandono transacional ajuda a prever se um cliente não comprará mais os seus produtos ou serviços num determinado período de tempo.

Tem de ter conhecimento do negócio para entender o que o abandono significa para o seu negócio. Apoiamos definições de abandono baseadas no tempo, o que significa que um cliente é considerado como tendo abandonado após um período de ausência de compras.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Para ambientes baseados em contas empresariais, podemos prever o abandono transacional de uma conta e também uma combinação de conta e outro nível de informação como a categoria de produto. Por exemplo, adicionar uma dimensão pode ajudar a determinar a probabilidade de a conta "Contoso" deixar de comprar a categoria de produto "papelaria de escritório". Além disso, para contas empresariais, também podemos utilizar a IA para gerar uma lista de possíveis motivos pelos quais uma conta provavelmente mudará para uma categoria de informações de nível secundário.

> [!TIP]
> Experimente a predição de abandono de transações utilizando dados de amostra: [Guia de amostra para a predição de abandono de transações](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões do contribuinte](permissions.md).
- Pelo menos, 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos.
- Identificador de Cliente, um identificador exclusivo para corresponder transcrições com os seus clientes.
- Dados de transações para, pelo menos, o dobro da janela de tempo selecionada, tal como dois a três anos do histórico de transações. Idealmente, pelo menos, duas transações por cliente. O histórico de transações tem de incluir:
  - **ID da Transação**: identificador exclusivo de uma compra ou transação.
  - **Data da Transação**: data da compra ou transação.
  - **Valor da transação**: valor monetário ou numérico da transação.
  - **ID exclusivo do produto:**: ID do produto ou serviço comprado se os seus dados estiverem a um nível de item de linha.
  - **Se esta transação foi uma devolução**: um campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** é negativo, inferimos uma devolução.
- Dados de atividade do cliente:
  - Identificador de Cliente, um identificador exclusivo para mapear atividades para os seus clientes.
  - **Chave primária:** identificador exclusivo para uma atividade. Por exemplo, uma visita ao website ou um registo de utilização que mostre que o cliente experimentou uma amostra do seu produto.
  - **Carimbo de data/hora:** data e hora do evento identificadas pela chave primária.
  - **Evento:** nome do evento que pretende utilizar. Por exemplo, um campo chamado "UserAction" numa mercearia pode ser um cupão de utilização pelo cliente.
  - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo chamado "CouponValue" numa mercearia pode ser o valor monetário do cupão.
- Menos de 20% de valores em falta no campo de dados da entidade fornecida

Para contas de negócio (B-para-B), adicione dados de clientes alinhados com atributos mais estáticos, para assegurar que o modelo tem o melhor desempenho:
- **CustomerID:** identificador exclusivo de um cliente.
- **Data de Criação:** data inicialmente adicionada pelo cliente.
- **Distrito:** a localização do distrito de um cliente.
- **País/região:** o país/região de um cliente.
- **Setor:** o tipo de setor de um cliente. Por exemplo, um campo chamado "Indústria" numa máquina de torrefação de café pode indicar se o cliente era retalhista.
- **Classificação:** categorização de um cliente para o seu negócio. Por exemplo, um campo chamado "ValueSegment" numa máquina de torrefação de café pode ser o escalão do cliente com base no tamanho do cliente.

> [!NOTE]
> Para um negócio com alta frequência de compra de clientes (a cada poucas semanas) é recomendado selecionar uma definição de janela de predição e de abandono mais curta. Para uma baixa frequência de compra (a cada poucos meses ou uma vez por ano), escolha uma definição de janela de predição e de abandono mais longa.

## <a name="create-a-transaction-churn-prediction"></a>Criar uma predição de abandono de transações

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** no mosaico **Modelo de abandono de clientes**.

1. Selecione **Transação** para o tipo de abandono e, em seguida, **Começar**.

1. **Nomeie este modelo** e o **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Seguinte**.

### <a name="define-customer-churn"></a>Definir abandono do cliente

Selecione **Guardar rascunho** a qualquer momento para guardar a predição como rascunho. A predição de rascunho é apresentada no separador **A minhas predições**.

1. Defina a **Janela de predição**. Por exemplo, prever o risco de abandono para os seus clientes durante os próximos 90 dias para se alinhar com os seus esforços de retenção de marketing. Prever o risco de abandono durante um período de tempo mais ou menos longo pode tornar mais difícil abordar os fatores no seu perfil de risco de abandono, mas depende das suas necessidades específicas de negócio.

1. Introduza o número de dias para definir o abandono no campo **Definição de abandono**. Por exemplo, se um cliente não tiver feito uma compra nos últimos 30 dias, pode ser considerado como sendo de abandono para o seu negócio.

1. Selecione **Seguinte**.

### <a name="add-purchase-history"></a>Adicionar histórico de compras

1. Selecione **Adicionar dados** para **Histórico de transações do cliente**.

1. Selecione o tipo de atividade semântica **SalesOrder** ou **SalesOrderLine** que contém as informações do histórico de transações. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos de atividade foram mapeados semanticamente quando a atividade foi criada, escolha os atributos ou a entidade específicos em que gostaria que o cálculo se focasse. Se o mapeamento semântico não ocorrer, selecione **Editar** e mapeie os dados.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Painel lateral a mostrar a escolha de atividades específicas sob o tipo semântico.":::

1. Selecione **Seguinte** e reveja os atributos necessários para este modelo.

1. Selecione **Guardar**.

1. Adicione mais atividades ou selecione **Seguinte**.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Adicionar dados adicionais (opcional)

1. Selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que contém os dados que pretende utilizar. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos de atividade foram mapeados semanticamente quando a atividade foi criada, escolha os atributos ou a entidade específicos em que gostaria que o cálculo se focasse. Se o mapeamento semântico não ocorrer, selecione **Editar** e mapeie os dados.

1. Selecione **Seguinte** e reveja os atributos necessários para este modelo.

1. Selecione **Guardar**.

1. Selecione **Seguinte**

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Selecionar nível de predição

A maioria das predições são criadas ao nível do cliente. Em algumas situações, isso pode não ser granular o suficiente para responder às necessidades do seu negócio. Utilize esta caraterística para prever o abandono de um ramo de um cliente, por exemplo, e não do cliente como um todo.

1. Selecione **Selecionar entidade para nível secundário**. Se a opção não estiver disponível, certifique-se de que concluiu a secção anterior.

1. Expanda as entidades a partir das quais pretende escolher o nível secundário ou utilize a caixa de filtro de pesquisa para filtrar as opções selecionadas.

1. Escolha o atributo que pretende utilizar como um nível secundário e, em seguida, selecione **Adicionar**.

1. Selecione **Seguinte**.

> [!NOTE]
> As entidades disponíveis nesta secção são mostradas porque têm uma relação com a entidade que escolheu na secção anterior. Se não vir a entidade que pretende adicionar, certifique-se de que tem uma relação válida presente nas **Relações**. Apenas as relações um para um e muitos para um são válidas para esta configuração.

### <a name="add-additional-data-optional"></a>Adicionar dados adicionais (opcional)

1. Selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que contém os dados que pretende utilizar. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos de atividade foram mapeados semanticamente quando a atividade foi criada, escolha os atributos ou a entidade específicos em que gostaria que o cálculo se focasse. Se o mapeamento semântico não ocorrer, selecione **Editar** e mapeie os dados.

1. Selecione **Seguinte** e reveja os atributos necessários para este modelo.

1. Selecione **Guardar**.

1. Selecione **Seguinte**

1. Opcionalmente, selecione **Adicionar dados** para os **Dados dos clientes**.

1. Mapeie os atributos semânticos para os campos nos dados dos seus próprios clientes, conforme identificado. Os dados nos campos utilizados não devem ser alterados frequentemente para garantir o melhor desempenho do modelo. Por exemplo, selecionar um campo de "Classificação" que muda todos os meses teria apenas o último valor utilizado na predição, embora historicamente o mesmo valor possa não aplicar-se ao cliente na criação dos padrões de predição.

1. Selecione **Seguinte**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Fornecer uma lista opcional de contas de referência

Adicione uma lista dos seus clientes e contas empresariais que pretende utilizar como referências. Os [detalhes para estas contas de referência](#view-prediction-results) incluem a respetiva classificação de abandono e caraterísticas mais influentes que afetaram a predição de abandono.

1. Selecione **+ Adicionar clientes**.

1. Escolha os clientes que atuam como uma referência.

1. Selecione **Seguinte**.

---

### <a name="set-update-schedule"></a>Definir agenda de atualização

1. Para o passo **Atualizações de dados**, escolha uma frequência para reeducar o modelo. Esta definição é importante para atualizar a precisão das previsões à medida que novos dados são ingeridos para o Customer Insights. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Rever e executar a configuração do modelo

O passo **Rever e executar** mostra um resumo da configuração e fornece uma oportunidade de efetuar alterações antes de criar a predição.

1. Selecione **Editar** em qualquer um dos passos para rever e efetuar quaisquer alterações.

1. Se estiver satisfeito com as suas seleções, selecione **Guardar e executar** para começar a executar o modelo. Selecionar **Concluído**. O separador **As minhas predições** é apresentado enquanto a predição está a ser criada. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver resultados da predição

1. Aceda a **Inteligência** > **Predições**.

1. No separador **As minhas predições**, selecione a predição que pretende ver.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Existem três secções primárias de dados dentro da página de resultados:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Existem três secções primárias de dados dentro da página de resultados:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Uma página de informações de **Análise de caraterísticas influentes** contém quatro secções de dados:

- No painel direito, selecione um item dos **Clientes principais** ou **Clientes de referência**. Ambas as listas são ordenadas diminuindo o valor da pontuação de abandono, se a pontuação é apenas para o cliente ou uma pontuação combinada para clientes e um nível secundário, como categoria de produto. O item selecionado determina o conteúdo desta página.

  - **Clientes principais**: lista de 10 clientes com maior risco de abandono e menor risco de abandono com base nas suas pontuações.
  - **Clientes de referência**: lista de até 10 clientes que foram selecionados enquanto configuravam o modelo.

- **Pontuação de abandono:** mostra a pontuação de abandono para o item selecionado no painel direito.

- **Distribuição do risco de abandono:** mostra a distribuição do risco de abandono entre os clientes e o percentil em que se encontra o cliente selecionado.

- **Principais caraterísticas que aumentam e diminuem o risco de abandono:** enumera as cinco principais caraterísticas que aumentaram e diminuíram o risco de abandono para o item selecionado no painel direito. Mostra o valor da caraterística para esse item e a sua influência na classificação de abandono para cada caraterística influente. O valor médio de cada característica nos segmentos de clientes de baixo, médio e alto abandono também é mostrado. Ajuda a contextualizar melhor os valores das principais características influentes para o item selecionado e a compará-lo com segmentos de clientes de baixo, médio e alto abandono.

  - Baixo: contas ou combinações de conta e nível secundário com uma pontuação de abandono entre 0 e 0,33.
  - Médio: contas ou combinações de contas e níveis secundários com uma pontuação de abandono entre 0,33 e 0,66.
  - Alto: contas ou combinações de contas e níveis secundários com uma pontuação de abandono superior a 0,66.

  Quando prevê um abandono ao nível da conta, todas as contas são consideradas na derivação dos valores médios das características para os segmentos de abandono. Para previsões de abandono ao nível secundário para cada conta, a derivação dos segmentos de abandono depende do nível secundário do item selecionado no painel lateral. Por exemplo, se um item tem um nível secundário de categoria de produto (material de escritório), apenas os itens que possuem material de escritório como a categoria de produto são considerados ao derivar os valores médios de características para segmentos de abandono. Esta lógica é aplicada para garantir uma comparação justa dos valores de características do item com os valores médios nos segmentos de baixo, médio e alto abandono.

  Em alguns casos, o valor médio dos segmentos de baixo, médio ou alto abandono está vazio ou não disponível porque não há itens que pertençam aos segmentos de abandono correspondentes com base na definição acima.

  A interpretação dos valores nas colunas média baixa, média e alta é diferente para os recursos categóricos como país ou indústria. Como a noção de valor de recurso "média" não se aplica aos recursos categóricos, os valores nestas colunas são a proporção de clientes em segmentos de baixo, médio ou alto abandono que têm o mesmo valor do recurso categórico em comparação com o item selecionado no painel lateral.

---

 > [!NOTE]
 > Na entidade de saída para este modelo, *ChurnScore* mostra a probabilidade prevista de abandono e *IsChurn* é uma etiqueta binária baseada em *ChurnScore* com limiar de 0,5. Se este limiar predefinido não funcionar para o seu cenário, pode [criar um novo segmento](segments.md#create-a-segment) com o seu limiar preferido. Nem todos os clientes são necessariamente clientes ativos. Alguns deles podem não ter qualquer atividade há muito tempo e já são considerados como tendo abandonado, com base na sua definição de abandono. Prever o risco de abandono de clientes que já efetuaram o abandono não é útil porque não são a audiência de interesse.
>
> Para ver a classificação de abandono, aceda a **Dados** > **Entidades** e veja o separador de dados para a entidade de saída que definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Predição de abandono de transações (contém vídeo)
description: Preveja se um cliente está em risco por ter deixado de comprar os seus produtos ou serviços.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 602a86a67006925faac00add8e089d28f7071c14
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967761"
---
# <a name="transaction-churn-prediction-preview"></a>Predição de abandono de transações (pré-visualização)

A previsão de abandono transacional ajuda a prever se um cliente não comprará mais os seus produtos ou serviços num determinado período de tempo. Pode criar novas predições de abandono em **Inteligência** > **Predições**. Selecione **Minhas previsões** para ver outras previsões que criou. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Para ambientes baseados em contas empresariais, podemos prever o abandono transacional de uma conta e também uma combinação de conta e outro nível de informação como a categoria de produto. Adicionar uma dimensão pode ajudar a descobrir a probabilidade de a conta "Contoso" deixar de comprar a categoria de produto "papelaria de escritório". Além disso, para contas empresariais, também podemos utilizar a IA para gerar uma lista de possíveis motivos pelos quais uma conta provavelmente mudará para uma categoria de informações de nível secundário.

> [!TIP]
> Experimente o tutorial para uma predição de abandono de transações utilizando dados de exemplo: [Guia de exemplo para a predição de abandono de transações (pré-visualização)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.
- Conhecimento de negócios para entender o que a abandono significa para o seu negócio. Apoiamos definições de abandono baseadas no tempo, o que significa que um cliente é considerado como tendo abandonado após um período de ausência de compras.
- Dados sobre as suas transações/compras e a sua história:
    - Identificadores de transações para distinguir compras/transações.
    - Identificadores de clientes para fazer corresponder as transações aos seus clientes.
    - As datas dos eventos da transação, que definem as datas em que a transação ocorreu.
    - O esquema de dados semânticos para compras/transações requer as seguintes informações:
        - **ID da transação**: um identificador exclusivo de uma compra ou transação.
        - **Data da transação**: a data da compra ou transação.
        - **Valor da transação**: o valor monetário/valor numérico da transação/item.
        - (Opcional) **ID de produto exclusivo**: o ID do produto ou serviço comprado se os seus dados estiverem ao nível do item.
        - (Opcional) **Se esta transação foi uma devolução**: um campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** é negativo, também utilizaremos esta informação para inferir uma devolução.
- (Opcional) Dados sobre as atividades dos clientes:
    - Identificadores de atividade para distinguir atividades do mesmo tipo.
    - Identificadores de clientes para mapear atividades para os seus clientes.
    - Informações de atividade que contêm o nome e a data da atividade.
    - O esquema de dados semânticos para atividades do cliente inclui:
        - **Chave primária:** um identificador exclusivo para uma atividade. Por exemplo, uma visita ao website ou um registo de utilização que mostre que o cliente experimentou uma amostra do seu produto.
        - **Carimbo de data/hora:** A data e a hora do evento identificadas pela chave primária.
        - **Evento:** o nome do evento que pretende utilizar. Por exemplo, um campo chamado "UserAction" numa mercearia pode ser um cupão de utilização pelo cliente.
        - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo chamado "CouponValue" numa mercearia pode ser o valor monetário do cupão.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.
- Conhecimento de negócios para entender o que a abandono significa para o seu negócio. Apoiamos definições de abandono baseadas no tempo, o que significa que um cliente é considerado como tendo abandonado após um período de ausência de compras.
- Dados sobre as suas transações/compras e a sua história:
    - Identificadores de transações para distinguir compras/transações.
    - Identificadores de clientes para fazer corresponder as transações aos seus clientes.
    - As datas dos eventos da transação, que definem as datas em que a transação ocorreu.
    - O esquema de dados semânticos para compras/transações requer as seguintes informações:
        - **ID da transação**: um identificador exclusivo de uma compra ou transação.
        - **Data da transação**: a data da compra ou transação.
        - **Valor da transação**: o valor monetário/valor numérico da transação/item.
        - (Opcional) **ID de produto exclusivo**: o ID do produto ou serviço comprado se os seus dados estiverem ao nível do item.
        - (Opcional) **Se esta transação foi uma devolução**: um campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** é negativo, também utilizaremos esta informação para inferir uma devolução.
- (Opcional) Dados sobre as atividades dos clientes:
    - Identificadores de atividade para distinguir atividades do mesmo tipo.
    - Identificadores de clientes para mapear atividades para os seus clientes.
    - Informações de atividade que contêm o nome e a data da atividade.
    - O esquema de dados semânticos para atividades do cliente inclui:
        - **Chave primária:** um identificador exclusivo para uma atividade. Por exemplo, uma visita ao website ou um registo de utilização que mostre que o cliente experimentou uma amostra do seu produto.
        - **Carimbo de data/hora:** A data e a hora do evento identificadas pela chave primária.
        - **Evento:** o nome do evento que pretende utilizar. Por exemplo, um campo chamado "UserAction" numa mercearia pode ser um cupão de utilização pelo cliente.
        - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo chamado "CouponValue" numa mercearia pode ser o valor monetário do cupão.
- (Opcional) Dados sobre os seus clientes:
    - Estes dados devem ser alinhados com atributos mais estáticos para garantir o melhor desempenho do modelo.
    - O esquema de dados semântico para os dados do cliente inclui:
        - **CustomerID:** um identificador exclusivo de um cliente.
        - **Data de Criação:** a data inicialmente adicionada pelo cliente.
        - **Distrito:** a localização do distrito de um cliente.
        - **País:** o país de um cliente.
        - **Indústria:** o tipo de indústria de um cliente. Por exemplo, um campo chamado "Indústria" numa máquina de torrefação de café pode indicar se o cliente era retalhista.
        - **Classificação:** a categorização de um cliente para o seu negócio. Por exemplo, um campo chamado "ValueSegment" numa máquina de torrefação de café pode ser o escalão do cliente com base no tamanho do cliente.

---

- Características de dados sugeridos:
    - Dados históricos suficientes: dados de transação para, pelo menos, o dobro da janela de tempo selecionada. De preferência, dois a três anos de histórico de transações. 
    - Compras múltiplas por cliente: idealmente, pelo menos, duas transações por cliente.
    - Número de clientes: pelo menos, 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos. O modelo falhará com menos de 10 clientes e dados históricos insuficientes.
    - Totalidade dos dados: menos de 20% de valores em falta no campo de dados da entidade fornecida.

> [!NOTE]
> Para um negócio com alta frequência de compra de clientes (a cada poucas semanas) é recomendado selecionar uma definição de janela de predição e de abandono mais curta. Para uma baixa frequência de compra (a cada poucos meses ou uma vez por ano), escolha uma definição de janela de predição e de abandono mais longa.

## <a name="create-a-transaction-churn-prediction"></a>Criar uma predição de abandono de transações

1. No Customer Insights, aceda a **Inteligência** > **Predições**.

1. Selecione o mosaico **Modelo de abandono do cliente (pré-visualização)** e selecione **Use este modelo**.

1. No painel **Modelo de abandono de clientes (pré-visualização)**, escolha **Transação** e selecione **Começar**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de ecrã com a opção de transação selecionada no painel Modelo de abandono de clientes.":::
 
### <a name="name-model"></a>Atribuir nome ao modelo

1. Forneça um nome para o modelo para distingui-lo de outros modelos.

1. Forneça um nome para a entidade de saída usando apenas letras e números, sem espaços. É o nome que a entidade modelo vai usar. 

1. Selecione **Seguinte**.

### <a name="define-customer-churn"></a>Definir abandono do cliente

1. Defina a **Janela de predição**. Por exemplo, prever o risco de abandono para os seus clientes durante os próximos 90 dias para se alinhar com os seus esforços de retenção de marketing. Prever o risco de abandono durante um período de tempo mais ou menos longo pode tornar mais difícil abordar os fatores no seu perfil de risco de abandono, mas depende das suas necessidades específicas de negócio.
   >[!TIP]
   > Pode selecionar **Guardar rascunho** a qualquer momento para guardar a predição como rascunho. Vais encontrar o rascunho de previsão no separador **Minhas previsões** para continuar.

1. Introduza o número de dias para definir o abandono no campo **Definição de abandono**. Por exemplo, se um cliente não tiver feito quaisquer compras nos últimos 30 dias, elas podem ser consideradas como sendo de abandono para o seu negócio. 

1. Selecione **Seguinte** para continuar.

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** e escolha o tipo de atividade no painel lateral que contém as informações de histórico de transação ou de compra necessárias.

1. Em **Atividades selecionadas**, escolha as atividades específicas do tipo de atividade selecionado em que gostaria que o cálculo se focasse.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Painel lateral a mostrar a escolha de atividades específicas sob o tipo semântico.":::

   Se ainda não mapeou a atividade para um tipo semântico, selecione **Editar** para o fazer. A experiência guiada para mapear atividades semânticas é aberto. Mapeie os seus dados para os campos correspondentes no tipo de atividade selecionado.

1. Mapear os atributos semânticos para os campos que são necessários para executar o modelo. Se os campos abaixo não estiverem preenchidos, configure a relação da sua entidade de histórico de compras com a entidade *Cliente*. Selecione **Guardar**.

1. No passo **Adicionar dados necessários**, selecione **Seguinte** para proceder se não pretender adicionar mais atividades.


# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Adicionar dados adicionais (opcional)

Configure a relação da sua entidade de atividade de cliente com a entidade *Cliente*.

1. Selecione o campo que identifica o cliente na tabela de atividades do cliente. Pode estar diretamente relacionado com o ID do cliente principal da sua entidade *Cliente*.

1. Selecione a entidade que é a sua entidade *Cliente* principal.

1. Introduza um nome que descreva a relação.

#### <a name="customer-activities"></a>Atividades do cliente

1. Opcionalmente, selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que contém os dados que pretende utilizar e, em seguida, selecione uma ou mais atividades na secção **Atividades**.

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está a configurar. Selecione **Criar novo** e escolher um tipo de atividade disponível ou criar um novo tipo.

1. Selecione **Seguinte** e, em seguida, **Guardar**.

1. Se tiver outras atividades do cliente que gostaria de incluir, repita os passos acima.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Selecionar nível de predição

A maioria das predições são criadas ao nível do cliente. Em algumas situações, isso pode não ser granular o suficiente para responder às necessidades do seu negócio. Pode utilizar esta característica para prever o abandono de um ramo de um cliente, por exemplo, e não do cliente como um todo.

1. Para criar uma predição a um nível mais granular do que o cliente, selecione **Selecionar entidade para um nível secundário**. Se a opção não estiver disponível, certifique-se de que concluiu a secção anterior.

1. Expanda as entidades a partir das quais pretende escolher o nível secundário ou utilize a caixa de filtro de pesquisa para filtrar as opções selecionadas.

1. Escolha o atributo que pretende utilizar como um nível secundário e, em seguida, selecione **Adicionar**.

1. Selecione **Seguinte**.

> [!NOTE]
> As entidades disponíveis nesta secção são mostradas porque têm uma relação com a entidade que escolheu na secção anterior. Se não vir a entidade que pretende adicionar, certifique-se de que tem uma relação válida presente nas **Relações**. Apenas as relações um para um e muitos para um são válidas para esta configuração.

### <a name="add-additional-data-optional"></a>Adicionar dados adicionais (opcional)

Configure a relação da sua entidade de atividade de cliente com a entidade *Cliente*.

1. Selecione o campo que identifica o cliente na tabela de atividades do cliente. Pode estar diretamente relacionado com o ID do cliente principal da sua entidade *Cliente*.

1. Selecione a entidade que é a sua entidade *Cliente* principal.

1. Introduza um nome que descreva a relação.

#### <a name="customer-activities"></a>Atividades do cliente

1. Opcionalmente, selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que contém os dados que pretende utilizar e, em seguida, selecione uma ou mais atividades na secção **Atividades**.

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está a configurar. Selecione **Criar novo** e escolher um tipo de atividade disponível ou criar um novo tipo.

1. Selecione **Seguinte** e, em seguida, **Guardar**.

1. Se tiver outras atividades do cliente que gostaria de incluir, repita os passos acima.

#### <a name="customers-data"></a>Dados de clientes

1. Opcionalmente, selecione **Adicionar dados** para os **Dados dos clientes**.

1. Mapeie os atributos semânticos para os campos nos dados dos seus próprios clientes, conforme identificado. Os dados nos campos utilizados não devem ser alterados frequentemente para garantir o melhor desempenho do modelo. Por exemplo, selecionar um campo de "Classificação" que muda todos os meses teria apenas o último valor utilizado na predição, embora historicamente o mesmo valor possa não aplicar-se ao cliente na criação dos padrões de predição.

1. Selecione **Seguinte**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Fornecer uma lista opcional de contas de referência

Adicione uma lista dos seus clientes e contas empresariais que pretende utilizar como referências. Obterá [detalhes para estas contas de referência](#review-a-prediction-status-and-results), incluindo a sua pontuação de abandono e características mais influentes que impactaram a predição de abandono.

1. Selecione **+ Adicionar clientes**.

1. Escolha os clientes que atuam como uma referência.

1. Selecione **Seguinte** para continuar.

---

### <a name="set-schedule-and-review-configuration"></a>Definir agenda e rever configuração

1. Defina uma frequência para reeducar o modelo. Esta definição é importante para atualizar a exatidão das predições à medida que novos dados são ingeridos. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.

1. Rever a configuração da predição. Pode voltar aos passos anteriores, selecionando **Editar** no valor apresentado. Ou pode selecionar um passo de configuração a partir do indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Guardar e executar** para iniciar o processo de previsão. No separador **Minhas previsões**, pode ver o estado das suas previsões. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Rever um estado de previsão e resultados

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione a predição que pretende rever.
   - **Nome da predição**: nome da predição fornecida na sua criação.
   - **Tipo de predição**: tipo de modelo utilizado para a predição
   - **Entidade de saída**: nome da entidade para armazenar a saída da predição. Pode encontrar uma entidade com este nome em **Dados** > **Entidades**.
     Na entidade de saída, *ChurnScore* é a probabilidade prevista de abandono e *IsChurn* é uma etiqueta binária baseada em *ChurnScore* com limiar de 0,5. O limiar predefinido pode não funcionar para o seu cenário. [Crie um novo segmento](segments.md#create-a-new-segment) com o seu limiar preferido.
     Nem todos os clientes são necessariamente clientes ativos. Alguns deles podem não ter qualquer atividade há muito tempo e já são considerados como tendo abandonado, com base na sua definição de abandono. Prever o risco de abandono de clientes que já efetuaram o abandono não é útil porque não são a audiência de interesse.
   - **Campo da predição**: este campo é povoado apenas para alguns tipos de predições, e não é utilizado na predição de abandono.
   - **Estado**: estado da execução da predição.
        - **Em fila**: a predição está à espera de outros processos.
        - **Atualizar**: a predição está atualmente em curso para produzir resultados que irão fluir para a entidade de produção.
        - **Falhou**: a execução da predição falhou. [Rever os registos](manage-predictions.md#troubleshoot-a-failed-prediction) para mais detalhes.
        - **Sucesso**: a predição foi bem sucedida. Selecione **Ver** por baixo das reticências verticais para rever a previsão
   - **Editada**: a data da em que a configuração para a predição foi alterada.
   - **Última atualização**: a data em que a predição foi atualizada resulta na entidade de saída.

1. Selecione as reticências verticais ao lado da previsão que pretende rever os resultados e selecione **Ver**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Exibir controlo para ver os resultados de uma predição.":::

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

1. Existem três secções primárias de dados dentro da página de resultados:
   - **Desempenho do modelo de preparação**: A, B ou C são possíveis pontuações. Esta pontuação indica o desempenho da predição e pode ajudá-lo a tomar a decisão de utilizar os resultados armazenados na entidade de saída. As pontuações são determinadas com base nas seguintes regras: 
        - **A** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é superior à base de referência em pelo menos 10%.
            
        - **B** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é até 10% superior à base de referência.
            
        - **C** quando o modelo previu com precisão menos de 50% do total das predições, ou quando a percentagem de predições exatas para os clientes que abandonaram é inferior à base de referência.
               
        - **Base de referência** toma a entrada do período de predição para o modelo (por exemplo, um ano) e o modelo cria diferentes frações de tempo dividindo-o por 2 até chegar a um mês ou menos. Utiliza estas frações para criar uma regra de negócio para clientes que não tenham efetuado compras neste período de tempo. Estes clientes são considerados como tendo abandonado. A regra empresarial baseada no tempo com a maior capacidade de predição de quem é suscetível de abandono é escolhida como modelo de base.
            
    - **Probabilidade de abandono (número de clientes)**: grupos de clientes com base no risco previsto de abandono. Estes dados podem ajudá-lo mais tarde se quiser criar um segmento de clientes com elevado risco de abandono. Estes segmentos ajudam a entender onde o seu limite dever ser para a adesão ao segmento.
       
    - **Fatores mais influentes**: há muitos fatores que são tidos em conta na criação da sua previsão. Cada um dos fatores tem a sua importância calculada para as predições agregadas que um modelo cria. Pode utilizar estes fatores para ajudar a validar os seus resultados de predição ou pode utilizar esta informação mais tarde para [criar segmentos](segments.md) que possam ajudar a influenciar o risco de abandono de clientes.


# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

1. Existem três secções primárias de dados dentro da página de resultados:
   - **Desempenho do modelo de preparação**: A, B ou C são possíveis pontuações. Esta pontuação indica o desempenho da predição e pode ajudá-lo a tomar a decisão de utilizar os resultados armazenados na entidade de saída. As pontuações são determinadas com base nas seguintes regras: 
        - **A** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é superior à base de referência em pelo menos 10%.
            
        - **B** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é até 10% superior à base de referência.
            
        - **C** quando o modelo previu com precisão menos de 50% do total das predições, ou quando a percentagem de predições exatas para os clientes que abandonaram é inferior à base de referência.
               
        - **Base de referência** toma a entrada do período de predição para o modelo (por exemplo, um ano) e o modelo cria diferentes frações de tempo dividindo-o por 2 até chegar a um mês ou menos. Utiliza estas frações para criar uma regra de negócio para clientes que não tenham efetuado compras neste período de tempo. Estes clientes são considerados como tendo abandonado. A regra empresarial baseada no tempo com a maior capacidade de predição de quem é suscetível de abandono é escolhida como modelo de base.
            
    - **Probabilidade de abandono (número de clientes)**: grupos de clientes com base no risco previsto de abandono. Estes dados podem ajudá-lo mais tarde se quiser criar um segmento de clientes com elevado risco de abandono. Estes segmentos ajudam a entender onde o seu limite dever ser para a adesão ao segmento.
       
    - **Fatores mais influentes**: há muitos fatores que são tidos em conta na criação da sua previsão. Cada um dos fatores tem a sua importância calculada para as predições agregadas que um modelo cria. Pode utilizar estes fatores para ajudar a validar os seus resultados de predição ou pode utilizar esta informação mais tarde para [criar segmentos](segments.md) que possam ajudar a influenciar o risco de abandono de clientes.


1. Para as contas empresariais, encontrará uma página de informações de **análise de características influentes**. Contém quatro secções de dados:

    - O item selecionado no painel direito determina o conteúdo desta página. Selecione um item dos **Clientes principais** ou **Clientes de referência**. Ambas as listas são ordenadas diminuindo o valor da pontuação de abandono, se a pontuação é apenas para o cliente ou uma pontuação combinada para clientes e um nível secundário, como categoria de produto.
        
        - **Clientes principais**: lista de 10 clientes com maior risco de abandono e menor risco de abandono com base nas suas pontuações. 
        - **Clientes de referência**: lista de até 10 clientes que foram selecionados enquanto configuravam o modelo.
 
    - **Pontuação de abandono:** mostra a pontuação de abandono para o item selecionado no painel direito.
    
    - **Distribuição do risco de abandono:** mostra a distribuição do risco de abandono entre os clientes e o percentil em que se encontra o cliente selecionado. 
    
    - **Principais características que aumentam e diminuem o risco de abandono:** no caso do item selecionado no painel direito, as cinco principais características que aumentaram e diminuíram o risco de abandono são listadas. No caso de cada característica influente, encontra-se o valor da característica para esse item e a sua influência na pontuação de abandono. O valor médio de cada característica nos segmentos de clientes de baixo, médio e alto abandono também é mostrado. Ajuda a contextualizar melhor os valores das principais características influentes para o item selecionado e a compará-lo com segmentos de clientes de baixo, médio e alto abandono.

       - Baixo: contas ou combinações de conta e nível secundário com uma pontuação de abandono entre 0 e 0,33
       - Médio: contas ou combinações de contas e níveis secundários com uma pontuação de abandono entre 0,33 e 0,66
       - Alto: contas ou combinações de contas e níveis secundários com uma pontuação de abandono superior a 0,66
    
       Quando prevê um abandono ao nível da conta, todas as contas são consideradas na derivação dos valores médios das características para os segmentos de abandono. Para previsões de abandono ao nível secundário para cada conta, a derivação dos segmentos de abandono depende do nível secundário do item selecionado no painel lateral. Por exemplo, se um item tem um nível secundário de categoria de produto = material de escritório, então apenas os itens que possuem material de escritório como a categoria de produto são considerados ao derivar os valores médios de características para segmentos de abandono. Esta lógica é aplicada para garantir uma comparação justa dos valores de características do item com os valores médios nos segmentos de baixo, médio e alto abandono.

       Em alguns casos, o valor médio dos segmentos de baixo, médio ou alto abandono está vazio ou não disponível porque não há itens que pertençam aos segmentos de abandono correspondentes com base na definição acima.
       
       > [!NOTE]
       > A interpretação dos valores nas colunas média baixa, média e alta é diferente para os recursos categóricos como país ou indústria. Como a noção de valor de recurso "média" não se aplica aos recursos categóricos, os valores nestas colunas são a proporção de clientes em segmentos de baixo, médio ou alto abandono que têm o mesmo valor do recurso categórico em comparação com o item selecionado no painel lateral.

---

## <a name="manage-predictions"></a>Gerir predições

É possível otimizar, resolver problemas, atualizar ou eliminar predições. Reveja um relatório de capacidade de utilização de dados de entrada para saber como tornar uma predição mais rápida e fiável. Para mais informações, aceda a [Gerir predições](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Predição de valor vitalício do cliente (CLV)
description: Prever o potencial de receita para clientes ativos no futuro.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 04c4252aae374cf25c16b71415ee4a89b51b0040
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954593"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Predição do valor vitalício do cliente (CLV) (Pré-visualização)

Preveja o valor potencial (receita) que os clientes ativos individuais irão trazer para o seu negócio através de um período de tempo definido no futuro. Esta funcionalidade pode ajudá-lo a alcançar vários objetivos: 
- Identifique clientes de alto valor e processe esta informação
- Criar segmentos de clientes estratégicos com base no seu valor potencial para executar campanhas personalizadas com vendas, marketing e esforços de suporte direcionados
- Oriente o desenvolvimento do produto focando-se em funcionalidades que aumentam o valor do cliente
- Otimize a estratégia de vendas ou de marketing e aloque o orçamento com mais precisão para a divulgação do cliente
- Reconheça e dê prémios a clientes de alto valor através de programas de fidelização ou recompensas 

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, reflita o que o CLV significa para o seu negócio. Atualmente, suportamos a predição de CLV baseada em transações. O valor previsto de um cliente baseia-se no histórico de transações comerciais. Para criar a predição, precisa de, pelo menos, permissões de [Contribuinte](permissions.md).

Uma vez que configurar e executar um modelo de CLV não demora muito tempo, considere criar vários modelos com diferentes preferências de entrada e compare os resultados do modelo para ver qual o cenário de modelo que melhor se adequa às necessidades do seu negócio.

###  <a name="data-requirements"></a>Requisitos de dados

São necessários os seguintes dados, e onde marcados como opcionais, recomendados para um maior desempenho do modelo. Quanto mais dados o modelo puder processar, mais precisa será a predição. Por isso, encorajamo-lo a ingerir mais dados de atividade do cliente, se disponíveis.

- Identificador de Cliente: identificador exclusivo para combinar transações com um cliente individual

- Histórico de Transações: registo de transações históricas com esquema de dados semânticos abaixo
    - **ID da Transação**: identificador exclusivo de cada transação
    - **Data da transação**: data, de preferência um carimbo de hora de cada transação
    - **Montante da transação**: valor monetário (por exemplo, receitas ou margem de lucro) de cada transação
    - **Etiqueta atribuída a devoluções** (opcional): valor booleano significando se a transação é uma devolução 
    - **ID do produto** (opcional): ID do produto envolvido na transação

- Dados adicionais (opcional), por exemplo
    - Atividades Web: histórico de visitas ao site, histórico de e-mails
    - Atividades de fidelização: acumulação de pontos de recompensa de fidelidade e histórico de redenção
    - Registo de suporte ao cliente, chamada de serviço, reclamação ou histórico de devoluções
- Dados sobre as atividades do cliente (opcional):
    - Identificadores de atividade para distinguir atividades do mesmo tipo
    - Identificadores de clientes para mapear atividades para os seus clientes
    - Informações de atividade que contêm o nome e a data da atividade
    - O esquema de dados semânticos para atividades inclui: 
        - **Chave primária**: um identificador exclusivo para uma atividade
        - **Carimbo de data/hora**: a data e a hora do evento identificadas pela chave primária
        - **Evento (nome da atividade)**: o nome do evento que pretende utilizar
        - **Detalhes (montante ou valor)**: detalhes sobre a atividade do cliente

- Características de dados sugeridos:
    - Dados históricos suficientes: pelo menos, um ano de dados transacionais. De preferência, dois a três anos de dados transacionais para prever CLV por um ano.
    - Compras múltiplas por cliente: idealmente, pelo menos, duas a três transações por ID de cliente, de preferência em várias datas.
    - Número de clientes: pelo menos, 100 clientes exclusivos, de preferência mais de 10.000 clientes. O modelo falhará com menos de 100 clientes e dados históricos insuficientes
    - Conclusão de dados: menos de 20% dos valores em falta nos campos obrigatórios nos dados de entrada   

> [!NOTE]
> - O modelo requer o histórico de transações dos seus clientes. Atualmente, apenas uma entidade de histórico de transações pode ser configurada. Se houver várias entidades de compra/transação, pode uni-las no Power Query antes da ingestão de dados.
> - Para dados de atividade de cliente adicionais (opcional), no entanto, pode adicionar as entidades de atividade de cliente que quiser para consideração pelo modelo.

## <a name="create-a-customer-lifetime-value-prediction"></a>Criar um predição do Valor Vitalício do Cliente

1. Nas informações de audiência, vá a **Inteligência** > **Predições**.

1. Selecione o mosaico **Valor vitalício do cliente** e selecione **Utilizar modelo**. 

1. No painel **Valor vitalício do cliente (pré-visualização)**, selecione **Começar**.

1. **Nomeie este modelo** e o **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Seguinte**.

### <a name="define-model-preferences"></a>Definir preferências de modelo

1. Defina um **Período de tempo de predição** para definir até onde pretende prever o CLV.    
   Por predefinição, a unidade é definida como meses. Pode mudá-lo para anos para que seja mais longe no futuro.

   > [!TIP]
   > Para prever com precisão o CLV para o período de tempo definido, precisa de um período comparável de dados históricos. Por exemplo, se quiser prever CLV para os próximos 12 meses, recomenda-se que tenha pelo menos 18 a 24 meses de dados históricos.

1. Especifique o que **Clientes ativos** significa para o seu negócio. Defina o intervalo de tempo em que um cliente deve ter tido pelo menos uma transação a considerar ativa. O modelo apenas irá prever o CLV para clientes ativos. 
   - **Deixe o modelo calcular o intervalo de compra (recomendado)**: o modelo analisa os seus dados e determina um período de tempo baseado em compras históricas.
   - **Definir o intervalo manualmente**: se tiver uma definição de negócio específica de um cliente ativo, escolha esta opção e defina o período de tempo em conformidade.

1. Defina o percentil de **Cliente de alto valor** para permitir que o modelo forneça resultados que se encaixem na definição de negócio.
    - **Cálculo do modelo (recomendado)**: o modelo analisa os seus dados e determina o que um cliente de alto valor pode ser para o seu negócio com base no histórico de transações dos seus clientes. O modelo usa uma regra heurística (inspirada na regra 80/20 ou princípio pareto) para encontrar a proporção de clientes de alto valor. A percentagem de clientes que contribuíram para uma receita acumulada de 80% para o seu negócio no período histórico são considerados clientes de alto valor. Normalmente, menos de 30% a 40% de clientes contribuem para uma receita acumulada de 80%. No entanto, este número pode variar dependendo do seu negócio e do seu setor.    
    - **Percentagem dos principais clientes ativos**: defina clientes de alto valor para o seu negócio como um percentil dos principais clientes pagadores ativos. Por exemplo, pode usar esta opção para definir clientes de alto valor como principais 20% dos futuros clientes pagadores.

    Se o seu negócio define clientes de alto valor de uma forma diferente, [diga-nos, pois gostaríamos de saber](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Selecione **Seguinte** e avance para o passo seguinte.

### <a name="add-required-data"></a>Adicionar dados necessários

1. No passo **Dados obrigatórios**, selecione **Adicionar dados** para o **Histórico de transações do cliente** e escolha a entidade que fornece as informações do histórico de transações conforme descrito nos [pré-requisitos](#prerequisites).

1. Mapear os campos semânticos a atributos dentro da sua entidade de histórico de compras e selecione **Seguinte**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Imagem do passo de configuração para mapear atributos de dados para dados obrigatórios.":::
 
1. Se os campos abaixo não estiverem povoados, configure a relação da sua entidade de histórico de compras para a entidade *Cliente* e selecione **Guardar**.
    1. Selecione a entidade de histórico de transações.
    1. Selecione o campo que identifica um cliente na entidade de histórico de compras. Tem de se relacionar com o ID do cliente primário da sua entidade Cliente.
    1. Selecione a entidade que corresponde à sua entidade principal de cliente.
    1. Introduza um nome que descreva a relação.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Imagem do passo de configuração para definir a relação com a entidade de cliente.":::

1. Selecione **Seguinte**.

### <a name="add-optional-data"></a>Adicionar dados opcionais

Os dados que refletem as principais interações do cliente (como Web, suporte ao cliente e registos de eventos) adicionam contexto aos registos de transações. Mais padrões encontrados nos dados da atividade do seu cliente podem melhorar a precisão das predições. 

1. No passo **Dados adicionais (opcional)**, selecione **Adicionar dados**. Escolha a entidade de atividade de cliente que fornece as informações de atividade de cliente, conforme descrito nos [pré-requisitos](#prerequisites).

1. Mapear os campos semânticos a atributos dentro da sua entidade de atividade do cliente e selecione **Seguinte**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Imagem do passo de configuração para mapear campos para dados adicionais.":::

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está a adicionar. Escolha entre os tipos de atividade existentes ou adicione um novo tipo de atividade.

1. Configure a relação da sua entidade de atividade de cliente com a entidade *Cliente*.
    
    1. Selecione o campo que identifica o cliente na tabela de atividades do cliente. Pode estar diretamente relacionado com o ID do cliente principal da sua entidade *Cliente*.
    1. Selecione a entidade *Cliente* que corresponde à sua entidade principal *Cliente*.
    1. Introduza um nome que descreva a relação.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Imagem do passo no fluxo de configuração para adicionar dados adicionais e configurar a atividade com exemplos preenchidos.":::

1. Selecione **Guardar**.    
    Adicione mais dados se houver outras atividades de cliente que pretende incluir.

1. Selecione **Seguinte**.

### <a name="set-update-schedule"></a>Definir agenda de atualização

1. Na passo **Agenda da atualização de dados**, escolha a frequência para reeducar o modelo com base nos dados mais recentes. Esta definição é importante para atualizar a exatidão das predições à medida que novos dados são ingeridos nas informações de audiência. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.


### <a name="review-and-run-the-model-configuration"></a>Rever e executar a configuração do modelo

1. Na passo **Rever os detalhes do modelo**, valide a configuração da predição. Pode voltar a qualquer parte da configuração de previsão selecionando **Editar** por abaixo do valor indicado. Também pode selecionar um passo de configuração a partir do indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Guardar e executar** para começar a executar o modelo. No separador **As minhas predições**, pode ver o estado do processo de predição. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

## <a name="review-prediction-status-and-results"></a>Rever o estado e resultados da predição

### <a name="review-prediction-status"></a>Rever estado da predição

1.  Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.
2.  Selecione a predição que pretende rever.

- **Nome da predição**: nome da predição fornecida na sua criação.
- **Tipo de predição**: tipo de modelo utilizado para a predição
- **Entidade de saída**: nome da entidade para armazenar a saída da predição. Vá a **Dados** > **Entidades** para encontrar a entidade com este nome.
- **Campo previsto**: este campo é povoado apenas para alguns tipos de predições, e não é usado na predição do valor vitalício do cliente.
- **Estado**: estado da execução da predição.
    - **Em fila**: a predição está à espera que outros processos completem.
    - **A atualizar**: a predição está atualmente em execução para criar resultados que fluirão para a entidade de saída.
    - **Falhou**: a execução da predição falhou. [Rever os registos](#troubleshoot-a-failed-prediction) para mais detalhes.
    - **Sucesso**: a predição foi bem sucedida. Selecione **Ver** sob as reticências verticais para rever os resultados predição.
- **Editada**: a data da em que a configuração para a predição foi alterada.
- **Última atualização**: a data em que a predição foi atualizada resulta na entidade de saída.


### <a name="review-prediction-results"></a>Rever os resultados da predição

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione as predição para as quais pretende rever os resultados.

Existem três secções primárias de dados dentro da página de resultados.

- **Desempenho do modelo de preparação**: A, B ou C são níveis possíveis. Este nível indica o desempenho da predição e pode ajudá-lo a tomar a decisão de utilizar os resultados armazenados na entidade de saída. Selecione **Saber mais sobre esta pontuação** para entender melhor as métricas de desempenho do modelo subjacente e como o nível do desempenho final do modelo foi derivado.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imagem da caixa de informação de nível do modelo com o nível A.":::

  Utilizando a definição de clientes de alto valor fornecidos ao configurar a predição, o sistema avalia o desempenho do modelo de IA na predição dos clientes de alto valor em comparação com um modelo de base.    

  Os níveis são determinados com base nas seguintes regras:
  - **A** quando o modelo previu com precisão, pelo menos, 5% mais clientes de alto valor em comparação com o modelo de base.
  - **B** quando o modelo previu com precisão entre a 0% a 5% mais clientes de alto valor em comparação com o modelo de base.
  - **C** quando o modelo previu com precisão menos clientes de alto valor em comparação com o modelo de base.

  O painel **Classificação do modelo** mostra mais detalhes sobre o desempenho do modelo de IA e o modelo de base. O modelo de base utiliza uma abordagem não baseada em IA para calcular o valor vitalício do cliente baseado principalmente em compras históricas feitas pelos clientes.     
  A fórmula padrão utilizada para calcular o CLV pelo modelo de base:    

  _**CLV para cada cliente** = Compra média mensal feita pelo cliente na janela de cliente ativo * Número de meses no período de predição de CLV * Taxa de retenção geral de todos os clientes*_

  O modelo de IA é comparado com o modelo de base com base em duas métricas de desempenho do modelo.
  
  - **Taxa de sucesso na predição de clientes de valor elevado**

    Veja a diferença na predição de clientes de alto valor utilizando o modelo de IA em comparação com o modelo de base. Por exemplo, uma taxa de sucesso de 84% significa que de todos os clientes de alto valor nos dados de preparação, o modelo de IA foi capaz de capturar com precisão 84%. Em seguida, comparamos esta taxa de sucesso com a taxa de sucesso do modelo de base para reportar a mudança relativa. Este valor é usado para atribuir um nível ao modelo.

  - **Métricas de erro**
    
    Outra métrica permite rever o desempenho geral do modelo em termos de erro na predição de valores futuros. Utilizamos a métrica geral do Erro do Desvio da Raiz Quadrada Média (RMSE) para avaliar este erro. A RMSE é uma forma padrão de medir o erro de um modelo na predição de dados quantitativos. A RMSE do modelo de IA é comparado com a RMSE do modelo de base e a diferença relativa é reportada.

  O modelo de IA dá prioridade à classificação precisa dos clientes de acordo com o valor que trazem para o seu negócio. Assim, apenas a taxa de sucesso da predição de clientes de alto valor é usada para obter o nível final do modelo. A métrica RMSE é sensível a valores atípicos. Em cenários em que tem uma pequena percentagem de clientes com valores de compra extraordinariamente elevados, a métrica geral da RMSE pode não dar a imagem completa do desempenho do modelo.   

- **Valor dos clientes por percentil**: utilizando a sua definição de clientes de alto valor, os clientes são agrupados em baixo valor e valor elevado, com base nas suas predições de CLV, e mostrados num gráfico. Pairando sobre as barras no histograma, pode ver o número de clientes em cada grupo e a média de CLV desse grupo. Estes dados podem ajudar se pretender [criar segmentos de clientes](segments.md) com base nas suas previsões de CLV.

- **Fatores mais influentes**: vários fatores são considerados ao criar a sua predição de CLV com base nos dados de entrada fornecidos ao modelo de IA. Cada um dos fatores tem a sua importância calculada para as previsões agregadas que um modelo cria. Pode utilizar estes fatores para ajudar a validar os resultados da sua previsão. Estes fatores também fornecem mais informações sobre os fatores mais influentes que contribuíram para a predição de CLV em todos os seus clientes.

## <a name="refresh-a-prediction"></a>Atualizar uma previsão

As predições atualizam-se automaticamente na mesma [agenda em que os seus dados são atualizados](system.md#schedule-tab), como configurados nas definições. Também é possível atualizá-las manualmente.

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.
2. Selecione as reticências verticais ao lado da previsão que pretende atualizar.
3. Selecione **Atualizar**.

## <a name="delete-a-prediction"></a>Eliminar uma previsão

A eliminação de uma predição também elimina a sua entidade de saída.

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.
2. Selecione as reticências verticais ao lado da previsão que pretende eliminar.
3. Selecione **Eliminar**.

## <a name="troubleshoot-a-failed-prediction"></a>Resolução de problemas de uma predição falhada

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.
2. Selecione as reticências verticais ao lado da predição para a qual deseja ver os registos de erros.
3. Selecionar **Registos**.
4. Rever todos os erros. Existem vários tipos de erros que podem ocorrer, e estes descrevem que condição causou o erro. Por exemplo, um erro que informa que não há dados suficientes para prever com precisão é, normalmente, resolvido carregando mais dados para as informações da audiência.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

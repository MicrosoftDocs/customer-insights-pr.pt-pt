---
title: Prever valor vitalício do cliente (CLV)
description: Prever o potencial de receita para clientes ativos no futuro.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610388"
---
# <a name="predict-customer-lifetime-value-clv"></a>Prever valor vitalício do cliente (CLV)

Preveja o valor potencial (receita) que os clientes ativos individuais irão trazer para o seu negócio através de um período de tempo definido no futuro. Esta predição ajuda-o a:

- Identificar clientes de alto valor e processar estas informações.
- Criar segmentos de clientes estratégicos com base no seu valor potencial para executar campanhas personalizadas com vendas, marketing e esforços de suporte direcionados.
- Orientar o desenvolvimento do produto focando-se em caraterísticas que aumentam o valor do cliente.
- Otimizar a estratégia de vendas ou de marketing e alocar o orçamento com mais precisão para a divulgação do cliente.
- Reconhecer e dar prémios a clientes de alto valor através de programas de fidelização ou recompensas.

Determinar o significado de CLV para a sua empresa. Suportamos a predição de CLV baseada em transações. O valor previsto de um cliente baseia-se no histórico de transações comerciais. Considere criar vários modelos com diferentes preferências de entrada e compare os resultados do modelo para ver qual o cenário de modelo que melhor se adequa às necessidades do seu negócio.

> [!TIP]
> Experimente o predição de CLV utilizando dados de amostra: [Guia de amostra de predição do Valor Vitalício do Cliente (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, permissões de [Contribuidor](permissions.md)
- Pelo menos, 100 clientes exclusivos, de preferência mais de 10.000 clientes
- Identificador de Cliente: um identificador exclusivo para combinar transações com um cliente individual
- Pelo menos, um anos de histórico de transações. de preferência, dois a três anos. Idealmente, pelo menos, duas a três transações por ID de cliente, de preferência em várias datas. O histórico de transações tem de incluir:
  - **ID da Transação**: identificador exclusivo de cada transação
  - **Data da transação**: data, ou carimbo de data/hora de cada transação
  - **Montante da transação**: valor monetário (por exemplo, receitas ou margem de lucro) de cada transação
  - **Etiqueta atribuída a devoluções**: valor true/false booleano que significa se a transação é uma devolução
  - **ID do produto**: ID do Produto envolvido na transação
- Dados sobre as atividades do cliente:
  - **Chave primária**: identificador exclusivo para uma atividade
  - **Carimbo de data/hora**: data e hora do evento identificadas pela chave primária
  - **Evento (nome da atividade)**: nome do evento que pretende utilizar
  - **Detalhes (montante ou valor)**: detalhes sobre a atividade do cliente
- Dados adicionais, tais como:
  - Atividades Web: histórico de visitas ao site ou histórico de e-mails
  - Atividades de fidelização: acumulação de pontos de recompensa de fidelidade e histórico de redenção
  - Registo de suporte ao cliente: chamada de serviço, reclamação ou histórico de devoluções
  - Informações de perfil de cliente
- Menos de 20% de valores em falta em campos obrigatórios

> [!NOTE]
> Apenas uma entidade de histórico de transações pode ser configurada. Se existirem várias entidades de compra ou de transação, pode combiná-las no Power Query antes da ingestão de dados.

## <a name="create-a-customer-lifetime-value-prediction"></a>Criar um predição do Valor Vitalício do Cliente

Selecione **Guardar rascunho** a qualquer momento para guardar a predição como rascunho. A predição de rascunho é apresentada no separador **A minhas predições**.

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** no mosaico **Valor vitalício do cliente**.

1. Selecione **Introdução**.

1. **Nomeie este modelo** e o **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Seguinte**.

### <a name="define-model-preferences"></a>Definir preferências de modelo

1. Defina um **Período de tempo de predição** para definir até onde pretende prever o CLV. Por predefinição, a unidade é definida como meses.

   > [!TIP]
   > Para prever com precisão o CLV para o período de tempo definido, é necessário um período comparável de dados históricos. Por exemplo, se quiser prever CLV para os próximos 12 meses, tenha, pelo menos, 18 a 24 meses de dados históricos.

1. Defina o intervalo de tempo em que um cliente deve ter tido pelo menos uma transação a considerar ativa. O modelo apenas prevê o CLV para **Clientes ativos**.
   - **Deixe o modelo calcular o intervalo de compra (recomendado)**: o modelo analisa os seus dados e determina um período de tempo baseado em compras históricas.
   - **Definir intervalo manualmente**: período de tempo para a sua definição de um cliente ativo.

1. Defina a percentil do **Cliente de alto valor**.
    - **Cálculo do modelo (recomendado)**: o modelo utiliza a regra 80/20. A percentagem de clientes que contribuíram para uma receita acumulada de 80% para o seu negócio no período histórico são considerados clientes de alto valor. Normalmente, menos de 30% a 40% de clientes contribuem para uma receita acumulada de 80%. No entanto, este número pode variar dependendo do seu negócio e do seu setor.
    - **Percentagem dos clientes ativos principais**: percentil específico para um cliente de alto valor. Por exemplo, introduza **25** para definir clientes de alto valor como os principais 25% dos futuros clientes pagadores.

    Se o seu negócio define clientes de alto valor de uma forma diferente, [diga-nos, pois gostaríamos de saber](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Selecione **Seguinte**.

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** para **Histórico de transações do cliente**.

1. Selecione o tipo de atividade semântica **SalesOrder** ou **SalesOrderLine** que contém o histórico de transações. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos de atividade foram mapeados semanticamente quando a atividade foi criada, escolha os atributos ou a entidade específicos em que gostaria que o cálculo se focasse. Se o mapeamento semântico não ocorrer, selecione **Editar** e mapeie os dados.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Adicionar dados obrigatórios ao modelo de CLV":::

1. Selecione **Seguinte** e reveja os atributos necessários para este modelo.

1. Selecione **Guardar**.

1. Adicione mais atividades ou selecione **Seguinte**.

### <a name="add-optional-activity-data"></a>Adicionar dados de atividade opcionais

Os dados que refletem as principais interações do cliente (como Web, suporte ao cliente e registos de eventos) adicionam contexto aos registos de transações. Mais padrões encontrados nos dados da atividade do seu cliente podem melhorar a precisão das predições.

1. Selecione **Adicionar dados** sob **Fomentar informações do modelo com dados de atividade adicionais**.

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está a adicionar. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos de atividade foram mapeados quando a atividade foi criada, escolha os atributos ou a entidade específicos em que gostaria que o cálculo se focasse. Se o mapeamento não ocorrer, selecione **Editar** e mapeie os dados.

1. Selecione **Seguinte** e reveja os atributos necessários para este modelo.

1. Selecione **Guardar**.

1. Selecione **Seguinte**.

1. [Adicione dados opcionais de clientes](#add-optional-customer-data) ou selecione **Seguinte** e aceda a [Definir agenda de atualização](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Adicionar dados de cliente opcionais

Selecione a partir dos 18 atributos de perfil de cliente utilizados comummente para incluir como entrada no modelo. Estes atributos podem levar a resultados de modelo mais personalizados, relevantes e acionáveis para os casos de utilização do negócio.

Por exemplo: a Contoso Coffee pretende prever o valor vitalício dos clientes para visar os clientes de elevado valor com uma oferta personalizada relacionada com o lançamento da nova máquina de café. A Contoso utiliza o modelo CLV e adiciona os 18 atributos de perfil de cliente para ver quais os fatores que influenciam os seus clientes de maior valor. Concluem que a localização do cliente é o fator mais influente para estes clientes.
Com estas informações, organizam um evento local para o lançamento da máquina de café e fazem uma parceria com fornecedores locais para fazerem ofertas personalizadas e oferecerem uma experiência especial no evento. Sem estas informações, a Contoso poderá ter enviado apenas e-mails de marketing genéricos e perdido a oportunidade de personalizar para este segmento local dos seus clientes de elevado valor.

1. Selecione **Adicionar dados** sob **Fomentar ainda mais informações do modelo com dados adicionais do cliente**.

1. Para **Entidade**, escolha **Cliente: CustomerInsights** para selecionar o perfil de cliente unificado que mapeia para dados de atributo do cliente. Para **ID de cliente**, escolha **System.Customer.CustomerId**.

1. Mapeie mais campos se os dados estiverem disponíveis nos seus perfis de cliente unificados.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exemplo de campos mapeados para dados de perfil de cliente.":::

1. Selecione **Guardar**.

1. Selecione **Seguinte**.

### <a name="set-update-schedule"></a>Definir agenda de atualização

1. Escolha a frequência para reeducar o modelo com base nos dados mais recentes. Esta definição é importante para atualizar a precisão das previsões à medida que novos dados são ingeridos para o Customer Insights. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Rever e executar a configuração do modelo

O passo **Rever e executar** mostra um resumo da configuração e fornece uma oportunidade de efetuar alterações antes de criar a predição.

1. Selecione **Editar** em qualquer um dos passos para rever e efetuar quaisquer alterações.

1. Se estiver satisfeito com as suas seleções, selecione **Guardar e executar** para começar a executar o modelo. Selecionar **Concluído**. O separador **As minhas predições** é apresentado enquanto a predição está a ser criada. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver resultados da predição

1. Aceda a **Inteligência** > **Predições**.

1. No separador **As minhas predições**, selecione a predição que pretende ver.

Existem três secções primárias de dados dentro da página de resultados.

- **Desempenho do modelo de preparação**: as notas A, B e C indicam o desempenho da predição e podem ajudá-lo a tomar a decisão de utilizar os resultados armazenados na entidade de saída.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imagem da caixa de informação de nível do modelo com o nível A.":::

  O Customer Insights avalia o desempenho do modelo de IA em prever os clientes de alto valor em comparação com um modelo de linha de base.

  Os níveis são determinados com base nas seguintes regras:
  - **A** quando o modelo previu com precisão, pelo menos, 5% mais clientes de alto valor em comparação com o modelo de base.
  - **B** quando o modelo previu com precisão entre 0% a 5% mais clientes de alto valor em comparação com o modelo de base.
  - **C** quando o modelo previu com precisão menos clientes de alto valor em comparação com o modelo de base.
  
  Selecione [**Conhecer esta classificação**](#learn-about-the-score) para abrir o painel **Classificação do modelo** mostra mais detalhes sobre o desempenho do modelo de IA e o modelo de linha de base. Irá ajudá-lo a entender melhor as métricas de desempenho do modelo subjacente e como a nota do desempenho final do modelo foi derivado. O modelo de base utiliza uma abordagem não baseada em IA para calcular o valor vitalício do cliente baseado principalmente em compras históricas feitas pelos clientes.

- **Valor de clientes por percentil**: clientes de baixo valor e de alto valor são apresentados num gráfico. Paire o cursor sobre as barras no histograma para ver o número de clientes em cada grupo e a média de CLV desse grupo. Opcionalmente, pode [criar segmentos de clientes](prediction-based-segment.md) com base nas suas previsões de CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Valor dos clientes por percentil para o modelo de CLV":::

- **Fatores mais influentes**: vários fatores são considerados ao criar a sua predição de CLV com base nos dados de entrada fornecidos ao modelo de IA. Cada um dos fatores tem a sua importância calculada para as previsões agregadas que um modelo cria. Utilize estes fatores para ajudar a validar os resultados da sua predição. Estes fatores também fornecem mais informações sobre os fatores mais influentes que contribuíram para a predição de CLV em todos os seus clientes.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Fatores mais influentes para o modelo de CLV":::

### <a name="learn-about-the-score"></a>Conhecer a classificação

A fórmula padrão utilizada para calcular o CLV pelo modelo de base:

 _**CLV para cada cliente** = Compra média mensal feita pelo cliente na janela de cliente ativo * Número de meses no período de predição de CLV * Taxa de retenção geral de todos os clientes_

O modelo de IA é comparado com o modelo de base com base em duas métricas de desempenho do modelo.
  
- **Taxa de sucesso na predição de clientes de valor elevado**

  Veja a diferença na predição de clientes de alto valor utilizando o modelo de IA em comparação com o modelo de base. Por exemplo, uma taxa de sucesso de 84% significa que de todos os clientes de alto valor nos dados de preparação, o modelo de IA foi capaz de capturar com precisão 84%. Em seguida, comparamos esta taxa de sucesso com a taxa de sucesso do modelo de base para reportar a mudança relativa. Este valor é usado para atribuir um nível ao modelo.

- **Métricas de erro**

  Consulte o desempenho geral do modelo em termos de erro na predição de valores futuros. Utilizamos a métrica geral do Erro do Desvio da Raiz Quadrada Média (RMSE) para avaliar este erro. A RMSE é uma forma padrão de medir o erro de um modelo na predição de dados quantitativos. A RMSE do modelo de IA é comparado com a RMSE do modelo de base e a diferença relativa é reportada.

O modelo de IA dá prioridade à classificação precisa dos clientes de acordo com o valor que trazem para o seu negócio. Assim, apenas a taxa de sucesso da predição de clientes de alto valor é usada para obter o nível final do modelo. A métrica RMSE é sensível a valores atípicos. Em cenários em que tem uma pequena percentagem de clientes com valores de compra extraordinariamente elevados, a métrica geral da RMSE pode não dar a imagem completa do desempenho do modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]

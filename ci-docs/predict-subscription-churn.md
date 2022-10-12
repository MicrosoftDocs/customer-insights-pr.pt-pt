---
title: Prever abandono de subscrições (contém vídeo)
description: Preveja se um cliente está em risco por ter deixado de utilizar os produtos ou serviços de subscrição da sua empresa.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610250"
---
# <a name="predict-subscription-churn"></a>Prever o abandono de subscrições

Preveja se um cliente está em risco por ter deixado de utilizar os produtos ou serviços de subscrição da sua empresa. Dados de subscrição incluem subscrições ativas e inativas para cada cliente, pelo que existem múltiplas entradas por ID de cliente.

Tem de ter conhecimento do negócio para entender o que o abandono significa para o seu negócio. Apoiamos definições de abandono baseadas em tempo, o que significa que um cliente é considerado como tendo alterado um período de tempo após o fim da sua subscrição.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Experimente a predição de abandono de subscrições utilizando dados de amostra: [Guia de amostra de predição do abandono de subscrições](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões do contribuinte](permissions.md).
- Pelo menos, 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos.
- Identificador de Cliente, um identificador exclusivo para corresponder subscrições com os seus clientes.
- Dados de subscrição para, pelo menos, o dobro da janela de tempo selecionada. De preferência, dois a três anos de dados de subscrição. O histórico de subscrições tem de incluir:
  - **ID da Subscrição:** identificador exclusivo de uma subscrição.
  - **Data de Fim da Subscrição:** data em que a subscrição expira para o cliente.
  - **Data de Início da Subscrição:** data em que a subscrição inicia para o cliente.
  - **Data da Transação:** data em que ocorreu uma alteração à subscrição. Por exemplo, um cliente comprando ou cancelando uma subscrição.
  - **É uma subscrição recorrente:** campo booleano true/false que determina se a subscrição vai renovar com o mesmo ID de subscrição sem intervenção do cliente.
  - **Frequência da Periodicidade (em meses):** para subscrições recorrentes, o mês em que a subscrição será renovada. Por exemplo, uma subscrição anual que renova automaticamente para um cliente todos os anos por mais um ano tem o valor 12.
  - **Montante da Subscrição:** montante da moeda que um cliente paga pela renovação da subscrição. Pode ajudar a identificar padrões para diferentes níveis de subscrições.
- Pelo menos, dois registos de atividade para 50% dos clientes para os quais pretende calcular o abandono. Atividades do cliente podem incluir:
  - **Chave primária:** identificador exclusivo para uma atividade. Por exemplo, uma visita ao site ou um registo de utilização mostrando que o cliente viu um episódio de programa de TV.
  - **Carimbo de data/hora:** data e hora do evento identificadas pela chave primária.
  - **Evento:** nome do evento que pretende utilizar. Por exemplo, um campo chamado "UserAction" num serviço de vídeo de transmissão em fluxo pode ter o valor de "Visualizado".
  - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo chamado "ShowTitle" num serviço de vídeo de transmissão em fluxo pode ter o valor de um vídeo que o cliente visualizou.
- Menos de 20% de valores em falta no campo de dados da entidade fornecida.

## <a name="create-a-subscription-churn-prediction"></a>Criar um previsão de abandono de subscrição

Selecione **Guardar rascunho** a qualquer momento para guardar a predição como rascunho. A predição de rascunho é apresentada no separador **A minhas predições**.

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** no mosaico **Modelo de abandono de clientes**.

1. Selecione **Subscrição** para o tipo de abandono e, em seguida, **Começar**.

1. **Nomeie este modelo** e o **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Seguinte**.

### <a name="define-customer-churn"></a>Definir abandono do cliente

1. Insira o número de **Dias desde que a subscrição terminou** que o seu negócio considera um cliente em estado de abandono. Este período é tipicamente associado a atividades empresariais como ofertas ou outros esforços de marketing tentando evitar a perda do cliente.

1. Introduza o número de **Dias para olhar para o futuro para prever o abandono**. Por exemplo, prever o risco de abandono para os seus clientes durante os próximos 90 dias para se alinhar com os seus esforços de retenção de marketing. Prever o risco de abandono por períodos de tempo mais longos ou mais curtos pode dificultar o processamento dos fatores do seu perfil de risco de abandono, dependendo dos requisitos específicos do seu negócio.

1. Selecione **Seguinte**.

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** para **Histórico de subscrições**.

1. Selecione o tipo de atividade semântica **Subscrição** que contém as informações de histórico de subscrição necessárias. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos de atividade foram mapeados semanticamente quando a atividade foi criada, escolha os atributos ou a entidade específicos em que gostaria que o cálculo se focasse. Se o mapeamento semântico não ocorrer, selecione **Editar** e mapeie os dados.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Adicionar dados obrigatórios ao modelo de Abandono de subscrições":::

1. Selecione **Seguinte** e reveja os atributos necessários para este modelo.

1. Selecione **Guardar**.

1. Selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que fornece as informações de atividade do cliente. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos de atividade foram mapeados semanticamente quando a atividade foi criada, escolha os atributos ou a entidade específicos em que gostaria que o cálculo se focasse. Se o mapeamento semântico não ocorrer, selecione **Editar** e mapeie os dados.

1. Selecione **Seguinte** e reveja os atributos necessários para este modelo.

1. Selecione **Guardar**.

1. Adicione mais atividades ou selecione **Seguinte**.

### <a name="set-update-schedule"></a>Definir agenda de atualização

1. Escolha a frequência para reeducar o modelo. Esta definição é importante para atualizar a precisão das previsões à medida que novos dados são ingeridos no Customer Insights. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Rever e executar a configuração do modelo

O passo **Rever e executar** mostra um resumo da configuração e fornece uma oportunidade de efetuar alterações antes de criar a predição.

1. Selecione **Editar** em qualquer um dos passos para rever e efetuar quaisquer alterações.

1. Se estiver satisfeito com as suas seleções, selecione **Guardar e executar** para começar a executar o modelo. Selecionar **Concluído**. O separador **As minhas predições** é apresentado enquanto a predição está a ser criada. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver resultados da predição

1. Aceda a **Inteligência** > **Predições**.

1. No separador **As minhas predições**, selecione a predição que pretende ver.

Existem três secções primárias de dados dentro da página de resultados:

- **Desempenho do modelo de preparação**: as notas A, B e C indicam o desempenho da predição e podem ajudá-lo a tomar a decisão de utilizar os resultados armazenados na entidade de saída.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Imagem da caixa de informação de nível do modelo com o nível A.":::

  Os níveis são determinados com base nas seguintes regras:
  - **A** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é superior à taxa de abandono média histórica em, pelo menos, 10%.
  - **B** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é até 10% superior à taxa de abandono média histórica.
  - **C** quando o modelo previu com precisão menos de 50% das previsões totais, ou quando a percentagem de previsões precisas para os clientes que se abandonaram é inferior à taxa de abandono média histórica.
  
- **Probabilidade de abandono (número de clientes)**: grupos de clientes com base no risco previsto de abandono. Opcionalmente, pode [criar segmentos de clientes](prediction-based-segment.md) com risco de abandono elevado. Estes segmentos ajudam a entender onde o seu limite dever ser para a adesão ao segmento.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Gráfico mostrando distribuição dos resultados de abandono, divididos em intervalos de 0 a 100%":::

- **Fatores mais influentes:** Há muitos fatores que são tidos em conta na criação da sua previsão. Cada um dos fatores tem a sua importância calculada para as predições agregadas que um modelo cria. Utilize estes fatores para ajudar a validar os resultados da sua predição. Ou utilize estas informações mais tarde para [criar segmentos](.//prediction-based-segment.md) que possam ajudar a influenciar o risco de abandono para os clientes.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Lista a mostrar fatores influentes e a sua importância na previsão do resultado.":::

> [!NOTE]
> Na entidade de saída para este modelo, *ChurnScore* é a probabilidade prevista de abandono e *IsChurn* é uma etiqueta binária baseada em *ChurnScore* com limiar de 0,5. Se este limiar predefinido não funcionar para o seu cenário, pode [criar um novo segmento](segments.md) com o seu limiar preferido. Para ver a classificação de abandono, aceda a **Dados** > **Entidades** e veja o separador de dados para a entidade de saída que definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]

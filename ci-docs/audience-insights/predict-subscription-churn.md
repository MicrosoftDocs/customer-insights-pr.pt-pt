---
title: Predição de abandono de subscrições (Vídeo)
description: Preveja se um cliente está em risco por ter deixado de utilizar os produtos ou serviços de subscrição da sua empresa.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 1ef2ff642731ee1ba0a142433745fc5a5b398c88
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/10/2021
ms.locfileid: "7904003"
---
# <a name="subscription-churn-prediction-preview"></a>Previsão de abandono de subscrição (pré-visualização)

A previsão de abandono de subscrição ajuda a prever se um cliente está em risco por ter deixado de utilizar os produtos ou serviços de subscrição da sua empresa. Pode criar uma nova previsão de abandono de subscrição na página **Informações** > **Previsões**. Selecione **Minhas previsões** para ver outras previsões que criou.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Experimente o tutorial para uma previsão de rotatividade de subscrição utilizando dados de amostra: [Guia de previsão da rotatividade da subscrição](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões do contribuinte](permissions.md).
- Conhecimento de negócios para entender o que a abandono significa para o seu negócio. Apoiamos definições de abandono baseadas em tempo, o que significa que um cliente é considerado como tendo alterado um período de tempo após o fim da sua subscrição.
- Dados sobre as suas subscrições e o respetivo histórico:
    - Identificadores de subscrição para distinguir subscrições.
    - Identificadores de clientes para combinar subscrições com os seus clientes.
    - Datas do evento de subscrição, que definem datas de início, datas de fim e as datas em que os eventos de subscrição ocorreram.
    - Informações de subscrição para definir se é uma subscrição recorrente e com que frequência renova.
    - O esquema de dados semânticos para subscrições requer as seguintes informações:
        - **ID da Subscrição:** um identificador exclusivo de uma subscrição.
        - **Data de Fim da Subscrição:** A data em que a subscrição expira para o cliente.
        - **Data de Início da Subscrição:** A data em que a subscrição inicia para o cliente.
        - **Data da Transação:** A data em que ocorreu uma alteração de subscrição. Por exemplo, um cliente comprando ou cancelando uma subscrição.
        - **É uma subscrição recorrente:** Um campo booleano true/false que determina se a subscrição vai renovar com o mesmo ID de subscrição sem intervenção do cliente
        - **Frequência da Periodicidade (em meses):** Para subscrições recorrentes, é o período para o qual a subscrição irá renovar. Está representado em meses. Por exemplo, uma subscrição anual que renova automaticamente para um cliente todos os anos por mais um ano tem o valor 12.
        - (Opcional) **Montante da Subscrição:** O valor da moeda que um cliente paga pela renovação da subscrição. Pode ajudar a identificar padrões para diferentes níveis de subscrições.
- Dados sobre as atividades do cliente:
    - Identificadores de atividade para distinguir atividades do mesmo tipo.
    - Identificadores de clientes para mapear atividades para os seus clientes.
    - Informações de atividade que contêm o nome e a data da atividade.
    - O esquema de dados semânticos para atividades do cliente inclui:
        - **Chave primária:** um identificador exclusivo para uma atividade. Por exemplo, uma visita ao site ou um registo de utilização mostrando que o cliente viu um episódio de programa de TV.
        - **Carimbo de data/hora:** A data e a hora do evento identificadas pela chave primária.
        - **Evento:** o nome do evento que pretende utilizar. Por exemplo, um campo chamado "UserAction" num serviço de vídeo de transmissão em fluxo pode ter o valor de "Visualizado".
        - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo chamado "ShowTitle" num serviço de vídeo de transmissão em fluxo pode ter o valor de um vídeo que o cliente visualizou.
- Características de dados sugeridos:
    - Dados históricos suficientes: dados de subscrição para, pelo menos, o dobro da janela de tempo selecionada. De preferência, dois a três anos de dados de subscrição.
    - Estado de subscrição: os dados incluem subscrições ativas e inativas para cada cliente, pelo que existem múltiplas entradas por ID de cliente.
    - Número de clientes: pelo menos, 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos. O modelo falhará com menos de 10 clientes e dados históricos insuficientes.
    - Totalidade dos dados: menos de 20% de valores em falta no campo de dados da entidade fornecida.
   
   > [!NOTE]
   > Vai precisar de, pelo menos, dois registos de atividade para 50% dos clientes para os quais pretende calcular o abandono.

## <a name="create-a-subscription-churn-prediction"></a>Criar um previsão de abandono de subscrição

1. Nas informações de audiência, vá a **Inteligência** > **Predições**.
1. Selecione o mosaico **Modelo de abandono de subscrição (pré-visualização)** e selecione **Utilizar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Mosaico do modelo de abandono da subscrição com o botão Utilizar este modelo.](media/subscription-churn-usethismodel.PNG "Mosaico do modelo de abandono da subscrição com o botão Utilizar este modelo")

### <a name="name-model"></a>Atribuir nome ao modelo

1. Forneça um nome para o modelo para distingui-lo de outros modelos.
1. Forneça um nome para a entidade de saída usando apenas letras e números, sem espaços. É o nome que a entidade modelo vai usar. Em seguida, selecione **Seguinte**.

### <a name="define-customer-churn"></a>Definir abandono de clientes

1. Insira o número de **Dias desde que a subscrição terminou** que o seu negócio considera um cliente em estado de abandono. Este período é tipicamente comparado a atividades empresariais como ofertas ou outros esforços de marketing tentando evitar a perda do cliente.
1. Insira o número de **Dias para investigar o futuro para prever o abandono** para definir uma janela para prever o qual prever o abandono. Por exemplo, para prever o risco de abandono para os seus clientes nos próximos 90 dias para se alinhar com os seus esforços de retenção de marketing. Prever o risco de abandono por períodos de tempo mais longos ou mais curtos pode dificultar o processamento dos fatores do seu perfil de risco de abandono, dependendo dos requisitos específicos do seu negócio. Selecione **Seguinte** para continuar
   >[!TIP]
   > Pode selecionar **Guardar e fechar** a qualquer momento para guardar a previsão como rascunho. Vais encontrar o rascunho de previsão no separador **Minhas previsões** para continuar.

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** para o **Histórico de subscrições** e selecione a entidade que fornece as informações do histórico de subscrições, conforme descrito nos [pré-requisitos](#prerequisites).
1. Se os campos abaixo não estiverem preenchidos, configuure a relação da sua entidade de histórico de subscrições com a entidade Cliente.
    1. Selecione a **Entidade de histórico de subscrições**.
    1. Selecione o **Campo** que identifica o cliente na entidade de histórico de subscrições. Tem de se relacionar com o ID do cliente primário da sua entidade Cliente.
    1. Selecione a **entidade Cliente** que corresponde à sua entidade principal de cliente.
    1. Introduza um nome que descreva a relação.
       > [!div class="mx-imgBorder"]
       > ![Página de histórico de subscrições mostrando a criação de uma relação com o cliente.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Página de histórico de subscrições mostrando a criação de uma relação com o cliente")
1. Selecione **Seguinte**.
1. Mapear os campos semânticos para atributos dentro da sua entidade de histórico de subscrições e selecione **Guardar**. Para descrições dos campos, veja os [pré-requisitos](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Página de histórico de subscrições mostrando atributos semânticos que são mapeados para campos na entidade de histórico de subscrições selecionada.](media/subscription-churn-subscriptionhistorymapping.PNG "Página de histórico de subscrições mostrando atributos semânticos que são mapeados para campos na entidade de histórico de subscrições selecionada")
1. Selecione **Adicionar dados** para as **Atividades do cliente** e selecione a entidade que fornece as informações de atividades do cliente, conforme descrito nos pré-requisitos.
1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está a configurar.  Selecione **Criar nova** e forneça um nome se não vir uma opção que corresponda ao tipo de atividade de que necessita.
1. Terá de configurar a relação da sua entidade de atividade do cliente com a entidade Cliente.
    1. Selecione o campo que identifica o cliente na tabela de atividade do cliente, que pode estar diretamente relacionado com o ID do cliente primário da sua entidade Cliente.
    1. Selecione a entidade Cliente que corresponde à sua entidade principal Cliente
    1. Introduza um nome que descreva a relação.
1. Selecione **Seguinte**.
1. Mapear os campos semânticos para atributos dentro da sua entidade de atividades do cliente e selecione **Guardar**. Para descrições dos campos, veja os [pré-requisitos](#prerequisites).
1. (Opcional) Se tiver outras atividades de cliente que gostaria de incluir, repita os passos acima.
   > [!div class="mx-imgBorder"]
   > ![Definir a relação entre entidades.](media/subscription-churn-customeractivitiesmapping.PNG "Página de atividades do cliente mostrando atributos semânticos que são mapeados para campos na entidade de atividades do cliente selecionada")
1. Selecione **Seguinte**.

### <a name="set-schedule-and-review-configuration"></a>Definir agenda e rever configuração

1. Defina uma frequência para reeducar o modelo. Esta definição é importante para atualizar a exatidão das predições à medida que novos dados são ingeridos nas informações de audiência. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.
1. Selecione **Seguinte**.
1. Rever a configuração. Pode voltar a qualquer parte da configuração de previsão selecionando **Editar** por abaixo do valor indicado. Ou pode selecionar um passo de configuração a partir do indicador de progresso.
1. Se todos os valores estiverem configurados corretamente, selecione **Guardar e executar** para iniciar o processo de previsão. No separador **Minhas previsões**, pode ver o estado das suas previsões. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Rever um estado de previsão e resultados

1. Vá para o separador **Minhas previsões** em **Informações** > **Previsões**.
   > [!div class="mx-imgBorder"]
   > ![Vista da página Minhas Previsões.](media/subscription-churn-mypredictions.PNG "Vista da página Minhas Previsões")
1. Selecione a predição que pretende rever.
   - **Nome da previsão:** O nome da previsão fornecida ao criá-la.
   - **Tipo de previsão:** O tipo de modelo utilizado para a previsão
   - **Entidade de saída:** Nome da entidade para armazenar a saída da previsão. Pode encontrar uma entidade com este nome em **Dados** > **Entidades**.    
     Na entidade de saída, *ChurnScore* é a probabilidade prevista de abandono e *IsChurn* é uma etiqueta binária baseada em *ChurnScore* com limiar de 0,5. O limiar predefinido pode não funcionar para o seu cenário. [Crie um novo segmento](segments.md#create-a-new-segment) com o seu limiar preferido.
   - **Campo previsto:** Este campo é povoado apenas para alguns tipos de previsões, e não é usado na previsão de abandono de subscrição.
   - **Estado:** O estado atual da execução da previsão.
        - **Em fila:** a previsão está neste momento à espera que outros processos sejam executados.
        - **Atualização:** A previsão está atualmente a executar a fase de processamento "pontuação" para produzir resultados que fluirão para a entidade de saída.
        - **Falhada:** a previsão falhou. Selecione **Registos** para obter mais detalhes.
        - **Bem sucedida:** a previsão foi bem sucedida. Selecione **Ver** por baixo das reticências verticais para rever a previsão
   - **Editada:** A data da em que a configuração para a previsão foi alterada.
   - **Última atualização:** A data em que a previsão foi atualizada resulta na entidade de saída.
1. Selecione as reticências verticais ao lado da previsão que pretende rever os resultados e selecione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista das opções no menu de reticências verticais para uma previsão, incluindo Editar, Atualizar, Ver, Registos e Eliminar.](media/subscription-churn-verticalellipses.PNG "Vista das opções no menu de reticências verticais para uma previsão, incluindo Editar, Atualizar, Ver, Registos e Eliminar")
1. Existem três secções primárias de dados dentro da página de resultados:
    1. **Desempenho do modelo de preparação:** A, B ou C são possíveis pontuações. Esta pontuação indica o desempenho da previsão, e pode ajudá-lo a tomar a decisão de usar os resultados armazenados na entidade de saída.
        - As pontuações são determinadas com base nas seguintes regras:
            - **A** quando o modelo previu com precisão pelo menos 50% do total das previsões, e quando a percentagem de previsões precisas para os clientes que abandonaram é superior à taxa média histórica de abandono em, pelo menos, 10% da taxa média histórica.
            - **B** quando o modelo previu com precisão pelo menos 50% do total das previsões, e quando a percentagem de previsões precisas para os clientes que abandonaram é até 10% superior à taxa média histórica de taxa abandono da taxa média histórica.
            - **C** quando o modelo previu com precisão menos 50% das previsões totais, ou quando a percentagem de previsões precisas para os clientes que se abandonaram é inferior à taxa de abandono média histórica.
               > [!div class="mx-imgBorder"]
               > ![Vista do resultado do desempenho do modelo.](media/subscription-churn-modelperformance.PNG "Vista do resultado do desempenho do modelo")
    1. **Probabilidade de abandono (número de clientes):** Grupos de clientes com base no risco previsto de abandono. Estes dados podem ajudá-lo mais tarde se quiser criar um segmento de clientes com elevado risco de abandono. Estes segmentos ajudam a entender onde o seu limite dever ser para a adesão ao segmento.
       > [!div class="mx-imgBorder"]
       > ![Gráfico mostrando distribuição dos resultados de abandono, divididos em intervalos de 0 a 100%.](media/subscription-churn-resultdistribution.PNG "Gráfico mostrando distribuição dos resultados de abandono, divididos em intervalos de 0 a 100%")
    1. **Fatores mais influentes:** Há muitos fatores que são tidos em conta na criação da sua previsão. Cada um dos fatores tem a sua importância calculada para as previsões agregadas que um modelo cria. Pode utilizar estes fatores para ajudar a validar os resultados da sua previsão. Ou pode usar estas informações mais tarde para [criar segmentos](segments.md) que possam ajudar a influenciar o risco de abandono para os clientes.
       > [!div class="mx-imgBorder"]
       > ![Lista a mostrar fatores influentes e a sua importância na previsão do resultado.](media/subscription-churn-influentialfactors.PNG "Lista mostrando fatores influentes e a sua importância na previsão do resultado")

## <a name="manage-predictions"></a>Gerir predições

É possível otimizar, resolver problemas, atualizar ou eliminar predições. Reveja um relatório de capacidade de utilização de dados de entrada para saber como tornar uma predição mais rápida e fiável. Para mais informações, consulte [Gerir predições](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

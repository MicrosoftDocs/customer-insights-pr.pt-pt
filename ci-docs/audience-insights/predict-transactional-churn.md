---
title: Predição de abandono transacional
description: Preveja se um cliente está em risco por ter deixado de comprar os seus produtos ou serviços.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644417"
---
# <a name="transactional-churn-prediction-preview"></a>Predição de abandono transacional (pré-visualização)

A previsão de abandono transacional ajuda a prever se um cliente não comprará mais os seus produtos ou serviços num determinado período de tempo. Pode criar novas predições de abandono em **Inteligência** > **Predições**. Selecione **Minhas previsões** para ver outras previsões que criou.

> [!TIP]
> Experimente o tutorial para uma predição de abandono transacional utilizando dados de amostra: [Guia de predição de abandono transacional (pré-visualização)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.
- Conhecimento de negócios para entender o que a abandono significa para o seu negócio. Apoiamos definições de abandono baseadas no tempo, o que significa que um cliente é considerado como tendo abandonado após um período de ausência de compras.
- Dados sobre as suas transações/compras e a sua história:
    - Identificadores de transações para distinguir compras/transações.
    - Identificadores de clientes para fazer corresponder as transações aos seus clientes.
    - As datas dos eventos da transação, que definem as datas em que a transação ocorreu.
    - O esquema de dados semânticos para compras/transações requer as seguintes informações:
        - **ID da transação:** Um identificador único de uma compra ou transação.
        - **Data da transação:** A data da compra ou transação.
        - **Valor da transação:** O valor monetário/valor numérico da transação/item.
        - (Opcional) **ID de produto único:** O ID do produto ou serviço adquirido se os seus dados estiverem ao nível do produto da linha.
        - (Opcional) **Se esta transação foi uma devolução:** Um campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** é negativo, também utilizaremos esta informação para inferir uma devolução.
- (Opcional) Dados sobre as atividades dos clientes:
    - Identificadores de atividade para distinguir atividades do mesmo tipo.
    - Identificadores de clientes para mapear atividades para os seus clientes.
    - Informações de atividade que contêm o nome e a data da atividade.
    - O esquema de dados semânticos para atividades do cliente inclui:
        - **Chave primária:** um identificador exclusivo para uma atividade. Por exemplo, uma visita ao website ou um registo de utilização que mostre que o cliente experimentou uma amostra do seu produto.
        - **Carimbo de data/hora:** A data e a hora do evento identificadas pela chave primária.
        - **Evento:** o nome do evento que pretende utilizar. Por exemplo, um campo chamado "UserAction" numa mercearia pode ser um cupão de utilização pelo cliente.
        - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo chamado "CouponValue" numa mercearia pode ser o valor monetário do cupão.

## <a name="create-a-transactional-churn-prediction"></a>Criar uma predição de abandono transacional

1. No Customer Insights, aceda a **Inteligência** > **Predições**.

1. Selecione o mosaico **Modelo de abandono do cliente (pré-visualização)** e selecione **Use este modelo**.
   
1. No painel **Modelo de abandono do cliente**, escolha **Transacional** e selecione **Iniciar**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de ecrã com opção transacional selecionada no painel do modelo de abandono do cliente.":::

### <a name="name-model"></a>Atribuir nome ao modelo

1. Forneça um nome para o modelo para distingui-lo de outros modelos.

1. Forneça um nome para a entidade de saída usando apenas letras e números, sem espaços. É o nome que a entidade modelo vai usar. 

1. Selecione **Seguinte**.

### <a name="define-customer-churn"></a>Definir abandono do cliente

1. Estabeleça uma margem de dias para predição do abandono no campo **Identificar clientes que possam abandonar nos próximos**. Por exemplo, prever o risco de abandono para os seus clientes durante os próximos 90 dias para se alinhar com os seus esforços de retenção de marketing. Prever o risco de abandono durante um período de tempo mais ou menos longo pode tornar mais difícil abordar os fatores no seu perfil de risco de abandono, mas depende das suas necessidades específicas de negócio. 
   >[!TIP]
   > Pode selecionar **Guardar e fechar** a qualquer momento para guardar a previsão como rascunho. Vais encontrar o rascunho de previsão no separador **Minhas previsões** para continuar.

1. Introduza o número de dias para definir o abandono no campo **Um cliente abandonou se não fez nenhuma compra em:**. Por exemplo, se um cliente não tiver feito quaisquer compras nos últimos 30 dias, elas podem ser consideradas como sendo de abandono para o seu negócio. 

1. Selecione **Seguinte** para continuar

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar datas** para **Histórico de compras** e escolher a entidade que fornece a informação sobre o histórico de transações/compras, tal como descrito no [pré-requisitos](#prerequisites).

1. Mapear os campos semânticos a atributos dentro da sua entidade de histórico de compras e selecione **Seguinte**. Para descrições dos campos, veja os [pré-requisitos](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapa de campos semânticos da entidade de compra.":::

1. ISe os campos abaixo não estiverem preenchidos, configure a relação da sua entidade de histórico de compras para a entidade Cliente.
    1. Selecione a **Entidade de histórico de compras**.
    1. Selecione o **Campo** que identifica o cliente na entidade do histórico de compras. Tem de se relacionar com o ID do cliente primário da sua entidade Cliente.
    1. Selecione a **entidade Cliente** que corresponde à sua entidade principal de cliente.
    1. Introduza um nome que descreva a relação.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Página de histórico de compras que mostra a criação de uma relação com o cliente.":::
   
1. Selecione **Seguinte**.

1. Opcionalmente, selecione **Adicionar dados** para **Atividades do cliente**. Escolher a entidade que fornece a informação sobre a atividade do cliente, tal como descrito nos pré-requisitos.

1. Mapear os campos semânticos a atributos dentro da sua entidade de atividade do cliente e selecione **Seguinte**. Para descrições dos campos, veja os [pré-requisitos](#prerequisites).

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está a configurar. Selecione **Criar novo** e escolher um tipo de atividade disponível ou criar um novo tipo.

1. Terá de configurar a relação da sua entidade de atividade do cliente com a entidade Cliente.
    1. Selecione o campo que identifica o cliente na tabela de atividades do cliente. Pode estar diretamente relacionado com o ID do cliente principal da sua entidade Cliente.
    1. Selecione a entidade Cliente que corresponde à sua entidade principal Cliente
    1. Introduza um nome que descreva a relação.

1. Selecione **Guardar**.

1. Se tiver outras atividades do cliente que gostaria de incluir, repita os passos acima.

1. Selecione **Seguinte**.

### <a name="set-schedule-and-review-configuration"></a>Definir agenda e rever configuração

1. Defina uma frequência para reeducar o modelo. Esta definição é importante para atualizar a exatidão das predições à medida que novos dados são ingeridos. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.

1. Rever a configuração da predição. Pode voltar aos passos anteriores, selecionando **Editar** no valor apresentado. Ou pode selecionar um passo de configuração a partir do indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Guardar e executar** para iniciar o processo de previsão. No separador **Minhas previsões**, pode ver o estado das suas previsões. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Rever um estado de previsão e resultados

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione a predição que pretende rever.
   - **Nome da predição:** Nome da predição fornecida na sua criação.
   - **Tipo de predição** Tipo de modelo utilizado para a predição
   - **Entidade de saída:** Nome da entidade para armazenar a saída da previsão. Pode encontrar uma entidade com este nome em **Dados** > **Entidades**.
   - **Campo da predição:** Este campo é povoado apenas para alguns tipos de predições, e não é usado na predição de abandono.
   - **Estado**: Estado da realização da predição.
        - **Em fila:** A predição está à espera de outros processos.
        - **Atualizar:** A predição está atualmente em curso para produzir resultados que irão fluir para a entidade de produção.
        - **Falhou:** A execução da predição falhou. [Rever os registos](#troubleshoot-a-failed-prediction) para mais detalhes.
        - **Sucesso:** A predição foi bem sucedida. Selecione **Ver** por baixo das reticências verticais para rever a previsão
   - **Editada:** A data da em que a configuração para a previsão foi alterada.
   - **Última atualização:** A data em que a previsão foi atualizada resulta na entidade de saída.

1. Selecione as reticências verticais ao lado da previsão que pretende rever os resultados e selecione **Ver**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Exibir controlo para ver os resultados de uma predição.":::   

1. Existem três secções primárias de dados dentro da página de resultados:
    1. **Desempenho do modelo de preparação:** A, B ou C são possíveis pontuações. Esta pontuação indica o desempenho da previsão, e pode ajudá-lo a tomar a decisão de usar os resultados armazenados na entidade de saída. As pontuações são determinadas com base nas seguintes regras:
         
         - **A** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é superior à base de referência em pelo menos 10%.
            
         - **B** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é até 10% superior à base de referência.
            
         - **C** quando o modelo previu com precisão menos de 50% do total das predições, ou quando a percentagem de predições exatas para os clientes que abandonaram é inferior à base de referência.
               
         - **Base de referência** toma a entrada do período de predição para o modelo (por exemplo, um ano) e o modelo cria diferentes frações de tempo dividindo-o por 2 até chegar a um mês ou menos. Utiliza estas frações para criar uma regra de negócio para clientes que não tenham efetuado compras neste período de tempo. Estes clientes são considerados como tendo abandonado. A regra empresarial baseada no tempo com a maior capacidade de predição de quem é suscetível de abandono é escolhida como modelo de base.
            
    1. **Probabilidade de abandono (número de clientes):** Grupos de clientes com base no risco previsto de abandono. Estes dados podem ajudá-lo mais tarde se quiser criar um segmento de clientes com elevado risco de abandono. Estes segmentos ajudam a entender onde o seu limite dever ser para a adesão ao segmento.
       
    1. **Fatores mais influentes:** Há muitos fatores que são tidos em conta na criação da sua previsão. Cada um dos fatores tem a sua importância calculada para as predições agregadas que um modelo cria. Pode utilizar estes fatores para ajudar a validar os resultados da sua previsão. Ou pode usar estas informações mais tarde para [criar segmentos](segments.md) que possam ajudar a influenciar o risco de abandono para os clientes.

## <a name="troubleshoot-a-failed-prediction"></a>Resolução de problemas de uma predição falhada

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione as reticências verticais ao lado da predição para a qual deseja ver os registos de erros.

1. Selecionar **Registos**.

1. Rever todos os erros. Existem vários tipos de erros que podem ocorrer, e estes descrevem que condição causou o erro. Por exemplo, um erro que não há dados suficientes para prever com precisão é, normalmente, resolvido carregando dados adicionais no Customer Insights.

## <a name="refresh-a-prediction"></a>Atualizar uma previsão

As previsões serão automaticamente atualizadas no mesmo [horário que as suas atualizações de dados](system.md#schedule-tab) como configurados nas definições. Também é possível atualizá-las manualmente.

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione as reticências verticais ao lado da previsão que pretende atualizar.

1. Selecione **Atualizar**.

## <a name="delete-a-prediction"></a>Eliminar uma previsão

A eliminação de uma predição também elimina a sua entidade de saída.

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione as reticências verticais ao lado da previsão que pretende eliminar.

1. Selecione **Eliminar**.

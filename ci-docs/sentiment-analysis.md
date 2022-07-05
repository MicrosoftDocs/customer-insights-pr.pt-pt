---
title: Analisar sentimentos para feedback do cliente (pré-visualização)
description: Aprenda a utilizar um modelo de análise de sentimentos no feedback do cliente no Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: af1afd3eff8a795a9e199b1c1d411b79dc2841b4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055550"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analisar sentimentos no feedback do cliente (pré-visualização)

Nos dias de hoje, os clientes esperam produtos, serviços e experiências de alta qualidade. Especialmente, clientes que partilham o seu feedback. É muito desafiante para as organizações analisarem um volume crescente de dados sem baixarem a precisão e sem um custo de mão-de-obra mais elevado. O Dynamics 365 Customer Insights oferece um modelo de análise de sentimentos para feedback do cliente que permite às organizações analisar os seus dados com mais precisão e a um custo mais baixo.

A análise de sentimentos permite-lhe sintetizar o sentimento do cliente e identificar os aspetos do negócio como oportunidades de melhoria. Esta funcionalidade do Customer Insights ajuda-o a compreender o que funciona bem e o que precisa de abordar. Concentre-se nas áreas de negócio mais relevantes e impactantes para melhorar a experiência para os seus clientes. Em última análise, pode ajudá-lo a impulsionar ações de negócio que permitem experiências que resultem em elevada satisfação e fidelização do cliente.

## <a name="overview"></a>Descrição geral

A funcionalidade de análise de sentimento gera dois insights derivados por ID do cliente. Uma pontuação de sentimento (de -5 a 5) e uma lista de aspetos de negócio aplicáveis (áreas de negócio) em conjunto ajudam-no a compreender melhor o feedback do cliente. 

Estas informações podem ajudá-lo a alcançar os seguintes resultados: 
- Obter uma descrição geral dos sentimentos do cliente em relação a uma marca ou organização
- Identificar clientes com sentimento negativo para focar as suas campanhas e compromissos e otimizar para um maior retorno  
- Identificar aspetos de negócio com problemas indicados pelos clientes  
- Segmentar clientes com base no respetivo sentimento para executar campanhas personalizadas com esforços de vendas, marketing e esforços direcionados
- Otimizar operações comerciais abordando áreas de preocupação ou oportunidades que foram mencionadas pelos clientes
- Reconhecer aspetos de negócio que têm bom desempenho e recompensar clientes felizes através de programas de fidelização e de promoção

Para garantir que pode confiar nos resultados dos modelos, fornecemos informações transparentes sobre como os modelos tomam decisões. Receberá uma lista de palavras que afetaram a decisão dos modelos de atribuir uma classificação de sentimentos particular ou aspeto de negócio a comentários de feedback.  

Utilizamos dois **Modelos de Processamento de Linguagem Natural (NLP)**: o primeiro atribui a cada comentário de feedback uma classificação de sentimento. O segundo modelo associa cada comentário a todos os aspetos de negócio aplicáveis. Os modelos são treinados em dados públicos de origens dos setores de redes sociais, retalho, restauração, produtos de consumo e automóvel.    
  
Os aspetos de negócio predefinidos para o modelo associado aos dados de feedback incluem:
-   Gestão de contas
-   Finalização e pagamento
-   Suporte ao cliente
-   Recolha na loja
-   Envio e recuperação de embalagens
-   Pré-encomenda
-   Preço
-   Privacidade e segurança
-   Promoções e recompensas
-   Recibo e garantia
-   Troca de devolução e cancelamento
-   Exatidão da conclusão
-   Qualidade do site/aplicação

> [!NOTE]
> Atualmente, apenas suportamos a análise de sentimentos no feedback do cliente em inglês. Serão suportados mais idiomas no futuro. Se o feedback noutros idiomas for carregado, o modelo ainda irá obter resultados. No entanto, estes resultados não serão precisos. 

## <a name="prerequisites"></a>Pré-requisitos

A análise de sentimentos baseia-se em dados de feedback de texto que passaram pelo [processo de unificação de dados](data-unification.md). Recomendamos vivamente que [configure previamente as suas entidades de dados de feedback como entidades de atividade de tipo semântico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Tipo de feedback). 

Para configurar um modelo de análise de sentimentos, é necessário, pelo menos, [Permissões de contribuinte](permissions.md).

O Customer Insights pode processar até 10 milhões de registos de feedback para uma única execução de modelo. O modelo pode analisar comentários de feedback até 128 palavras. Se um comentário de feedback for mais longo, a análise considera apenas as primeiras 128 palavras.

### <a name="data-requirements"></a>Requisitos de dados
  
Os atributos de dados seguintes são necessários:
- ID Unificado do Cliente (UCID) para corresponder registos de dados de feedback de texto a um cliente individual. Este ID é um resultado do [processo de unificação de dados](data-unification.md).
- ID dos Comentários
- Carimbo de data/hora do feedback
- Texto dos comentários   

> [!TIP]
> A análise de sentimento requer o feedback de texto dos seus clientes. Atualmente, apenas uma entidade de feedback pode ser configurada. Se existirem várias entidades de feedback, pode uni-las no Power Query antes de começar a ingestão de dados.

## <a name="configure-a-sentiment-analysis"></a>Configurar uma análise de sentimentos 

1. No Customer Insights, aceda a **Inteligência** > **Predições**.

1. No mosaico **Análise de sentimentos do cliente**, selecione **Utilizar modelo**.

1. No painel **Análise de sentimentos do cliente (pré-visualização)**, selecione **Começar**.

1. No passo **Nome do modelo**, forneça um **Nome** à sua análise. 

1. Forneça o **Nome da entidade de saída de aspeto do negócio** e o **Nome da entidade de saída de classificação de sentimentos** e, em seguida, selecione **Seguinte**.

1. No passo **Dados requeridos**, selecione **Adicionar dados**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Adicionar fluxo de dados no modelo de análise de sentimentos.":::

1. No painel **Adicionar dados**, escolha o tipo semântico **Feedback** da lista.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Passo de configuração para selecionar atividades de feedback para análise de sentimentos.":::

1. Selecione as atividades a utilizar nesta análise de sentimentos e, em seguida, selecione **Seguinte**.
 
1. Mapeie os atributos nos seus dados para os atributos do modelo. Selecione **Guardar** para aplicar as seleções. 

1. Vê o estado do mapeamento de dados. Selecione **Seguinte** para continuar. 

1. Na passo **Rever os seus detalhes do modelo**, valide a configuração da sua análise de sentimentos. Pode regressar a qualquer parte da configuração de predição. Selecione **Guardar e executar** para iniciar a análise. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Passo de revisão para o modelo de sentimentos a mostrar todos os itens configurados.":::

1. Selecione **Concluído** para sair da experiência de configuração. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizada. 

## <a name="review-analysis-status"></a>Rever estado da análise

1.  Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.
2.  Selecione a predição que pretende rever.
- **Nome da predição**: nome da predição fornecida na sua criação.
- **Tipo de predição**: tipo de modelo utilizado para a predição.
- **Entidade de saída**: nome da entidade para armazenar a saída da predição. Vá a **Dados** > **Entidades** para encontrar a entidade com este nome.
- **Campo previsto**: este campo é povoado apenas para alguns tipos de predições, e não é usado na predição do valor vitalício do cliente.
- **Estado**: estado da execução da predição.
  - **Em fila**: a predição está à espera que outros processos completem.
  - **A atualizar**: a predição está atualmente em execução para criar resultados que fluirão para a entidade de saída.
  - **Falhou**: a execução da predição falhou. Rever os registos para mais detalhes.
  - **Sucesso**: a predição foi bem sucedida. Selecione Ver sob as reticências verticais para rever os resultados predição.
- **Editada**: a data da em que a configuração para a predição foi alterada.
- **Última atualização**: a data em que a predição teve resultados atualizados na entidade de saída.

## <a name="manage-sentiment-analysis"></a>Gerir análise de sentimentos

Pode otimizar, resolver problemas, atualizar ou eliminar predições. Reveja um relatório de capacidade de utilização de dados de entrada para saber como tornar uma predição mais rápida e fiável. Para mais informações, consulte [Gerir predições](manage-predictions.md).

## <a name="review-analysis-results"></a>Rever resultados da análise
 
1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**. 
1. Selecione o nome da predição para a qual pretende rever os resultados. Neste caso, selecione a análise de sentimentos que pretende rever. 

### <a name="summary-tab"></a>Separador Resumo

Há quatro secções primárias de dados dentro da página de resultados. 

- **Classificação de sentimentos média**: ajuda-o a compreender o sentimento geral de todos os clientes. As classificações de sentimentos são agrupadas em três categorias: 
  1.    Negativo (-5 > 2)
  2.    Neutro (-1 > 1)
  3.    Positivo (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representação visual do sentimento do cliente geral.":::

- **Distribuição de clientes por classificação de sentimentos**: os clientes são categorizados pelos grupos Negativo, Neutro e Positivo, com base nas respetivas classificações de sentimentos. Paire o cursor do rato sobre as barras no histograma para ver o número de clientes e a classificação de sentimentos média em cada grupo. Estes dados podem ajudá-lo a [criar segmentos de clientes](segments.md) com base nas respetivas classificações de sentimentos.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gráfico de barras a mostrar o sentimento do cliente nos três grupos de sentimentos.":::

- **Classificação de sentimentos média ao longo do tempo**: o sentimento do cliente pode mudar ao longo do tempo. Fornecemos tendências nos sentimentos dos seus clientes para o intervalo de tempo dos seus dados. Esta vista pode ajudá-lo a avaliar o efeito de promoções sazonais, lançamentos de produtos ou outras intervenções com limite de tempo no sentimento do cliente. Consulte o gráfico selecionando o ano de juros do menu pendente. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gráfico histórico com a classificação do sentimento ao longo do tempo representada como uma linha.":::
 
- **Sentimento entre aspetos de negócio**: esta tabela enumera o sentimento médio entre os aspetos de negócio. Pode ajudá-lo a avaliar que aspetos do seu negócio já satisfazem clientes ou aspetos que requerem mais atenção. Os registos de feedback que não se alinham com nenhum dos aspetos de negócio suportados são categorizados sob **Outros**. Por predefinição, a tabela é ordenada alfabeticamente. Pode modificar a ordenação selecionando um cabeçalho de tabela.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista de aspetos de negócio com o valor de sentimento associado e o número de clientes que o mencionam.":::
 
  Selecione o nome de um aspeto de negócio para ver informações adicionais, como um aspeto de negócio ser identificado pelo modelo. Este painel contém duas partes: 

  - **Palavras influentes**: mostra as principais palavras que influenciaram a identificação do modelo de IA de um aspeto de negócio no feedback do cliente. 
    **Mostrar palavras ofensivas**: permite-lhe incluir palavras ofensivas na lista a partir de dados originais de feedback do cliente. Por predefinição, está desativado.  A máscara de palavras ofensivas utiliza tecnologia de um modelo de IA e pode não detetar todas as palavras ofensivas. Continuamos a iterar e a treinar o classificador para um desempenho ideal. Se detetar uma palavra ofensiva que não foi filtrada como esperado, avise-nos. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista de palavras influentes com o comutador a mostrar ou ocultar palavras ofensivas.":::
 
  - **Amostras de feedback**: mostra registos de feedback reais nos seus dados. As palavras são codificadas por cores de acordo com a sua influência na identificação de um aspeto de negócio. 


### <a name="influential-words-analysis-tab"></a>Separador de análise de palavras influentes

Existem três secções de informações adicionais que explicam como o modelo de sentimentos funciona.
  
1. **Principais palavras que contribuem para o sentimento positivo**: mostra as palavras principais que influenciaram a identificação do modelo de IA de sentimento positivo no feedback do cliente.  
2. **Principais palavras que contribuem para o sentimento negativo**: mostra as palavras principais que influenciaram a identificação do modelo de IA de sentimento negativo no feedback do cliente.  
3. **Amostras de feedback**: mostra registos de feedback reais, um com um sentimento negativo e outro com um sentimento positivo. As palavras nos registos de feedback são destacadas de acordo com a sua contribuição para a classificação de sentimentos atribuída. As palavras que contribuem para uma classificação de sentimentos positiva são destacadas a verde. As palavras que contribuem para uma classificação negativa são destacadas a vermelho.
   Selecione **Ver mais** para carregar mais amostras de feedback que fornecem mais informações e contexto de como o modelo de sentimentos funciona.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemplos de análise de sentimentos no feedback do cliente.":::
 
**Mostrar palavras ofensivas**: permite-lhe incluir palavras ofensivas na lista a partir de dados originais de feedback do cliente. Por predefinição, está desativado.  A máscara de palavras ofensivas utiliza tecnologia de um modelo de IA e pode não detetar todas as palavras ofensivas. Continuamos a iterar e a treinar o classificador para um desempenho ideal. Se detetar uma palavra ofensiva que não foi filtrada como esperado, avise-nos. 

## <a name="act-on-analysis-results"></a>Agir em resultados da análise

Pode facilmente começar a criar novos segmentos de clientes a partir da página de resultados da análise de sentimentos selecionando **Criar Segmentos** no topo da página de resultados do modelo.

:::image type="content" source="media/create-segment-model.png" alt-text="Barra de comando com opções em modelos de predição.":::
 
## <a name="potential-bias"></a>Desvio potencial

Tal como com qualquer funcionalidade que utilize inteligência artificial preditiva, deve estar ciente de um potencial desvio nos dados que utiliza para prever o sentimento do cliente. Por exemplo, se apenas recolher feedback digitalmente, poderá perder feedback de clientes que efetuam negócios consigo principalmente pessoalmente, o que pode afetar a produção da funcionalidade.

Uma vez que esta funcionalidade utiliza meios automatizados para avaliar dados e fazer predições com base nesses dados, tem, portanto, a capacidade de ser utilizado como um método de análise para otimização, uma vez que esse termo é definido pelo Regulamento Geral sobre Proteção de Dados ("RGPD"). A sua utilização desta funcionalidade para processar dados pode estar sujeita ao RGPD ou a outras leis ou regulamentos. É responsável por garantir que a sua utilização do Dynamics 365 Customer Insights, incluindo a análise de sentimentos, cumpre todas as leis e regulamentos aplicáveis, incluindo leis relacionadas com privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

[!INCLUDE [footer-include](includes/footer-banner.md)]


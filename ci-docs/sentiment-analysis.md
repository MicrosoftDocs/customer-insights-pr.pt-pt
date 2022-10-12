---
title: Analisar sentimentos para feedback do cliente (pré-visualização)
description: Aprenda a utilizar um modelo de análise de sentimentos no feedback do cliente no Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610480"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analisar sentimentos no feedback do cliente (pré-visualização)

A análise de sentimentos permite-lhe sintetizar o sentimento do cliente e identificar os aspetos do negócio como oportunidades de melhoria. Esta funcionalidade do Customer Insights ajuda-o a compreender o que funciona bem e o que precisa de abordar. Pode ajudá-lo a fomentar ações de negócio que permitem experiências que resultem em elevada satisfação e fidelização do cliente.

## <a name="overview"></a>Descrição geral

A funcionalidade de análise de sentimento gera dois insights derivados por ID do cliente. Uma pontuação de sentimento (de -5 a 5) e uma lista de aspetos de negócio aplicáveis (áreas de negócio) que, em conjunto, o ajudam a compreender melhor o feedback do cliente.

Esta análise ajuda-o a:
- Obter uma descrição geral dos sentimentos do cliente em relação a uma marca ou organização
- Identificar clientes com sentimento negativo para focar as suas campanhas e compromissos e otimizar para um maior retorno  
- Identificar aspetos de negócio com problemas indicados pelos clientes  
- Segmentar clientes com base no respetivo sentimento para executar campanhas personalizadas com esforços de vendas, marketing e esforços direcionados
- Otimizar operações comerciais abordando áreas de preocupação ou oportunidades que foram mencionadas pelos clientes
- Reconhecer aspetos de negócio que têm bom desempenho e recompensar clientes felizes através de programas de fidelização e de promoção

O modelo fornece uma lista de palavras que afetaram a decisão do modelo de atribuir uma classificação de sentimentos particular ou aspeto de negócio a comentários de feedback.  

Utilizamos dois **Modelos de Processamento de Linguagem Natural (NLP)**: o primeiro atribui a cada comentário de feedback uma classificação de sentimento. O segundo modelo associa cada comentário a todos os aspetos de negócio aplicáveis. Os modelos são treinados em dados públicos de origens dos setores de redes sociais, retalho, restauração, produtos de consumo e automóvel.
  
Os aspetos de negócio predefinidos para o modelo associado aos dados de feedback incluem:
- Gestão de contas
- Finalização e pagamento
- Suporte ao cliente
- Recolha na loja
- Envio e recuperação de embalagens
- Pré-encomenda
- Preço
- Privacidade e segurança
- Promoções e recompensas
- Recibo e garantia
- Troca de devolução e cancelamento
- Exatidão da conclusão
- Qualidade do site/aplicação

> [!NOTE]
> Atualmente, apenas suportamos a análise de sentimentos no feedback do cliente em inglês. Serão suportados mais idiomas no futuro. Se o feedback noutros idiomas for carregado, o modelo ainda irá obter resultados. No entanto, estes resultados não serão precisos.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [permissões de Contribuidor](permissions.md)
- Dados de feedback de texto [unificados](data-unification.md). Recomendamos vivamente que [configure as suas entidades de dados de feedback como entidades de atividade de tipo semântico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Tipo de feedback).
- ID Unificado do Cliente (UCID) da unificação de dados para corresponder registos de dados de feedback de texto a um cliente individual.
- ID dos Comentários
- Carimbo de data/hora do feedback
- Texto dos comentários

O Customer Insights pode processar até 10 milhões de registos de feedback para uma única execução de modelo. O modelo pode analisar comentários de feedback até 128 palavras. Se um comentário de feedback for mais longo, a análise considera apenas as primeiras 128 palavras.

> [!NOTE]
> Apenas uma entidade de feedback pode ser configurada. Se existirem várias entidades de feedback, combine-as no Power Query antes da ingestão de dados.

## <a name="configure-a-sentiment-analysis"></a>Configurar uma análise de sentimentos

1. Aceda a **Inteligência** > **Predições**.

1. No separador **Criar**, selecione **Utilizar modelo** no mosaico **Análise de sentimentos do cliente (pré-visualização)**.

1. Selecione **Introdução**.

1. **Dê um nome** à análise e forneça o **Nome da entidade de saída de aspeto do negócio** e o **Nome da entidade de saída de classificação de sentimentos**.

1. Selecione **Seguinte**.

1. Selecione **Adicionar dados** para **Feedback do cliente**.

1. Selecione o tipo de atividade semântica **Feedback** que contém os dados de feedback. Se a atividade não tiver sido configurada, selecione **aqui** e crie-a.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Passo de configuração para selecionar atividades de feedback para análise de sentimentos.":::

1. Selecione as atividades a utilizar nesta análise de sentimentos e, em seguida, selecione **Seguinte**.

1. Mapeie os atributos nos seus dados para os atributos do modelo. 

1. Selecione **Guardar**.

1. Selecione **Seguinte**. O passo **Rever e executar** mostra um resumo da configuração e fornece uma oportunidade de efetuar alterações antes de criar a análise.

1. Selecione **Editar** em qualquer um dos passos para rever e efetuar quaisquer alterações.

1. Se estiver satisfeito com as suas seleções, selecione **Guardar e executar** para começar a executar o modelo. Selecionar **Concluído**. O separador **As minhas predições** é apresentado enquanto a predição está a ser criada. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Ver resultados da análise

1. Aceda a **Inteligência** > **Predições**.

1. No separador **As minhas predições**, selecione a predição que pretende ver.

Existem dois separadores de resultados.

### <a name="sumary-tab"></a>Separador Resumo

Há quatro secções primárias de dados dentro da página de resultados.

- **Classificação de sentimentos média**: classificações de sentimentos ajuda-o a compreender o sentimento geral de todos os clientes.
  - **Negativa** (-5 > 2)
  - **Neutra** (-1 > 1)
  - **Positiva** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representação visual do sentimento do cliente geral.":::

- **Distribuição de clientes por classificação de sentimentos**: os clientes são categorizados pelos grupos Negativo, Neutro e Positivo, com base nas respetivas classificações de sentimentos. Paire o cursor do rato sobre as barras no histograma para ver o número de clientes e a classificação de sentimentos média em cada grupo. Estes dados podem ajudá-lo a [criar segmentos de clientes](prediction-based-segment.md) com base nas respetivas classificações de sentimentos.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gráfico de barras a mostrar o sentimento do cliente nos três grupos de sentimentos.":::

- **Classificação de sentimentos média ao longo do tempo**: o sentimento do cliente pode mudar ao longo do tempo. Fornecemos tendências nos sentimentos dos seus clientes para o intervalo de tempo dos seus dados. Esta vista ajuda-o a avaliar o efeito de promoções sazonais, lançamentos de produtos ou outras intervenções com limite de tempo no sentimento do cliente. Consulte o gráfico selecionando o ano de juros do menu pendente.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gráfico histórico com a classificação do sentimento ao longo do tempo representada como uma linha.":::

- **Sentimento em todos os aspetos do negócio**: sentimento médio em todos os aspetos do negócio ajuda-o a avaliar que aspetos do seu negócio já satisfazem os clientes ou requerem mais atenção. Os registos de feedback que não se alinham com nenhum dos aspetos de negócio suportados são categorizados sob **Outros**. Ordene os dados selecionando qualquer coluna.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista de aspetos de negócio com o valor de sentimento associado e o número de clientes que o mencionam.":::

  Selecione o nome de um aspeto de negócio para ver como um aspeto de negócio ser identificado pelo modelo:

  - **Palavras influentes**: principais palavras que influenciaram a identificação do modelo de IA de um aspeto de negócio no feedback do cliente.
    **Mostrar palavras ofensivas**: permite-lhe incluir palavras ofensivas na lista a partir de dados originais de feedback do cliente. Por predefinição, está desativado.  A máscara de palavras ofensivas utiliza tecnologia de um modelo de IA e pode não detetar todas as palavras ofensivas. Se detetar uma palavra ofensiva que não foi filtrada como esperado, avise-nos.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista de palavras influentes com o comutador a mostrar ou ocultar palavras ofensivas.":::

  - **Amostras de feedback**: registos de feedback reais nos seus dados. As palavras são codificadas por cores de acordo com a sua influência na identificação de um aspeto de negócio.

### <a name="influential-words-analysis-tab"></a>Separador de análise de palavras influentes

Existem três secções de informações adicionais que explicam como o modelo de sentimentos funciona.
  
- **Principais palavras que contribuem para o sentimento positivo**: palavras principais que influenciaram a identificação do modelo de IA de sentimento positivo no feedback do cliente.  

- **Principais palavras que contribuem para o sentimento negativo**: palavras principais que influenciaram a identificação do modelo de IA de sentimento negativo no feedback do cliente.

- **Amostras de feedback**: registos de feedback reais, um com um sentimento negativo e outro com um sentimento positivo. As palavras nos registos de feedback são destacadas de acordo com a sua contribuição para a classificação de sentimentos atribuída. As palavras que contribuem para uma classificação de sentimentos positiva são destacadas a verde. As palavras que contribuem para uma classificação negativa são destacadas a vermelho.
   Selecione **Ver mais** para carregar mais amostras de feedback.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemplos de análise de sentimentos no feedback do cliente.":::

**Mostrar palavras ofensivas**: permite-lhe incluir palavras ofensivas na lista a partir de dados originais de feedback do cliente. Por predefinição, está desativado.  A máscara de palavras ofensivas utiliza tecnologia de um modelo de IA e pode não detetar todas as palavras ofensivas. Se detetar uma palavra ofensiva que não foi filtrada como esperado, avise-nos.

## <a name="act-on-analysis-results"></a>Agir em resultados da análise

Para criar novos segmentos de clientes a partir de resultados da análise de sentimentos, selecione **Criar segmentos** no topo da página de resultados do modelo.

## <a name="potential-bias"></a>Desvio potencial

Tal como com qualquer caraterística que utilize inteligência artificial preditiva, pode existir um potencial desvio nos dados que utiliza para prever o sentimento do cliente. Por exemplo, se apenas recolher feedback digitalmente, poderá perder feedback de clientes que efetuam negócios consigo principalmente pessoalmente, o que afeta a saída da caraterística.

Uma vez que esta funcionalidade utiliza meios automatizados para avaliar dados e fazer predições com base nesses dados, tem, portanto, a capacidade de ser utilizado como um método de análise para otimização, uma vez que esse termo é definido pelo Regulamento Geral sobre Proteção de Dados ("RGPD"). A sua utilização desta funcionalidade para processar dados pode estar sujeita ao RGPD ou a outras leis ou regulamentos. É responsável por garantir que a sua utilização do Dynamics 365 Customer Insights, incluindo a análise de sentimentos, cumpre todas as leis e regulamentos aplicáveis, incluindo leis relacionadas com privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

[!INCLUDE [footer-include](includes/footer-banner.md)]


---
title: Localizar clientes similares com IA (pré-visualização) (contém vídeo)
description: Encontre segmentos de clientes semelhantes com inteligência artificial.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170741"
---
# <a name="find-similar-customers-with-ai-preview"></a>Localizar clientes similares com IA (pré-visualização)

Encontre clientes semelhantes na sua base de clientes usando inteligência artificial. Precisa de pelo menos um segmento criado para utilizar esta funcionalidade. Expandir os critérios de um segmento existente ajuda a encontrar clientes semelhantes a esse segmento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Localizar clientes semelhantes* utiliza meios automatizados para avaliar os dados e fazer previsões com base nesse dados. Assim, tem a capacidade de ser utilizado como método de análise para otimização, uma vez que esse termo está definido pelo Regulamento Geral da Proteção de Dados ("GDPR"). A utilização desta funcionalidade por parte do Cliente para tratar os dados pode estar sujeita aos RGPD ou a outras leis ou regulamentos. O utilizador é responsável por garantir que a sua utilização do Dynamics 365 Customer Insights, incluindo predições, cumpre com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas com a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

## <a name="find-similar-customers"></a>Encontrar clientes semelhantes

1. Aceda a **Segmentos** e selecione o segmento em que pretende basear o novo segmento. É o seu *segmento de origem*.

1. Selecione **Localizar clientes semelhantes**.

1. Reveja o nome sugerido para o seu novo segmento e altere-o se necessário.

1. Opcionalmente, adicione [etiquetas](work-with-tags-columns.md#manage-tags) ao novo segmento.

1. Reveja os campos que definem o seu novo segmento. Estes campos definem a base em que o sistema tentará encontrar clientes semelhantes ao seu segmento de origem. O sistema seleciona os campos recomendados por predefinição. Se for necessário, adicione mais campos.
  Os campos que podem reduzir significativamente o desempenho do modelo são automaticamente excluídos:
  
   - Campos com os seguintes tipos de dados: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campos com cardinalidade (número de elementos num campo) inferiores a 2 ou mais de 30

1. Escolha se pretende incluir **Todos os clientes**, exceto o segmento de origem, ou apenas clientes num **segmento diferente** no seu novo segmento.

1. Por predefinição, o sistema sugere que inclua apenas 20% do tamanho da audiência alvo na sua saída. Edite este limiar conforme necessário. Aumentar o limiar reduzirá a precisão.

1. Inclua clientes no segmento de origem selecionando a caixa de verificação **Incluir membros do segmento de origem para além de clientes com atributos semelhantes**.

1. Selecione **Executar** na parte inferior da página para iniciar uma [tarefa de classificação binária](#about-similarity-scores) (um método de aprendizagem automática) que analisa o conjunto de dados.

## <a name="view-the-similar-segment"></a>Ver o segmento semelhante

Após o processamento do segmento semelhante, encontrará o novo segmento listado na página **Segmentos** com o tipo **Expansão**.

Selecione **Ver** para ver a distribuição de resultados em [classificações de semelhança](#about-similarity-scores) e em valores de classificação de semelhança em **Pré-visualizar membros do segmento**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segmento de clientes semelhantes.":::

## <a name="manage-a-similar-segment"></a>Gerir um segmento semelhante

[Trabalhe com um segmento semelhante ou faça a sua gestão](segments.md#manage-existing-segments) como faz com outros segmentos. Por exemplo, exportar o segmento ou criar uma medida.

Edite, atualize, mude o nome, transfira e elimine um segmento semelhante. Editar um segmento semelhante reprocessa os seus dados. O segmento anteriormente criado é atualizado com dados atualizados.

## <a name="about-similarity-scores"></a>Sobre pontuações de semelhança

O modelo de machine learning de classificação binária atribui uma pontuação aos clientes do segmento semelhante. A pontuação baseia-se na semelhança com os clientes do segmento de origem.

- Pontuações de semelhança abaixo de 0,55 são clientes que o sistema classificou como *não semelhantes* aos clientes no segmento de origem
- As pontuações de semelhança entre 0,55 e 0,7 são classificadas como *um pouco semelhantes*
- As pontuações de semelhança entre 0,7 e 0,85 são classificadas como *semelhantes*
- Pontuações de semelhança entre 0,85 e 1 são clientes que o sistema classifica como *muito semelhantes*

Os clientes com pontuações de semelhança inferiores a 0,4 não estão incluídos na saída do modelo. O sistema não os considera semelhantes o suficiente ao segmento de origem.

[!INCLUDE [footer-include](includes/footer-banner.md)]

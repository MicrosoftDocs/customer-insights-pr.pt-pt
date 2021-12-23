---
title: Localizar clientes similares com IA (Vídeo)
description: Encontre segmentos de clientes semelhantes com inteligência artificial.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7999c4964773c3b5c49537027a2ed67f0ad57ec5
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903904"
---
# <a name="similar-customers-preview"></a>Clientes semelhantes (pré-visualização)

Esta funcionalidade permite encontrar clientes semelhantes na sua base de clientes utilizando inteligência artificial. Precisa de ter, pelo menos, um segmento criado para utilizar esta funcionalidade. Expandir os critérios de um segmento existente ajuda a encontrar clientes semelhantes a esse segmento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Encontrar clientes semelhantes* utiliza meios automatizados para avaliar dados e fazer previsões com base nesses dados, pelo que tem a capacidade de ser usado como um método de criar perfis, uma vez que esse termo é definido pelo Regulamento Geral de Proteção de Dados ("RGPD"). A utilização desta funcionalidade por parte do Cliente para tratar os dados pode estar sujeita aos RGPD ou a outras leis ou regulamentos. O utilizador é responsável por garantir que a sua utilização do Dynamics 365 Customer Insights, incluindo predições, cumpre com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas com a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

## <a name="finding-similar-customers"></a>Localizar clientes semelhantes

1. Nos insights de audiência, aceda a **Segmentos** e selecione o segmento em que pretende basear o seu novo segmento. É o seu *segmento de origem*.

1. Na barra de ação, selecione **Localizar clientes semelhantes**.

1. Reveja o nome sugerido para o seu novo segmento e altere-o se necessário.

1. Reveja os campos que definem o seu novo segmento. Estes campos definem a base em que o sistema tentará encontrar clientes semelhantes ao seu segmento de origem. O sistema selecionará os campos recomendados por predefinição.
  Os campos que podem reduzir significativamente o desempenho do modelo são automaticamente excluídos:
  
   - Campos com os seguintes tipos de dados: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campos com cardinalidade (número de elementos num campo) inferiores a 2 ou mais de 30

1. Escolha se pretende incluir **Todos os clientes** ou apenas clientes num **Segmento específico existente** no seu novo segmento.

1. Exclua os clientes no seu segmento de origem selecionando a caixa de verificação **Excluir todos os utilizadores no segmento de origem**.

1. Por predefinição, o sistema sugere que inclua apenas 20% do tamanho da audiência alvo na sua saída. Edite este limiar conforme necessário. Aumentar o limiar reduzirá a precisão.

1. Selecione **Executar** na parte inferior da página para iniciar uma tarefa de classificação binária (um método de aprendizagem automática) que analisa o conjunto de dados.

## <a name="view-the-similar-segment"></a>Ver o segmento semelhante

Após o processamento do segmento semelhante, encontrará o novo segmento listado na página **Segmentos**.

> [!div class="mx-imgBorder"]
> ![Segmento de clientes semelhantes.](media/expanded-segment.png "Segmento de clientes semelhantes")

Selecione **Ver** na barra de ação para abrir o detalhe do segmento. Esta visão contém informações sobre a distribuição dos resultados entre [pontuações de semelhança](#about-similarity-scores). Também encontrará os valores de pontuação de semelhança na **Pré-visualização dos membros do segmento**.

## <a name="use-the-output-of-a-similar-segment"></a>Utilize a saída de um segmento semelhante

Pode [trabalhar com a saída de um segmento semelhante](segments.md) como faz com outros segmentos. Por exemplo, exportar o segmento ou criar uma medida.

## <a name="refresh-and-edit-a-similar-segment"></a>Atualizar e editar um segmento semelhante

Para atualizar um segmento semelhante, selecione-o na página **Segmentos** e selecione **Atualizar** na barra de ação.

Editar um segmento semelhante irá voltar a processar os seus dados. O segmento anteriormente criado é atualizado com dados atualizados.    
Para editar um segmento semelhante, selecione-o na página **Segmentos** e selecione **Editar** na barra de ação. Aplique as alterações e selecione **Executar** para iniciar o processamento.

## <a name="delete-a-similar-segment"></a>Eliminar um segmento semelhante

Selecione o segmento semelhante na página **Segmentos** e selecione **Eliminar** na barra de ação. Em seguida, confirme a eliminação.

## <a name="about-similarity-scores"></a>Sobre pontuações de semelhança

O modelo de machine learning de classificação binária atribui uma pontuação aos clientes do segmento semelhante. A pontuação baseia-se na semelhança com os clientes do segmento de origem.

- Pontuações de semelhança abaixo de 0,55 são clientes que o sistema classificou como *não semelhantes* aos clientes no segmento de origem
- As pontuações de semelhança entre 0,55 e 0,7 são classificadas como *um pouco semelhantes*
- As pontuações de semelhança entre 0,7 e 0,85 são classificadas como *semelhantes*
- Pontuações de semelhança entre 0,85 e 1 são clientes que o sistema classifica como *muito semelhantes*

Os clientes com pontuações de semelhança inferiores a 0,4 não estão incluídos na saída do modelo. O sistema não os considera semelhantes o suficiente ao segmento de origem.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
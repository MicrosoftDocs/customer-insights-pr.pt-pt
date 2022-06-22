---
title: Melhorar perfis de clientes com dados de marcas e interesses da Microsoft
description: Utilize dados proprietários da Microsoft para melhorar os dados dos seus clientes com afinidades e quota de voz.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953779"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Melhore os perfis do cliente com afinidades e quota de voz (pré-visualização)

Utilize dados proprietários da Microsoft para melhorar os dados dos seus clientes com afinidades de marcas, afinidades de interesses e quota de voz (SoV). Estas afinidades e SoV são baseados em dados de pessoas com dados demográficos semelhantes aos dos seus clientes. Esta informação ajuda-o a compreender melhor e a segmentar os seus clientes com base nas suas afinidades ou SoV a marcas e interesses específicos.

## <a name="how-we-determine-affinities-and-sov"></a>Como determinamos afinidades e SoV

Utilizamos os dados de pesquisa online da Microsoft para encontrar afinidades e SoV para marcas e interesses em vários segmentos demográficos (definidos por idade, sexo ou localização). O volume de pesquisa online para uma marca ou interesse constitui a base para determinar a afinidade ou a SoV. No entanto, cada um fornece uma perspetiva diferente para compreender os seus clientes.

- A afinidade é um comparativo entre segmentos demográficos. Pode utilizar esta informação para identificar segmentos demográficos que tenham a maior afinidade para uma determinada marca ou interesse, em comparação com outros segmentos.

- A Quota de Voz é um comparativo entre as suas marcas ou interesses selecionados. Pode utilizar esta informação para identificar qual a marca ou o interesse que tem a maior quota de voz para um determinado segmento demográfico, em comparação com outras marcas ou interesses que selecionou.

## <a name="affinity-level-and-score"></a>Nível e pontuação de afinidade

Em cada perfil de cliente melhorado, fornecemos dois valores relacionados: nível de afinidade e pontuação de afinidade. Estes valores ajudam-no a determinar quão forte é a afinidade para o segmento demográfico desse perfil, para uma marca ou interesse, em comparação com outros segmentos demográficos.

O *nível de afinidade* consiste em quatro níveis e a *pontuação de afinidade* é calculada numa escala de 100 pontos que mapeia para os níveis de afinidade.

|Nível de afinidade |Pontuação de afinidade  |
|---------|---------|
|Muito alta     | 85-100       |
|Alto     | 70-84        |
|Médio     | 35-69        |
|Baixo     | 1-34        |

Dependendo da granularidade que gostaria para medir a afinidade, pode utilizar o nível de afinidade ou a pontuação. A pontuação de afinidade dá-lhe um controlo mais preciso.

## <a name="share-of-voice-sov"></a>Quota de Voz (SoV)

Calculamos a SoV numa escala de 100 pontos. O total de SoV em todas as marcas ou interesses por cada perfil de cliente melhorado soma até 100. Ao contrário das afinidades, a SoV é relativa às marcas e aos interesses que seleciona. Por exemplo, os valores SoV para 'Microsoft' podem ser diferentes se as marcas selecionadas forem ('Microsoft', 'GitHub') versus ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Países/regiões suportados

Atualmente, suportamos as seguintes opções de país/região: Austrália, Canadá (inglês), França, Alemanha, Reino Unido ou Estados Unidos (inglês).

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

   - Para configurar as afinidades de marcas e o melhoramento da SoV, selecione **Melhorar os meus dados** no mosaico **Marcas**.

   - Para configurar as afinidades de interesses e o melhoramento da SoV, selecione **Melhorar os meus dados** no mosaico **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Mosaicos Marcas e Interesses.](media/BrandsInterest-tile-Hub.png "Mosaicos Marcas e Interesses")

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Para alterar o seu país ou região, selecione **Alterar** junto de **País/Região**. No painel **Definições de País/Região**, escolha um [país/região suportado](#supported-countriesregions) e selecione **Aplicar**.

   > [!NOTE]
   > Ao escolher as suas próprias marcas, o sistema fornece sugestões baseadas no país ou região selecionados. Ao escolher um setor, obterá as marcas ou interesses mais relevantes com base no país ou região selecionados.

1. Escolha até cinco marcas ou interesses utilizando uma ou ambas as opções:

   - **Setor**: selecione o seu setor da lista pendente e, em seguida, escolha entre as marcas ou interesses principais para esse setor.
   - **Escolha o seu**: introduza uma marca ou interesse que seja relevante para a sua organização e, em seguida, escolha entre as sugestões correspondentes. Se não listarmos uma marca ou um interesse que procura, envie-nos comentários com a ligação **Sugerir**.

1. Selecione **Seguinte** e reveja as suas preferências de melhoramento predefinidas e atualize-as conforme necessário.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de ecrã da janela de preferências de melhoramento.":::

1. Selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar com os dados da Microsoft. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

1. Selecione **Seguinte**.

1. Mapeie os campos a partir da entidade de cliente unificada para os dados da Microsoft.

   > [!NOTE]
   > São necessários, pelo menos, atributos de Data de Nascimento ou de Género. São necessários País/Região e, pelo menos, Cidade (e Distrito) ou Código postal. Recomendamos que a data de nascimento seja convertida no tipo DateTime durante a ingestão de dados. Alternativamente, pode ser uma cadeia no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:mm".

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento. O **Nome da entidade de saída** é selecionado automaticamente.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisão de interesses e atribuir nome à página.":::

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

   Ao melhorar perfis, melhoraremos todos os perfis de clientes para os quais obtemos dados para as marcas e interesses selecionados, incluindo perfis que não estão no país ou região selecionados. Por exemplo, se selecionou Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados disponíveis para as marcas e interesses selecionados nos EUA.

## <a name="enrichment-results"></a>Resultados do enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Pré-visualização dos resultados depois de executar o processo de enriquecimento.":::

Os resultados incluem os gráficos **Nível de Afinidade** ou **Quota de Voz**.

As entidades criadas a partir dos melhoramentos são listadas sob o grupo **Melhoramento** em **Dados** > **Entidades**. Os dados melhorados para as marcas vão para as entidades **BrandAffinityFromMicrosoft** e **BrandShareOfVoiceFromMicrosoft**. Os dados relativos aos interesses encontram-se nas entidades **InterestAffinityFromMicrosoft** e **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Ver dados de enriquecimento no cartão de cliente

A SoV de marca e interesse também pode ser vista em cartões de clientes individuais. Aceda a **Clientes** e selecione um perfil de cliente. No cartão do cliente, encontrará gráficos para a SoV de marca ou interesse com base nas pessoas no perfil demográfico desse cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos.":::

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Enriquecer perfis de clientes com dados da Microsoft
description: Utilize dados proprietários da Microsoft para melhorar os dados dos seus clientes com afinidades e quota de voz.
ms.date: 11/11/2021
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
ms.openlocfilehash: 77972475c9a448186cee3b1b62eeda7b1996edfc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355343"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Melhore os perfis do cliente com afinidades e quota de voz (pré-visualização)

Utilize dados proprietários da Microsoft para melhorar os dados dos seus clientes com afinidades de marcas, afinidades de interesses e quota de voz (SoV). Estas afinidades e SoV são baseados em dados de pessoas com dados demográficos semelhantes aos dos seus clientes. Esta informação ajuda-o a compreender melhor e a segmentar os seus clientes com base nas suas afinidades ou SoV a marcas e interesses específicos.

Nas informações da audiência, vá a **Dados** > **Melhoramento** para [configurar e ver melhoramentos](enrichment-hub.md).

Para configurar as afinidades de marcas e o melhoramento da SoV, vá ao separador **Descobrir** e selecione **Melhorar os meus dados** no mosaico **Marcas**.

Para configurar as afinidades de interesses e o melhoramento da SoV, vá ao separador **Descobrir** e selecione **Melhorar os meus dados** no mosaico **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Mosaicos Marcas e Interesses.](media/BrandsInterest-tile-Hub.png "Mosaicos Marcas e Interesses")

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

Para selecionar um país ou região, abra **Melhoramento de marcas** ou **Melhoramento de interesses** e selecione **Alterar** junto a **País/Região**. No painel de **Definições de País/Região**, escolha uma opção e selecione **Aplicar**.

### <a name="implications-related-to-country-selection"></a>Implicações relacionadas com a seleção do país

- Ao [escolher as suas próprias marcas](#define-your-brands-or-interests), o sistema fornece sugestões baseadas no país ou região selecionados.

- Ao [escolher um setor](#define-your-brands-or-interests), obterá as marcas ou interesses mais relevantes com base no país ou região selecionados.

- Ao [melhorar perfis](#refresh-enrichment), melhoraremos todos os perfis de clientes para os quais obtemos dados para as marcas e interesses selecionados, incluindo perfis que não estão no país ou região selecionados. Por exemplo, se selecionou Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados disponíveis para as marcas e interesses selecionados nos EUA.

## <a name="configure-enrichment"></a>Configurar melhoramento

Uma experiência guiada ajuda-o através da configuração dos enriquecimentos. 

### <a name="define-your-brands-or-interests"></a>Definir as suas marcas ou interesses

Escolha até cinco marcas ou interesses utilizando uma ou ambas as opções:

- **Setor**: selecione o seu setor da lista pendente e, em seguida, escolha entre as marcas ou interesses principais para esse setor.
- **Escolha o seu**: introduza uma marca ou interesse que seja relevante para a sua organização e, em seguida, escolha entre as sugestões correspondentes. Se não listarmos uma marca ou um interesse que procura, envie-nos comentários com a ligação **Sugerir**.

### <a name="review-enrichment-preferences"></a>Rever preferências de melhoramento

Reveja as suas preferências de melhoramento predefinidas e atualize-as conforme necessário.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de ecrã da janela de preferências de melhoramento.":::

### <a name="select-entity-to-enrich"></a>Selecione a entidade a melhorar

Selecione **Entidade melhorada** e escolha o conjunto de dados que pretende melhorar com os dados da Microsoft. Pode selecionar a entidade Cliente para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.

### <a name="map-your-fields"></a>Mapear os seus campos

Mapeie os campos da sua entidade de cliente unificada para definir o segmento demográfico que pretende que o sistema utilize para melhorar os dados do seu cliente. Mapeie País/Região e, pelo menos, os atributos Data de Nascimento e Sexo. Adicionalmente, tem de mapear pelo menos uma Localidade (e Distrito) ou Código postal. Selecione **Editar** para definir o mapeamento dos campos e selecione **Aplicar** quando tiver terminado. Selecione **Guardar** para concluir o mapeamento de campos.

Os seguintes formatos e valores são suportados (os valores não são sensíveis às maiúsculas e minúsculas):

- **Data de Nascimento**: recomendamos que a data de nascimento seja convertida para o tipo DateTime durante a ingestão de dados. Alternativamente, pode ser uma cadeia no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:mm".
- **Sexo**: Masculino, Feminino, Desconhecido.
- **Código postal**: Códigos postais de cinco dígitos para os Estados Unidos, código postal padrão em todos os outros locais.
- **Cidade**: nome da cidade em inglês.
- **Estado/Província**: abreviatura de duas letras para os EUA e Canadá. Abreviatura de duas ou três letras para a Austrália. Não aplicável à França, Alemanha ou Reino Unido.
- **País/Região**:

  - EUA: Estados Unidos da América, Estados Unidos, EUA, EU, América
  - CA: Canadá, CA
  - GB: Reino Unido, RU, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha
  - AU: Austrália, AU, Comunidade da Austrália
  - FR: França, FR, República Francesa
  - AL: Alemanha, Alemão, Deutschland, Allemagne, DE, República Federal da Alemanha, República da Alemanha

## <a name="review-and-name-the-enrichment"></a>Reveja e atribua um nome ao enriquecimento

Por fim, pode rever as informações e fornecer um nome ao enriquecimento.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisão de interesses e atribuir nome à página.":::

## <a name="refresh-enrichment"></a>Atualizar enriquecimento

Execute o melhoramento depois de configurar as marcas, os interesses e o mapeamento de campos para a demografia. Para iniciar o processo, selecione **Executar** na página de configuração da marcas ou interesses. Para além disso, pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma atualização agendada.

Consoante o tamanho dos dados dos seus clientes, a execução do melhoramento poderá demorar vários minutos.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultados do enriquecimento

Depois de executar o processo de melhoramento, aceda a **Meus enriquecimentos** para rever o número total de clientes melhorados e uma discriminação de marcas ou interesses nos perfis de cliente melhorados.

:::image type="content" source="media/my-enrichments.png" alt-text="Pré-visualização dos resultados depois de executar o processo de enriquecimento.":::

Encontrará um gráfico com o número de perfis de clientes melhorados ao longo do tempo e pré-visualizações das entidades melhoradas. Reveja os dados melhorados selecionando **Ver mais** nos gráficos **Nível de Afinidade** ou **Quota de Voz**. Os dados melhorados para as marcas vão para as entidades **BrandAffinityFromMicrosoft** e **BrandShareOfVoiceFromMicrosoft**. Os dados relativos aos interesses encontram-se nas entidades **InterestAffinityFromMicrosoft** e **InterestShareOfVoiceFromMicrosoft**. Também encontrará estas entidades listadas no grupo **Enriquecimento** em **Dados** > **Entidades**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Ver dados de enriquecimento no cartão de cliente

A SoV de marca e interesse também pode ser vista em cartões de clientes individuais. Aceda a **Clientes** e selecione um perfil de cliente. No cartão do cliente, encontrará gráficos para a SoV de marca ou interesse com base nas pessoas no perfil demográfico desse cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos.":::

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]

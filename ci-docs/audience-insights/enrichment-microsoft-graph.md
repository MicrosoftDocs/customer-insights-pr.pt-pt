---
title: Melhore o perfil dos clientes com o Microsoft Graph
description: Utilize os dados proprietários do Microsoft Graph para melhorar os dados dos clientes com afinidades de marca e de interesse.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406617"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Melhorar perfis de cliente com afinidades de marca e interesse (pré-visualização)

Utilize os dados proprietários do Microsoft Graph para melhorar os dados dos clientes com afinidades de marca e de interesse. Estas afinidades são determinadas com base nos dados de pessoas com dados demográficos semelhantes aos dos seus clientes. Estas informações ajudam-no a compreender melhor e segmentar os clientes com base nas afinidades com marcas e interesses específicos.

Nos insights da audiência, vá a **Dados** > **Melhoramento** para [configurar e ver melhoramentos](enrichment-hub.md).

Para configurar o enriquecimento de afinidades de marcas, vá ao separador **Descubrir** e selecione **Enriquecer os meus dados** no mosaico **Marcas**.

Para configurar o enriquecimento de afinidades de interesses, vá ao separador **Descubrir** e selecione **Enriquecer os meus dados** no mosaico **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Mosaicos de Marcas e Interesses](media/BrandsInterest-tile-Hub.png "Mosaicos de Marcas e Interesses")

## <a name="about-microsoft-graph"></a>Sobre o Microsoft Graph

Utilizados os dados de pesquisa online do Microsoft Graph para localizar afinidades de marcas e interesses em vários segmentos demográficos (definidos por idade, sexo ou localização). O volume de pesquisa online para uma marca ou um interesse determina quanta afinidade um segmento demográfico, em comparação com outros segmentos, tem com essa marca ou interesse.

[Saber mais sobre o Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Classificação de afinidade e confiança

A **classificação de afinidade** é calculada numa escala de 100 pontos, com 100 representando o segmento que tem a afinidade mais elevada para uma marca ou interesse.

A **confiança de afinidade** também é calculada numa escala de 100 pontos. Indica o nível de confiança do sistema da afinidade de um segmento para a marca ou o interesse. O nível de confiança baseia-se no tamanho do segmento e na granularidade do segmento. O tamanho do segmento é determinado pela quantidade de dados que temos para um determinado segmento. A granularidade do segmento é determinada pelo número de atributos (idade, sexo, localização) disponíveis num perfil.

Não normalizamos as pontuações para o seu conjunto de dados. Consequentemente, poderá não ver todos os valores de pontuação de afinidade possíveis para o seu conjunto de dados. Por exemplo, poderá não existir nenhum perfil de cliente melhorado com pontuação de afinidade de 100 nos dados. Isto é possível se não existirem clientes no segmento demográfico com pontuação de 100 para uma determinada marca ou interesse.

> [!TIP]
> Ao [criar segmentos](segments.md) utilizando pontuações de afinidade, reveja a distribuição das pontuações de afinidade para o seu conjunto de dados antes de decidir quais os limiares de pontuação apropriados. Por exemplo, uma pontuação de afinidade de 10 pode ser considerada significativa num conjunto de dados que tenha uma pontuação de afinidade mais elevada de apenas 25 para uma determinada marca ou interesse.

## <a name="supported-countriesregions"></a>Países/regiões suportados

Atualmente, suportamos as seguintes opções de país/região: Austrália, Canadá (inglês), França, Alemanha, Reino Unido ou Estados Unidos (inglês).

Para selecionar um país, abra o **Enriquecimento de marcas** ou o **Enriquecimento de interesses** e selecione **Alterar** ao lado de **País/Região**. No painel de **Definições de País/Região**, escolha uma opção e selecione **Aplicar**.

### <a name="implications-related-to-country-selection"></a>Implicações relacionadas com a seleção do país

- Ao [escolher as suas próprias marcas](#define-your-brands-or-interests), iremos fornecer sugestões com base no país/região selecionado.

- Ao [escolher um setor de atividade](#define-your-brands-or-interests), identificaremos as marcas ou interesses mais relevantes com base no país/região selecionado.

- Ao [mapear os seus campos](#map-your-fields), se o campo País/Região não estiver mapeado, usaremos os dados do Microsoft Graph a partir do país/região selecionado para enriquecer os seus perfis de clientes. Também usaremos essa seleção para enriquecer os seus perfis de clientes que não dispõem de dados de país/região disponíveis.

- Ao [enriquecer perfis](#refresh-enrichment), enriqueceremos todos os perfis de clientes para os quais temos dados do Microsoft Graph disponíveis para as marcas e interesses selecionados, incluindo perfis que não estão no país/região selecionado. Por exemplo, se selecionar a Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados do Microsoft Graph disponíveis para as marcas e interesses selecionados nos EUA.

## <a name="configure-enrichment"></a>Configurar Enriquecimento

Configurar o enriquecimento de marcas ou interesses consiste em dois passos:

### <a name="define-your-brands-or-interests"></a>Definir as suas marcas ou interesses

Seleccione uma das seguintes opções:

- **Setor** : o sistema identifica as principais marcas ou interesses relevantes para o seu setor e melhora os dados do seu cliente com eles.
- **Escolher os seus próprios**: selecione até cinco itens a partir da lista de marcas ou interesses que são mais relevantes para a sua organização.

Para adicionar uma marca ou um interesse, introduza-o na área de introdução para obter sugestões em função da correspondência de termos. Se não listarmos uma marca ou um interesse que procura, envie-nos comentários com a ligação **Sugerir**.

### <a name="map-your-fields"></a>Mapear os seus campos

Mapeie os campos da sua entidade de cliente unificada para, pelo menos, dois atributos para definir o segmento demográfico que pretende que utilizemos para melhorar os dados dos seus clientes. Selecione **Editar** para definir o mapeamento dos campos e selecione **Aplicar** quando tiver terminado. Selecione **Guardar** para concluir o mapeamento de campos.

Os seguintes formatos e valores são suportados, os valores não são sensíveis às maiúsculas e minúsculas:

- **Data de Nascimento**: recomendamos que a data de nascimento seja convertida para o tipo DateTime durante a ingestão de dados. Alternativamente, pode ser uma cadeia no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ssZ".
- **Sexo**: Masculino, Feminino, Desconhecido
- **Código postal**: xódigos postais de cinco dígitos para EUA, código postal padrão em todos os outros lugares
- **Cidade**: nome da cidade em inglês
- **Estado/Província**: abreviatura de duas letras para os EUA e Canadá. Abreviatura de duas ou três letras para a Austrália. Não aplicável à França, Alemanha ou Reino Unido.
- **País/Região**:

  - EUA: Estados Unidos da América, Estados Unidos, EUA, EU, América
  - CA: Canadá, CA
  - GB: Reino Unido, RU, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha
  - AU: Austrália, AU, Comunidade da Austrália
  - FR: França, FR, República Francesa
  - AL: Alemanha, Alemão, Deutschland, Allemagne, DE, República Federal da Alemanha, República da Alemanha

## <a name="refresh-enrichment"></a>Atualizar enriquecimento

Execute o melhoramento depois de configurar as marcas, os interesses e o mapeamento de campos para a demografia. Para iniciar o processo, selecione **Executar** na página de configuração da marcas ou interesses. Para além disso, pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma atualização agendada.
Consoante o tamanho dos dados dos seus clientes, a execução do melhoramento poderá demorar vários minutos.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="enrichment-results"></a>Resultados do enriquecimento

Depois de executar o processo de melhoramento, aceda a **Meus enriquecimentos** para rever o número total de clientes melhorados e uma discriminação de marcas ou interesses nos perfis de cliente melhorados.

:::image type="content" source="media/my-enrichments.png" alt-text="Pré-visualização dos resultados depois de executar o processo de enriquecimento":::

Reveja os dados melhorados ao selecionar **Ver dados melhorados** no gráfico. Os dados melhorados para as marcas vão para a entidade **BrandAffinityFromMicrosoft**. Os dados para os interesses estão na entidade **InterestAffinityFromMicrosoft**. Também encontrará estas entidades listadas no grupo **Enriquecimento** em **Dados** > **Entidades**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Ver dados de enriquecimento no cartão de cliente

As afinidades de marca e de interesses também podem ser vistas em cartões de clientes individuais. Aceda a **Clientes** e selecione um perfil de cliente. No cartão de cliente, encontrará gráficos para as marcas ou interesses pelas quais as pessoas no perfil demográfico desse cliente têm afinidade.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos":::

## <a name="next-steps"></a>Passos seguintes

Desenvolva a partir dos seus dados de clientes melhorados. Crie [Segmentos](segments.md), [Medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.

---
title: Melhore o perfil dos clientes com o Microsoft Graph
description: Utilize os dados proprietários do Microsoft Graph para melhorar os dados dos clientes com afinidades de marca e de interesse.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596467"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Melhorar perfis de cliente com afinidades de marca e interesse (pré-visualização)

Utilize os dados proprietários do Microsoft Graph para melhorar os dados dos clientes com afinidades de marca e de interesse. Estas afinidades são determinadas com base nos dados de pessoas com dados demográficos semelhantes aos dos seus clientes. Estas informações ajudam-no a compreender melhor e segmentar os clientes com base nas afinidades com marcas e interesses específicos.

Nas informações da audiência, vá a **Dados** > **Melhoramento** para [configurar e ver melhoramentos](enrichment-hub.md).

Para configurar o enriquecimento de afinidades de marcas, vá ao separador **Descubrir** e selecione **Enriquecer os meus dados** no mosaico **Marcas**.

Para configurar o enriquecimento de afinidades de interesses, vá ao separador **Descubrir** e selecione **Enriquecer os meus dados** no mosaico **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Mosaicos de Marcas e Interesses](media/BrandsInterest-tile-Hub.png "Mosaicos de Marcas e Interesses")

## <a name="about-microsoft-graph"></a>Sobre o Microsoft Graph

Utilizados os dados de pesquisa online do Microsoft Graph para localizar afinidades de marcas e interesses em vários segmentos demográficos (definidos por idade, sexo ou localização). O volume de pesquisa online para uma marca ou um interesse determina quanta afinidade um segmento demográfico, em comparação com outros segmentos, tem com essa marca ou interesse.

[Saber mais sobre o Microsoft Graph](/graph/overview).

## <a name="affinity-level-and-score"></a>Nível e pontuação de afinidade

Em cada perfil de cliente melhorado, fornecemos dois valores relacionados – nível de afinidade e pontuação de afinidade. Estes valores ajudam-no a determinar quão forte é a afinidade para o segmento demográfico desse perfil, para uma marca ou interesse, em comparação com outros segmentos demográficos.

O *nível de afinidade* consiste em quatro níveis e a *pontuação de afinidade* é calculada numa escala de 100 pontos que mapeia para os níveis de afinidade.


|Nível de afinidade |Pontuação de afinidade  |
|---------|---------|
|Muito alta     | 85-100       |
|Alto     | 70-84        |
|Médio     | 35-69        |
|Baixo     | 1-34        |

Dependendo da granularidade que gostaria para medir a afinidade, pode utilizar o nível de afinidade ou a pontuação. A pontuação de afinidade dá-lhe um controlo mais preciso.

## <a name="supported-countriesregions"></a>Países/regiões suportados

Atualmente, suportamos as seguintes opções de país/região: Austrália, Canadá (inglês), França, Alemanha, Reino Unido ou Estados Unidos (inglês).

Para selecionar um país, abra o **Enriquecimento de marcas** ou o **Enriquecimento de interesses** e selecione **Alterar** ao lado de **País/Região**. No painel de **Definições de País/Região**, escolha uma opção e selecione **Aplicar**.

### <a name="implications-related-to-country-selection"></a>Implicações relacionadas com a seleção do país

- Ao [escolher as suas próprias marcas](#define-your-brands-or-interests), o sistema fornece sugestões baseadas no país ou região selecionados.

- Ao [escolher um setor](#define-your-brands-or-interests), obterá as marcas ou interesses mais relevantes com base no país ou região selecionados.

- Ao [melhorar perfis](#refresh-enrichment), melhoraremos todos os perfis de cliente para os quais obtemos dados para as marcas e interesses selecionados. Incluindo perfis que não estão no país ou região selecionados. Por exemplo, se selecionar a Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados do Microsoft Graph disponíveis para as marcas e interesses selecionados nos EUA.

## <a name="configure-enrichment"></a>Configurar Enriquecimento

### <a name="define-your-brands-or-interests"></a>Definir as suas marcas ou interesses

Selecione uma das seguintes opções:

- **Setor** : o sistema identifica as principais marcas ou interesses relevantes para o seu setor e melhora os dados do seu cliente com eles.
- **Escolher os seus próprios**: selecione até cinco itens a partir da lista de marcas ou interesses que são mais relevantes para a sua organização.

Para adicionar uma marca ou um interesse, introduza-o na área de introdução para obter sugestões em função da correspondência de termos. Se não listarmos uma marca ou um interesse que procura, envie-nos comentários com a ligação **Sugerir**.

### <a name="review-enrichment-preferences"></a>Rever preferências de melhoramento

Reveja as suas preferências de melhoramento predefinidas e atualize-as conforme necessário.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de ecrã da janela de preferências de melhoramento.":::

### <a name="select-entity-to-enrich"></a>Selecione a entidade a melhorar

Selecione **Entidade melhorada** e escolha o conjunto de dados que pretende melhorar com os dados da empresa a partir do Microsoft Graph. Pode selecionar a entidade Cliente para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.

### <a name="map-your-fields"></a>Mapear os seus campos

Mapeie os campos da sua entidade de cliente unificada para definir o segmento demográfico que pretende que o sistema utilize para melhorar os dados do seu cliente. Mapeie País/Região e, pelo menos, os atributos Data de Nascimento e Sexo. Adicionalmente, tem de mapear pelo menos uma Localidade (e Distrito) ou Código postal. Selecione **Editar** para definir o mapeamento dos campos e selecione **Aplicar** quando tiver terminado. Selecione **Guardar** para concluir o mapeamento de campos.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
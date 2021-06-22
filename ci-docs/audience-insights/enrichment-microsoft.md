---
title: Enriquecer perfis de clientes com dados da Microsoft
description: Utilize dados proprietários da Microsoft para enriquecer os dados dos seus clientes com afinidades de marcas e interesses.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245721"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="51eba-103">Melhorar perfis de cliente com afinidades de marca e interesse (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="51eba-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="51eba-104">Utilize dados proprietários da Microsoft para enriquecer os dados dos seus clientes com afinidades de marcas e interesses.</span><span class="sxs-lookup"><span data-stu-id="51eba-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="51eba-105">Estas afinidades são determinadas com base nos dados de pessoas com dados demográficos semelhantes aos dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="51eba-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="51eba-106">Estas informações ajudam-no a compreender melhor e segmentar os clientes com base nas afinidades com marcas e interesses específicos.</span><span class="sxs-lookup"><span data-stu-id="51eba-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="51eba-107">Nas informações da audiência, vá a **Dados** > **Melhoramento** para [configurar e ver melhoramentos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="51eba-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="51eba-108">Para configurar o enriquecimento de afinidades de marcas, vá ao separador **Descubrir** e selecione **Enriquecer os meus dados** no mosaico **Marcas**.</span><span class="sxs-lookup"><span data-stu-id="51eba-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="51eba-109">Para configurar o enriquecimento de afinidades de interesses, vá ao separador **Descubrir** e selecione **Enriquecer os meus dados** no mosaico **Interesses**.</span><span class="sxs-lookup"><span data-stu-id="51eba-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="51eba-110">![Mosaicos de Marcas e Interesses](media/BrandsInterest-tile-Hub.png "Mosaicos de Marcas e Interesses")</span><span class="sxs-lookup"><span data-stu-id="51eba-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="51eba-111">Como determinamos afinidades</span><span class="sxs-lookup"><span data-stu-id="51eba-111">How we determine affinities</span></span>

<span data-ttu-id="51eba-112">Utilizamos os dados de pesquisa online da Microsoft para encontrar afinidades com marcas e interesses em vários segmentos demográficos (definidos por idade, sexo ou localização).</span><span class="sxs-lookup"><span data-stu-id="51eba-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="51eba-113">O volume de pesquisa online para uma marca ou um interesse determina quanta afinidade um segmento demográfico, em comparação com outros segmentos, tem com essa marca ou interesse.</span><span class="sxs-lookup"><span data-stu-id="51eba-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="51eba-114">Nível e pontuação de afinidade</span><span class="sxs-lookup"><span data-stu-id="51eba-114">Affinity level and score</span></span>

<span data-ttu-id="51eba-115">Em cada perfil de cliente melhorado, fornecemos dois valores relacionados – nível de afinidade e pontuação de afinidade.</span><span class="sxs-lookup"><span data-stu-id="51eba-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="51eba-116">Estes valores ajudam-no a determinar quão forte é a afinidade para o segmento demográfico desse perfil, para uma marca ou interesse, em comparação com outros segmentos demográficos.</span><span class="sxs-lookup"><span data-stu-id="51eba-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="51eba-117">O *nível de afinidade* consiste em quatro níveis e a *pontuação de afinidade* é calculada numa escala de 100 pontos que mapeia para os níveis de afinidade.</span><span class="sxs-lookup"><span data-stu-id="51eba-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="51eba-118">Nível de afinidade</span><span class="sxs-lookup"><span data-stu-id="51eba-118">Affinity level</span></span> |<span data-ttu-id="51eba-119">Pontuação de afinidade</span><span class="sxs-lookup"><span data-stu-id="51eba-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="51eba-120">Muito alta</span><span class="sxs-lookup"><span data-stu-id="51eba-120">Very high</span></span>     | <span data-ttu-id="51eba-121">85-100</span><span class="sxs-lookup"><span data-stu-id="51eba-121">85-100</span></span>       |
|<span data-ttu-id="51eba-122">Alto</span><span class="sxs-lookup"><span data-stu-id="51eba-122">High</span></span>     | <span data-ttu-id="51eba-123">70-84</span><span class="sxs-lookup"><span data-stu-id="51eba-123">70-84</span></span>        |
|<span data-ttu-id="51eba-124">Médio</span><span class="sxs-lookup"><span data-stu-id="51eba-124">Medium</span></span>     | <span data-ttu-id="51eba-125">35-69</span><span class="sxs-lookup"><span data-stu-id="51eba-125">35-69</span></span>        |
|<span data-ttu-id="51eba-126">Baixo</span><span class="sxs-lookup"><span data-stu-id="51eba-126">Low</span></span>     | <span data-ttu-id="51eba-127">1-34</span><span class="sxs-lookup"><span data-stu-id="51eba-127">1-34</span></span>        |

<span data-ttu-id="51eba-128">Dependendo da granularidade que gostaria para medir a afinidade, pode utilizar o nível de afinidade ou a pontuação.</span><span class="sxs-lookup"><span data-stu-id="51eba-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="51eba-129">A pontuação de afinidade dá-lhe um controlo mais preciso.</span><span class="sxs-lookup"><span data-stu-id="51eba-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="51eba-130">Países/regiões suportados</span><span class="sxs-lookup"><span data-stu-id="51eba-130">Supported countries/regions</span></span>

<span data-ttu-id="51eba-131">Atualmente, suportamos as seguintes opções de país/região: Austrália, Canadá (inglês), França, Alemanha, Reino Unido ou Estados Unidos (inglês).</span><span class="sxs-lookup"><span data-stu-id="51eba-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="51eba-132">Para selecionar um país, abra o **Enriquecimento de marcas** ou o **Enriquecimento de interesses** e selecione **Alterar** ao lado de **País/Região**.</span><span class="sxs-lookup"><span data-stu-id="51eba-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="51eba-133">No painel de **Definições de País/Região**, escolha uma opção e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="51eba-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="51eba-134">Implicações relacionadas com a seleção do país</span><span class="sxs-lookup"><span data-stu-id="51eba-134">Implications related to country selection</span></span>

- <span data-ttu-id="51eba-135">Ao [escolher as suas próprias marcas](#define-your-brands-or-interests), o sistema fornece sugestões baseadas no país ou região selecionados.</span><span class="sxs-lookup"><span data-stu-id="51eba-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="51eba-136">Ao [escolher um setor](#define-your-brands-or-interests), obterá as marcas ou interesses mais relevantes com base no país ou região selecionados.</span><span class="sxs-lookup"><span data-stu-id="51eba-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="51eba-137">Ao [melhorar perfis](#refresh-enrichment), melhoraremos todos os perfis de cliente para os quais obtemos dados para as marcas e interesses selecionados.</span><span class="sxs-lookup"><span data-stu-id="51eba-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="51eba-138">Incluindo perfis que não estão no país ou região selecionados.</span><span class="sxs-lookup"><span data-stu-id="51eba-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="51eba-139">Por exemplo, se selecionou Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados disponíveis para as marcas e interesses selecionados nos EUA.</span><span class="sxs-lookup"><span data-stu-id="51eba-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="51eba-140">Configurar Enriquecimento</span><span class="sxs-lookup"><span data-stu-id="51eba-140">Configure Enrichment</span></span>

<span data-ttu-id="51eba-141">Uma experiência guiada ajuda-o através da configuração dos enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="51eba-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="51eba-142">Definir as suas marcas ou interesses</span><span class="sxs-lookup"><span data-stu-id="51eba-142">Define your brands or interests</span></span>

<span data-ttu-id="51eba-143">Escolha até cinco marcas ou interesses utilizando uma ou ambas as opções:</span><span class="sxs-lookup"><span data-stu-id="51eba-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="51eba-144">**Setor**: selecione o seu setor na lista pendente e, em seguida, escolha entre as principais marcas ou interesses para este setor.</span><span class="sxs-lookup"><span data-stu-id="51eba-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="51eba-145">**Escolha o seu**: introduza uma marca ou interesse que seja relevante para a sua organização e, em seguida, escolha entre as sugestões correspondentes.</span><span class="sxs-lookup"><span data-stu-id="51eba-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="51eba-146">Se não listarmos uma marca ou um interesse que procura, envie-nos comentários com a ligação **Sugerir**.</span><span class="sxs-lookup"><span data-stu-id="51eba-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="51eba-147">Rever preferências de melhoramento</span><span class="sxs-lookup"><span data-stu-id="51eba-147">Review enrichment preferences</span></span>

<span data-ttu-id="51eba-148">Reveja as suas preferências de melhoramento predefinidas e atualize-as conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="51eba-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de ecrã da janela de preferências de melhoramento.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="51eba-150">Selecione a entidade a melhorar</span><span class="sxs-lookup"><span data-stu-id="51eba-150">Select entity to enrich</span></span>

<span data-ttu-id="51eba-151">Selecione **Entidade enriquecida** e escolha o conjunto de dados que pretende enriquecer com os dados da empresa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51eba-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="51eba-152">Pode selecionar a entidade Cliente para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="51eba-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="51eba-153">Mapear os seus campos</span><span class="sxs-lookup"><span data-stu-id="51eba-153">Map your fields</span></span>

<span data-ttu-id="51eba-154">Mapeie os campos da sua entidade de cliente unificada para definir o segmento demográfico que pretende que o sistema utilize para melhorar os dados do seu cliente.</span><span class="sxs-lookup"><span data-stu-id="51eba-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="51eba-155">Mapeie País/Região e, pelo menos, os atributos Data de Nascimento e Sexo.</span><span class="sxs-lookup"><span data-stu-id="51eba-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="51eba-156">Adicionalmente, tem de mapear pelo menos uma Localidade (e Distrito) ou Código postal.</span><span class="sxs-lookup"><span data-stu-id="51eba-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="51eba-157">Selecione **Editar** para definir o mapeamento dos campos e selecione **Aplicar** quando tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="51eba-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="51eba-158">Selecione **Guardar** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="51eba-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="51eba-159">Os seguintes formatos e valores são suportados, os valores não são sensíveis às maiúsculas e minúsculas:</span><span class="sxs-lookup"><span data-stu-id="51eba-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="51eba-160">**Data de Nascimento**: recomendamos que a data de nascimento seja convertida para o tipo DateTime durante a ingestão de dados.</span><span class="sxs-lookup"><span data-stu-id="51eba-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="51eba-161">Alternativamente, pode ser uma cadeia no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="51eba-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="51eba-162">**Sexo**: Masculino, Feminino, Desconhecido</span><span class="sxs-lookup"><span data-stu-id="51eba-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="51eba-163">**Código postal**: xódigos postais de cinco dígitos para EUA, código postal padrão em todos os outros lugares</span><span class="sxs-lookup"><span data-stu-id="51eba-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="51eba-164">**Cidade**: nome da cidade em inglês</span><span class="sxs-lookup"><span data-stu-id="51eba-164">**City**: City name in English</span></span>
- <span data-ttu-id="51eba-165">**Estado/Província**: abreviatura de duas letras para os EUA e Canadá.</span><span class="sxs-lookup"><span data-stu-id="51eba-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="51eba-166">Abreviatura de duas ou três letras para a Austrália.</span><span class="sxs-lookup"><span data-stu-id="51eba-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="51eba-167">Não aplicável à França, Alemanha ou Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="51eba-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="51eba-168">**País/Região**:</span><span class="sxs-lookup"><span data-stu-id="51eba-168">**Country/Region**:</span></span>

  - <span data-ttu-id="51eba-169">EUA: Estados Unidos da América, Estados Unidos, EUA, EU, América</span><span class="sxs-lookup"><span data-stu-id="51eba-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="51eba-170">CA: Canadá, CA</span><span class="sxs-lookup"><span data-stu-id="51eba-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="51eba-171">GB: Reino Unido, RU, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha</span><span class="sxs-lookup"><span data-stu-id="51eba-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="51eba-172">AU: Austrália, AU, Comunidade da Austrália</span><span class="sxs-lookup"><span data-stu-id="51eba-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="51eba-173">FR: França, FR, República Francesa</span><span class="sxs-lookup"><span data-stu-id="51eba-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="51eba-174">AL: Alemanha, Alemão, Deutschland, Allemagne, DE, República Federal da Alemanha, República da Alemanha</span><span class="sxs-lookup"><span data-stu-id="51eba-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="51eba-175">Reveja e atribua um nome ao enriquecimento</span><span class="sxs-lookup"><span data-stu-id="51eba-175">Review and name the enrichment</span></span>

<span data-ttu-id="51eba-176">Por fim, pode rever as informações e fornecer um nome ao enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="51eba-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisão de interesses e atribuir nome à página.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="51eba-178">Atualizar enriquecimento</span><span class="sxs-lookup"><span data-stu-id="51eba-178">Refresh enrichment</span></span>

<span data-ttu-id="51eba-179">Execute o melhoramento depois de configurar as marcas, os interesses e o mapeamento de campos para a demografia.</span><span class="sxs-lookup"><span data-stu-id="51eba-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="51eba-180">Para iniciar o processo, selecione **Executar** na página de configuração da marcas ou interesses.</span><span class="sxs-lookup"><span data-stu-id="51eba-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="51eba-181">Para além disso, pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="51eba-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="51eba-182">Consoante o tamanho dos dados dos seus clientes, a execução do melhoramento poderá demorar vários minutos.</span><span class="sxs-lookup"><span data-stu-id="51eba-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="51eba-183">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="51eba-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="51eba-184">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="51eba-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="51eba-185">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="51eba-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="51eba-186">Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="51eba-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="51eba-187">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="51eba-187">Enrichment results</span></span>

<span data-ttu-id="51eba-188">Depois de executar o processo de melhoramento, aceda a **Meus enriquecimentos** para rever o número total de clientes melhorados e uma discriminação de marcas ou interesses nos perfis de cliente melhorados.</span><span class="sxs-lookup"><span data-stu-id="51eba-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pré-visualização dos resultados depois de executar o processo de enriquecimento":::

<span data-ttu-id="51eba-190">Reveja os dados melhorados ao selecionar **Ver dados melhorados** no gráfico.</span><span class="sxs-lookup"><span data-stu-id="51eba-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="51eba-191">Os dados melhorados para as marcas vão para a entidade **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="51eba-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="51eba-192">Os dados para os interesses estão na entidade **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="51eba-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="51eba-193">Também encontrará estas entidades listadas no grupo **Enriquecimento** em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="51eba-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="51eba-194">Ver dados de enriquecimento no cartão de cliente</span><span class="sxs-lookup"><span data-stu-id="51eba-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="51eba-195">As afinidades de marca e de interesses também podem ser vistas em cartões de clientes individuais.</span><span class="sxs-lookup"><span data-stu-id="51eba-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="51eba-196">Aceda a **Clientes** e selecione um perfil de cliente.</span><span class="sxs-lookup"><span data-stu-id="51eba-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="51eba-197">No cartão de cliente, encontrará gráficos para as marcas ou interesses pelas quais as pessoas no perfil demográfico desse cliente têm afinidade.</span><span class="sxs-lookup"><span data-stu-id="51eba-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos":::

## <a name="next-steps"></a><span data-ttu-id="51eba-199">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="51eba-199">Next steps</span></span>

<span data-ttu-id="51eba-200">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="51eba-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="51eba-201">Crie [Segmentos](segments.md), [Medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="51eba-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

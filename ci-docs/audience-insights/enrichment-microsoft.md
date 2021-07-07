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
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305170"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="48d1c-103">Melhorar perfis de cliente com afinidades de marca e interesse (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="48d1c-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="48d1c-104">Utilize dados proprietários da Microsoft para enriquecer os dados dos seus clientes com afinidades de marcas e interesses.</span><span class="sxs-lookup"><span data-stu-id="48d1c-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="48d1c-105">Estas afinidades são baseadas em dados de pessoas com demografia semelhante à dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="48d1c-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="48d1c-106">Estas informações ajudam-no a compreender melhor e segmentar os clientes com base nas afinidades com marcas e interesses específicos.</span><span class="sxs-lookup"><span data-stu-id="48d1c-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="48d1c-107">Nas informações da audiência, vá a **Dados** > **Melhoramento** para [configurar e ver melhoramentos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="48d1c-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="48d1c-108">Para configurar o enriquecimento de afinidades de marcas, vá ao separador **Descubrir** e selecione **Enriquecer os meus dados** no mosaico **Marcas**.</span><span class="sxs-lookup"><span data-stu-id="48d1c-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="48d1c-109">Para configurar o enriquecimento de afinidades de interesses, vá ao separador **Descubrir** e selecione **Enriquecer os meus dados** no mosaico **Interesses**.</span><span class="sxs-lookup"><span data-stu-id="48d1c-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48d1c-110">![Mosaicos Marcas e Interesses](media/BrandsInterest-tile-Hub.png "Mosaicos Marcas e Interesses")</span><span class="sxs-lookup"><span data-stu-id="48d1c-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="48d1c-111">Como determinamos afinidades</span><span class="sxs-lookup"><span data-stu-id="48d1c-111">How we determine affinities</span></span>

<span data-ttu-id="48d1c-112">Utilizamos os dados de pesquisa online da Microsoft para encontrar afinidades com marcas e interesses em vários segmentos demográficos (definidos por idade, sexo ou localização).</span><span class="sxs-lookup"><span data-stu-id="48d1c-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="48d1c-113">O volume de pesquisa online para uma marca ou um interesse determina quanta afinidade um segmento demográfico, em comparação com outros segmentos, tem com essa marca ou interesse.</span><span class="sxs-lookup"><span data-stu-id="48d1c-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="48d1c-114">Nível e pontuação de afinidade</span><span class="sxs-lookup"><span data-stu-id="48d1c-114">Affinity level and score</span></span>

<span data-ttu-id="48d1c-115">Em cada perfil de cliente melhorado, fornecemos dois valores relacionados: nível de afinidade e pontuação de afinidade.</span><span class="sxs-lookup"><span data-stu-id="48d1c-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="48d1c-116">Estes valores ajudam-no a determinar quão forte é a afinidade para o segmento demográfico desse perfil, para uma marca ou interesse, em comparação com outros segmentos demográficos.</span><span class="sxs-lookup"><span data-stu-id="48d1c-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="48d1c-117">O *nível de afinidade* consiste em quatro níveis e a *pontuação de afinidade* é calculada numa escala de 100 pontos que mapeia para os níveis de afinidade.</span><span class="sxs-lookup"><span data-stu-id="48d1c-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="48d1c-118">Nível de afinidade</span><span class="sxs-lookup"><span data-stu-id="48d1c-118">Affinity level</span></span> |<span data-ttu-id="48d1c-119">Pontuação de afinidade</span><span class="sxs-lookup"><span data-stu-id="48d1c-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="48d1c-120">Muito alta</span><span class="sxs-lookup"><span data-stu-id="48d1c-120">Very high</span></span>     | <span data-ttu-id="48d1c-121">85-100</span><span class="sxs-lookup"><span data-stu-id="48d1c-121">85-100</span></span>       |
|<span data-ttu-id="48d1c-122">Alto</span><span class="sxs-lookup"><span data-stu-id="48d1c-122">High</span></span>     | <span data-ttu-id="48d1c-123">70-84</span><span class="sxs-lookup"><span data-stu-id="48d1c-123">70-84</span></span>        |
|<span data-ttu-id="48d1c-124">Médio</span><span class="sxs-lookup"><span data-stu-id="48d1c-124">Medium</span></span>     | <span data-ttu-id="48d1c-125">35-69</span><span class="sxs-lookup"><span data-stu-id="48d1c-125">35-69</span></span>        |
|<span data-ttu-id="48d1c-126">Baixo</span><span class="sxs-lookup"><span data-stu-id="48d1c-126">Low</span></span>     | <span data-ttu-id="48d1c-127">1-34</span><span class="sxs-lookup"><span data-stu-id="48d1c-127">1-34</span></span>        |

<span data-ttu-id="48d1c-128">Dependendo da granularidade que gostaria para medir a afinidade, pode utilizar o nível de afinidade ou a pontuação.</span><span class="sxs-lookup"><span data-stu-id="48d1c-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="48d1c-129">A pontuação de afinidade dá-lhe um controlo mais preciso.</span><span class="sxs-lookup"><span data-stu-id="48d1c-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="48d1c-130">Países/regiões suportados</span><span class="sxs-lookup"><span data-stu-id="48d1c-130">Supported countries/regions</span></span>

<span data-ttu-id="48d1c-131">Atualmente, suportamos as seguintes opções de país/região: Austrália, Canadá (inglês), França, Alemanha, Reino Unido ou Estados Unidos (inglês).</span><span class="sxs-lookup"><span data-stu-id="48d1c-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="48d1c-132">Para selecionar um país ou região, abra **Melhoramento de marcas** ou **Melhoramento de interesses** e selecione **Alterar** junto a **País/Região**.</span><span class="sxs-lookup"><span data-stu-id="48d1c-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="48d1c-133">No painel de **Definições de País/Região**, escolha uma opção e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="48d1c-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="48d1c-134">Implicações relacionadas com a seleção do país</span><span class="sxs-lookup"><span data-stu-id="48d1c-134">Implications related to country selection</span></span>

- <span data-ttu-id="48d1c-135">Ao [escolher as suas próprias marcas](#define-your-brands-or-interests), o sistema fornece sugestões baseadas no país ou região selecionados.</span><span class="sxs-lookup"><span data-stu-id="48d1c-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="48d1c-136">Ao [escolher um setor](#define-your-brands-or-interests), obterá as marcas ou interesses mais relevantes com base no país ou região selecionados.</span><span class="sxs-lookup"><span data-stu-id="48d1c-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="48d1c-137">Ao [melhorar perfis](#refresh-enrichment), melhoraremos todos os perfis de clientes para os quais obtemos dados para as marcas e interesses selecionados, incluindo perfis que não estão no país ou região selecionados.</span><span class="sxs-lookup"><span data-stu-id="48d1c-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="48d1c-138">Por exemplo, se selecionou Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados disponíveis para as marcas e interesses selecionados nos EUA.</span><span class="sxs-lookup"><span data-stu-id="48d1c-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="48d1c-139">Configurar melhoramento</span><span class="sxs-lookup"><span data-stu-id="48d1c-139">Configure enrichment</span></span>

<span data-ttu-id="48d1c-140">Uma experiência guiada ajuda-o através da configuração dos enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="48d1c-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="48d1c-141">Definir as suas marcas ou interesses</span><span class="sxs-lookup"><span data-stu-id="48d1c-141">Define your brands or interests</span></span>

<span data-ttu-id="48d1c-142">Escolha até cinco marcas ou interesses utilizando uma ou ambas as opções:</span><span class="sxs-lookup"><span data-stu-id="48d1c-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="48d1c-143">**Setor**: selecione o seu setor da lista pendente e, em seguida, escolha entre as marcas ou interesses principais para esse setor.</span><span class="sxs-lookup"><span data-stu-id="48d1c-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="48d1c-144">**Escolha o seu**: introduza uma marca ou interesse que seja relevante para a sua organização e, em seguida, escolha entre as sugestões correspondentes.</span><span class="sxs-lookup"><span data-stu-id="48d1c-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="48d1c-145">Se não listarmos uma marca ou um interesse que procura, envie-nos comentários com a ligação **Sugerir**.</span><span class="sxs-lookup"><span data-stu-id="48d1c-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="48d1c-146">Rever preferências de melhoramento</span><span class="sxs-lookup"><span data-stu-id="48d1c-146">Review enrichment preferences</span></span>

<span data-ttu-id="48d1c-147">Reveja as suas preferências de melhoramento predefinidas e atualize-as conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="48d1c-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de ecrã da janela de preferências de melhoramento.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="48d1c-149">Selecione a entidade a melhorar</span><span class="sxs-lookup"><span data-stu-id="48d1c-149">Select entity to enrich</span></span>

<span data-ttu-id="48d1c-150">Selecione **Entidade enriquecida** e escolha o conjunto de dados que pretende enriquecer com os dados da empresa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="48d1c-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="48d1c-151">Pode selecionar a entidade Cliente para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="48d1c-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="48d1c-152">Mapear os seus campos</span><span class="sxs-lookup"><span data-stu-id="48d1c-152">Map your fields</span></span>

<span data-ttu-id="48d1c-153">Mapeie os campos da sua entidade de cliente unificada para definir o segmento demográfico que pretende que o sistema utilize para melhorar os dados do seu cliente.</span><span class="sxs-lookup"><span data-stu-id="48d1c-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="48d1c-154">Mapeie País/Região e, pelo menos, os atributos Data de Nascimento e Sexo.</span><span class="sxs-lookup"><span data-stu-id="48d1c-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="48d1c-155">Adicionalmente, tem de mapear pelo menos uma Localidade (e Distrito) ou Código postal.</span><span class="sxs-lookup"><span data-stu-id="48d1c-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="48d1c-156">Selecione **Editar** para definir o mapeamento dos campos e selecione **Aplicar** quando tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="48d1c-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="48d1c-157">Selecione **Guardar** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="48d1c-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="48d1c-158">Os seguintes formatos e valores são suportados (os valores não são sensíveis às maiúsculas e minúsculas):</span><span class="sxs-lookup"><span data-stu-id="48d1c-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="48d1c-159">**Data de Nascimento**: recomendamos que a data de nascimento seja convertida para o tipo DateTime durante a ingestão de dados.</span><span class="sxs-lookup"><span data-stu-id="48d1c-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="48d1c-160">Alternativamente, pode ser uma cadeia no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:mm".</span><span class="sxs-lookup"><span data-stu-id="48d1c-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="48d1c-161">**Sexo**: Masculino, Feminino, Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="48d1c-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="48d1c-162">**Código postal**: Códigos postais de cinco dígitos para os Estados Unidos, código postal padrão em todos os outros locais.</span><span class="sxs-lookup"><span data-stu-id="48d1c-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="48d1c-163">**Cidade**: nome da cidade em inglês.</span><span class="sxs-lookup"><span data-stu-id="48d1c-163">**City**: City name in English.</span></span>
- <span data-ttu-id="48d1c-164">**Estado/Província**: abreviatura de duas letras para os EUA e Canadá.</span><span class="sxs-lookup"><span data-stu-id="48d1c-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="48d1c-165">Abreviatura de duas ou três letras para a Austrália.</span><span class="sxs-lookup"><span data-stu-id="48d1c-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="48d1c-166">Não aplicável à França, Alemanha ou Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="48d1c-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="48d1c-167">**País/Região**:</span><span class="sxs-lookup"><span data-stu-id="48d1c-167">**Country/Region**:</span></span>

  - <span data-ttu-id="48d1c-168">EUA: Estados Unidos da América, Estados Unidos, EUA, EU, América</span><span class="sxs-lookup"><span data-stu-id="48d1c-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="48d1c-169">CA: Canadá, CA</span><span class="sxs-lookup"><span data-stu-id="48d1c-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="48d1c-170">GB: Reino Unido, RU, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha</span><span class="sxs-lookup"><span data-stu-id="48d1c-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="48d1c-171">AU: Austrália, AU, Comunidade da Austrália</span><span class="sxs-lookup"><span data-stu-id="48d1c-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="48d1c-172">FR: França, FR, República Francesa</span><span class="sxs-lookup"><span data-stu-id="48d1c-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="48d1c-173">AL: Alemanha, Alemão, Deutschland, Allemagne, DE, República Federal da Alemanha, República da Alemanha</span><span class="sxs-lookup"><span data-stu-id="48d1c-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="48d1c-174">Reveja e atribua um nome ao enriquecimento</span><span class="sxs-lookup"><span data-stu-id="48d1c-174">Review and name the enrichment</span></span>

<span data-ttu-id="48d1c-175">Por fim, pode rever as informações e fornecer um nome ao enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="48d1c-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisão de interesses e atribuir nome à página.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="48d1c-177">Atualizar enriquecimento</span><span class="sxs-lookup"><span data-stu-id="48d1c-177">Refresh enrichment</span></span>

<span data-ttu-id="48d1c-178">Execute o melhoramento depois de configurar as marcas, os interesses e o mapeamento de campos para a demografia.</span><span class="sxs-lookup"><span data-stu-id="48d1c-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="48d1c-179">Para iniciar o processo, selecione **Executar** na página de configuração da marcas ou interesses.</span><span class="sxs-lookup"><span data-stu-id="48d1c-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="48d1c-180">Para além disso, pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="48d1c-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="48d1c-181">Consoante o tamanho dos dados dos seus clientes, a execução do melhoramento poderá demorar vários minutos.</span><span class="sxs-lookup"><span data-stu-id="48d1c-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="48d1c-182">Há [seis tipos de estados](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="48d1c-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="48d1c-183">Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="48d1c-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="48d1c-184">Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa.</span><span class="sxs-lookup"><span data-stu-id="48d1c-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="48d1c-185">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, encontrará informações adicionais: tempo de processamento, data do último processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="48d1c-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="48d1c-186">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="48d1c-186">Enrichment results</span></span>

<span data-ttu-id="48d1c-187">Depois de executar o processo de melhoramento, aceda a **Meus enriquecimentos** para rever o número total de clientes melhorados e uma discriminação de marcas ou interesses nos perfis de cliente melhorados.</span><span class="sxs-lookup"><span data-stu-id="48d1c-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pré-visualização dos resultados depois de executar o processo de enriquecimento":::

<span data-ttu-id="48d1c-189">Reveja os dados melhorados ao selecionar **Ver dados melhorados** no gráfico.</span><span class="sxs-lookup"><span data-stu-id="48d1c-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="48d1c-190">Os dados melhorados para as marcas vão para a entidade **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="48d1c-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="48d1c-191">Os dados para os interesses estão na entidade **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="48d1c-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="48d1c-192">Também encontrará estas entidades listadas no grupo **Enriquecimento** em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="48d1c-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="48d1c-193">Ver dados de enriquecimento no cartão de cliente</span><span class="sxs-lookup"><span data-stu-id="48d1c-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="48d1c-194">As afinidades de marca e de interesses também podem ser vistas em cartões de clientes individuais.</span><span class="sxs-lookup"><span data-stu-id="48d1c-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="48d1c-195">Aceda a **Clientes** e selecione um perfil de cliente.</span><span class="sxs-lookup"><span data-stu-id="48d1c-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="48d1c-196">No cartão de cliente, encontrará gráficos para as marcas ou interesses pelas quais as pessoas no perfil demográfico desse cliente têm afinidade.</span><span class="sxs-lookup"><span data-stu-id="48d1c-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos":::

## <a name="next-steps"></a><span data-ttu-id="48d1c-198">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="48d1c-198">Next steps</span></span>

<span data-ttu-id="48d1c-199">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="48d1c-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="48d1c-200">Crie [Segmentos](segments.md), [Medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="48d1c-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Enriquecimento de melhorias de endereços
description: Enriqueça e normalize a informação de endereço dos perfis de cliente com os modelos da Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965592"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="49725-103">Enriquecimento de perfis de clientes com endereços melhorados</span><span class="sxs-lookup"><span data-stu-id="49725-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="49725-104">Os endereços nos seus dados podem não estar estruturados, estar incompletos ou incorretos.</span><span class="sxs-lookup"><span data-stu-id="49725-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="49725-105">Utilize os modelos da Microsoft para normalizar e enriquecer os seus endereços no [formato do Common Data Model](/common-data-model/schema/core/applicationcommon/address) para uma melhor precisão e informações.</span><span class="sxs-lookup"><span data-stu-id="49725-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="49725-106">Como melhoramos endereços</span><span class="sxs-lookup"><span data-stu-id="49725-106">How we enhance addresses</span></span>

<span data-ttu-id="49725-107">O nosso modelo passa por um processo em dois passos para melhorar um endereço.</span><span class="sxs-lookup"><span data-stu-id="49725-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="49725-108">Em primeiro lugar, analisa o endereço para identificar os seus componentes e coloca-os num formato estruturado.</span><span class="sxs-lookup"><span data-stu-id="49725-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="49725-109">Depois, utilizamos inteligência artificial para corrigir, completar e uniformizar os valores no endereço.</span><span class="sxs-lookup"><span data-stu-id="49725-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="49725-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="49725-110">Example</span></span>

<span data-ttu-id="49725-111">As informações de endereço podem estar num formato não padrão e conter erros ortográficos.</span><span class="sxs-lookup"><span data-stu-id="49725-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="49725-112">O modelo pode corrigir estes problemas e criar endereços consistentes em perfis de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="49725-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="49725-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="49725-113">Limitations</span></span>

<span data-ttu-id="49725-114">Os endereços melhorados apenas funcionam com os valores que já existem nos dados de endereços ingeridos.</span><span class="sxs-lookup"><span data-stu-id="49725-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="49725-115">O modelo não:</span><span class="sxs-lookup"><span data-stu-id="49725-115">The model doesn't:</span></span> 

1. <span data-ttu-id="49725-116">Verifica se o endereço é um endereço válido.</span><span class="sxs-lookup"><span data-stu-id="49725-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="49725-117">Verifica se algum dos valores, tais como códigos postais ou nomes de rua, são válidos.</span><span class="sxs-lookup"><span data-stu-id="49725-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="49725-118">Muda valores que não reconhece.</span><span class="sxs-lookup"><span data-stu-id="49725-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="49725-119">O modelo utiliza técnicas baseadas em aprendizagem automática para melhorar endereços.</span><span class="sxs-lookup"><span data-stu-id="49725-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="49725-120">Embora apliquemos um limiar de confiança elevado para quando o modelo muda um valor de entrada, como em qualquer modelo baseado em ML, a precisão de 100% não é garantida.</span><span class="sxs-lookup"><span data-stu-id="49725-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="49725-121">Países ou regiões suportados</span><span class="sxs-lookup"><span data-stu-id="49725-121">Supported countries or regions</span></span>

<span data-ttu-id="49725-122">Atualmente, suportamos endereços enriquecedores nestes países ou regiões:</span><span class="sxs-lookup"><span data-stu-id="49725-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="49725-123">Austrália</span><span class="sxs-lookup"><span data-stu-id="49725-123">Australia</span></span>
- <span data-ttu-id="49725-124">Canadá</span><span class="sxs-lookup"><span data-stu-id="49725-124">Canada</span></span>
- <span data-ttu-id="49725-125">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="49725-125">United Kingdom</span></span>
- <span data-ttu-id="49725-126">Estados Unidos da América</span><span class="sxs-lookup"><span data-stu-id="49725-126">United States</span></span>

<span data-ttu-id="49725-127">Os endereços têm de conter um valor de país/região.</span><span class="sxs-lookup"><span data-stu-id="49725-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="49725-128">Não processamos endereços para países ou regiões que não são suportados e endereços que não têm nenhum país ou região fornecido.</span><span class="sxs-lookup"><span data-stu-id="49725-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="49725-129">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="49725-129">Configure the enrichment</span></span>

1. <span data-ttu-id="49725-130">Aceda a **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="49725-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="49725-131">Selecione **Enriquecer os meus dados** no mosaico **Endereços melhorados**.</span><span class="sxs-lookup"><span data-stu-id="49725-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de ecrã do mosaico de endereços melhorados.":::

1. <span data-ttu-id="49725-133">Selecione o **Conjunto de dados do cliente** e escolha a entidade que contém os endereços que pretende enriquecer.</span><span class="sxs-lookup"><span data-stu-id="49725-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="49725-134">Pode selecionar a entidade *Cliente* para enriquecer endereços em todos os seus perfis de clientes ou selecionar uma entidade de segmento para enriquecer endereços apenas nos perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="49725-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="49725-135">Selecionar a forma como os endereços estão formatados no seu conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="49725-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="49725-136">Escolha **Endereço de atributo único** se os endereços dos seus dados utilizarem um único campo.</span><span class="sxs-lookup"><span data-stu-id="49725-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="49725-137">Escolha **Endereço de vários atributos** se os endereços dos seus dados utilizarem mais do que um campo de dados.</span><span class="sxs-lookup"><span data-stu-id="49725-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49725-138">País/Região é obrigatório tanto no endereço de atributo único como no endereço de vários atributos.</span><span class="sxs-lookup"><span data-stu-id="49725-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="49725-139">Endereços que não contenham valores válidos ou valores de país/região suportados não serão enriquecidos</span><span class="sxs-lookup"><span data-stu-id="49725-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="49725-140">Mapeie os campos de endereço da sua entidade de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="49725-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Página de mapeamento de campo de endereço melhorado.":::

1. <span data-ttu-id="49725-142">Selecione **Seguinte** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="49725-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="49725-143">Forneça um nome para o enriquecimento e para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="49725-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="49725-144">Selecione **Guardar enriquecimento** depois de rever as suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="49725-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="49725-145">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="49725-145">Enrichment results</span></span>

<span data-ttu-id="49725-146">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="49725-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="49725-147">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="49725-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="49725-148">O tempo de processamento depende do tamanho dos dados do seu cliente.</span><span class="sxs-lookup"><span data-stu-id="49725-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="49725-149">Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="49725-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="49725-150">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="49725-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="49725-151">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="49725-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="49725-152">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="49725-152">Next steps</span></span>

<span data-ttu-id="49725-153">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="49725-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="49725-154">Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="49725-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Melhoramento com o melhoramento de terceiros da Experian
description: Informações gerais sobre o melhoramento de terceiros da Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309834"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f5729-103">Melhore perfis do cliente com demografia a partir da Experian (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="f5729-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f5729-104">A Experian é um líder global em serviços de relatórios e marketing de crédito ao consumo e às empresas.</span><span class="sxs-lookup"><span data-stu-id="f5729-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f5729-105">Com os serviços de melhoramento de dados da Experian, pode obter uma compreensão mais profunda dos seus clientes melhorando os seus perfis com dados demográficos, tal como agregado familiar, rendimento e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f5729-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5729-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f5729-106">Prerequisites</span></span>

<span data-ttu-id="f5729-107">Para configurar a Experian, os seguintes pré-requisitos têm de ser cumpridos:</span><span class="sxs-lookup"><span data-stu-id="f5729-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f5729-108">Tem uma subscrição ativa da Experian.</span><span class="sxs-lookup"><span data-stu-id="f5729-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f5729-109">Para obter uma subscrição, [contacte a Experian](https://www.experian.com/marketing-services/contact) diretamente.</span><span class="sxs-lookup"><span data-stu-id="f5729-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f5729-110">[Mais informações sobre o Melhoramento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="f5729-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="f5729-111">Uma ligação Experian já foi configurada por um administrador *ou* tem permissões de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="f5729-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="f5729-112">Também precisa do ID de Utilizador, ID de Entidade e Número de Modelo para a sua conta de Transporte Seguro (ST) ativada por SSH que a Experian criou para si.</span><span class="sxs-lookup"><span data-stu-id="f5729-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="f5729-113">Países/regiões suportados</span><span class="sxs-lookup"><span data-stu-id="f5729-113">Supported countries/regions</span></span>

<span data-ttu-id="f5729-114">Atualmente, suportamos apenas o melhoramento de perfis de clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="f5729-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="f5729-115">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="f5729-115">Configure the enrichment</span></span>

1. <span data-ttu-id="f5729-116">Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="f5729-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f5729-117">Selecione **Melhorar os meus dados** no mosaico da Experian.</span><span class="sxs-lookup"><span data-stu-id="f5729-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5729-118">![mosaico Experian](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="f5729-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="f5729-119">Selecione uma [ligação](connections.md) na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="f5729-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="f5729-120">Contacte um administrador se não houver nenhuma ligação disponível.</span><span class="sxs-lookup"><span data-stu-id="f5729-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="f5729-121">Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação** e escolhendo a Experian na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="f5729-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="f5729-122">Selecione **Ligar à Experian** para confirmar a seleção da ligação.</span><span class="sxs-lookup"><span data-stu-id="f5729-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="f5729-123">Selecione **Seguinte** e escolha o **Conjunto de dados de cliente** que pretende melhorar com dados demográficos da Experian.</span><span class="sxs-lookup"><span data-stu-id="f5729-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="f5729-124">Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="f5729-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. <span data-ttu-id="f5729-126">Selecione **Seguinte** e defina que tipo de campos dos seus perfis unificados devem ser utilizados para procurar dados demográficos correspondentes a partir da Experian.</span><span class="sxs-lookup"><span data-stu-id="f5729-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="f5729-127">Pelo menos, um dos campos **Nome e endereço**, **Telefone** ou **E-mail** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="f5729-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="f5729-128">Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos.</span><span class="sxs-lookup"><span data-stu-id="f5729-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="f5729-129">Esta seleção irá afetar os campos de mapeamento a que tem acesso no próximo passo.</span><span class="sxs-lookup"><span data-stu-id="f5729-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="f5729-130">Mais atributos de identificador chave enviados para o Experian, provavelmente, produzem uma taxa de correspondência mais alta.</span><span class="sxs-lookup"><span data-stu-id="f5729-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f5729-131">Selecione **Seguinte** para iniciar o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="f5729-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="f5729-132">Defina que campos dos seus perfis unificados devem ser utilizados para procurar dados demográficos correspondentes a partir da Experian.</span><span class="sxs-lookup"><span data-stu-id="f5729-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="f5729-133">Os campos obrigatórios estão marcados.</span><span class="sxs-lookup"><span data-stu-id="f5729-133">Required fields are marked.</span></span>

1. <span data-ttu-id="f5729-134">Forneça um nome para o enriquecimento e um nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="f5729-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="f5729-135">Selecione **Guardar enriquecimento** depois de rever as suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="f5729-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="f5729-136">Configurar a ligação à Experian</span><span class="sxs-lookup"><span data-stu-id="f5729-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="f5729-137">Tens de ser um administrador para configurar ligações.</span><span class="sxs-lookup"><span data-stu-id="f5729-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f5729-138">Selecione **Adicionar ligação** ao configurar um melhoramento *ou* aceda a **Admin** > **Ligações** e selecione **Configurar** no mosaico da Experian.</span><span class="sxs-lookup"><span data-stu-id="f5729-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="f5729-139">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="f5729-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="f5729-140">Introduza um nome para a ligação na caixa **Nome a Apresentar**.</span><span class="sxs-lookup"><span data-stu-id="f5729-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f5729-141">Introduza o ID de Utilizador, ID de Entidade e Número de Modelo válidos para a sua conta de Transporte Seguro da Experian.</span><span class="sxs-lookup"><span data-stu-id="f5729-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="f5729-142">Reveja e forneça o seu consentimento para a **Privacidade e conformidade dos dados** selecionando **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="f5729-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="f5729-143">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="f5729-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f5729-144">Depois de concluir a verificação, selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f5729-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Painel de configuração da ligação à Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="f5729-146">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="f5729-146">Enrichment results</span></span>

<span data-ttu-id="f5729-147">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="f5729-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f5729-148">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f5729-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f5729-149">O tempo de processamento dependerá do tamanho dos dados do seu cliente e dos processos de melhoramento configurados para a sua conta pela Experian.</span><span class="sxs-lookup"><span data-stu-id="f5729-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f5729-150">Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="f5729-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f5729-151">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="f5729-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f5729-152">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="f5729-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5729-153">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="f5729-153">Next steps</span></span>

<span data-ttu-id="f5729-154">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="f5729-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f5729-155">Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="f5729-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f5729-156">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="f5729-156">Data privacy and compliance</span></span>

<span data-ttu-id="f5729-157">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a Experian, permite a transferência de dados para fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="f5729-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f5729-158">A Microsoft transferirá esses dados conforme as suas instruções, mas você é responsável por garantir que a Experian cumpre quaisquer obrigações de privacidade ou de segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="f5729-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f5729-159">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f5729-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f5729-160">O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f5729-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

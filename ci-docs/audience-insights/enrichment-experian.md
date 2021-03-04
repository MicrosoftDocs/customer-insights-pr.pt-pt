---
title: Enriquecimento com o enriquecimento de terceiros Experian
description: Informação geral sobre o enriquecimento de terceiros Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269574"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="14c81-103">Enriquecer perfis de clientes com dados demográficos da Experian (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="14c81-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="14c81-104">A Experian é líder global em serviços de marketing e relatórios de crédito para consumidor e empresas.</span><span class="sxs-lookup"><span data-stu-id="14c81-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="14c81-105">Com os serviços de enriquecimento de dados da Experian, pode criar uma compreensão mais profunda dos seus clientes enriquecendo os seus perfis de clientes com dados demográficos como tamanho da casa, rendimento e muito mais.</span><span class="sxs-lookup"><span data-stu-id="14c81-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14c81-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="14c81-106">Prerequisites</span></span>

<span data-ttu-id="14c81-107">Para configurar a Experian, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="14c81-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="14c81-108">Tem uma subscrição ativa da Experian.</span><span class="sxs-lookup"><span data-stu-id="14c81-108">You have an active Experian subscription.</span></span> <span data-ttu-id="14c81-109">Para obter uma subscrição, [contacte a Experian](https://www.experian.com/marketing-services/contact) diretamente.</span><span class="sxs-lookup"><span data-stu-id="14c81-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="14c81-110">[Saiba mais sobre o Enriquecimento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="14c81-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="14c81-111">Tem o ID de Utilizador, ID de Grupo e Número de Modelo para a sua conta de Transporte Seguro (ST) ativada por SSH que a Experian criou para si.</span><span class="sxs-lookup"><span data-stu-id="14c81-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="14c81-112">Tem permissões de [Administrador](permissions.md#administrator) nos insights de audiência.</span><span class="sxs-lookup"><span data-stu-id="14c81-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="14c81-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="14c81-113">Configuration</span></span>

1. <span data-ttu-id="14c81-114">Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="14c81-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="14c81-115">Selecione **Enriquecer os meus dados** no mosaico da Experian.</span><span class="sxs-lookup"><span data-stu-id="14c81-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14c81-116">![Mosaico da Experian](media/experian-tile.png "Mosaico da Experian")</span><span class="sxs-lookup"><span data-stu-id="14c81-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="14c81-117">Selecione **Começar** e introduza o ID de Utilizador, o ID de Grupo e o Número de Modelo para a sua conta de Transporte Seguro da Experian.</span><span class="sxs-lookup"><span data-stu-id="14c81-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="14c81-118">Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="14c81-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="14c81-119">Confirme todas as entradas selecionando **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="14c81-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="14c81-120">Mapear os seus campos</span><span class="sxs-lookup"><span data-stu-id="14c81-120">Map your fields</span></span>

1.  <span data-ttu-id="14c81-121">Selecione **Adicionar dados** e escolha **Conjunto de dados do cliente** que pretende melhorar com os dados demográficos da Experian.</span><span class="sxs-lookup"><span data-stu-id="14c81-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="14c81-122">Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="14c81-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="14c81-123">Selecione os seus identificadores chave a partir de **Nome e Endereço**, **E-mail** ou **Telefone** para enviar à Experian para a resolução de identidade.</span><span class="sxs-lookup"><span data-stu-id="14c81-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="14c81-124">Mais atributos de identificadores chave enviados à Experian provavelmente produzem uma taxa de correspondência mais alta.</span><span class="sxs-lookup"><span data-stu-id="14c81-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="14c81-125">Selecione **Seguinte** e mapeie os atributos correspondentes da sua entidade de cliente unificada para os campos de identificação chave selecionados.</span><span class="sxs-lookup"><span data-stu-id="14c81-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="14c81-126">Selecione **Adicionar atributo** para mapear quaisquer atributos adicionais que gostaria de enviar à Experian.</span><span class="sxs-lookup"><span data-stu-id="14c81-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="14c81-127">Selecione **Guardar** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="14c81-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="14c81-128">![Mapeamento de campos da Experian](media/experian-field-mapping.png "Mapeamento de campos da Experian")</span><span class="sxs-lookup"><span data-stu-id="14c81-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="14c81-129">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="14c81-129">Enrichment results</span></span>

<span data-ttu-id="14c81-130">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="14c81-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="14c81-131">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="14c81-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="14c81-132">O tempo de processamento dependerá do tamanho dos dados do seu cliente e dos processos de enriquecimento criados para a sua conta pela Experian.</span><span class="sxs-lookup"><span data-stu-id="14c81-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="14c81-133">Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="14c81-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="14c81-134">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="14c81-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="14c81-135">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="14c81-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="14c81-136">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="14c81-136">Next steps</span></span>

<span data-ttu-id="14c81-137">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="14c81-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="14c81-138">Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="14c81-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="14c81-139">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="14c81-139">Data privacy and compliance</span></span>

<span data-ttu-id="14c81-140">Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Experian, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="14c81-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="14c81-141">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Experian cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="14c81-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="14c81-142">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="14c81-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="14c81-143">O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="14c81-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
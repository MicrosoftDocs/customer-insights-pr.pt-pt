---
title: Enriquecimento com o enriquecimento de terceiros Experian
description: Informação geral sobre o enriquecimento de terceiros Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896387"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="11a4a-103">Enriquecer perfis de clientes com dados demográficos da Experian (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="11a4a-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="11a4a-104">A Experian é líder global em serviços de marketing e relatórios de crédito para consumidor e empresas.</span><span class="sxs-lookup"><span data-stu-id="11a4a-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="11a4a-105">Com os serviços de enriquecimento de dados da Experian, pode criar uma compreensão mais profunda dos seus clientes enriquecendo os seus perfis de clientes com dados demográficos como tamanho da casa, rendimento e muito mais.</span><span class="sxs-lookup"><span data-stu-id="11a4a-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="11a4a-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="11a4a-106">Prerequisites</span></span>

<span data-ttu-id="11a4a-107">Para configurar a Experian, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="11a4a-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="11a4a-108">Tem uma subscrição ativa da Experian.</span><span class="sxs-lookup"><span data-stu-id="11a4a-108">You have an active Experian subscription.</span></span> <span data-ttu-id="11a4a-109">Para obter uma subscrição, [contacte a Experian](https://www.experian.com/marketing-services/contact) diretamente.</span><span class="sxs-lookup"><span data-stu-id="11a4a-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="11a4a-110">[Saiba mais sobre o Enriquecimento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="11a4a-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="11a4a-111">Uma ligação Experian já foi configurada por um administrador *ou* tem permissões de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="11a4a-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="11a4a-112">Também precisa do ID de Utilizador, ID de Parte e Número de Modelo para a sua conta ST (Secure Transport) compatível com SSH que a Experian criou para si.</span><span class="sxs-lookup"><span data-stu-id="11a4a-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="11a4a-113">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="11a4a-113">Configure the enrichment</span></span>

1. <span data-ttu-id="11a4a-114">Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="11a4a-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="11a4a-115">Selecione **Enriquecer os meus dados** no mosaico da Experian.</span><span class="sxs-lookup"><span data-stu-id="11a4a-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11a4a-116">![Mosaico da Experian](media/experian-tile.png "Mosaico da Experian")</span><span class="sxs-lookup"><span data-stu-id="11a4a-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="11a4a-117">Selecione uma [ligação](connections.md) na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="11a4a-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="11a4a-118">Contacte um administrador se não houver nenhuma ligação disponível.</span><span class="sxs-lookup"><span data-stu-id="11a4a-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="11a4a-119">Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação** e escolhendo a Experian na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="11a4a-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="11a4a-120">Selecione **Ligar à Experian** para confirmar a seleção da ligação.</span><span class="sxs-lookup"><span data-stu-id="11a4a-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="11a4a-121">Selecione **Seguinte** e escolha o **Conjunto de dados de cliente** que pretende enriquecer com dados demográficos da Experian.</span><span class="sxs-lookup"><span data-stu-id="11a4a-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="11a4a-122">Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="11a4a-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. <span data-ttu-id="11a4a-124">Selecione **Seguinte** e defina que tipos de campos dos seus perfis unificados devem ser utilizados para procurar dados demográficos correspondentes a partir da Experian.</span><span class="sxs-lookup"><span data-stu-id="11a4a-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="11a4a-125">Pelo menos, um dos campos **Nome e endereço**, **Telefone** ou **E-mail** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="11a4a-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="11a4a-126">Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos.</span><span class="sxs-lookup"><span data-stu-id="11a4a-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="11a4a-127">Esta seleção irá afetar os campos de mapeamento a que tem acesso no próximo passo.</span><span class="sxs-lookup"><span data-stu-id="11a4a-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="11a4a-128">Mais atributos de identificadores chave enviados à Experian provavelmente produzem uma taxa de correspondência mais alta.</span><span class="sxs-lookup"><span data-stu-id="11a4a-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="11a4a-129">Selecione **Seguinte** para iniciar o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="11a4a-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="11a4a-130">Defina que campos dos seus perfis unificados devem ser utilizados para procurar dados demográficos correspondentes a partir da Experian.</span><span class="sxs-lookup"><span data-stu-id="11a4a-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="11a4a-131">Os campos obrigatórios estão marcados.</span><span class="sxs-lookup"><span data-stu-id="11a4a-131">Required fields are marked.</span></span>

1. <span data-ttu-id="11a4a-132">Forneça um nome para o enriquecimento e um nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="11a4a-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="11a4a-133">Selecione **Guardar enriquecimento** depois de rever as suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="11a4a-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="11a4a-134">Configurar a ligação para a Experian</span><span class="sxs-lookup"><span data-stu-id="11a4a-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="11a4a-135">Tens de ser um administrador para configurar ligações.</span><span class="sxs-lookup"><span data-stu-id="11a4a-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="11a4a-136">Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico da Experian.</span><span class="sxs-lookup"><span data-stu-id="11a4a-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="11a4a-137">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="11a4a-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="11a4a-138">Introduza um nome para a ligação na caixa **Nome a Apresentar**.</span><span class="sxs-lookup"><span data-stu-id="11a4a-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="11a4a-139">Introduza o ID de Utilizador, o ID de Parte e o Número de Modelo válidos para a sua conta de Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="11a4a-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="11a4a-140">Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**</span><span class="sxs-lookup"><span data-stu-id="11a4a-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="11a4a-141">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="11a4a-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="11a4a-142">Depois de concluir a verificação, selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="11a4a-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Painel de configuração de ligação à Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="11a4a-144">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="11a4a-144">Enrichment results</span></span>

<span data-ttu-id="11a4a-145">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="11a4a-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="11a4a-146">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="11a4a-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="11a4a-147">O tempo de processamento dependerá do tamanho dos dados do seu cliente e dos processos de enriquecimento criados para a sua conta pela Experian.</span><span class="sxs-lookup"><span data-stu-id="11a4a-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="11a4a-148">Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="11a4a-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="11a4a-149">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="11a4a-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="11a4a-150">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="11a4a-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="11a4a-151">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="11a4a-151">Next steps</span></span>

<span data-ttu-id="11a4a-152">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="11a4a-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="11a4a-153">Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="11a4a-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="11a4a-154">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="11a4a-154">Data privacy and compliance</span></span>

<span data-ttu-id="11a4a-155">Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Experian, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="11a4a-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="11a4a-156">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Experian cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="11a4a-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="11a4a-157">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="11a4a-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="11a4a-158">O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="11a4a-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

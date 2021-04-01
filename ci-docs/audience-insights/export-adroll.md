---
title: Exportar dados do Customer Insights para o AdRoll
description: Aprenda a configurar a ligação ao AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697088"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="e17cb-103">Conector para o AdRoll (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="e17cb-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="e17cb-104">Exportar segmentos de perfis de clientes unificados para o AdRoll e usá-los para publicidade.</span><span class="sxs-lookup"><span data-stu-id="e17cb-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e17cb-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e17cb-105">Prerequisites</span></span>

-   <span data-ttu-id="e17cb-106">Tem uma [conta do AdRoll](https://www.adroll.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="e17cb-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e17cb-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="e17cb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e17cb-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="e17cb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="e17cb-109">Ligar à AdRoll</span><span class="sxs-lookup"><span data-stu-id="e17cb-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="e17cb-110">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="e17cb-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e17cb-111">Sob **AdRoll**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e17cb-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="e17cb-112">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="e17cb-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Painel de configuração para a ligação ao AdRoll.":::

1. <span data-ttu-id="e17cb-114">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="e17cb-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e17cb-115">Selecione **Ligar** para inicializar a ligação ao AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e17cb-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="e17cb-116">Selecione **Autenticar com o AdRoll** e forneça as suas credenciais de administrador para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e17cb-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="e17cb-117">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e17cb-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e17cb-118">Introduza o seu **ID de anunciante do AdRoll** [AdRoll para publicidade](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="e17cb-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="e17cb-119">Selecione **Seguinte** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="e17cb-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e17cb-120">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="e17cb-120">Configure the connector</span></span>

1. <span data-ttu-id="e17cb-121">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="e17cb-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e17cb-122">É necessário exportar segmentos para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e17cb-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="e17cb-123">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="e17cb-123">Select the segments you want to export.</span></span> <span data-ttu-id="e17cb-124">Selecione um segmento com, pelo menos, 100 membros.</span><span class="sxs-lookup"><span data-stu-id="e17cb-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="e17cb-125">Não pode exportar segmentos menores.</span><span class="sxs-lookup"><span data-stu-id="e17cb-125">You can't export smaller segments.</span></span> <span data-ttu-id="e17cb-126">Além disso, o tamanho máximo de um segmento para exportar é de 250.000 membros por exportação.</span><span class="sxs-lookup"><span data-stu-id="e17cb-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="e17cb-127">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e17cb-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e17cb-128">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="e17cb-128">Export the data</span></span>

<span data-ttu-id="e17cb-129">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e17cb-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e17cb-130">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e17cb-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e17cb-131">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="e17cb-131">Known limitations</span></span>

- <span data-ttu-id="e17cb-132">Pode exportar até 250.000 perfis por exportação para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e17cb-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="e17cb-133">Não pode exportar segmentos com menos de 100 perfis para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e17cb-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="e17cb-134">A exportação para o AdRoll está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="e17cb-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="e17cb-135">Exportar até 250.000 perfis para o AdRoll pode demorar até 10 minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="e17cb-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="e17cb-136">O número de perfis que pode exportar para o AdRoll é dependente e limitado no seu contrato com o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e17cb-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e17cb-137">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="e17cb-137">Data privacy and compliance</span></span>

<span data-ttu-id="e17cb-138">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o AdRoll, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="e17cb-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e17cb-139">A Microsoft transferirá esses dados a seu pedido, mas o utilizador responsável por garantir que o AdRoll cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="e17cb-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e17cb-140">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e17cb-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e17cb-141">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="e17cb-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

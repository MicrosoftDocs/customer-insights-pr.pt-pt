---
title: Exportar dados Customer Insights para a Marketo
description: Saiba como configurar a ligação a Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570417"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="6d036-103">Ligação para Marketo (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="6d036-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="6d036-104">Exportar segmentos de perfis unificados de clientes para gerar campanhas, fornecer marketing por e-mail e utilizar grupos específicos de clientes com Marketo.</span><span class="sxs-lookup"><span data-stu-id="6d036-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d036-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6d036-105">Prerequisites</span></span>

-   <span data-ttu-id="6d036-106">Tem uma [conta Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="6d036-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6d036-107">Existem listas na Marketo e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="6d036-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="6d036-108">Para mais informações, consulte [listas da Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="6d036-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="6d036-109">Tem [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6d036-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="6d036-110">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="6d036-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="6d036-111">Ligar a Marketo</span><span class="sxs-lookup"><span data-stu-id="6d036-111">Connect to Marketo</span></span>

1. <span data-ttu-id="6d036-112">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="6d036-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6d036-113">Em **Marketo**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6d036-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="6d036-114">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="6d036-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6d036-115">Introduza a sua **[ID de cliente da Marketo, segredo do cliente e nome do ponto final REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="6d036-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="6d036-116">Introduza a sua **[Id da lista Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="6d036-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="6d036-117">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados** e selecione **Ligar** para iniciar a ligação a Marketo.</span><span class="sxs-lookup"><span data-stu-id="6d036-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="6d036-118">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6d036-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Exportar captura de ecrã para ligação a Marketo":::

1. <span data-ttu-id="6d036-120">Selecione **Seguinte** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="6d036-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6d036-121">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="6d036-121">Configure the connector</span></span>

1. <span data-ttu-id="6d036-122">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="6d036-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="6d036-123">Opcionalmente, pode exportar o **nome próprio**, **apelido**, **cidade**, **estado**, e **país/região**  como campos adicionais para criar e-mails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="6d036-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="6d036-124">Selecione **Adicionar atributo** para mapear estes campos.</span><span class="sxs-lookup"><span data-stu-id="6d036-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="6d036-125">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="6d036-125">Select the segments you want to export.</span></span> <span data-ttu-id="6d036-126">Pode exportar até 1 milhão de perfis de clientes no total para a Marketo.</span><span class="sxs-lookup"><span data-stu-id="6d036-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Selecionar campos e segmentos a exportar para Marketo":::

1. <span data-ttu-id="6d036-128">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d036-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6d036-129">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="6d036-129">Export the data</span></span>

<span data-ttu-id="6d036-130">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6d036-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6d036-131">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6d036-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6d036-132">Na Marketo, pode agora encontrar os seus segmentos nas [listas da Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="6d036-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6d036-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="6d036-133">Known limitations</span></span>

- <span data-ttu-id="6d036-134">Até 1 milhão de perfis por exportar para a Marketo.</span><span class="sxs-lookup"><span data-stu-id="6d036-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="6d036-135">A exportação para a Marketo é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="6d036-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="6d036-136">A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 3 horas.</span><span class="sxs-lookup"><span data-stu-id="6d036-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="6d036-137">O número de perfis que pode exportar para a Marketo está dependente e limitado ao seu contrato com a Marketo.</span><span class="sxs-lookup"><span data-stu-id="6d036-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6d036-138">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="6d036-138">Data privacy and compliance</span></span>

<span data-ttu-id="6d036-139">Quando ativa Dynamics 365 Customer Insights para transmitir dados à Marketo, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="6d036-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6d036-140">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Marketo cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="6d036-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6d036-141">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6d036-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6d036-142">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="6d036-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

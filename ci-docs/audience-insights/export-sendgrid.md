---
title: Exportar dados do Customer Insights para o SendGrid
description: Aprenda a configurar a ligação ao SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268746"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="363ec-103">Conector para o SendGrid (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="363ec-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="363ec-104">Exportar segmentos de perfis unificados de clientes para listas de contactos do SendGrid e utilizá-los para campanhas e marketing de e-mail no SendGrid.</span><span class="sxs-lookup"><span data-stu-id="363ec-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="363ec-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="363ec-105">Prerequisites</span></span>

-   <span data-ttu-id="363ec-106">Tem uma [conta do SendGrid](https://sendgrid.com/) e credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="363ec-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="363ec-107">Existem listas de contactos existentes no SendGrid e IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="363ec-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="363ec-108">Para mais informações, consulte [SendGrid – Gerir contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="363ec-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="363ec-109">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="363ec-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="363ec-110">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="363ec-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="363ec-111">Ligar ao SendGrid</span><span class="sxs-lookup"><span data-stu-id="363ec-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="363ec-112">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="363ec-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="363ec-113">Sob **SendGrid**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="363ec-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="363ec-114">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="363ec-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Painel de configuração de exportação do SendGrid.":::

1. <span data-ttu-id="363ec-116">Insira a sua **Chave de API do SendGrid** [Chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="363ec-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="363ec-117">Insira o seu **[ID da lista SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="363ec-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="363ec-118">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="363ec-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="363ec-119">Selecione **Ligar** para inicializar a ligação ao SendGrid.</span><span class="sxs-lookup"><span data-stu-id="363ec-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="363ec-120">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="363ec-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="363ec-121">Selecione **Seguinte** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="363ec-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="363ec-122">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="363ec-122">Configure the connector</span></span>

1. <span data-ttu-id="363ec-123">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="363ec-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="363ec-124">Repita os mesmos passos para outros campos opcionais como **Nome próprio**, **Apelido**, **País/Região**, **Estado**, **Cidade** e **Código Postal**.</span><span class="sxs-lookup"><span data-stu-id="363ec-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="363ec-125">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="363ec-125">Select the segments you want to export.</span></span> <span data-ttu-id="363ec-126">**Recomendamos que não exporte mais de 100.000 perfis de clientes no total** para o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="363ec-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="363ec-127">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="363ec-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="363ec-128">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="363ec-128">Export the data</span></span>

<span data-ttu-id="363ec-129">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="363ec-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="363ec-130">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="363ec-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="363ec-131">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="363ec-131">Known limitations</span></span>

- <span data-ttu-id="363ec-132">Até 100.000 perfis no total para SendGrid.</span><span class="sxs-lookup"><span data-stu-id="363ec-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="363ec-133">A exportação para o SendGrid está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="363ec-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="363ec-134">Exportar até 100.000 perfis para o SendGrid pode demorar até algumas horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="363ec-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="363ec-135">O número de perfis que pode exportar para o SendGrid é dependente e limitado no seu contrato com o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="363ec-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="363ec-136">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="363ec-136">Data privacy and compliance</span></span>

<span data-ttu-id="363ec-137">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o SendGrid, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="363ec-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="363ec-138">A Microsoft transferirá esses dados a seu pedido, mas você é responsável por garantir que o SendGrid cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="363ec-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="363ec-139">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="363ec-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="363ec-140">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="363ec-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
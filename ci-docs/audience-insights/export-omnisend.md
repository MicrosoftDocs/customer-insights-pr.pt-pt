---
title: Exportar dados do Customer Insights para o Omnisend
description: Aprenda a configurar a ligação e exportar para o Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124535"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="1c1df-103">Exportar segmentos para o Omnisend (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="1c1df-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="1c1df-104">Exporte segmentos de perfis de clientes unificados para o Omnisend e utilize-os para atividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="1c1df-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1c1df-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1c1df-105">Prerequisites</span></span>

-   <span data-ttu-id="1c1df-106">Tem uma [conta do Omnisend](https://www.omnisend.com/) e credenciais correspondentes de administrador.</span><span class="sxs-lookup"><span data-stu-id="1c1df-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1c1df-107">Tem [segmentos configurados](segments.md) nos insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="1c1df-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1c1df-108">Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.</span><span class="sxs-lookup"><span data-stu-id="1c1df-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1c1df-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="1c1df-109">Known limitations</span></span>

- <span data-ttu-id="1c1df-110">Pode exportar até 1 milhão de perfis por exportação para o Omnisend e pode levar até 4 horas para completar.</span><span class="sxs-lookup"><span data-stu-id="1c1df-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="1c1df-111">A exportação para o Omnisend limita-se a segmentos.</span><span class="sxs-lookup"><span data-stu-id="1c1df-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="1c1df-112">O número de perfis que pode exportar para o Omnisend depende do seu contrato com o Omnisend.</span><span class="sxs-lookup"><span data-stu-id="1c1df-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="1c1df-113">Configurar ligação ao Omnisend</span><span class="sxs-lookup"><span data-stu-id="1c1df-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="1c1df-114">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="1c1df-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1c1df-115">Selecione **Adicionar ligação** e escolha **Omnisend** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="1c1df-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="1c1df-116">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="1c1df-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1c1df-117">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="1c1df-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1c1df-118">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="1c1df-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1c1df-119">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="1c1df-119">Choose who can use this connection.</span></span> <span data-ttu-id="1c1df-120">Por predefinição, são apenas administradores.</span><span class="sxs-lookup"><span data-stu-id="1c1df-120">By default it's only administrators.</span></span> <span data-ttu-id="1c1df-121">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1c1df-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1c1df-122">Introduza a sua [chave de API do Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="1c1df-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="1c1df-123">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="1c1df-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1c1df-124">Selecione **Ligar** para inicializar a ligação ao Omnisend.</span><span class="sxs-lookup"><span data-stu-id="1c1df-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="1c1df-125">Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1c1df-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1c1df-126">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="1c1df-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1c1df-127">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="1c1df-127">Configure an export</span></span>

<span data-ttu-id="1c1df-128">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="1c1df-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1c1df-129">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1c1df-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1c1df-130">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="1c1df-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1c1df-131">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="1c1df-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1c1df-132">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Omnisend.</span><span class="sxs-lookup"><span data-stu-id="1c1df-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="1c1df-133">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="1c1df-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1c1df-134">Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente.</span><span class="sxs-lookup"><span data-stu-id="1c1df-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1c1df-135">É obrigatório exportar segmentos para o Omnisend.</span><span class="sxs-lookup"><span data-stu-id="1c1df-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="1c1df-136">Opcionalmente, pode exportar Nome próprio, Apelido, Endereço, País/Região, Estado, Cidade e Código Postal para criar e-mails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="1c1df-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="1c1df-137">Selecione **Adicionar atributo** para mapear estes campos.</span><span class="sxs-lookup"><span data-stu-id="1c1df-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1c1df-138">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1c1df-138">Select **Save**.</span></span>

<span data-ttu-id="1c1df-139">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="1c1df-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1c1df-140">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1c1df-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1c1df-141">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1c1df-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1c1df-142">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="1c1df-142">Data privacy and compliance</span></span>

<span data-ttu-id="1c1df-143">Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Omnisend, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="1c1df-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1c1df-144">A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que o Omnisend cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="1c1df-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1c1df-145">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1c1df-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1c1df-146">O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="1c1df-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

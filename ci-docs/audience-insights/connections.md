---
title: Ligações a outros serviços do Customer Insights.
description: Partilhar dados com outros serviços.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304986"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="49839-103">Descrição geral das ligações (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="49839-103">Connections (preview) overview</span></span>

<span data-ttu-id="49839-104">As ligações são a chave para ativar a partilha de dados de e para o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="49839-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="49839-105">Cada ligação estabelece a partilha de dados com um serviço específico.</span><span class="sxs-lookup"><span data-stu-id="49839-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="49839-106">As ligações são a base para [configurar enriquecimentos de terceiros](enrichment-hub.md) e [configurar exportações](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="49839-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="49839-107">A mesma ligação pode ser utilizada várias vezes.</span><span class="sxs-lookup"><span data-stu-id="49839-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="49839-108">Por exemplo, uma ligação ao Dynamics 365 Marketing funciona para múltiplas exportações e uma ligação Leadspace pode ser usada para vários enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="49839-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="49839-109">Aceda a **Admin** > **Ligações** para criar e ver ligações.</span><span class="sxs-lookup"><span data-stu-id="49839-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="49839-110">O separador **Ligações** mostra todas as ligações ativas.</span><span class="sxs-lookup"><span data-stu-id="49839-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="49839-111">A lista mostra uma linha para cada ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="49839-112">Obtenha uma descrição geral rápida, descrição e descubra o que pode fazer com cada opção de extensibilidade no separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="49839-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="49839-113">Exportações</span><span class="sxs-lookup"><span data-stu-id="49839-113">Exports</span></span>

<span data-ttu-id="49839-114">Apenas os administradores podem configurar novas ligações, mas podem conceder acesso aos contribuidores para utilizarem as ligações existentes.</span><span class="sxs-lookup"><span data-stu-id="49839-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="49839-115">Os administradores controlam onde os dados podem ir, os contribuidores definem o payload e a frequência que correspondem às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="49839-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="49839-116">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="49839-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="49839-117">Melhoramentos</span><span class="sxs-lookup"><span data-stu-id="49839-117">Enrichments</span></span>

<span data-ttu-id="49839-118">Apenas os administradores podem configurar novas ligações, mas as ligações criadas estão sempre disponíveis tanto para administradores como para contribuidores.</span><span class="sxs-lookup"><span data-stu-id="49839-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="49839-119">Os administradores gerem credenciais e dão consentimento às transferências de dados.</span><span class="sxs-lookup"><span data-stu-id="49839-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="49839-120">As ligações podem então ser utilizadas para enriquecimentos por administradores e contribuidores.</span><span class="sxs-lookup"><span data-stu-id="49839-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="49839-121">Adicionar uma nova ligação</span><span class="sxs-lookup"><span data-stu-id="49839-121">Add a new connection</span></span>

<span data-ttu-id="49839-122">Para adicionar ligações, precisa de ter [permissões de administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="49839-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="49839-123">Se ligar a outros serviços da Microsoft, assumimos que ambos os serviços estão na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="49839-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="49839-124">Aceda a **Admin** > **Ligações (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="49839-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="49839-125">Vá ao separador **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="49839-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="49839-126">Selecione **Adicionar ligação** para criar uma nova ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="49839-127">Escolha do menu pendente que tipo de ligação pretende criar.</span><span class="sxs-lookup"><span data-stu-id="49839-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="49839-128">No painel **Configurar ligação**, forneça os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="49839-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="49839-129">O **Nome a Apresentar** e o tipo de ligação descrevem uma ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="49839-130">Recomendamos a escolha de um nome que explique o propósito e o destino desta ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="49839-131">Os campos exatos dependem do serviço a que se está a ligar.</span><span class="sxs-lookup"><span data-stu-id="49839-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="49839-132">Pode aprender sobre detalhes de um tipo de ligação específico no artigo sobre o serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="49839-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="49839-133">Para criar a ligação, selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="49839-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="49839-134">Também pode selecionar **Configurar** num mosaico no separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="49839-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="49839-135">Permita que os contribuidores utilizem uma ligação para exportações</span><span class="sxs-lookup"><span data-stu-id="49839-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="49839-136">Ao definir ou editar uma ligação de exportação, escolha que utilizadores estão autorizados a utilizar esta ligação específica para definir [exportações](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="49839-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="49839-137">Por predefinição, está disponível uma ligação para utilizadores com uma função de administrador.</span><span class="sxs-lookup"><span data-stu-id="49839-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="49839-138">Pode alterar esta definição em **Escolher quem pode utilizar esta ligação** e permitir que os utilizadores com a função de contribuidor utilizem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="49839-139">Os contribuidores não poderão ver ou editar a ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="49839-140">Só verão o nome a apresentar e o seu tipo na criação de uma exportação.</span><span class="sxs-lookup"><span data-stu-id="49839-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="49839-141">Ao partilhar uma ligação, permite que os contribuidores utilizem uma ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="49839-142">Os contribuidores verão ligações partilhadas quando configurarem exportações.</span><span class="sxs-lookup"><span data-stu-id="49839-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="49839-143">Podem gerir todas as exportações que utilizam esta ligação específica.</span><span class="sxs-lookup"><span data-stu-id="49839-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="49839-144">Pode alterar esta definição mantendo as exportações que já foram definidas pelos contribuidores.</span><span class="sxs-lookup"><span data-stu-id="49839-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="49839-145">Editar uma ligação</span><span class="sxs-lookup"><span data-stu-id="49839-145">Edit a connection</span></span>

1. <span data-ttu-id="49839-146">Aceda a **Admin** > **Ligações (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="49839-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="49839-147">Vá ao separador **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="49839-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="49839-148">Selecione as reticências verticais da ligação que pretende editar.</span><span class="sxs-lookup"><span data-stu-id="49839-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="49839-149">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="49839-149">Select **Edit**.</span></span>

1. <span data-ttu-id="49839-150">Altere os valores que pretende atualizar e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="49839-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="49839-151">Remover uma ligação</span><span class="sxs-lookup"><span data-stu-id="49839-151">Remove a connection</span></span>

<span data-ttu-id="49839-152">Se a ligação que está a remover for utilizada por enriquecimentos ou exportações, tem de os separar ou remover primeiro.</span><span class="sxs-lookup"><span data-stu-id="49839-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="49839-153">O diálogo de remoção irá guiá-lo para os enriquecimentos ou exportações relevantes.</span><span class="sxs-lookup"><span data-stu-id="49839-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="49839-154">Enriquecimentos e exportações separados tornam-se inativos.</span><span class="sxs-lookup"><span data-stu-id="49839-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="49839-155">Reativa-os adicionando-lhes outra ligação na página [Enriquecimentos](enrichment-hub.md) ou [Exportações](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="49839-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="49839-156">Aceda a **Admin** > **Ligações (pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="49839-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="49839-157">Vá ao separador **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="49839-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="49839-158">Selecione as reticências verticais da ligação que pretende remover.</span><span class="sxs-lookup"><span data-stu-id="49839-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="49839-159">Selecione **Remover** no menu pendente.</span><span class="sxs-lookup"><span data-stu-id="49839-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="49839-160">É apresentado um diálogo de confirmação.</span><span class="sxs-lookup"><span data-stu-id="49839-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="49839-161">Se houver enriquecimentos ou exportações a utilizar esta ligação, selecione o botão para ver o que está a utilizar a ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="49839-162">**Exportações:** pode optar por remover ou desligar as exportações para poder remover a ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="49839-163">Para desligar uma exportação, os administradores podem utilizar a ação **Desligar**.</span><span class="sxs-lookup"><span data-stu-id="49839-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="49839-164">Esta ação está disponível para exportações individuais e múltiplas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="49839-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="49839-165">Ao desligar, mantenha a configuração de exportação, mas não será executada até que outra ligação lhe seja adicionada.</span><span class="sxs-lookup"><span data-stu-id="49839-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="49839-166">**Enriquecimentos:** pode optar por remover ou desativar os enriquecimentos para poder remover a ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="49839-167">Quando a ligação não tiver mais dependências, regresse a **Admin** > **Ligações** e tente remover novamente a ligação.</span><span class="sxs-lookup"><span data-stu-id="49839-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="49839-168">Para confirmar a eliminação, selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="49839-168">To confirm the deletion, select **Remove**.</span></span>


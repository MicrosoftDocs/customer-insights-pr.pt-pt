---
title: Exportar dados Customer Insights para anfitriões SFTP
description: Aprenda a configurar a ligação e exportar para uma localização SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976953"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="1270d-103">Exportar listas de segmentos e outros dados para o SFTP (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="1270d-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="1270d-104">Utilize os dados dos seus clientes em aplicações de terceiros exportando-os para uma localização do SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="1270d-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1270d-105">Pré-requisitos para a ligação</span><span class="sxs-lookup"><span data-stu-id="1270d-105">Prerequisites for connection</span></span>

- <span data-ttu-id="1270d-106">Disponibilidade de um anfitrião SFTP e credenciais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="1270d-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1270d-107">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="1270d-107">Known limitations</span></span>

- <span data-ttu-id="1270d-108">O runtime de uma exportação depende do desempenho do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="1270d-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="1270d-109">Recomendamos dois núcleos CPU e 1 Gb de memória como configuração mínima do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="1270d-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="1270d-110">As entidades exportadoras com até 100 milhões de perfis de clientes podem demorar 90 minutos quando utilizam a configuração mínima recomendada de dois núcleos CPU e 1 Gb de memória.</span><span class="sxs-lookup"><span data-stu-id="1270d-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="1270d-111">Configurar ligação ao SFTP</span><span class="sxs-lookup"><span data-stu-id="1270d-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="1270d-112">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="1270d-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1270d-113">Selecione **Adicionar ligação** e escolha **SFTP** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="1270d-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="1270d-114">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="1270d-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1270d-115">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="1270d-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1270d-116">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="1270d-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1270d-117">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="1270d-117">Choose who can use this connection.</span></span> <span data-ttu-id="1270d-118">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="1270d-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1270d-119">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1270d-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1270d-120">Forneça um **Nome de utilizador**, **Palavra-passe**, **Nome do anfitrião** e **Pasta de exportação** para a sua conta SFTP.</span><span class="sxs-lookup"><span data-stu-id="1270d-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="1270d-121">Selecione **Verificar** para testar a ligação.</span><span class="sxs-lookup"><span data-stu-id="1270d-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="1270d-122">Escolha se pretende exportar os seus dados em **Gzip** ou **Deszipados** e o **delimitador de campo** para os ficheiros exportados.</span><span class="sxs-lookup"><span data-stu-id="1270d-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="1270d-123">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="1270d-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1270d-124">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="1270d-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1270d-125">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="1270d-125">Configure an export</span></span>

<span data-ttu-id="1270d-126">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="1270d-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1270d-127">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1270d-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1270d-128">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="1270d-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1270d-129">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="1270d-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1270d-130">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção SFTP.</span><span class="sxs-lookup"><span data-stu-id="1270d-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="1270d-131">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="1270d-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1270d-132">Selecione as entidades, para segmentos de exemplo, que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="1270d-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1270d-133">Cada entidade selecionada será dividida em até cinco ficheiros de saída quando exportada.</span><span class="sxs-lookup"><span data-stu-id="1270d-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="1270d-134">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1270d-134">Select **Save**.</span></span>

<span data-ttu-id="1270d-135">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="1270d-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1270d-136">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1270d-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1270d-137">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1270d-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1270d-138">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="1270d-138">Data privacy and compliance</span></span>

<span data-ttu-id="1270d-139">Quando ativa Dynamics 365 Customer Insights para transmitir dados através de SFTP, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="1270d-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1270d-140">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o destino de exportação cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="1270d-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1270d-141">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1270d-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1270d-142">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="1270d-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

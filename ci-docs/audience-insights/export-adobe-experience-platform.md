---
title: Exportar dados do Customer Insights para a Plataforma de Experiência do Adobe
description: Aprenda a utilizar os segmentos de informações de audiência na Plataforma de Experiência do Adobe.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305538"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="4e5ec-103">Usar segmentos do Customer Insights na Plataforma de Experiência do Adobe (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="4e5ec-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="4e5ec-104">Como utilizador de informações de audiência no Dynamics 365 Customer Insights, pode ter criado segmentos para tornar as suas campanhas de marketing mais eficientes, direcionadas a audiências relevantes.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="4e5ec-105">Para utilizar um segmento a partir das informações da audiência na Plataforma de Experiência do Adobe e aplicações como o Adobe Campaign Standard, é necessário seguir alguns passos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="4e5ec-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4e5ec-107">Prerequisites</span></span>

-   <span data-ttu-id="4e5ec-108">Licença do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4e5ec-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="4e5ec-109">Licença da Plataforma de Experiência do Adobe</span><span class="sxs-lookup"><span data-stu-id="4e5ec-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="4e5ec-110">Licença do Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4e5ec-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="4e5ec-111">Conta de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="4e5ec-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="4e5ec-112">Descrição Geral da Campanha</span><span class="sxs-lookup"><span data-stu-id="4e5ec-112">Campaign Overview</span></span>

<span data-ttu-id="4e5ec-113">Para entender melhor como pode usar segmentos das informações da audiência na Plataforma de Experiência do Adobe, vamos ver uma campanha de exemplo fictícia.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="4e5ec-114">Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="4e5ec-115">Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="4e5ec-116">Para manter estes clientes, pretende enviar-lhes uma oferta promocional por e-mail, utilizando a Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="4e5ec-117">Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="4e5ec-118">Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="4e5ec-119">Identificar a audiência alvo</span><span class="sxs-lookup"><span data-stu-id="4e5ec-119">Identify your target audience</span></span>

<span data-ttu-id="4e5ec-120">No nosso cenário, supomos que os endereços de e-mail dos clientes estão disponíveis nas informações da audiência e as suas preferências promocionais foram analisadas para identificar membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="4e5ec-121">O [segmento que definiu nas informações da audiência](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a estes clientes a promoção de e-mail.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

<span data-ttu-id="4e5ec-123">O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="4e5ec-124">Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="4e5ec-125">Exportar a audiência alvo</span><span class="sxs-lookup"><span data-stu-id="4e5ec-125">Export your target audience</span></span>

<span data-ttu-id="4e5ec-126">Com a nossa audiência alvo identificada, podemos configurar a exportação das informações da audiência para uma conta de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="4e5ec-127">Configurar uma ligação</span><span class="sxs-lookup"><span data-stu-id="4e5ec-127">Configure a connection</span></span>

1. <span data-ttu-id="4e5ec-128">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4e5ec-129">Selecione **Adicionar ligação** e escolha a **Armazenamento de Blobs do Azure** ou selecione **Configurar** no mosaico **Armazenamento de Blobs do Azure** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuração do Armazenamento de Blobs do Azure."::: 

1. <span data-ttu-id="4e5ec-131">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4e5ec-132">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4e5ec-133">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4e5ec-134">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-134">Choose who can use this connection.</span></span> <span data-ttu-id="4e5ec-135">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4e5ec-136">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4e5ec-137">Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da sua conta de Armazenamento de Blobs para onde pretende exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. "::: 
   
    - <span data-ttu-id="4e5ec-139">Para saber mais sobre como encontrar o nome da conta de Armazenamento de Blobs e a chave da conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="4e5ec-140">Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="4e5ec-141">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="4e5ec-142">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="4e5ec-142">Configure an export</span></span>

<span data-ttu-id="4e5ec-143">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4e5ec-144">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4e5ec-145">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4e5ec-146">Para criar um nova exportação, selecione **Adicionar exportação**.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="4e5ec-147">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="4e5ec-148">Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="4e5ec-149">Escolha o segmento que pretende exportar.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="4e5ec-150">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. <span data-ttu-id="4e5ec-152">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-152">Select **Save**.</span></span>

<span data-ttu-id="4e5ec-153">Depois de guardar o destino de exportação, encontra-o em **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="4e5ec-154">Agora pode [exportar o segmento a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="4e5ec-155">A exportação também será executada com cada [atualização agendada](system.md).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4e5ec-156">Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="4e5ec-157">Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="4e5ec-158">O seguinte caminho de pasta é automaticamente criado no seu recipiente:</span><span class="sxs-lookup"><span data-stu-id="4e5ec-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="4e5ec-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="4e5ec-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="4e5ec-160">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="4e5ec-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="4e5ec-161">O *model.json* para as entidades exportadas reside ao nível *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="4e5ec-162">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="4e5ec-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="4e5ec-163">Definir o Modelo de Dados de Experiência (XDM) na Plataforma de Experiência do Adobe</span><span class="sxs-lookup"><span data-stu-id="4e5ec-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="4e5ec-164">Antes de os dados exportados das informações da audiência poderem ser utilizados na Plataforma de Experiência do Adobe, precisamos de definir o esquema do Modelo de Dados de Experiência e [configurar os dados para o Perfil de Cliente em Tempo Real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="4e5ec-165">Saiba [o que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e compreenda as [noções básicas da composição do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="4e5ec-166">Importar dados para a Plataforma de Experiência do Adobe</span><span class="sxs-lookup"><span data-stu-id="4e5ec-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="4e5ec-167">Agora que está tudo pronto, precisamos de importar os dados de audiência preparados das informações da audiência para a Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="4e5ec-168">Em primeiro lugar, [crie uma ligação de origem do Armazenamento de Blobs do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="4e5ec-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="4e5ec-169">Depois de definir a ligação de origem, [configure um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para uma ligação de lote do armazenamento na nuvem para importar a saída do segmento das informações da audiência para a Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="4e5ec-170">Criar uma audiência no Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4e5ec-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="4e5ec-171">Para enviar o e-mail para esta campanha, utilizaremos o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="4e5ec-172">Depois de importar os dados para a Plataforma de Experiência do Adobe, precisamos de [criar uma audiência](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) no Adobe Campaign Standard utilizando os dados na Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="4e5ec-173">Saiba como [usar o construtor de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) no Adobe Campaign Standard para definir uma audiência com base nos dados da Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="4e5ec-174">Criar e enviar o e-mail usando o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4e5ec-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="4e5ec-175">Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.</span><span class="sxs-lookup"><span data-stu-id="4e5ec-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::

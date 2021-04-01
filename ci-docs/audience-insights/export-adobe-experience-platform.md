---
title: Exportar dados do Customer Insights para a Plataforma de Experiência do Adobe
description: Saiba como usar segmentos de informações da audiência na Plataforma de Experiência do Adobe.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596283"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="d5d6a-103">Usar segmentos do Customer Insights na Plataforma de Experiência do Adobe (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="d5d6a-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="d5d6a-104">Como utilizador de informações da audiência no Dynamics 365 Customer Insights, pode ter criado segmentos para tornar as suas campanhas de marketing mais eficientes, direcionando a audiência relevante.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="d5d6a-105">Para utilizar um segmento a partir das informações da audiência na Plataforma de Experiência do Adobe e aplicações como o Adobe Campaign Standard, é necessário seguir alguns passos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="d5d6a-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d5d6a-107">Prerequisites</span></span>

-   <span data-ttu-id="d5d6a-108">Licença do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d5d6a-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="d5d6a-109">Licença da Plataforma de Experiência do Adobe</span><span class="sxs-lookup"><span data-stu-id="d5d6a-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="d5d6a-110">Licença do Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d5d6a-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="d5d6a-111">Conta de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="d5d6a-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="d5d6a-112">Descrição Geral da Campanha</span><span class="sxs-lookup"><span data-stu-id="d5d6a-112">Campaign Overview</span></span>

<span data-ttu-id="d5d6a-113">Para entender melhor como pode usar segmentos das informações da audiência na Plataforma de Experiência do Adobe, vamos ver uma campanha de exemplo fictícia.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="d5d6a-114">Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="d5d6a-115">Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="d5d6a-116">Para manter estes clientes, pretende enviar-lhes uma oferta promocional por e-mail, utilizando a Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="d5d6a-117">Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="d5d6a-118">Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="d5d6a-119">Identificar a audiência alvo</span><span class="sxs-lookup"><span data-stu-id="d5d6a-119">Identify your target audience</span></span>

<span data-ttu-id="d5d6a-120">No nosso cenário, supomos que os endereços de e-mail dos clientes estão disponíveis nas informações da audiência e as suas preferências promocionais foram analisadas para identificar membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="d5d6a-121">O [segmento que definiu nas informações da audiência](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a estes clientes a promoção de e-mail.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

<span data-ttu-id="d5d6a-123">O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="d5d6a-124">Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="d5d6a-125">Exportar a audiência alvo</span><span class="sxs-lookup"><span data-stu-id="d5d6a-125">Export your target audience</span></span>

<span data-ttu-id="d5d6a-126">Com a nossa audiência alvo identificada, podemos configurar a exportação das informações da audiência para uma conta de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="d5d6a-127">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d5d6a-128">No mosaico **Armazenamento de Blobs do Azure**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuração do Armazenamento de Blobs do Azure.":::

1. <span data-ttu-id="d5d6a-130">Forneça um **Nome a apresentar** para este novo destino de exportação e, em seguida, introduza o **Nome da conta**, **Chave da conta** e **Recipiente** da conta de Armazenamento de Blobs do Azure para onde pretende exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. "::: 

   - <span data-ttu-id="d5d6a-132">Para saber mais sobre como localizar o nome da conta de armazenamento do Azure Blob e a chave de conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d5d6a-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="d5d6a-133">Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="d5d6a-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="d5d6a-134">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-134">Select **Next**.</span></span>

1. <span data-ttu-id="d5d6a-135">Escolha o segmento que pretende exportar.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="d5d6a-136">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. <span data-ttu-id="d5d6a-138">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-138">Select **Save**.</span></span>

<span data-ttu-id="d5d6a-139">Depois de guardar o destino de exportação, encontra-o em **Administrador** > **Exportações** > **Os meus destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Captura de ecrã com lista de exportações e segmento de exemplo em destaque.":::

<span data-ttu-id="d5d6a-141">Agora pode [exportar o segmento a pedido](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d5d6a-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="d5d6a-142">A exportação também será executada com cada [atualização agendada](system.md).</span><span class="sxs-lookup"><span data-stu-id="d5d6a-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d5d6a-143">Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="d5d6a-144">Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="d5d6a-145">O seguinte caminho de pasta é automaticamente criado no seu recipiente:</span><span class="sxs-lookup"><span data-stu-id="d5d6a-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="d5d6a-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="d5d6a-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="d5d6a-147">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="d5d6a-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="d5d6a-148">O *model.json* para as entidades exportadas reside ao nível *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="d5d6a-149">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="d5d6a-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="d5d6a-150">Definir o Modelo de Dados de Experiência (XDM) na Plataforma de Experiência do Adobe</span><span class="sxs-lookup"><span data-stu-id="d5d6a-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="d5d6a-151">Antes de os dados exportados das informações da audiência poderem ser utilizados na Plataforma de Experiência do Adobe, precisamos de definir o esquema do Modelo de Dados de Experiência e [configurar os dados para o Perfil de Cliente em Tempo Real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="d5d6a-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="d5d6a-152">Saiba [o que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e compreenda as [noções básicas da composição do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="d5d6a-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="d5d6a-153">Importar dados para a Plataforma de Experiência do Adobe</span><span class="sxs-lookup"><span data-stu-id="d5d6a-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="d5d6a-154">Agora que está tudo pronto, precisamos de importar os dados de audiência preparados das informações da audiência para a Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="d5d6a-155">Em primeiro lugar, [crie uma ligação de origem do Armazenamento de Blobs do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="d5d6a-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="d5d6a-156">Depois de definir a ligação de origem, [configure um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para uma ligação de lote do armazenamento na nuvem para importar a saída do segmento das informações da audiência para a Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="d5d6a-157">Criar uma audiência no Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d5d6a-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="d5d6a-158">Para enviar o e-mail para esta campanha, vamos usar o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="d5d6a-159">Depois de importar os dados para a Plataforma de Experiência do Adobe, precisamos de [criar uma audiência](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) no Adobe Campaign Standard utilizando os dados na Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="d5d6a-160">Saiba como [usar o construtor de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) no Adobe Campaign Standard para definir uma audiência com base nos dados da Plataforma de Experiência do Adobe.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="d5d6a-161">Criar e enviar o e-mail usando o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d5d6a-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="d5d6a-162">Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.</span><span class="sxs-lookup"><span data-stu-id="d5d6a-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::
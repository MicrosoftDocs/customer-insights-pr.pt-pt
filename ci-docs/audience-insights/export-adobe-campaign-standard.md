---
title: Exportar dados do Customer Insights para o Adobe Campaign Standard
description: Saiba como usar segmentos de informações da audiência no Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305400"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="871b3-103">Usar segmentos do Customer Insights no Adobe Campaign Standard (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="871b3-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="871b3-104">Como utilizador de informações de audiência no Dynamics 365 Customer Insights, pode ter criado segmentos para tornar as suas campanhas de marketing mais eficientes, direcionadas a audiências relevantes.</span><span class="sxs-lookup"><span data-stu-id="871b3-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="871b3-105">Para utilizar um segmento a partir das informações da audiência na Plataforma de Experiência do Adobe e aplicações como o Adobe Campaign Standard, é necessário seguir alguns passos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="871b3-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="871b3-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="871b3-107">Prerequisites</span></span>

-   <span data-ttu-id="871b3-108">Licença do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="871b3-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="871b3-109">Licença do Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="871b3-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="871b3-110">Conta de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="871b3-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="871b3-111">Descrição geral da campanha</span><span class="sxs-lookup"><span data-stu-id="871b3-111">Campaign overview</span></span>

<span data-ttu-id="871b3-112">Para entender melhor como pode usar segmentos das informações da audiência na Plataforma de Experiência do Adobe, vamos ver uma campanha de exemplo fictícia.</span><span class="sxs-lookup"><span data-stu-id="871b3-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="871b3-113">Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="871b3-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="871b3-114">Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição.</span><span class="sxs-lookup"><span data-stu-id="871b3-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="871b3-115">Para manter estes clientes, pretende enviar-lhes uma oferta promocional por e-mail, utilizando o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="871b3-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="871b3-116">Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez.</span><span class="sxs-lookup"><span data-stu-id="871b3-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="871b3-117">Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez.</span><span class="sxs-lookup"><span data-stu-id="871b3-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="871b3-118">No entanto, as informações da audiência e o Adobe Campaign Standard também podem ser configurados para trabalhar num cenário de campanha recorrente.</span><span class="sxs-lookup"><span data-stu-id="871b3-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="871b3-119">Identificar a audiência alvo</span><span class="sxs-lookup"><span data-stu-id="871b3-119">Identify your target audience</span></span>

<span data-ttu-id="871b3-120">No nosso cenário, supomos que os endereços de e-mail dos clientes estão disponíveis nas informações da audiência e as suas preferências promocionais foram analisadas para identificar membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="871b3-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="871b3-121">O [segmento que definiu nas informações da audiência](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a estes clientes a promoção de e-mail.</span><span class="sxs-lookup"><span data-stu-id="871b3-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

<span data-ttu-id="871b3-123">O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente.</span><span class="sxs-lookup"><span data-stu-id="871b3-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="871b3-124">Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.</span><span class="sxs-lookup"><span data-stu-id="871b3-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="871b3-125">Exportar a audiência alvo</span><span class="sxs-lookup"><span data-stu-id="871b3-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="871b3-126">Configurar uma ligação</span><span class="sxs-lookup"><span data-stu-id="871b3-126">Configure a connection</span></span>

<span data-ttu-id="871b3-127">Com a nossa audiência alvo identificada, podemos configurar a exportação das informações da audiência para uma conta de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="871b3-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="871b3-128">No Audience Insights, vá a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="871b3-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="871b3-129">Selecione **Adicionar ligação** e escolha a **Adobe Campaign** para configurar a ligação ou selecione **Configurar** no mosaico **Adobe Campaign**.</span><span class="sxs-lookup"><span data-stu-id="871b3-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuração do Adobe Campaign Standard.":::

1. <span data-ttu-id="871b3-131">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="871b3-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="871b3-132">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="871b3-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="871b3-133">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="871b3-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="871b3-134">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="871b3-134">Choose who can use this connection.</span></span> <span data-ttu-id="871b3-135">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="871b3-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="871b3-136">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="871b3-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="871b3-137">Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da conta de Armazenamento de Blobs do Azure para onde pretende exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="871b3-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. "::: 

   - <span data-ttu-id="871b3-139">Para saber mais sobre como localizar o nome da conta de Armazenamento do Azure Blob e a chave de conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="871b3-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="871b3-140">Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="871b3-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="871b3-141">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="871b3-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="871b3-142">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="871b3-142">Configure an export</span></span>

<span data-ttu-id="871b3-143">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="871b3-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="871b3-144">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="871b3-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="871b3-145">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="871b3-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="871b3-146">Para criar um nova exportação, selecione **Adicionar exportação**.</span><span class="sxs-lookup"><span data-stu-id="871b3-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="871b3-147">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="871b3-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="871b3-148">Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="871b3-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="871b3-149">Escolha o segmento que pretende exportar.</span><span class="sxs-lookup"><span data-stu-id="871b3-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="871b3-150">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="871b3-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. <span data-ttu-id="871b3-152">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="871b3-152">Select **Next**.</span></span>

1. <span data-ttu-id="871b3-153">Agora mapeamos os campos **Origem** do segmento de informações da audiência para os nomes de campo **Destino** no esquema de perfil do Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="871b3-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapeamento de campo para o conector do Adobe Campaign Standard.":::

   <span data-ttu-id="871b3-155">Se quiser adicionar mais atributos, selecione **Adicionar atributo**.</span><span class="sxs-lookup"><span data-stu-id="871b3-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="871b3-156">O nome de destino pode ser diferente do nome do campo de origem para que ainda possa mapear a saída do segmento das informações da audiência para o Adobe Campaign Standard se os campos não tiverem o mesmo nome nos dois sistemas.</span><span class="sxs-lookup"><span data-stu-id="871b3-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="871b3-157">O endereço de e-mail é usado como campo de identidade, mas pode usar qualquer outro identificador do perfil de cliente das informações da audiência para mapear dados para o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="871b3-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="871b3-158">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="871b3-158">Select **Save**.</span></span>

<span data-ttu-id="871b3-159">Depois de guardar o destino de exportação, encontra-o em **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="871b3-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="871b3-160">Agora pode [exportar o segmento a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="871b3-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="871b3-161">A exportação também será executada com cada [atualização agendada](system.md).</span><span class="sxs-lookup"><span data-stu-id="871b3-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="871b3-162">Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="871b3-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="871b3-163">Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima.</span><span class="sxs-lookup"><span data-stu-id="871b3-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="871b3-164">O seguinte caminho de pasta é automaticamente criado no seu recipiente:</span><span class="sxs-lookup"><span data-stu-id="871b3-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="871b3-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="871b3-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="871b3-166">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="871b3-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="871b3-167">Configurar o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="871b3-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="871b3-168">Quando um segmento das informações da audiência é exportado, contém as colunas selecionadas ao definir o destino de exportação no passo anterior.</span><span class="sxs-lookup"><span data-stu-id="871b3-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="871b3-169">Estes dados podem ser utilizados para [criar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="871b3-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="871b3-170">Para utilizar o segmento no Adobe Campaign Standard, precisamos de alargar o esquema de perfil no Adobe Campaign Standard para incluir dois campos adicionais.</span><span class="sxs-lookup"><span data-stu-id="871b3-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="871b3-171">Saiba como [alargar o recurso de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) com novos campos no Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="871b3-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="871b3-172">No nosso exemplo, estes campos são *Nome do Segmento e Data do Segmento (opcional)*.</span><span class="sxs-lookup"><span data-stu-id="871b3-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="871b3-173">Vamos usar estes campos para identificar os perfis no Adobe Campaign Standard que queremos direcionar para esta campanha.</span><span class="sxs-lookup"><span data-stu-id="871b3-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="871b3-174">Se não houver outros registos no Adobe Campaign Standard, para além do que vai importar, pode ignorar este passo.</span><span class="sxs-lookup"><span data-stu-id="871b3-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="871b3-175">Importar dados para o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="871b3-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="871b3-176">Agora que está tudo pronto, precisamos de importar os dados de audiência preparados das informações da audiência para o Adobe Campaign Standard para criar perfis.</span><span class="sxs-lookup"><span data-stu-id="871b3-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="871b3-177">Saiba [como importar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) utilizando um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="871b3-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="871b3-178">O fluxo de trabalho de importação na imagem abaixo foi configurado para ser executado de oito em oito horas e procurar segmentos de informações de audiência exportados (ficheiro .csv no Armazenamento de Blobs do Azure).</span><span class="sxs-lookup"><span data-stu-id="871b3-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="871b3-179">O fluxo de trabalho extrai o conteúdo do ficheiro .csv numa ordem de coluna especificada.</span><span class="sxs-lookup"><span data-stu-id="871b3-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="871b3-180">Este fluxo de trabalho foi concebido para executar o processamento básico de erros e garantir que cada registo tem um endereço de e-mail antes de ativar os dados no Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="871b3-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="871b3-181">O fluxo de trabalho também extrai o nome do segmento do nome do ficheiro antes de se reverter para os dados de perfil do Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="871b3-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de ecrã de um fluxo de trabalho de importação na interface de utilizador do Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="871b3-183">Obter a audiência no Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="871b3-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="871b3-184">Uma vez importados os dados para o Adobe Campaign Standard, [pode criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes com base no *Nome do Segmento* e *Data do Segmento* para selecionar os perfis que foram identificados para a nossa campanha de exemplo.</span><span class="sxs-lookup"><span data-stu-id="871b3-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="871b3-185">Criar e enviar o e-mail usando o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="871b3-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="871b3-186">Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.</span><span class="sxs-lookup"><span data-stu-id="871b3-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::

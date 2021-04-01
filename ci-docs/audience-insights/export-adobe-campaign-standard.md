---
title: Exportar dados do Customer Insights para o Adobe Campaign Standard
description: Saiba como usar segmentos de informações da audiência no Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596329"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="170dc-103">Usar segmentos do Customer Insights no Adobe Campaign Standard (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="170dc-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="170dc-104">Como utilizador de informações da audiência no Dynamics 365 Customer Insights, pode ter criado segmentos para tornar as suas campanhas de marketing mais eficientes, direcionando a audiência relevante.</span><span class="sxs-lookup"><span data-stu-id="170dc-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="170dc-105">Para utilizar um segmento a partir das informações da audiência na Plataforma de Experiência do Adobe e aplicações como o Adobe Campaign Standard, é necessário seguir alguns passos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="170dc-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="170dc-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="170dc-107">Prerequisites</span></span>

-   <span data-ttu-id="170dc-108">Licença do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="170dc-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="170dc-109">Licença do Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="170dc-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="170dc-110">Conta de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="170dc-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="170dc-111">Descrição Geral da Campanha</span><span class="sxs-lookup"><span data-stu-id="170dc-111">Campaign Overview</span></span>

<span data-ttu-id="170dc-112">Para entender melhor como pode usar segmentos das informações da audiência na Plataforma de Experiência do Adobe, vamos ver uma campanha de exemplo fictícia.</span><span class="sxs-lookup"><span data-stu-id="170dc-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="170dc-113">Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="170dc-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="170dc-114">Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição.</span><span class="sxs-lookup"><span data-stu-id="170dc-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="170dc-115">Para manter estes clientes, pretende enviar-lhes uma oferta promocional por e-mail, utilizando o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="170dc-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="170dc-116">Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez.</span><span class="sxs-lookup"><span data-stu-id="170dc-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="170dc-117">Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez.</span><span class="sxs-lookup"><span data-stu-id="170dc-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="170dc-118">No entanto, as informações da audiência e o Adobe Campaign Standard também podem ser configurados para trabalhar num cenário de campanha recorrente.</span><span class="sxs-lookup"><span data-stu-id="170dc-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="170dc-119">Identificar a audiência alvo</span><span class="sxs-lookup"><span data-stu-id="170dc-119">Identify your target audience</span></span>

<span data-ttu-id="170dc-120">No nosso cenário, supomos que os endereços de e-mail dos clientes estão disponíveis nas informações da audiência e as suas preferências promocionais foram analisadas para identificar membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="170dc-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="170dc-121">O [segmento que definiu nas informações da audiência](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a estes clientes a promoção de e-mail.</span><span class="sxs-lookup"><span data-stu-id="170dc-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

<span data-ttu-id="170dc-123">O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente.</span><span class="sxs-lookup"><span data-stu-id="170dc-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="170dc-124">Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.</span><span class="sxs-lookup"><span data-stu-id="170dc-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="170dc-125">Exportar a audiência alvo</span><span class="sxs-lookup"><span data-stu-id="170dc-125">Export your target audience</span></span>

<span data-ttu-id="170dc-126">Com a nossa audiência alvo identificada, podemos configurar a exportação das informações da audiência para uma conta de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="170dc-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="170dc-127">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="170dc-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="170dc-128">No mosaico **Adobe Campaign**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="170dc-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuração do Adobe Campaign Standard.":::

1. <span data-ttu-id="170dc-130">Forneça um **Nome a apresentar** para este novo destino de exportação e, em seguida, introduza o **Nome da conta**, **Chave da conta** e **Recipiente** da conta de Armazenamento de Blobs do Azure para onde pretende exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="170dc-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. "::: 

   - <span data-ttu-id="170dc-132">Para saber mais sobre como localizar o nome da conta de armazenamento do Azure Blob e a chave de conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="170dc-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="170dc-133">Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="170dc-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="170dc-134">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="170dc-134">Select **Next**.</span></span>

1. <span data-ttu-id="170dc-135">Escolha o segmento que pretende exportar.</span><span class="sxs-lookup"><span data-stu-id="170dc-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="170dc-136">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="170dc-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. <span data-ttu-id="170dc-138">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="170dc-138">Select **Next**.</span></span>

1. <span data-ttu-id="170dc-139">Agora mapeamos os campos **Origem** do segmento de informações da audiência para os nomes de campo **Destino** no esquema de perfil do Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="170dc-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapeamento de campo para o conector do Adobe Campaign Standard.":::

   <span data-ttu-id="170dc-141">Se quiser adicionar mais atributos, selecione **Adicionar atributo**.</span><span class="sxs-lookup"><span data-stu-id="170dc-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="170dc-142">O nome de destino pode ser diferente do nome do campo de origem para que ainda possa mapear a saída do segmento das informações da audiência para o Adobe Campaign Standard se os campos não tiverem o mesmo nome nos dois sistemas.</span><span class="sxs-lookup"><span data-stu-id="170dc-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="170dc-143">O endereço de e-mail é usado como campo de identidade, mas pode usar qualquer outro identificador do perfil de cliente das informações da audiência para mapear dados para o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="170dc-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="170dc-144">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="170dc-144">Select **Save**.</span></span>

<span data-ttu-id="170dc-145">Depois de guardar o destino de exportação, encontra-o em **Administrador** > **Exportações** > **Os meus destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="170dc-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Captura de ecrã com lista de exportações e segmento de exemplo em destaque.":::

<span data-ttu-id="170dc-147">Agora pode [exportar o segmento a pedido](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="170dc-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="170dc-148">A exportação também será executada com cada [atualização agendada](system.md).</span><span class="sxs-lookup"><span data-stu-id="170dc-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="170dc-149">Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="170dc-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="170dc-150">Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima.</span><span class="sxs-lookup"><span data-stu-id="170dc-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="170dc-151">O seguinte caminho de pasta é automaticamente criado no seu recipiente:</span><span class="sxs-lookup"><span data-stu-id="170dc-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="170dc-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="170dc-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="170dc-153">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="170dc-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="170dc-154">Configurar o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="170dc-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="170dc-155">Quando um segmento das informações da audiência é exportado, contém as colunas selecionadas ao definir o destino de exportação no passo anterior.</span><span class="sxs-lookup"><span data-stu-id="170dc-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="170dc-156">Estes dados podem ser utilizados para [criar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="170dc-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="170dc-157">Para utilizar o segmento no Adobe Campaign Standard, precisamos de alargar o esquema de perfil no Adobe Campaign Standard para incluir dois campos adicionais.</span><span class="sxs-lookup"><span data-stu-id="170dc-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="170dc-158">Saiba como [alargar o recurso de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) com novos campos no Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="170dc-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="170dc-159">No nosso exemplo, estes campos são *Nome do Segmento e Data do Segmento (opcional).*</span><span class="sxs-lookup"><span data-stu-id="170dc-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="170dc-160">Vamos usar estes campos para identificar os perfis no Adobe Campaign Standard que queremos direcionar para esta campanha.</span><span class="sxs-lookup"><span data-stu-id="170dc-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="170dc-161">Se não houver outros registos no Adobe Campaign Standard, para além do que vai importar, pode ignorar este passo.</span><span class="sxs-lookup"><span data-stu-id="170dc-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="170dc-162">Importar dados para o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="170dc-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="170dc-163">Agora que está tudo pronto, precisamos de importar os dados de audiência preparados das informações da audiência para o Adobe Campaign Standard para criar perfis.</span><span class="sxs-lookup"><span data-stu-id="170dc-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="170dc-164">Saiba [como importar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) utilizando um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="170dc-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="170dc-165">O fluxo de trabalho de importação na imagem abaixo foi configurado para ser executado de 8 em 8 horas e procura segmentos de informações da audiência exportados (ficheiro .csv no Armazenamento de Blobs do Azure).</span><span class="sxs-lookup"><span data-stu-id="170dc-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="170dc-166">O fluxo de trabalho extrai o conteúdo do ficheiro .csv numa ordem de coluna especificada.</span><span class="sxs-lookup"><span data-stu-id="170dc-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="170dc-167">Este fluxo de trabalho foi concebido para executar o processamento básico de erros e garantir que cada registo tem um endereço de e-mail antes de ativar os dados no Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="170dc-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="170dc-168">O fluxo de trabalho também extrai o nome do segmento do nome de ficheiro antes de atualizar/inserir nos dados do Perfil ACS.</span><span class="sxs-lookup"><span data-stu-id="170dc-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de ecrã de um fluxo de trabalho de importação na interface de utilizador do Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="170dc-170">Obter a audiência no Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="170dc-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="170dc-171">Uma vez importados os dados para o Adobe Campaign Standard, [pode criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes com base no *Nome do Segmento* e *Data do Segmento* para selecionar os perfis que foram identificados para a nossa campanha de exemplo.</span><span class="sxs-lookup"><span data-stu-id="170dc-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="170dc-172">Criar e enviar o e-mail usando o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="170dc-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="170dc-173">Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.</span><span class="sxs-lookup"><span data-stu-id="170dc-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::
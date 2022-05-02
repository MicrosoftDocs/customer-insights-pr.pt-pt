---
title: Exportar dados do Customer Insights para o Adobe Experience Platform
description: Saiba como utilizar segmentos do Customer Insights no Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 42a4e0c6bce67a63b449a541299620ef2f4a3259
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647259"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Utilizar segmentos do Customer Insights no Adobe Experience Platform (pré-visualização)

Como utilizador do Dynamics 365 Customer Insights, poderá ter criado segmentos para tornar as suas campanhas de marketing mais eficientes visando audiências relevantes. Para utilizar um segmento do Customer Insights no Adobe Experience Platform e aplicações como o Adobe Campaign Standard, tem de seguir alguns passos descritos neste artigo.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

-   Licença do Dynamics 365 Customer Insights
-   Licença do Adobe Experience Platform
-   Licença do Adobe Campaign Standard
-   Conta de Armazenamento de Blobs do Azure

## <a name="campaign-overview"></a>Descrição Geral da Campanha

Para compreender melhor como pode utilizar segmentos do Customer Insights no Adobe Experience Platform, vejamos uma campanha de amostra fictícia.

Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos. Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição. Para manter estes clientes, pretende enviar-lhes uma oferta promocional via e-mail, utilizando o Adobe Experience Platform.

Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez. Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez.

## <a name="identify-your-target-audience"></a>Identificar a audiência alvo

No nosso cenário, partimos do princípio que os endereços e-mail dos clientes estão disponíveis no Customer Insights e que as respetivas preferências promocionais foram analisadas para identificar membros do segmento.

O [segmento que definiu no Customer Insights](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a promoção por e-mail a estes clientes.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente. Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.

## <a name="export-your-target-audience"></a>Exportar a audiência alvo

Com a nossa audiência alvo identificada, podemos configurar a exportação do Customer Insights para uma conta de Armazenamento de Blobs do Azure.

### <a name="configure-a-connection"></a>Configurar uma ligação

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha a **Armazenamento de Blobs do Azure** ou selecione **Configurar** no mosaico **Armazenamento de Blobs do Azure** para configurar a ligação.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuração do Armazenamento de Blobs do Azure."::: 

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da sua conta de Armazenamento de Blobs para onde pretende exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. "::: 
   
    - Para saber mais sobre como encontrar o nome da conta de Armazenamento de Blobs e a chave da conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
    - Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Guardar** para concluir a ligação. 

### <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar um nova exportação, selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Armazenamento de Blobs do Azure. Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.

1. Escolha o segmento que pretende exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Guardar**.

Depois de guardar o destino de exportação, encontra-o em **Dados** > **Exportações**.

Agora pode [exportar o segmento a pedido](export-destinations.md#run-exports-on-demand). A exportação também será executada com cada [atualização agendada](system.md).

> [!NOTE]
> Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença do Adobe Campaign Standard.

Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima. O seguinte caminho de pasta é automaticamente criado no seu recipiente:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

O *model.json* para as entidades exportadas reside ao nível *%ExportDestinationName%*.

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir o Experience Data Model (XDM) no Adobe Experience Platform

Antes de os dados exportados do Customer Insights poderem ser utilizados dentro do Adobe Experience Platform, temos de definir o esquema de Modelo de Dados de Experiência e [configure os dados para o Perfil de Cliente em Tempo Real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saiba [o que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e compreenda as [noções básicas da composição do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar dados para o Adobe Experience Platform

Agora que tudo está preparado, é necessário importar os dados de audiência preparados do Customer Insights para o Adobe Experience Platform.

Em primeiro lugar, [crie uma ligação de origem do Armazenamento de Blobs do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Depois de definir a ligação de origem, [configure um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para uma ligação de lote de armazenamento na nuvem para importar a saída do segmento do Customer Insights para o Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Criar uma audiência no Adobe Campaign Standard

Para enviar o e-mail para esta campanha, utilizaremos o Adobe Campaign Standard. Depois de importar os dados para o Adobe Experience Platform, precisamos de [criar uma audiência](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) no Adobe Campaign Standard usando os dados no Adobe Experience Platform.


Saiba como [utilizar o criador de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) no Adobe Campaign Standard para definir uma audiência com base nos dados no Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o e-mail usando o Adobe Campaign Standard

Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::

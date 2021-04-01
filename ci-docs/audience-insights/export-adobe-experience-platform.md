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
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Usar segmentos do Customer Insights na Plataforma de Experiência do Adobe (pré-visualização)

Como utilizador de informações da audiência no Dynamics 365 Customer Insights, pode ter criado segmentos para tornar as suas campanhas de marketing mais eficientes, direcionando a audiência relevante. Para utilizar um segmento a partir das informações da audiência na Plataforma de Experiência do Adobe e aplicações como o Adobe Campaign Standard, é necessário seguir alguns passos descritos neste artigo.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

-   Licença do Dynamics 365 Customer Insights
-   Licença da Plataforma de Experiência do Adobe
-   Licença do Adobe Campaign Standard
-   Conta de Armazenamento de Blobs do Azure

## <a name="campaign-overview"></a>Descrição Geral da Campanha

Para entender melhor como pode usar segmentos das informações da audiência na Plataforma de Experiência do Adobe, vamos ver uma campanha de exemplo fictícia.

Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos. Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição. Para manter estes clientes, pretende enviar-lhes uma oferta promocional por e-mail, utilizando a Plataforma de Experiência do Adobe.

Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez. Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez.

## <a name="identify-your-target-audience"></a>Identificar a audiência alvo

No nosso cenário, supomos que os endereços de e-mail dos clientes estão disponíveis nas informações da audiência e as suas preferências promocionais foram analisadas para identificar membros do segmento.

O [segmento que definiu nas informações da audiência](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a estes clientes a promoção de e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente. Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.

## <a name="export-your-target-audience"></a>Exportar a audiência alvo

Com a nossa audiência alvo identificada, podemos configurar a exportação das informações da audiência para uma conta de Armazenamento de Blobs do Azure.

1. Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.

1. No mosaico **Armazenamento de Blobs do Azure**, selecione **Configurar**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuração do Armazenamento de Blobs do Azure.":::

1. Forneça um **Nome a apresentar** para este novo destino de exportação e, em seguida, introduza o **Nome da conta**, **Chave da conta** e **Recipiente** da conta de Armazenamento de Blobs do Azure para onde pretende exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. "::: 

   - Para saber mais sobre como localizar o nome da conta de armazenamento do Azure Blob e a chave de conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

   - Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Seguinte**.

1. Escolha o segmento que pretende exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Guardar**.

Depois de guardar o destino de exportação, encontra-o em **Administrador** > **Exportações** > **Os meus destinos de exportação**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Captura de ecrã com lista de exportações e segmento de exemplo em destaque.":::

Agora pode [exportar o segmento a pedido](export-destinations.md#export-data-on-demand). A exportação também será executada com cada [atualização agendada](system.md).

> [!NOTE]
> Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença de Adobe Campaign Standard.

Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima. O seguinte caminho de pasta é automaticamente criado no seu recipiente:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

O *model.json* para as entidades exportadas reside ao nível *%ExportDestinationName%*.

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir o Modelo de Dados de Experiência (XDM) na Plataforma de Experiência do Adobe

Antes de os dados exportados das informações da audiência poderem ser utilizados na Plataforma de Experiência do Adobe, precisamos de definir o esquema do Modelo de Dados de Experiência e [configurar os dados para o Perfil de Cliente em Tempo Real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saiba [o que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e compreenda as [noções básicas da composição do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar dados para a Plataforma de Experiência do Adobe

Agora que está tudo pronto, precisamos de importar os dados de audiência preparados das informações da audiência para a Plataforma de Experiência do Adobe.

Em primeiro lugar, [crie uma ligação de origem do Armazenamento de Blobs do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Depois de definir a ligação de origem, [configure um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para uma ligação de lote do armazenamento na nuvem para importar a saída do segmento das informações da audiência para a Plataforma de Experiência do Adobe.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Criar uma audiência no Adobe Campaign Standard

Para enviar o e-mail para esta campanha, vamos usar o Adobe Campaign Standard. Depois de importar os dados para a Plataforma de Experiência do Adobe, precisamos de [criar uma audiência](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) no Adobe Campaign Standard utilizando os dados na Plataforma de Experiência do Adobe.

Saiba como [usar o construtor de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) no Adobe Campaign Standard para definir uma audiência com base nos dados da Plataforma de Experiência do Adobe.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o e-mail usando o Adobe Campaign Standard

Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::
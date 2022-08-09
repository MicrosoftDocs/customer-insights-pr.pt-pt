---
title: Exportar segmentos para o Adobe Experience Platform (pré-visualização)
description: Saiba como utilizar segmentos do Customer Insights no Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195304"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportar segmentos para o Adobe Experience Platform (pré-visualização)

Exportar segmentos que visam audiências relevantes para o Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

- Uma licença do Adobe Experience Platform.
- Uma licença do Adobe Campaign Standard.
- Uma chave de conta e nome de [conta de Armazenamento de Blobs do Azure](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar o nome e a chave, consulte [Gerir definições de conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
- Um [contentor do Armazenamento de Blobs do Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Vamos configurar a exportação do Customer Insights para uma conta de Armazenamento de Blobs do Azure.

### <a name="set-up-connection-to-azure-blob-storage"></a>Configurar ligação ao Armazenamento de Blobs do Azure

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Armazenamento de Blobs do Azure**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da sua conta de Armazenamento de Blobs para onde pretende exportar o segmento.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. ":::

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

### <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Armazenamento de Blobs do Azure. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Escolha o segmento que pretende exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença do Adobe Campaign Standard.

Os dados exportados são armazenados no contentor do Armazenamento de Blobs do Azure que configurou. Os seguintes caminhos de pastas são criados automaticamente no seu contentor:

- Para entidades de origem e entidades geradas pelo sistema:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- O *model.json* para as entidades exportadas reside ao nível de *%ExportDestinationName%*.

  Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir o Experience Data Model (XDM) no Adobe Experience Platform

Antes dos dados exportados do Customer Insights poderem ser utilizados no Adobe Experience Platform, defina o esquema Modelo de Dados de Experiência e [configure os dados para o Perfil de Cliente em Tempo Real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saiba [o que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e compreenda as [noções básicas da composição do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar dados para o Adobe Experience Platform

Importe os dados de audiência preparados do Customer Insights para o Adobe Experience Platform.

1. [Criar uma ligação de origem do Armazenamento de Blobs do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Configure um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para uma ligação ao lote de armazenamento na cloud para importar a saída do segmento do Customer Insights para o Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Criar uma audiência no Adobe Campaign Standard

Para enviar o e-mail para esta campanha, utilizaremos o Adobe Campaign Standard.

1. [Crie uma audiência](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) no Adobe Campaign Standard com os dados no Adobe Experience Platform.

1. [Utilize o criador de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) no Adobe Campaign Standard para definir uma audiência com base nos dados no Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o e-mail usando o Adobe Campaign Standard

Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Exportar segmentos do Customer Insights para o Adobe Campaign Standard (pré-visualização)
description: Saiba como utilizar segmentos do Customer Insights no Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195534"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Exportar segmentos do Customer Insights para o Adobe Campaign Standard (pré-visualização)

Exportar segmentos que visam audiências relevantes para o Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

- Uma licença do Adobe Campaign Standard.
- Uma chave de conta e nome de [conta de Armazenamento de Blobs do Azure](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar o nome e a chave, consulte [Gerir definições de conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
- Um [contentor do Armazenamento de Blobs do Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Descrição geral da campanha

Para compreender melhor como pode utilizar segmentos do Customer Insights no Adobe Experience Platform, vejamos uma campanha de amostra fictícia.

Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos. Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição. Para manter estes clientes, pretende enviar-lhes uma oferta promocional via e-mail, utilizando o Adobe Campaign Standard.

Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez. Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez. No entanto, o Customer Insights e o Adobe Campaign Standard também podem ser configurados para funcionarem num cenário de campanha recorrente.

## <a name="identify-your-target-audience"></a>Identificar a audiência alvo

No nosso cenário, partimos do princípio que os endereços e-mail dos clientes estão disponíveis no Customer Insights e que as respetivas preferências promocionais foram analisadas para identificar membros do segmento.

O [segmento que definiu no Customer Insights](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a promoção por e-mail a estes clientes.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente. Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.

## <a name="export-your-target-audience"></a>Exportar a audiência alvo

### <a name="set-up-connection-to-adobe-campaign"></a>Configurar ligação ao Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Adobe Campaign**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da sua conta de Armazenamento de Blobs.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. ":::

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

### <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação à exportação**, escolha uma ligação a partir da secção Adobe Campaign. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Escolha o segmento que pretende exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Seguinte**.

1. Mapeie os campos **Origem** do segmento Customer Insights para o campo **Destino** no esquema de perfis do Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapeamento de campo para o conector do Adobe Campaign Standard.":::

   Se quiser adicionar mais atributos, selecione **Adicionar atributo**. O nome de destino pode diferir do nome do campo de origem, por isso, ainda pode mapear a saída do segmento do Customer Insights para o Adobe Campaign Standard se os campos não tiverem o mesmo nome nos dois sistemas.

   > [!NOTE]
   > O endereço de e-mail é utilizado como um campo de identidade, mas pode utilizar qualquer outro identificador do perfil de cliente para mapear dados para o Adobe Campaign Standard.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença do Adobe Campaign Standard.

Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima. O seguinte caminho de pasta é criado automaticamente no contentor: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar o Adobe Campaign Standard

Os segmentos exportados contêm as colunas que selecionou ao configurar a exportação. Estes dados podem ser utilizados para [criar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para utilizar o segmento no Adobe Campaign Standard, [expanda o esquema de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) no Adobe Campaign Standard para incluir dois campos adicionais.

No nosso exemplo, estes campos são Nome do Segmento e Data do Segmento. Iremos utilizar estes campos para identificar os perfis no Adobe Campaign Standard que queremos direcionar para esta campanha.

Se não houver outros registos no Adobe Campaign Standard, para além dos que vai importar, ignore este passo.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar dados para o Adobe Campaign Standard

Importe os dados de audiência preparados do Customer Insights para o Adobe Campaign Standard para [criar perfis através de um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

O fluxo de trabalho de importação na imagem abaixo foi configurado para ser executado a cada oito horas e procurar por segmentos do Customer Insights exportados (ficheiro .csv no Armazenamento de Blobs do Azure). O fluxo de trabalho extrai o conteúdo do ficheiro .csv numa ordem de coluna especificada. Este fluxo de trabalho foi criado para efetuar o processamento básico de erros e garantir que cada registo tem um endereço de e-mail antes de hidratar os dados no Adobe Campaign Standard. O fluxo de trabalho também extrai o nome do segmento do nome do ficheiro antes de se reverter para os dados de perfil do Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de ecrã de um fluxo de trabalho de importação na interface de utilizador do Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Obter a audiência no Adobe Campaign Standard

Depois de importados os dados para o Adobe Campaign Standard, [crie um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consulte](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes com base no Nome de Segmento e Data do Segmento para selecionar os perfis que foram identificados para a nossa campanha de exemplo.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o e-mail usando o Adobe Campaign Standard

Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]

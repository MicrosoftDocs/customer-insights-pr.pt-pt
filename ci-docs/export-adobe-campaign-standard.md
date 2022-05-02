---
title: Exportar dados do Customer Insights para o Adobe Campaign Standard
description: Saiba como utilizar segmentos do Customer Insights no Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646969"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Utilizar segmentos do Customer Insights no Adobe Campaign Standard (pré-visualização)

Como utilizador do Dynamics 365 Customer Insights, poderá ter criado segmentos para tornar as suas campanhas de marketing mais eficientes visando audiências relevantes. Para utilizar um segmento do Customer Insights no Adobe Experience Platform e aplicações como o Adobe Campaign Standard, tem de seguir alguns passos descritos neste artigo.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

-   Licença do Dynamics 365 Customer Insights
-   Licença do Adobe Campaign Standard
-   Conta de Armazenamento de Blobs do Azure

## <a name="campaign-overview"></a>Descrição geral da campanha

Para compreender melhor como pode utilizar segmentos do Customer Insights no Adobe Experience Platform, vejamos uma campanha de amostra fictícia.

Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos. Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição. Para manter estes clientes, pretende enviar-lhes uma oferta promocional via e-mail, utilizando o Adobe Campaign Standard.

Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez. Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez. No entanto, o Customer Insights e o Adobe Campaign Standard também podem ser configurados para funcionarem num cenário de campanha recorrente.

## <a name="identify-your-target-audience"></a>Identificar a audiência alvo

No nosso cenário, partimos do princípio que os endereços e-mail dos clientes estão disponíveis e que as respetivas preferências promocionais foram analisadas para identificar membros do segmento.

O [segmento que definiu no Customer Insights](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a promoção por e-mail a estes clientes.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente. Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.

## <a name="export-your-target-audience"></a>Exportar a audiência alvo

### <a name="configure-a-connection"></a>Configurar uma ligação

Com a nossa audiência alvo identificada, podemos configurar a exportação para uma conta de Armazenamento de Blobs do Azure.

1. No Customer Insights, aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha a **Adobe Campaign** para configurar a ligação ou selecione **Configurar** no mosaico **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuração para o Adobe Campaign Standard.":::

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Introduza o **Nome da conta**, a **Chave da conta** e o **Contentor** da conta de Armazenamento de Blobs do Azure para onde pretende exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de ecrã da configuração da conta de armazenamento. "::: 

   - Para saber mais sobre como localizar o nome da conta de Armazenamento do Azure Blob e a chave de conta, consulte [Gerir definições da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

   - Para saber mais sobre como criar um contentor, consulte [Criar um contentor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Guardar** para concluir a ligação.

### <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar um nova exportação, selecione **Adicionar exportação**.

1. No campo **Ligação à exportação**, escolha uma ligação a partir da secção Adobe Campaign. Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.

1. Escolha o segmento que pretende exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Seguinte**.

1. Agora, mapeamos os campos **Origem** do segmento Customer Insights para o campo **Destino** no esquema de perfis do Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapeamento de campo para o conector do Adobe Campaign Standard.":::

   Se quiser adicionar mais atributos, selecione **Adicionar atributo**. O nome de destino pode diferir do nome do campo de origem, por isso, ainda pode mapear a saída do segmento do Customer Insights para o Adobe Campaign Standard se os campos não tiverem o mesmo nome nos dois sistemas.

   > [!NOTE]
   > O endereço de e-mail é utilizado como um campo de identidade, mas pode utilizar qualquer outro identificador do perfil de cliente para mapear dados para o Adobe Campaign Standard.

1. Selecione **Guardar**.

Depois de guardar o destino de exportação, encontra-o em **Dados** > **Exportações**.

Agora pode [exportar o segmento a pedido](export-destinations.md#run-exports-on-demand). A exportação também será executada com cada [atualização agendada](system.md).

> [!NOTE]
> Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença do Adobe Campaign Standard.

Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima. O seguinte caminho de pasta é automaticamente criado no seu recipiente:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar o Adobe Campaign Standard

Os segmentos exportados contêm as colunas que selecionou durante a definição do destino de exportação no passo anterior. Estes dados podem ser utilizados para [criar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para utilizar o segmento no Adobe Campaign Standard, precisamos de alargar o esquema de perfis no Adobe Campaign Standard para incluir dois campos adicionais. Saiba como [alargar o recurso do perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) com novos campos no Adobe Campaign Standard.

No nosso exemplo, estes campos são *Nome do Segmento e Data do Segmento (opcional)*.

Iremos utilizar estes campos para identificar os perfis no Adobe Campaign Standard que queremos direcionar para esta campanha.

Se não houver outros registos no Adobe Campaign Standard, para além dos que vai importar, pode saltar este passo.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar dados para o Adobe Campaign Standard

Agora que tudo está preparado, é necessário importar os dados de audiência preparados do Customer Insights para o Adobe Campaign Standard para criar perfis. Saiba [como importar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) utilizando um fluxo de trabalho.

O fluxo de trabalho de importação na imagem abaixo foi configurado para ser executado a cada oito horas e procurar por segmentos do Customer Insights exportados (ficheiro .csv no Armazenamento de Blobs do Azure). O fluxo de trabalho extrai o conteúdo do ficheiro .csv numa ordem de coluna especificada. Este fluxo de trabalho foi criado para efetuar o processamento básico de erros e garantir que cada registo tem um endereço de e-mail antes de hidratar os dados no Adobe Campaign Standard. O fluxo de trabalho também extrai o nome do segmento do nome do ficheiro antes de se reverter para os dados de perfil do Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de ecrã de um fluxo de trabalho de importação na interface de utilizador do Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Obter a audiência no Adobe Campaign Standard

Uma vez importados os dados para o Adobe Campaign Standard, [pode criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes com base no *Nome do Segmento* e *Data do Segmento* para selecionar perfis que foram identificados para a nossa campanha de exemplo.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o e-mail usando o Adobe Campaign Standard

Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::

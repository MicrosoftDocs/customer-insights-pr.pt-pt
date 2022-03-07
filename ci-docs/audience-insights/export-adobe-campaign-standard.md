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
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Usar segmentos do Customer Insights no Adobe Campaign Standard (pré-visualização)

Como utilizador de informações de audiência no Dynamics 365 Customer Insights, pode ter criado segmentos para tornar as suas campanhas de marketing mais eficientes, direcionadas a audiências relevantes. Para utilizar um segmento a partir das informações da audiência na Plataforma de Experiência do Adobe e aplicações como o Adobe Campaign Standard, é necessário seguir alguns passos descritos neste artigo.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de processo dos passos descritos neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

-   Licença do Dynamics 365 Customer Insights
-   Licença do Adobe Campaign Standard
-   Conta de Armazenamento de Blobs do Azure

## <a name="campaign-overview"></a>Descrição geral da campanha

Para entender melhor como pode usar segmentos das informações da audiência na Plataforma de Experiência do Adobe, vamos ver uma campanha de exemplo fictícia.

Vamos supor que a sua empresa oferece um serviço mensal baseado em subscrições aos seus clientes nos Estados Unidos. Pretende identificar os clientes cujas subscrições deverão ser renovadas nos próximos oito dias, mas ainda não renovaram a sua subscrição. Para manter estes clientes, pretende enviar-lhes uma oferta promocional por e-mail, utilizando o Adobe Campaign Standard.

Neste exemplo, queremos realizar a campanha promocional de e-mail uma vez. Este artigo não aborda o caso de utilização de realização da campanha mais do que uma vez. No entanto, as informações da audiência e o Adobe Campaign Standard também podem ser configurados para trabalhar num cenário de campanha recorrente.

## <a name="identify-your-target-audience"></a>Identificar a audiência alvo

No nosso cenário, supomos que os endereços de e-mail dos clientes estão disponíveis nas informações da audiência e as suas preferências promocionais foram analisadas para identificar membros do segmento.

O [segmento que definiu nas informações da audiência](segments.md) chama-se **ChurnProneCustomers** e planeia enviar a estes clientes a promoção de e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de ecrã da página de segmentos com o segmento ChurnProneCustomers criado.":::

O e-mail de oferta que pretende enviar irá conter o nome próprio, apelido e a data de fim da subscrição do cliente. Informa os clientes sobre o desconto que obterão se renovarem a subscrição antes desta terminar.

## <a name="export-your-target-audience"></a>Exportar a audiência alvo

### <a name="configure-a-connection"></a>Configurar uma ligação

Com a nossa audiência alvo identificada, podemos configurar a exportação das informações da audiência para uma conta de Armazenamento de Blobs do Azure.

1. No Audience Insights, vá a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha a **Adobe Campaign** para configurar a ligação ou selecione **Configurar** no mosaico **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuração do Adobe Campaign Standard.":::

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

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Adobe Campaign. Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.

1. Escolha o segmento que pretende exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de ecrã da interface de utilizador de seleção do segmento com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Seguinte**.

1. Agora mapeamos os campos **Origem** do segmento de informações da audiência para os nomes de campo **Destino** no esquema de perfil do Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapeamento de campo para o conector do Adobe Campaign Standard.":::

   Se quiser adicionar mais atributos, selecione **Adicionar atributo**. O nome de destino pode ser diferente do nome do campo de origem para que ainda possa mapear a saída do segmento das informações da audiência para o Adobe Campaign Standard se os campos não tiverem o mesmo nome nos dois sistemas.

   > [!NOTE]
   > O endereço de e-mail é usado como campo de identidade, mas pode usar qualquer outro identificador do perfil de cliente das informações da audiência para mapear dados para o Adobe Campaign Standard.

1. Selecione **Guardar**.

Depois de guardar o destino de exportação, encontra-o em **Dados** > **Exportações**.

Agora pode [exportar o segmento a pedido](export-destinations.md#run-exports-on-demand). A exportação também será executada com cada [atualização agendada](system.md).

> [!NOTE]
> Certifique-se de que o número de registos no segmento exportado está dentro do limite permitido da sua licença de Adobe Campaign Standard.

Os dados exportados são armazenados no recipiente do Armazenamento de Blobs do Azure que configurou acima. O seguinte caminho de pasta é automaticamente criado no seu recipiente:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar o Adobe Campaign Standard

Quando um segmento das informações da audiência é exportado, contém as colunas selecionadas ao definir o destino de exportação no passo anterior. Estes dados podem ser utilizados para [criar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para utilizar o segmento no Adobe Campaign Standard, precisamos de alargar o esquema de perfil no Adobe Campaign Standard para incluir dois campos adicionais. Saiba como [alargar o recurso de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) com novos campos no Adobe Campaign Standard.

No nosso exemplo, estes campos são *Nome do Segmento e Data do Segmento (opcional)*.

Vamos usar estes campos para identificar os perfis no Adobe Campaign Standard que queremos direcionar para esta campanha.

Se não houver outros registos no Adobe Campaign Standard, para além do que vai importar, pode ignorar este passo.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar dados para o Adobe Campaign Standard

Agora que está tudo pronto, precisamos de importar os dados de audiência preparados das informações da audiência para o Adobe Campaign Standard para criar perfis. Saiba [como importar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) utilizando um fluxo de trabalho.

O fluxo de trabalho de importação na imagem abaixo foi configurado para ser executado de oito em oito horas e procurar segmentos de informações de audiência exportados (ficheiro .csv no Armazenamento de Blobs do Azure). O fluxo de trabalho extrai o conteúdo do ficheiro .csv numa ordem de coluna especificada. Este fluxo de trabalho foi concebido para executar o processamento básico de erros e garantir que cada registo tem um endereço de e-mail antes de ativar os dados no Adobe Campaign Standard. O fluxo de trabalho também extrai o nome do segmento do nome do ficheiro antes de se reverter para os dados de perfil do Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de ecrã de um fluxo de trabalho de importação na interface de utilizador do Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Obter a audiência no Adobe Campaign Standard

Uma vez importados os dados para o Adobe Campaign Standard, [pode criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes com base no *Nome do Segmento* e *Data do Segmento* para selecionar os perfis que foram identificados para a nossa campanha de exemplo.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o e-mail usando o Adobe Campaign Standard

Crie o conteúdo do e-mail e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mail de exemplo com oferta de renovação do Adobe Campaign Standard.":::

---
title: Criar uma ligação entre as informações de audiência e as informações de cativação
description: Crie uma ligação ativa entre as informações audiência e as informações de cativação para permitir a partilha bidirecional de dados.
ms.date: 07/22/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 870209a7e19fec464ec41462a02365771bd653bd
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461027"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Criar uma ligação entre as informações de audiência e as informações de cativação

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A integração entre informações de cativação e informações de audiência liga ambientes de ambas as capacidades e permite que os dados sejam partilhados bidirecionalmente entre eles.

Utilize perfis e segmentos unificados a partir de informações de audiência para mais opções de análise em informações de cativação. Exporte eventos que têm um alto valor de negócio a partir de informações de cativação. Utilize estes eventos para adicionar dados a perfis unificados em informações de audiência.

## <a name="prerequisites"></a>Pré-requisitos

- Os perfis de informações de audiência têm de ser armazenados numa conta Azure Data Lake Storage que possui ou num data lake gerido pelo [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). 

- Precisa de permissões administrador para ambos os ambientes de informações de cativação e de informações de audiência.

- Os ambientes ligados têm de estar na mesma região geográfica.

> [!NOTE]
> - Se a subscrição de informações de audiência for uma versão de avaliação, a qual utiliza um data lake de informações de audiência gerido internamente, contacte [pirequest@microsoft.com](mailto:pirequest@microsoft.com) para obter assistência. 
> - Se o seu ambiente de informações de audiência utilizar o seu próprio Azure Data Lake Storage para armazenar dados, tem de adicionar um principal de serviço de informações de cativação do Azure à sua conta de armazenamento. Para mais detalhes, vá a [Ligar a uma conta do Azure Data Lake Storage com um principal de serviço do Azure para informações de audiência](../audience-insights/connect-service-principal.md). Além disso, o seu ambiente de informações de audiência deve ter um [ambiente do Dataverse associado](../audience-insights/get-started-paid.md). 

## <a name="create-an-environment-link"></a>Criar uma ligação ao ambiente

Pode criar uma ligação ao ambiente atualizando as definições **Admin** > **Ambiente** em informações de cativação.

**Para estabelecer uma ligação ativa entre as informações de audiência e as informações de cativação**

1. Na página **Admin de ambiente**, selecione o separador **Ligar ambientes**.

    :::image type="content" source="media/integrate1.png" alt-text="Configurar um ambiente.":::

1. Selecione **Configurar ambientes** no canto superior esquerdo ou na parte inferior do ecrã.

     :::image type="content" source="media/integrate2.png" alt-text="Selecionar um ambiente de informações de audiência.":::

1. Selecione um ambiente de informações de audiência e, em seguida, selecione ***Seguinte** para terminar. Agora, pode selecionar funcionalidades opcionais para os ambientes ligados.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Capacitar atributos e segmentos de perfis unificados de informações de audiência

Depois de ligar ambientes, pode selecionar funcionalidades opcionais para os ambientes ligados. Estas funcionalidades permitem a análise interativa de dados de clientes dos atributos e segmentos de perfil unificados a partir de informações de audiência.

**Para analisar dados Web em informações de cativação**

1. Na página **Admin de ambiente**, ative o comutador **Partilhar dados de informações de audiência com informações de cativação** e, em seguida, selecione **Seguinte**.

    :::image type="content" source="media/integrate4.png" alt-text="Selecionar funcionalidades.":::

1. Selecione os atributos dos perfis unificados que se tornarão dimensões em informações de cativação. (Nem todos os atributos são dimensões úteis. Por exemplo, não é provável que precise de **Nome próprio** ou **Apelido** como um atributo para análise dos eventos do seu site.)

    :::image type="content" source="media/integrate5.png" alt-text="Organizar dimensões.":::

   >[!NOTE]
   > Todos os atributos de perfil de informações de audiência que representam identificadores (como **ID** e **ID alternativo**) são filtrados dos atributos disponíveis e tornam-se dimensões em informações de cativação.

1. Quando terminar de selecionar atributos, selecione **Seguinte**.
1. Adicione utilizadores que possam ver as dimensões e segmentos de perfil de informações de audiência em informações de cativação.

    :::image type="content" source="media/integrate6.png" alt-text="Gerir acesso aos dados dos clientes.":::

   > [!IMPORTANT]
   > Se não adicionar explicitamente utilizadores neste passo, os dados serão ocultados dos utilizadores em informações de cativação.

1. Reveja a sua seleção e selecione **Concluir**.

    :::image type="content" source="media/integrate7.png" alt-text="Rever as definições de dados do cliente.":::

## <a name="export-refined-events-to-audience-insights"></a>Exportar eventos refinados para as informações de audiência

Depois de criar uma ligação entre ambientes, pode exportar eventos refinados das informações de cativação para as informações de audiência e ingeri-los como uma nova origem de dados. 

Para obter mais informações, vá a [Integrar dados Web de informações de cativação com informações de audiência](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]

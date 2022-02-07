---
title: Exportar dados Customer Insights para o Dynamics 365 Marketing
description: Aprenda a configurar a ligação e exportar para o Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
---

# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Utilizar segmentos no Dynamics 365 Marketing (pré-visualização)



Utilize os [segmentos](segments.md) para gerar campanhas e contactar grupos específicos de clientes com Dynamics 365 Marketing. Para mais informações, consulte [Usar segmentos do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Se estiver a utilizar as novas capacidades do Dynamics 365 Marketing para orquestração do percurso do cliente em tempo real numa organização do Dataverse, não precisa de criar uma exportação padrão para o Dynamics 365 Marketing. Contactos e segmentos de informações de audiência estão disponíveis diretamente no Dynamics 365 Marketing após a ligação ao Marketing e ao Customer Insights. Antes de eliminar as exportações existentes, reveja a documentação sobre [como conectar informações de audiência e a orquestração do percurso do cliente do Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Pré-requisito para uma ligação

- Os registos de contacto têm de estar presentes no Dynamics 365 Marketing antes de poder exportar um segmento do Customer Insights para o Marketing. Leia mais sobre como ingerir contactos no [Dynamics 365 Marketing utilizando o Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > A exportação de segmentos a partir de informações da audiência para o Marketing não criarão novos registos de contacto nas instâncias do Marketing. Os registos de contacto do Marketing têm de ser ingeridos nas informações da audiência e utilizados como origem de dados. Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.

## <a name="set-up-connection-to-marketing"></a>Configure a ligação para o Marketing

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Dynamics 365 Marketing** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o URL do Marketing da sua organização no campo **Endereço do servidor**.

1. Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Marketing.

1. Mapear o campo de ID de Contacto na entidade Cliente para o ID de Contacto do Dynamics 365.

1. Selecione **Guardar** para concluir a ligação. 

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Dynamics 365 Marketing. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Escolher um ou mais segmentos.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]

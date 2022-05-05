---
title: Exportar dados Customer Insights para o Dynamics 365 Sales
description: Aprenda a configurar a ligação e exportar para o Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 987690283090ec83ca75f50bf8f3cd8da9295887
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646840"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Utilizar segmentos no Dynamics 365 Sales (pré-visualização)



Utilize os dados dos seus clientes para criar listas de marketing, dar seguimento a fluxos de trabalho e enviar promoções com o Dynamics 365 Sales.

## <a name="known-limitations"></a>Limitações conhecidas

- As exportações para o Dynamics 365 Sales estão limitadas a 100.000 membros por segmento.
- As exportações de segmentos para o Dynamics 365 Sales podem demorar até 3 horas para serem concluídas. 

## <a name="prerequisite-for-connection"></a>Pré-requisito para a ligação

1. Os registos de contacto têm de estar presentes no Dynamics 365 Sales antes de poder exportar um segmento do Customer Insights para o Sales. Obtenha mais informações sobre como ingerir os contactos a partir do [Dynamics 365 Sales através do Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > A exportação de segmentos do Customer Insights para o Sales não criará novos registos de contactos nas instâncias do Sales. Os registos de contacto do Sales têm de ser ingeridos no Customer Insights e utilizados como uma origem de dados. Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.

## <a name="set-up-the-connection-to-sales"></a>Configure a ligação para o Sales

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Dynamics 365 Sales** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o URL do Sales da sua organização no campo **Endereço do servidor**.

1. Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Sales.

1. Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.

1. Selecione **Guardar** para concluir a ligação. 

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Dynamics 365 Sales. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Escolher um ou mais segmentos.

1. Selecione **Guardar**

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
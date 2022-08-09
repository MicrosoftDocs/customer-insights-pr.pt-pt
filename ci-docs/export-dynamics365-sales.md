---
title: Exportar segmentos para o Dynamics 365 Sales (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195995"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportar segmentos para o Dynamics 365 Sales (pré-visualização)

Utilize os dados dos seus clientes para criar listas de marketing, dar seguimento a fluxos de trabalho e enviar promoções com o Dynamics 365 Sales.

## <a name="prerequisites"></a>Pré-requisitos

Os registos de contacto têm de estar presentes no Dynamics 365 Sales antes de poder exportar um segmento do Customer Insights para o Sales. Obtenha mais informações sobre como ingerir os contactos a partir do [Dynamics 365 Sales através do Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > A exportação de segmentos do Customer Insights para o Sales não criará novos registos de contactos nas instâncias do Sales. Os registos de contacto do Sales têm de ser ingeridos no Customer Insights e utilizados como uma origem de dados. Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.

## <a name="known-limitations"></a>Limitações conhecidas

As exportações para o Dynamics 365 Sales estão limitadas a 100.000 por segmento, o que pode demorar até 3 horas a concluir.

## <a name="set-up-connection-to-sales"></a>Configurar ligação ao Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Dynamics 365 Sales**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o URL do Sales da sua organização no campo **Endereço do servidor**.

1. Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Sales.

1. Mapear um campo de ID de cliente para o ID de contacto Dynamics 365.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Dynamics 365 Sales. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Selecione o campo ID de Contacto na entidade Cliente que corresponde ao ID de Contacto do Dynamics 365.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

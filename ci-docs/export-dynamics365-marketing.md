---
title: Exportar segmentos para o Dynamics 365 Marketing (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196638"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Exportar segmentos para o Dynamics 365 Marketing (pré-visualização)

Utilize os [segmentos](segments.md) para gerar campanhas e contactar grupos específicos de clientes com o [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Se estiver a utilizar as novas capacidades do Dynamics 365 Marketing para orquestração do percurso do cliente em tempo real numa organização do Dataverse, não precisa de criar uma exportação padrão para o Dynamics 365 Marketing. Os contactos e segmentos do Customer Insights estão disponíveis diretamente no Dynamics 365 Marketing depois de ligar o Marketing e o Customer Insights. Antes de eliminar exportações existentes, reveja a documentação em [como ligar a orquestração do percurso do cliente do Customer Insights e Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Pré-requisito

Os registos de contacto têm de estar presentes no Dynamics 365 Marketing antes de poder exportar um segmento do Customer Insights para o Marketing. Leia mais sobre como ingerir contactos no [Dynamics 365 Marketing utilizando o Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> A exportação de segmentos do Customer Insights para o Marketing não criará novos registos de contactos nas instâncias do Marketing. Os registos de contacto do Marketing têm de ser ingeridos no Customer Insights e utilizados como uma origem de dados. Também precisam de ser incluídos na entidade unificada do Cliente para mapear IDs de cliente para contactar IDs antes que os segmentos possam ser exportados.

## <a name="set-up-connection-to-marketing"></a>Configure a ligação para o Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Dynamics 365 Marketing**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o URL do Marketing da sua organização no campo **Endereço do servidor**.

1. Na secção **Conta de administrador do servidor**, selecione **Iniciar sessão** e selecione uma conta do Dynamics 365 Marketing.

1. Mapear o campo de ID de Contacto na entidade Cliente para o ID de Contacto do Dynamics 365.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Dynamics 365 Marketing. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Selecione o campo ID de Contacto na entidade Cliente que corresponde ao ID de Contacto do Dynamics 365.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

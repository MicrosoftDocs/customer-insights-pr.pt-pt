---
title: Exportar dados do Customer Insights para o Braze
description: Saiba como configurar a ligação e exportar para o Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646678"
---
# <a name="export-segment-lists-to-braze-preview"></a>Exportar listas de segmentos para o Braze (pré-visualização)

Exporte segmentos do unified customer profiles para o Braze e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta Braze](https://www.braze.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) no Customer Insights.
-   Unified customer profiles nos segmentos exportados contém um campo que representa um endereço de e-mail e um ID de cliente do Braze. 

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação para o Braze está limitada a segmentos.
- A exportação de até 1 milhão de perfis de clientes para o Braze pode levar até 40 minutos para ficar concluída. 
- O número de perfis de clientes que pode exportar para o Braze está dependente e limitado no seu contrato com o Braze.

## <a name="set-up-connection-to-braze"></a>Configure a ligação ao Braze

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Braze** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça a sua [chave de API do Braze](https://www.braze.com/docs/api/basics/) para continuar a iniciar sessão. 

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Braze.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação na secção Braze. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.  

3. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente, no campo "ID do Cliente", selecione o campo que representa o ID Braze do cliente. É necessário exportar segmentos para o Braze. Os segmentos no Braze serão criados com o mesmo nome de segmento que no Dynamics 365 Customer Insights. Pode escolher campos adicionais, opcionais para corresponder dados. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados ao Braze, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá estes dados após a sua instrução, mas é responsável por assegurar que o Braze cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

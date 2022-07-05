---
title: Exportar segmentos para o Braze (pré-visualização)
description: Saiba como configurar a ligação e exportar para o Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081491"
---
# <a name="export-segments-to-braze-preview"></a>Exportar segmentos para o Braze (pré-visualização)

Exporte segmentos do unified customer profiles para o Braze e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta Braze](https://www.braze.com/) e credenciais de administrador correspondentes.
- Os [segmentos no Bronze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Segmentos configurados](segments.md) no Customer Insights.
- Unified customer profiles nos segmentos exportados contém um campo que representa um endereço de e-mail e um ID de cliente do Braze.

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

1. No campo **Ligação para a exportação**, escolha uma ligação na secção Braze. Se não visualizar esta secção, não há ligações deste tipo disponíveis.  

1. Adicionar um **Nome a apresentar** à exportação.

1. Adicionar o identificador de API do segmento Braze para o qual pretende exportar no campo **Identificador de API do Segmento Braze**. Pode encontrar o identificador nos detalhes do segmento na plataforma Braze.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. No campo **ID do cliente**, selecione o campo que representa o ID Braze do cliente. É necessário exportar segmentos para o Braze. Opcionalmente, pode escolher mais campos.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados ao Braze, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá estes dados após a sua instrução, mas é responsável por assegurar que o Braze cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

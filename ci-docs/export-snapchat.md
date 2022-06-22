---
title: Exportar dados do Customer Insights para o Snapchat
description: Aprenda a configurar a ligação e exportar para o Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947290"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segmentos para o Snapchat (pré-visualização)

Exporte segmentos de perfis de clientes unificados para o Snapchat e utilize-os para publicidade. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta Snapchat Business](https://business.snapchat.com/), uma [conta Snapchat Ads](https://ads.snapchat.com/) e credenciais de administrador correspondentes. Tem, pelo menos, de ser membro de uma Conta de Organização e de um Gestor de Dados de uma Conta de Publicidade específica. 
-   Tem, pelo menos, uma audiência no Gestor de Audiências do Snapchat do tipo SAM (Correspondência de Audiências de Encaixe). 
-   Tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação para o Snapchat limita-se a segmentos.
- A exportação de até 1 milhão de perfis de clientes para o Snapchat pode levar até 15 minutos para ficar concluída. 

## <a name="set-up-connection-to-snapchat"></a>Configurar ligação ao Snapchat

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Snapchat** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Snapchat.

1. Selecione **Autenticar com o Snapchat** e forneça as suas credenciais de admin para o Snapchat. 

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Snapchat. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o [**Segmento do Snapchat/ID da Audiência**](https://businesshelp.snapchat.com/s/article/custom-audiences). O ID da audiência pode ser encontrado no URL depois de selecionar a audiência no Gestor de Audiências do Snapchat. 

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. É obrigatório exportar segmentos para o Snapchat.

1. Selecione os segmentos que quer exportar. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Snapchat, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que o Snapchat cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

---
title: Exportar segmentos para o Microsoft Advertising (pré-visualização)
description: Aprenda a configurar a ligação e exportar para para o Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca37159ec6473ad5c331a0ce1aa8424d277529ff
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081551"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segmentos para o Microsoft Advertising (pré-visualização)

Exporte segmentos do Customer Insights para o Microsoft Advertising para criar audiências de Correspondência de Clientes. Utilize estas audiências para as suas campanhas publicitárias.

## <a name="prerequisites"></a>Pré-requisitos

-   Uma [conta do Microsoft Advertising](https://ads.microsoft.com/) e credenciais correspondentes de administrador.
-   Aceitou os termos de utilização de Correspondência de Clientes. 
-   [Segmentos configurados](segments.md) no Customer Insights.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo com um endereço de e-mail.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 500.000 perfis de clientes por exportação para o Microsoft Advertising.
- A exportação para o Microsoft Advertising limita-se a segmentos.
- A exportação de até 500.000 perfis de clientes para o Microsoft Advertising pode levar até 10 minutos para ficar concluída. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Configure a ligação ao Microsoft Advertising

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Microsoft Advertising** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. A predefinição é administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Microsoft Advertising.

1. Selecione **Autenticar com o Microsoft Advertising** e forneça as suas credenciais de admin para o Microsoft Advertising.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Microsoft Advertising. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Selecione os segmentos a exportar. As audiências de Correspondência de Clientes no Microsoft Advertising são automaticamente criadas com o nome dos segmentos selecionados para exportação. Cada segmento resultará num audiência de Correspondência de Clientes separada. 

1. Introduza o seu **ID de Cliente e ID da Conta do Microsoft Advertising**. Pode encontrar o ID de Cliente (`cid`) e o ID da Conta (`aid`) nos parâmetros do URL quando estiver registado no Microsoft Advertising.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo com o endereço de e-mail de um cliente. É obrigatório exportar segmentos para o Microsoft Advertising.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Microsoft Advertising, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que o Microsoft Advertising cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para parar a utilização desta funcionalidade.

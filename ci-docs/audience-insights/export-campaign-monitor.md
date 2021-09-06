---
title: Exportar dados do Customer Insights para a Campaign Monitor
description: Aprenda a configurar a ligação e exportar para a Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d2cc3ec944faa1d77ffb44e8abb422d753c5625d0ccef75cbb7efb14cb7c3741
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031901"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segmentos para o Monitor de Campanha (pré-visualização)

Exporte segmentos de perfis de clientes unificados para a Campaign Monitor e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta da Campaign Monitor](https://www.campaignmonitor.com/) e credenciais correspondentes de administrador.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 1 milhão de perfis por exportação para a Campaign Monitor.
- A exportação para a Campaign Monitor limita-se a segmentos.
- Exportar até 1 milhão de perfis para a Campaign Monitor pode levar até 20 minutos a ser concluído. 
- O número de perfis que pode exportar para a Campaign Monitor dependente e está limitado no seu contrato com a Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar ligação aa Campaign Monitor

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Campaign Monitor** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação à Campaign Monitor.

1. Selecione **Autenticar com a Campaign Monitor** e forneça as suas credenciais de admin para a Campaign Monitor.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Campaign Monitor. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o seu [**ID da Lista da Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Gerar a chave de API](https://www.campaignmonitor.com/api/getting-started/) a partir de **Definições de Conta** na Campaign Monitor primeiro para ver o ID da lista de API.  

3. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. É obrigatório exportar segmentos para a Campaign Monitor.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a Campaign Monitor, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que a Campaign Monitor cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

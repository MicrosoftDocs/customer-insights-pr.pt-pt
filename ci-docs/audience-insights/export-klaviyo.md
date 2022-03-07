---
title: Exportar dados do Customer Insights para o Klaviyo
description: Aprenda a configurar a ligação e a exportar para o Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 027aee70d9fdab0a92d7fd99209a6ac2ca3cc361
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225482"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Exportar listas de segmentos para o Klaviyo (pré-visualização)

Exporte segmentos de perfis de clientes unificados para o Klaviyo e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta Klaviyo](https://www.klaviyo.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 100.000 perfis de clientes por exportação para o Klaviyo.
- A exportação para Klaviyo está limitada a segmentos.
- A exportação de até 1 milhão de perfis de clientes para o Klaviyo pode levar até 20 minutos para ficar concluída. 
- O número de perfis de clientes que pode exportar para o Klaviyo está dependente e limitado no seu contrato com o Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Configurar a ligação para o Klaviyo

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Klaviyo** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça a sua [chave de API Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) para continuar a iniciar sessão. 

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação para o Klaviyo.

1. Selecione **Autenticar com Klaviyo** e forneça as suas credenciais de admin para Klaviyo.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação à exportação**, escolha uma ligação a partir da secção Klaviyo. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o [**ID de Lista Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. É obrigatório para exportar segmentos para Klaviyo.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Klaviyo, permite a transferência de dados para fora do limite de conformidade para o Dynamics 365 Customer Insights , incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados conforme as suas instruções, mas você é responsável por garantir que o Klaviyo cumpre quaisquer obrigações de privacidade ou de segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

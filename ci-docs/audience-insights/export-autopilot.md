---
title: Exportar dados do Customer Insights para o Autopilot
description: Aprenda a configurar a ligação e exportar para o Autopilot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7a7a67a52fcf39da8d50bd95817d25470fc90b6f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227680"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportar segmentos para o Autopilot (pré-visualização)

Exportar segmentos de perfis unificados de clientes para o Autopilot e utilizá-los para marketing de e-mail no Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta do Autopilot](https://www.autopilothq.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 100.000 perfis de clientes no total para o Autopilot.
- A exportação para o Autopilot está limitada a segmentos.
- A exportação de até 100.000 perfis de clientes para o Autopilot pode levar até algumas horas para ficar concluída. 
- O número de perfis de clientes que pode exportar para o Autopilot está dependente e limitado no seu contrato com o Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Configure a ligação para o Autopilot

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Autopilot** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a sua [chave de API do Autopilot](https://autopilot.docs.apiary.io/#).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Autopilot.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Autopilot. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. Repita os mesmos passos para outros campos opcionais, tais como **Nome próprio**, **Apelido**.

1. Selecione os segmentos que quer exportar. **Recomendamos que não exporte mais de 100.000 perfis de clientes no total** para o Autopilot. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Autopilot, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados a seu pedido, mas você é responsável por garantir que o Autopilot cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

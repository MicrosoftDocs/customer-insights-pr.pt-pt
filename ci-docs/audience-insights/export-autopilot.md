---
title: Exportar dados do Customer Insights para o Autopilot
description: Aprenda a configurar a ligação e exportar para o Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9ada8a6f4e4546990a1360567b400033050119c4c4c9a3df1af8fcaab75e157
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032039"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportar segmentos para o Autopilot (pré-visualização)

Exportar segmentos de perfis unificados de clientes para o Autopilot e utilizá-los para marketing de e-mail no Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta do Autopilot](https://www.autopilothq.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 100.000 perfis no total para o Autopilot.
- A exportação para o Autopilot está limitada a segmentos.
- Exportar até 100.000 perfis para o Autopilot pode demorar até algumas horas para ser concluído. 
- O número de perfis que pode exportar para o Autopilot é dependente e limitado no seu contrato com o Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Configure a ligação para o Autopilot

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Autopilot** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

3. Introduza a sua [chave de API do Autopilot](https://autopilot.docs.apiary.io/#).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Autopilot.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Autopilot. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

3. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. Repita os mesmos passos para outros campos opcionais, tais como **Nome próprio**, **Apelido**.

1. Selecione os segmentos que quer exportar. **Recomendamos que não exporte mais de 100.000 perfis de clientes no total** para o Autopilot. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Autopilot, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados a seu pedido, mas você é responsável por garantir que o Autopilot cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

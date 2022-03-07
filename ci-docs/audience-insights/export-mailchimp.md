---
title: Exportar dados Customer Insights para a Mailchimp
description: Aprenda a configurar a ligação e exportar para o Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f7a33f2eddb6b625ddb8663b97103de75beab44c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226860"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportar segmentos para o Mailchimp (pré-visualização)

Exportar segmentos de perfis unificados de clientes para Mailchimp para criar boletins informativos e campanhas de correio eletrónico.

## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

-   Tem uma [conta Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.
-   Existem audiências na Mailchimp e os IDs correspondentes. Para mais informações, consulte [audiências da Mailchimp](https://mailchimp.com/help/create-audience/).
-   Tem [segmentos configurados](segments.md)
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de clientes por exportação para o Mailchimp.
- A exportação para a Mailchimp é limitada a segmentos.
- A exportação de segmentos com 1 milhão de perfis de clientes pode levar até três horas. 
- O número de perfis de clientes que pode exportar para o Mailchimp está dependente e limitado no seu contrato com o Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Configurar ligação ao Mailchimp

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Mailchimp** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Mailchimp.

1. Selecione **Autenticar com a Mailchimp** e forneça as suas credenciais da Mailchimp.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação. 

## <a name="configure-the-connector"></a>Configurar o conector

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados**> **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Mailchimp. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o seu **[ID da audiência do Mailchimp](https://mailchimp.com/help/find-audience-id/)**

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. 

1. Opcionalmente, pode exportar **Nome próprio** e **Apelido** para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para a Mailchimp.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à Mailchimp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Mailchimp cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

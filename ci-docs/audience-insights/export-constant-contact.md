---
title: Exportar dados do Customer Insights para a Constant Contact
description: Aprenda a configurar a ligação e exportar para a Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124287"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportar segmentos para o Constant Contact (pré-visualização)

Exporte segmentos de perfis de clientes unificados para a Constant Contact e utilize-os para atividades de marketing. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta da Constant Contact](https://www.constantcontact.com/account-home) e credenciais correspondentes de administrador.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 1 milhão de perfis por exportação para a Constant Contact.
- A exportação para a Constant Contact limita-se a segmentos.
- Exportar até 1 milhão de perfis para a Constant Contact pode levar até 1 hora a ser concluído. 
- O número de perfis que pode exportar para a Constant Contact dependente e está limitado no seu contrato com a Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Configurar uma ligação à Constant Contact

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Constant Contact** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação à Constant Contact.

1. Selecione **Autenticar com o AdRoll** e forneça as suas credenciais de admin para a Constant Contact. 

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Constant Contact. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o seu [**ID da Lista da Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Abra uma lista na Constant Contact para encontrar o ID da lista no URL.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. É obrigatório exportar segmentos para a Constant Contact.

1. Opcionalmente, pode exportar o nome próprio e o apelido como campos adicionais para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a Constant Contact, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que a Constant Contact cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

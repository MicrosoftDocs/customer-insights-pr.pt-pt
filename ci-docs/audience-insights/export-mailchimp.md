---
title: Exportar dados Customer Insights para a Mailchimp
description: Saiba como configurar a ligação a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598215"
---
# <a name="connector-for-mailchimp-preview"></a>Ligação para Mailchimp (pré-visualização)

Exportar segmentos de perfis unificados de clientes para Mailchimp para criar boletins informativos e campanhas de correio eletrónico.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.
-   Existem audiências na Mailchimp e os IDs correspondentes. Para mais informações, consulte [audiências da Mailchimp](https://mailchimp.com/help/create-audience/).
-   Tem [segmentos configurados](segments.md)
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="connect-to-mailchimp"></a>Ligar ao Mailchimp

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Em **Mailchimp**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Introduza a sua **[ID de audiência da Mailchimp](https://mailchimp.com/help/find-audience-id/)** e selecione **Ligar** para iniciar a ligação à Mailchimp.

1. Selecione **Autenticar com a Mailchimp** e forneça as suas credenciais da Mailchimp.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Exportar captura de ecrã para ligação a Mailchimp":::

1. Selecione **Seguinte** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. 

1. Opcionalmente, pode exportar o **nome próprio** e o **apelido** como campos adicionais para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para a Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selecionar campos e segmentos a exportar para Mailchimp":::

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab). Na Mailchimp, pode agora encontrar os seus segmentos nas [audiências da Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportar para a Mailchimp.
- A exportação para a Mailchimp é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode demorar até três horas devido a limitações do lado do fornecedor. 
- O número de perfis que pode exportar para a Mailchimp está dependente e limitado ao seu contrato com a Mailchimp.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à Mailchimp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Mailchimp cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
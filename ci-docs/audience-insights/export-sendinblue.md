---
title: Exportar dados do Customer Insights para a Sendinblue
description: Aprenda a configurar a ligação e a exportar para a Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314658"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportar segmentos para a Sendinblue (pré-visualização)

Exporte segmentos de perfis de clientes unificados para gerar campanhas, fornecer marketing por e-mail e utilizar grupos de clientes específicos com a Sendinblue.

## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

-   Tem uma [conta Sendinblue](https://www.sendinblue.com/) e credenciais de administrador correspondentes.
-   Existem listas existentes na Sendinblue e nos IDs correspondentes.
-   Tem [segmentos configurados](segments.md).
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportação para a Sendinblue.
- A exportação para Sendinblue está limitada a segmentos.
- Exportar segmentos com um total de 1 milhão de perfis pode demorar até 90 minutos. 
- O número de perfis que pode exportar para a Sendinblue está dependente e limitado no seu contrato com a Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Configurar ligação à Sendinblue

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Sendinblue** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a **[chave de API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados** e selecione **Ligar** para inicializar a ligação à Sendinblue.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação à exportação**, escolha uma ligação a partir da secção Sendinblue. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o **ID de lista Sendinblue** 

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. 

1. Opcionalmente, pode exportar **Nome próprio**, **Apelido** e **Telefone** para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a Sendinblue, permite a transferência de dados para fora do limite de conformidade para o Dynamics 365 Customer Insights , incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados conforme as suas instruções, mas você é responsável por garantir que a Sendinblue cumpre quaisquer obrigações de privacidade ou de segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

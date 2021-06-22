---
title: Exportar dados Customer Insights para a DotDigital
description: Aprenda a configurar a ligação e exportar para a DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124425"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segmentos para a DotDigital (pré-visualização)

Exportar segmentos de perfis unificados de clientes para a DotDigital e utilizá-los em campanhas, marketing por e-mail, e construir segmentos de clientes com a DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta DotDigital](https://dotdigital.com/) e as correspondentes credenciais de administrador.
-   Existem livros de endereços na DotDigital e os IDs correspondentes. A ID pode ser encontrada no URL ao selecionar e abrir um livro de endereços. Para mais informações, ver [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportar para a DotDigital.
- A exportação para a DotDigital é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 3 horas devido a limitações do lado do fornecedor. 
- O número de perfis que pode exportar para a DotDigital está dependente e limitado ao seu contrato com a DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Configurar ligação à DotDigital

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **DotDigital** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o seu **nome de utilizador e a palavra-passe DotDigital**.

1. Introduza a sua **[ID do livro de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para iniciar a ligação a DotDigital.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação. 

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção DotDigital. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.


1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. Repita os mesmos passos para outros campos opcionais, tais como **nome próprio**, **nome próprio**, **nome completo**, **género**, e **código postal**.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para a DotDigital.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 
 
Na DotDigital, pode agora encontrar os seus segmentos nos [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à DotDigital, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a DotDigital cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

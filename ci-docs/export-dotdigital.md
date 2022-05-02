---
title: Exportar dados Customer Insights para a DotDigital
description: Aprenda a configurar a ligação e exportar para a DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f63a0f5f5f93e96681a88fd758381c012a404f43
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646490"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segmentos para a DotDigital (pré-visualização)

Exportar segmentos de perfis unificados de clientes para a DotDigital e utilizá-los em campanhas, marketing por e-mail, e construir segmentos de clientes com a DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta DotDigital](https://dotdigital.com/) e criou um [utilizador da API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Precisará de utilizar as credenciais de utilizador da API para criar uma ligação
-   Existem livros de endereços na DotDigital e os IDs correspondentes. A ID pode ser encontrada no URL ao selecionar e abrir um livro de endereços. Para mais informações, ver [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de clientes por exportação para o DotDigital.
- A exportação para a DotDigital é limitada a segmentos.
- Os segmentos de exportação com um total de 1 milhão de perfis de clientes podem levar até 3 horas devido a limitações do lado do fornecedor. 
- O número de perfis de clientes que pode exportar para o DotDigital está dependente e limitado no seu contrato com o DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Configurar ligação à DotDigital

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **DotDigital** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o seu **nome de utilizador e a palavra-passe da API do DotDigital**. 

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


1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. Repita os mesmos passos para outros campos opcionais, tais como **nome próprio**, **nome próprio**, **nome completo**, **género**, e **código postal**.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para a DotDigital.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 
 
Na DotDigital, pode agora encontrar os seus segmentos nos [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à DotDigital, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a DotDigital cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]

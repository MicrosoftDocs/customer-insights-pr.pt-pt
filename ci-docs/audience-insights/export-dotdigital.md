---
title: Exportar dados Customer Insights para a DotDigital
description: Saiba como configurar a ligação a DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598031"
---
# <a name="connector-for-dotdigital-preview"></a>Ligação para DotDigital (pré-visualização)

Exportar segmentos de perfis unificados de clientes para a DotDigital e utilizá-los em campanhas, marketing por e-mail, e construir segmentos de clientes com a DotDigital. 

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta DotDigital](https://dotdigital.com/) e as correspondentes credenciais de administrador.
-   Existem livros de endereços na DotDigital e os IDs correspondentes. A ID pode ser encontrada no URL ao selecionar e abrir um livro de endereços. Para mais informações, ver [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="connect-to-dotdigital"></a>Ligar a DotDigital

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Em **DotDigital**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Painel de configuração para exportação DotDigital.":::

1. Introduza o seu **nome de utilizador e a palavra-passe DotDigital**.

1. Introduza a sua **[ID do livro de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para iniciar a ligação a DotDigital.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Seguinte** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. Repita os mesmos passos para outros campos opcionais, tais como **nome próprio**, **nome próprio**, **nome completo**, **género**, e **código postal**.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para a DotDigital.

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab). Na DotDigital, pode agora encontrar os seus segmentos nos [livros de endereços DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportar para a DotDigital.
- A exportação para a DotDigital é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 3 horas devido a limitações do lado do fornecedor. 
- O número de perfis que pode exportar para a DotDigital está dependente e limitado ao seu contrato com a DotDigital.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à DotDigital, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a DotDigital cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
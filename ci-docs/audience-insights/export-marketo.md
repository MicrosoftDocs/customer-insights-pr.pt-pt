---
title: Exportar dados Customer Insights para a Marketo
description: Saiba como configurar a ligação a Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597985"
---
# <a name="connector-for-marketo-preview"></a>Ligação para Marketo (pré-visualização)

Exportar segmentos de perfis unificados de clientes para gerar campanhas, fornecer marketing por e-mail e utilizar grupos específicos de clientes com Marketo.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.
-   Existem listas na Marketo e os IDs correspondentes. Para mais informações, consulte [listas da Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Tem [segmentos configurados](segments.md).
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="connect-to-marketo"></a>Ligar a Marketo

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Em **Marketo**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.

1. Introduza a sua **[ID de cliente da Marketo, segredo do cliente e nome do ponto final REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Introduza a sua **[Id da lista Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados** e selecione **Ligar** para iniciar a ligação a Marketo.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Exportar captura de ecrã para ligação a Marketo":::

1. Selecione **Seguinte** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. 

1. Opcionalmente, pode exportar o **nome próprio**, **apelido**, **cidade**, **estado**, e **país/região**  como campos adicionais para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para a Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Selecionar campos e segmentos a exportar para Marketo":::

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab). Na Marketo, pode agora encontrar os seus segmentos nas [listas da Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportar para a Marketo.
- A exportação para a Marketo é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 3 horas. 
- O número de perfis que pode exportar para a Marketo está dependente e limitado ao seu contrato com a Marketo.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à Marketo, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Marketo cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
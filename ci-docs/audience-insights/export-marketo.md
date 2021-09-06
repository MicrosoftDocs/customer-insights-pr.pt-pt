---
title: Exportar dados Customer Insights para a Marketo
description: Aprenda a configurar a ligação e exportar para a Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0d5eaa769973c861d89287bba0ed29509ab2efc653bdd8e177cc49b3560c698e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033507"
---
# <a name="export-segments-to-marketo-preview"></a>Exportar segmentos para a Marketo (pré-visualização)

Exportar segmentos de perfis unificados de clientes para gerar campanhas, fornecer marketing por e-mail e utilizar grupos específicos de clientes com Marketo.

## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

-   Tem uma [conta Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.
-   Existem listas na Marketo e os IDs correspondentes. Para mais informações, consulte [listas da Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Tem [segmentos configurados](segments.md).
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportar para a Marketo.
- A exportação para a Marketo é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode demorar até 3 horas. 
- O número de perfis que pode exportar para a Marketo está dependente e limitado ao seu contrato com a Marketo.

## <a name="set-up-connection-to-marketo"></a>Configure a ligação para a Marketo

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Marketo** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a sua **[ID de cliente da Marketo, segredo do cliente e nome do ponto final REST](https://developers.marketo.com/rest-api/authentication/)**. O Nome do Anfitrião do Ponto Final REST é apenas o nome de anfitrião, sem `https://`. Exemplo: `xyz-abc-123.mktorest.com`. 

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados** e selecione **Ligar** para iniciar a ligação a Marketo.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Marketo. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o seu **[ID da lista Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. O ID da lista é um valor puramente numérico. Por exemplo, se o seu ID da lista de Marketo for ST12345A7, remova o caráter antes e depois dos algarismos e introduza `12345`. 

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. 

1. Opcionalmente, pode exportar **Nome próprio**, **Apelido**, **Cidade**, **Estado** e **País/Região** para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione os segmentos que quer exportar. Pode exportar até 1 milhão de perfis de clientes no total para a Marketo.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). Na Marketo, pode agora encontrar os seus segmentos nas [listas da Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à Marketo, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Marketo cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

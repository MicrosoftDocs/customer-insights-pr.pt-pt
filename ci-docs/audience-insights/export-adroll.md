---
title: Exportar dados do Customer Insights para o AdRoll
description: Aprenda a configurar a ligação e exportar para o AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e48f67ec21bb9b883dd30544ccf4dcfbf487acb1abaf0a0557764bc3d955e41a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032085"
---
# <a name="export-segments-to-adroll-preview"></a>Exportar segmentos para o AdRoll (pré-visualização)

Exportar segmentos de perfis de clientes unificados para o AdRoll e usá-los para publicidade. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta do AdRoll](https://www.adroll.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 250.000 perfis de cada vez para o AdRoll.
- Não pode exportar segmentos com menos de 100 perfis para o AdRoll. 
- A exportação para o AdRoll está limitada a segmentos.
- Exportar até 250.000 perfis para o AdRoll pode demorar até 10 minutos para ser concluído. 
- O número de perfis que pode exportar para o AdRoll está dependente do seu contrato com o AdRoll.

## <a name="set-up-connection-to-adroll"></a>Configure a ligação para o AdRoll

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **AdRoll** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao AdRoll.

1. Selecione **Autenticar com o AdRoll** e forneça as suas credenciais de administrador para o AdRoll. 

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção AdRoll. Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.

1. Introduza o seu **ID do Anunciante do AdRoll**. Para obter mais informações, consulte [Perfis de Anunciante do AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. É necessário exportar segmentos para o AdRoll.

1. Selecione os segmentos que quer exportar. Selecione um segmento com, pelo menos, 100 membros. Não pode exportar segmentos menores. Além disso, o tamanho máximo de um segmento para exportar é de 250.000 membros por exportação. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). 

Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o AdRoll, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados a seu pedido, mas o utilizador responsável por garantir que o AdRoll cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.
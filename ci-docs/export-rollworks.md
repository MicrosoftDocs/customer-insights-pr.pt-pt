---
title: Exportar segmentos para a RollWorks (pré-visualização)
description: Aprenda a configurar a ligação e exportar para a RollWorks.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 83c3f2437b9822d29d1d2f99ead96815b1b0881a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055182"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportar segmentos para a RollWorks (pré-visualização)

Exporte segmentos de perfis de clientes unificados para a RollWorks e utilize-os para publicidade. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta da RollWorks](https://www.rollworks.com/) e credenciais correspondentes de administrador.
-   Tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 250.000 perfis de clientes por exportação para a RollWorks.
- Não pode exportar segmentos com menos de 100 perfis de clientes para a RollWorks. 
- A exportação para a RollWorks limita-se a segmentos.
- A exportação de até 250.000 perfis de clientes para a RollWorks pode levar até 10 minutos para ficar concluída. 
- O número de perfis de clientes que pode exportar para a RollWorks está dependente e limitado no seu contrato com a RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Configurar ligação à RollWorks

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **RollWorks** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação à RollWorks.

1. Selecione **Autenticar com a RollWorks** e forneça as suas credenciais de admin para a RollWorks.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção RollWorks. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o seu **ID de Anunciante da RollWorks** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. É obrigatório exportar segmentos para a RollWorks.

1. Selecione os segmentos que quer exportar. Selecione um segmento com, pelo menos, 100 membros. Não pode exportar segmentos menores. Além disso, o tamanho máximo de um segmento para exportar é de 250.000 membros por exportação. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a RollWorks, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que a RollWorks cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

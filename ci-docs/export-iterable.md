---
title: Exportar segmentos para o Iterable (pré-visualização)
description: Saiba como configurar a ligação e exportar para o Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 98d5aeab6b0e932d291213053d509ec72da82e47
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052249"
---
# <a name="export-segments-to-iterable-preview"></a>Exportar segmentos para o Iterable (pré-visualização)

Exporte segmentos do unified customer profiles para o Iterable e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta Iterable](https://iterable.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação para o Iterable está limitada a segmentos.
- A exportação de até 1 milhão de perfis de clientes para o Iterable pode levar até 30 minutos para ficar concluída. 
- O número de perfis de clientes que pode exportar para o Iterable está dependente e limitado no seu contrato com o Iterable.

## <a name="set-up-connection-to-iterable"></a>Configure a ligação ao Iterable

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Iterable** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça a sua [chave de API do Iterable](https://support.iterable.com/hc/en-us/articles/360043464871) para continuar a iniciar sessão. 

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Iterable.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação na secção Iterable. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

3. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. É necessário exportar segmentos para o Iterable. A lista criada no Iterable receberá exatamente o mesmo nome que o nome do seu segmento no Dynamics 365 Customer Insights.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Iterable, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá estes dados após a sua instrução, mas é responsável por assegurar que o Iterable cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

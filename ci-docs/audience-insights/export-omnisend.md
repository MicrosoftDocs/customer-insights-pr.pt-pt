---
title: Exportar dados do Customer Insights para o Omnisend
description: Aprenda a configurar a ligação e exportar para o Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 15fc6fc2426ad3958268e5bcc200b8eb2b0fd13a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226780"
---
# <a name="export-segments-to-omnisend-preview"></a>Exportar segmentos para o Omnisend (pré-visualização)

Exporte segmentos de perfis de clientes unificados para o Omnisend e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta do Omnisend](https://www.omnisend.com/) e credenciais correspondentes de administrador.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 1 milhão de perfis de clientes por exportação para o Omnisend e isso pode levar até 4 horas para ficar concluído.
- A exportação para o Omnisend limita-se a segmentos.
- O número de perfis de clientes que pode exportar para o Omnisend depende do seu contrato com o Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Configurar ligação ao Omnisend

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Omnisend** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a sua [chave de API do Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao Omnisend.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Omnisend. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. É obrigatório exportar segmentos para o Omnisend. Opcionalmente, pode exportar Nome próprio, Apelido, Endereço, País/Região, Estado, Cidade e Código Postal para criar e-mails mais personalizados. Selecione **Adicionar atributo** para mapear estes campos.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Omnisend, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com a sua instrução, mas você é responsável por garantir que o Omnisend cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

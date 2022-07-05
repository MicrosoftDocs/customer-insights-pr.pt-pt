---
title: Exportar segmentos para o Criteo (pré-visualização)
description: Saiba como configurar a ligação e exportar para o Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081546"
---
# <a name="export-segments-to-criteo-preview"></a>Exportar segmentos para o Criteo (pré-visualização)

Exporte segmentos de perfis de cliente unificados para gerar campanhas, fornecer marketing por e-mail e utilizar grupos de clientes específicos com o Criteo.

## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

-   Tem uma [conta Criteo Dynamics Retargeting](https://www.criteo.com/login/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md).
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de clientes por exportação para o Criteo.
- A exportação para o Criteo está limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis de clientes pode levar até 30 minutos. 
- O número de perfis de clientes que pode exportar para o Criteo está dependente e limitado no seu contrato com o Criteo.

## <a name="set-up-connection-to-criteo"></a>Configure a ligação ao Criteo

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Criteo** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Aceito** para confirmar a **Privacidade e conformidade de dados** e selecione **Ligar** para inicializar a ligação ao Criteo.

1. Selecione **Autenticar com o Criteo** e forneça o nome de utilizador e as credenciais de administrador para o Criteo. 

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação na secção Criteo. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si. 

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. 

1. Opcionalmente, pode exportar o **ID do Anunciante** e o **Nome**

1. Selecione os segmentos que quer exportar. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados ao Criteo, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá estes dados após a sua instrução, mas é responsável por assegurar que o Criteo cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](includes/footer-banner.md)]

---
title: Exportar dados do Customer Insights para a ActiveCampaign
description: Aprenda a configurar a ligação e a exportar para a ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4fbdd5a51a3df35d31ad072eef64d20ee967d7ee
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618167"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportar segmentos para a ActiveCampaign (pré-visualização)

Exporte segmentos de perfis de clientes unificados para a ActiveCampaign e utilize-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta ActiveCampaign](https://www.activecampaign.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo com um endereço de e-mail.

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 1 milhão de perfis de clientes por exportação para o ActiveCampaign e isso pode levar até 90 minutos para ficar concluído.
- A exportação para ActiveCampaign está limitada a segmentos.
- O número de perfis de clientes que pode exportar para o ActiveCampaign depende do seu contrato com o ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Configure a ligação para a ActiveCampaign

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **ActiveCampaign** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a [chave de API ActiveCampaign e o Nome do Anfitrião de Ponto Final REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). O Nome do Anfitrião do Ponto Final REST é apenas o nome de anfitrião, sem https://. 

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação para a ActiveCampaign.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar uma exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação à exportação**, escolha uma ligação a partir da secção ActiveCampaign. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Introduza o [**ID de Lista ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. É obrigatório para exportar segmentos para ActiveCampaign. Opcionalmente, pode exportar Nome próprio, Apelido e Telefone para criar e-mails mais personalizados. Selecione Adicionar atributo para mapear estes campos.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a ActiveCampaign, permite a transferência de dados para fora do limite de conformidade para o Dynamics 365 Customer Insights , incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados conforme as suas instruções, mas você é responsável por garantir que a ActiveCampaign cumpre quaisquer obrigações de privacidade ou de segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

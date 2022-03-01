---
title: Exportar dados do Customer Insights para o AdRoll
description: Aprenda a configurar a ligação ao AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697088"
---
# <a name="connector-for-adroll-preview"></a>Conector para o AdRoll (pré-visualização)

Exportar segmentos de perfis de clientes unificados para o AdRoll e usá-los para publicidade. 

## <a name="prerequisites"></a>Pré-requisitos

-   Tem uma [conta do AdRoll](https://www.adroll.com/) e credenciais de administrador correspondentes.
-   Tem [segmentos configurados](segments.md) nos insights da audiência.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="connect-to-adroll"></a>Ligar à AdRoll

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Sob **AdRoll**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Painel de configuração para a ligação ao AdRoll.":::

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao AdRoll.

1. Selecione **Autenticar com o AdRoll** e forneça as suas credenciais de administrador para o AdRoll. 

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Introduza o seu **ID de anunciante do AdRoll** [AdRoll para publicidade](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Selecione **Seguinte** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo no seu perfil unificado de cliente que representa o endereço de correio eletrónico de um cliente. É necessário exportar segmentos para o AdRoll.

1. Selecione os segmentos que quer exportar. Selecione um segmento com, pelo menos, 100 membros. Não pode exportar segmentos menores. Além disso, o tamanho máximo de um segmento para exportar é de 250.000 membros por exportação. 

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitações conhecidas

- Pode exportar até 250.000 perfis por exportação para o AdRoll.
- Não pode exportar segmentos com menos de 100 perfis para o AdRoll. 
- A exportação para o AdRoll está limitada a segmentos.
- Exportar até 250.000 perfis para o AdRoll pode demorar até 10 minutos para ser concluído. 
- O número de perfis que pode exportar para o AdRoll é dependente e limitado no seu contrato com o AdRoll.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o AdRoll, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados a seu pedido, mas o utilizador responsável por garantir que o AdRoll cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

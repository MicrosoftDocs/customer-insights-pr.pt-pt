---
title: Melhoramento com o melhoramento de terceiros da HERE Technologies
description: Informação geral sobre o enriquecimento de terceiros HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: be0ac9fa29ce1569d06e4e539e95824c0a3ada4dcf49802c2b574e9d91730630
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032588"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquecimento de perfis de clientes com HERE Technologies (pré-visualização)

A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização. Com os serviços de melhoramento de dados da HERE Technologies, pode construir uma compreensão mais precisa da localização dos seus clientes com normalização de endereços, extração de latitude e longitude, e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o enriquecimento com a HERE Technologies, devem ser cumpridos os seguintes pré-requisitos:

- Tem de ter uma subscrição ativa da HERE Technologies. Para obter uma subscrição, pode [inscreva-se aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacte a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente. [Saiba mais sobre o enriquecimento da localização da HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Uma [ligação](connections.md) à HERE está disponível *ou* tem permissões de [administrador](permissions.md#administrator) e chave de API da HERE Technologies.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento**. 

1. Selecione **Enriquecer os meus dados** no mosaico da HERE Technologies e selecione **Começar**.

   > [!div class="mx-imgBorder"]
   > ![Mosaico HERE Technologies.](media/HERE-tile.png "Mosaico HERE Technologies")

1. Selecione uma [ligação](connections.md) na lista pendente. Contacte um administrador se não houver nenhuma ligação disponível. Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação**. Escolha **HERE Technologies** da lista pendente. 

1. Selecione **Ligar à HERE Technologies** para confirmar a seleção da ligação.

1.  Selecione **Seguinte** e escolha o **Conjunto de dados de cliente** que pretende enriquecer com dados de localização da HERE Technologies. Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. Escolha se deseja mapear campos para o endereço primário e/ou secundário. Pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis de ambos os endereços separadamente. Por exemplo, se houver um endereço residencial e de negócios. Selecione **Seguinte**.

1. Defina que campos dos seus perfis unificados devem ser utilizados para procurar dados de localização correspondentes da HERE Technologies. Os campos **Rua 1** e **Código Postal** são necessários para o endereço primário e/ou secundário selecionado. Para uma maior precisão de correspondência, podem ser acrescentados mais campos.

   > [!div class="mx-imgBorder"]
   > ![Página de configuração de melhoramento da HERE Technologies.](media/enrichment-HERE-configuration.png "Página de configuração de melhoramento da HERE Technologies")

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento. 

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar a ligação para a HERE Technologies 

Tens de ser um administrador para configurar ligações. Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico da HERE Technologies.

1. Introduza um nome para a ligação na caixa **Nome a Apresentar**.

1. Forneça uma chave de API válida da HERE Technologies.

1. Reveja e forneça o seu consentimento para a **Privacidade e conformidade dos dados** selecionando **Concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Guardar**.

   > [!div class="mx-imgBorder"]
   > ![Página de configuração de ligação à HERE Technologies.](media/enrichment-HERE-connection.png "Página de configuração de ligação à HERE Technologies")

## <a name="enrichment-results"></a>Resultados do enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando. Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos seus dados de cliente e dos tempos de resposta API da HERE Technologies.

Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

## <a name="next-steps"></a>Passos seguintes

Desenvolva a partir dos seus dados de clientes melhorados. Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a HERE Technologies cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

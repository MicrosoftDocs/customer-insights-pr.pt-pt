---
title: Enriquecimento com o enriquecimento de terceiros HERE Technologies
description: Informação geral sobre o enriquecimento de terceiros HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597755"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquecimento de perfis de clientes com HERE Technologies (pré-visualização)

A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização. Com os serviços de melhoramento de dados da HERE Technologies, pode construir uma compreensão mais precisa da localização dos seus clientes com normalização de endereços, extração de latitude e longitude, e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o enriquecimento com a HERE Technologies, devem ser cumpridos os seguintes pré-requisitos:

- Tem de ter uma subscrição ativa da HERE Technologies. Para obter uma subscrição, pode [inscreva-se aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacte a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente. [Saiba mais sobre o enriquecimento da localização da HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Tem a chave API da HERE Technologies.

- Tem permissões de [Administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuração

1. Aceda a **Dados** > **Enriquecimento**.

1. Selecione **Melhorar os meus dados** no mosaico HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Mosaico HERE Technologies](media/HERE-tile.png "Mosaico HERE Technologies")

1. Insira uma **chave API da HERE Technologies** ativa. Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**. 

1. Confirmar ambas as entradas, selecionando **Ligar a HERE**.

1.  Selecione **Adicionar dados** e escolha **Conjunto de dados do cliente** que pretende melhorar com os dados de localização da HERE Technologies. Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. Escolha se deseja mapear campos para o endereço primário e/ou secundário. Pode especificar um mapeamento de campo para ambos os endereços (por exemplo, um endereço de casa e um endereço comercial) e melhorar os perfis para ambos os endereços separadamente. Selecione **Seguinte**.

1. Defina que campos dos seus perfis unificados devem ser utilizados para procurar dados de localização correspondentes da HERE Technologies. Os campos **Rua 1** e **Código Postal** são necessários para o endereço primário e/ou secundário selecionado. Para uma maior precisão de correspondência, podem ser acrescentados mais campos.

   > [!div class="mx-imgBorder"]
   > ![Página de configuração de melhoramento da HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuração de melhoramento da HERE Technologies")

1. Selecione **Aplicar** para completar o mapeamento de campo.

## <a name="enrichment-results"></a>Resultados do enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando. Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos seus dados de cliente e dos tempos de resposta API da HERE Technologies.

Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

## <a name="next-steps"></a>Passos seguintes

Desenvolva a partir dos seus dados de clientes melhorados. Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a HERE Technologies cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
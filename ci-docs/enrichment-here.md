---
title: Melhorar os perfis dos clientes com HERE Technologies (pré-visualização)
description: Informação geral sobre o enriquecimento de terceiros HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237872"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Melhorar os perfis dos clientes com HERE Technologies (pré-visualização)

A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização. Os serviços de melhoramento de dados da HERE Technologies melhoram a precisão das informações de localização sobre os seus clientes. Fornece normalização de endereço, extração de latitude e longitude, entre outros.

## <a name="prerequisites"></a>Pré-requisitos

- Uma subscrição ativa da HERE Technologies. Para obter uma subscrição, [inscreva-se aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacte a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente. [Saiba mais sobre o enriquecimento da localização da HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Uma [ligação](connections.md) HERE é [configurada](#configure-the-connection-for-here-technologies) por um administrador.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar a ligação para a HERE Technologies

Tem de ser um [administrador](permissions.md#admin) no Customer Insights e ter uma chave de API da HERE Technologies ativa.

1. Selecione **Adicionar ligação** ao configurar um enriquecimento ou vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico da HERE Technologies.

1. Introduza um nome para a ligação e uma chave de API da HERE Technologies válida.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Guardar**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Página de configuração de ligação à HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Melhorar os meus dados** no mosaico **Localização** da HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Mosaico HERE Technologies.":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione a ligação. Contacte um administrador se não houver nenhuma ligação disponível.

1. Selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar com os dados da HERE Technologies. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

1. Defina o tipo de campos dos seus perfis unificados a utilizar para correspondência: o endereço primário e/ou secundário. Pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis de ambos os endereços separadamente. Por exemplo, para um endereço doméstico e um endereço empresarial. Selecione **Seguinte**.

1. Mapeie os seus campos para os dados a partir da HERE Technologies. Os campos **Rua 1** e **Código Postal** são necessários para o endereço primário e/ou secundário selecionado. Para uma maior precisão de correspondência, adicione mais campos.

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o melhoramento e o **Nome da entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

## <a name="view-enrichment-results"></a>Ver resultados de melhoramento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes melhorados por campo** proporciona uma desagregação da cobertura de cada campo melhorado.

## <a name="next-steps"></a>Próximos passos

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

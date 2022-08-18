---
title: Melhorar perfis de clientes com dados de localização da Azure Maps (pré-visualização)
description: Informações gerais sobre o melhoramento de propriedade do Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238056"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Melhorar perfis de clientes com dados de localização da Azure Maps (pré-visualização)

O Azure Maps fornece dados e serviços baseados na localização para proporcionar experiências baseadas em dados geoespaciais com inteligência de localização incorporada. Os serviços de melhoramento de dados do Azure Maps melhoram a precisão das informações de localização sobre os seus clientes. Traz capacidades como a normalização do endereços e a extração de latitude e de longitude para o Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

- Uma subscrição ativa do Azure Maps. Para obter uma subscrição [inscreva-se ou obtenha um versão de avaliação gratuita](https://azure.microsoft.com/services/azure-maps/).

- Uma [ligação](connections.md) do Azure Maps é [configurada](#configure-the-connection-for-azure-maps) por um administrador.

## <a name="configure-the-connection-for-azure-maps"></a>Configurar a ligação ao Azure Maps

Tem de ser um [administrador](permissions.md#admin) no Customer Insights e ter uma chave de API do Azure Maps ativa.

1. Selecione **Adicionar ligação** ao configurar um melhoramento ou aceda a **Admin** > **Ligações** e selecione **Configurar** no mosaico do Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Página de configuração de ligação ao Azure Maps.":::

1. Introduza um nome para a ligação e uma chave de API do Azure Maps válida.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Guardar**.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Melhorar os meus dados** no mosaico **Localização** do Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Mosaico do Azure Maps.":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione a ligação. Contacte um administrador se não houver nenhuma ligação disponível.

1. Selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar com os dados da Microsoft. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

1. Defina o tipo de campos dos seus perfis unificados a utilizar para correspondência: o endereço primário e/ou secundário. Pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis de ambos os endereços separadamente. Por exemplo, para um endereço doméstico e um endereço empresarial. Selecione **Seguinte**.

1. Mapeie os campos para o dados de localização a partir do Azure Maps. Os campos **Rua 1** e **Código Postal** são necessários para o endereço primário e/ou secundário selecionado. Para maior precisão de correspondência, adicione mais campos.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapeamento de atributos do Azure Maps.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Reveja as **Definições Avançadas** que oferecem máxima flexibilidade para processar casos de utilização avançada. No entanto, os seguintes valores predefinidos, normalmente, não necessitam de ser alterados.

   - **Tipo de endereços**: obtém a melhor correspondência de endereços mesmo que esteja incompleto. Para obter apenas endereços completos&mdash;por exemplo, endereços que incluem o número da casa&mdash;limpe todas as caixas de verificação, exceto **Endereços de Ponto**.
   - **Idioma**: os endereços são obtidos no idioma com base na região do endereço. Para aplicar um idioma de endereço padronizado, selecione o idioma do menu pendente. Por exemplo, selecionar **portugues**, obtém **Copenhaga, Dinamarca**, em vez de **København, Danmark**.
   - **Número máximo de resultados**: número de resultados por endereço.

1. Selecione **Seguinte**.

1. Forneça um **Nome** para o melhoramento e o **Nome da entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

## <a name="view-enrichment-results"></a>Ver resultados de melhoramento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes melhorados por campo** proporciona uma desagregação da cobertura de cada campo melhorado.

## <a name="next-steps"></a>Próximos passos

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

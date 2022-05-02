---
title: Melhorar perfis de clientes com dados de localização do Azure Maps
description: Informações gerais sobre o melhoramento de propriedade do Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 6a1c3791076a7dda4531664ca88632f7f1b914e3
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646530"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Melhoramento de perfis de clientes com o Azure Maps (pré-visualização)

O Azure Maps fornece dados e serviços centrados na localização para fornecer experiências baseadas em dados geoespaciais com inteligência de localização incorporada. Os serviços de melhoramento de dados do Azure Maps melhoram a precisão das informações de localização sobre os seus clientes. Traz capacidades como a normalização do endereços e a extração de latitude e de longitude para o Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o melhoramento de dados do Azure Maps, devem ser cumpridos os seguintes pré-requisitos:

- Tem uma subscrição ativa do Azure Maps. Para obter uma subscrição, pode [inscrever-se ou obter uma avaliação gratuita](https://azure.microsoft.com/services/azure-maps/).

- Uma [ligação](connections.md) ao Azure Maps está disponível, *ou* tem permissões de [administrador](permissions.md#admin) e uma chave de API do Azure Maps ativa.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento**. 

1. No mosaico **Localização**, selecione **Melhorar os meus dados**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Mosaico do Azure Maps.":::

1. Selecione uma [ligação](connections.md) na lista pendente. Contacte um administrador se não estiver disponível nenhuma ligação ao Azure Maps. Se for um administrador, pode [configurar a ligação ao Azure Maps](#configure-the-connection-for-azure-maps). 

1. Selecione **Seguinte** para confirmar a seleção.

1. Escolha o **Conjunto de dados de cliente** que pretende melhorar com dados de localização a partir do Azure Maps. Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de clientes unificados ou selecionar uma entidade de segmento para melhorar apenas os perfis de clientes contidos nesse segmento.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Captura de ecrã ao escolher o conjunto de dados do cliente.":::

1. Escolha se deseja mapear campos para o endereço primário e/ou secundário. Pode especificar um mapeamento de campo para ambos os endereços e melhorar os perfis de ambos os endereços separadamente&mdash;por exemplo, para um endereço doméstico e um endereço de negócio. Selecione **Seguinte**.

1. Defina que campos os seus perfis unificados a utilizar para procurar dados de localização correspondentes a partir do Azure Maps. Os campos **Rua 1** e **Código Postal** são obrigatórios para o endereço primário ou secundário selecionado. Para uma maior precisão de correspondência, pode adicionar mais campos.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Página de configuração de melhoramento do Azure Maps.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Avalie se pretende modificar as **Definições Avançadas**. Estas são fornecidas para dar a máxima flexibilidade para processar casos de utilização avançada, mas os valores predefinidos serão adequados na maioria dos casos:
   - **Tipo de endereços**: o comportamento predefinido é que o melhoramento devolverá a melhor correspondência de endereço, mesmo que esteja incompleta. Para obter apenas endereços completos&mdash;por exemplo, endereços que incluem o número da casa&mdash;limpe todas as caixas de verificação, exceto **Endereços de Ponto**. 
   - **Idioma**: por predefinição, os endereços são obtidos no idioma para a região a que o endereço foi determinado pertencer. Para aplicar um idioma de endereço padronizado, selecione o idioma do menu pendente. Por exemplo, selecionar **Inglês** irá obter **Copenhagen, Denmark** em vez de **København, Danmark**.

1. Forneça um nome para o enriquecimento.

1. Reveja as suas escolhas e, em seguida, selecione **Guardar melhoramento**.

## <a name="configure-the-connection-for-azure-maps"></a>Configurar a ligação ao Azure Maps

Tem de ser um administrador no Customer Insights para configurar ligações. Selecione **Adicionar ligação** ao configurar um melhoramento ou aceda a **Admin** > **Ligações** e selecione **Configurar** no mosaico do Azure Maps.

1. Na caixa **Nome a apresentar**, introduza um nome para a ligação.

1. Forneça uma chave de API do Azure Maps válida.

1. Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Guardar**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Página de configuração de ligação ao Azure Maps.":::

## <a name="enrichment-results"></a>Resultados do enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando. Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados do cliente e dos tempos de resposta da API.

Após o processo de melhoramento ser concluído, pode rever os dados de perfis de clientes recentemente melhorados em **Os meus melhoramentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o Azure Maps, permite a transferência de dados para fora do limite de conformidade para o Dynamics 365 Customer Insights , incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados conforme as suas instruções, mas você é responsável por garantir que o Azure Maps cumpre quaisquer obrigações de privacidade ou de segurança que possa ter. Para mais informações, aceda à [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.

[!INCLUDE [footer-include](includes/footer-banner.md)]

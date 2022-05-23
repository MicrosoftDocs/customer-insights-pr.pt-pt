---
title: Melhoramento de perfis de empresa com Dun & Bradstreet
description: Informações gerais sobre o melhoramento de terceiros da Dun & Bradstreet
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755414"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Melhoramento de perfis de empresa com Dun & Bradstreet (Pré-visualização)

A Dun & Bradstreet fornece dados, análises e informações comerciais para empresas. Permite que os clientes com perfis de clientes unificados para as empresas enriqueçam os seus dados. Os melhoramentos incluem atributos como o número DUNS, o tamanho da empresa, a localização, o setor e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o melhoramento da Dun & Bradstreet, devem ser cumpridos os seguintes pré-requisitos:

- Tem uma licença de cloud da [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) ativa.
- Tem [perfis de clientes unificados](customer-profiles.md) para empresas.
- Uma [ligação](connections.md) Dun & Bradstreet é configurada por um administrador. Pode criar se tiver permissões de [administrador](permissions.md#admin) e as credenciais da Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Configurar o seu projeto Dun & Bradstreet

Enquanto utilizador licenciado da Dun & Bradstreet, pode configurar um projeto no [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Inicie sessão em [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Para obter credenciais, [restaure a sua palavra-passe](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Transfira [o nosso ficheiro de modelo csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) que será utilizado para mapear os campos de Customer Insights para os campos Dun & Bradstreet correspondentes.

1. Carregue o ficheiro no passo **Carregar dados** da experiência de criação de projetos da Dun & Bradstreet.

1. Selecione os pontos horizontais sob a **origem** relevante no recém-criado criado projeto Dun & Bradstreet para ver as opções disponíveis.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de ecrã de pontos num projeto Dun & Bradstreet.":::

1. Escolha **Detalhes de S3**. Armazene essas informações num local seguro. Irá precisar delas para [para configurar a ligação para o melhoramento](#configure-a-connection-for-dun--bradstreet) em Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de ecrã da seleção de informações S3 num projeto Dun & Bradstreet.":::

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento**.

1. Selecione **Melhorar os meus dados** no mosaico Dun & Bradstreet e selecione **Começar**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de ecrã do mosaico Dun & Bradstreet.":::

1. Selecione uma [ligação](connections.md) na lista pendente. Contacte um administrador se não houver nenhuma ligação disponível. Se for um administrador, pode criar uma ligação. Selecione **Adicionar ligação** e escolha **Dun & Bradstreet**.

1. Selecione **Ligar à Dun & Bradstreet** para confirmar a ligação.

1. Selecione **Seguinte** e escolha o **Conjunto de dados do cliente** que pretende melhorar com dados de empresa da Dun & Bradstreet. Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade segmento para melhorar apenas os perfis de cliente unificados nesse segmento.

1. Selecione **Seguinte** e defina que campos dos seus perfis unificados são utilizados para procurar dados de empresa correspondentes da Dun & Bradstreet. São necessários os campos **Número DUNS** ou **Nome da empresa** ou **País/Região**. O campo do país/região suporta [indicativos de duas ou três letras](https://www.iso.org/iso-3166-country-codes.html), nome do país em inglês, nome do país no idioma nativo e prefixo de telefone. Algumas variantes comuns de país/região incluem:

- EUA: Estados Unidos da América, Estados Unidos, EUA, América.
- CA: Canadá.
- GB: Reino Unido, RU, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha.
- AU: Austrália, Comunidade da Austrália.
- FR: França, República Francesa.
- DE: Alemanha, Alemão, Alemanha de Leste, Allemagne, República Federal da Alemanha, República da Alemanha.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Painel de mapeamento de campos da Dun & Bradstreet.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento e selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurar uma ligação à Dun & Bradstreet

Tens de ser um administrador para configurar ligações. Selecione **Adicionar ligação** ao configurar um melhoramento *ou* vá para **Admin** > **Ligações** e selecione **Configurar** no mosaico Dun & Bradstreet.

1. Selecione **Começar**.

1. Introduza um nome para a ligação na caixa **Nome a Apresentar**.

1. Forneça credenciais Dun & Bradstreet válidas e os detalhes do projeto *Região, Caminho da pasta de entrega e Nome da pasta de entrega* da Dun & Bradstreet. Obterá [estas informações](#setting-up-your-dun--bradstreet-project) do projeto Dun & Bradstreet.

1. Reveja e forneça o seu consentimento para a **Privacidade e conformidade dos dados** selecionando **Concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Guardar**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Página de configuração de ligação à Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Resultados do enriquecimento

Depois de atualizar o enriquecimento, pode rever os dados da empresa recentemente enriquecidos em [Os meus enriquecimentos](enrichment-hub.md). Pode encontrar a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados à Dun & Bradstreet, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá estes dados após a sua instrução, mas fica responsável por assegurar que a Dun & Bradstreet cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.

[!INCLUDE[footer-include](includes/footer-banner.md)]

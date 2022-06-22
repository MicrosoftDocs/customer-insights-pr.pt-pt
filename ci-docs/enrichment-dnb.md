---
title: Melhoramento de perfis de empresa com Dun & Bradstreet
description: Informações gerais sobre o melhoramento de terceiros da Dun & Bradstreet
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953905"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Melhoramento de perfis de empresa com Dun & Bradstreet (Pré-visualização)

A Dun & Bradstreet fornece dados, análises e informações comerciais para empresas. Permite que os clientes com perfis de clientes unificados para as empresas enriqueçam os seus dados. Os melhoramentos incluem atributos como o número DUNS, o tamanho da empresa, a localização, o setor e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

- Uma licença de cloud da [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) ativa.
- [Perfis de cliente unificados](customer-profiles.md) para empresas.
- É configurado um [projeto](#set-up-your-dun--bradstreet-project) da Dun & Bradstreet.
- Uma [ligação](connections.md) Dun & Bradstreet é [configurada](#configure-a-connection-for-dun--bradstreet) por um administrador.

## <a name="set-up-your-dun--bradstreet-project"></a>Configurar o seu projeto Dun & Bradstreet

Enquanto utilizador licenciado da Dun & Bradstreet, pode configurar um projeto no [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Inicie sessão em [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Para obter credenciais, [restaure a sua palavra-passe](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Transfira [o nosso ficheiro de modelo csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) que será utilizado para mapear os campos de Customer Insights para os campos Dun & Bradstreet correspondentes.

1. Carregue o ficheiro no passo **Carregar dados** da experiência de criação de projetos da Dun & Bradstreet.

1. Selecione os pontos horizontais sob a **origem** relevante no recém-criado criado projeto Dun & Bradstreet para ver as opções disponíveis.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de ecrã de pontos num projeto Dun & Bradstreet.":::

1. Escolha **Detalhes de S3**. Armazene essas informações num local seguro. Irá precisar delas para [para configurar a ligação para o melhoramento](#configure-a-connection-for-dun--bradstreet) em Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de ecrã da seleção de informações S3 num projeto Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurar uma ligação à Dun & Bradstreet

Tem de ser [administrador](permissions.md#admin) no Customer Insights e de ter as credenciais da Dun & Bradstreet Connect.

1. Selecione **Adicionar ligação** ao configurar um melhoramento ou vá para **Admin** > **Ligações** e selecione **Configurar** no mosaico Dun & Bradstreet.

1. Introduzir um nome para a ligação.

1. Forneça credenciais Dun & Bradstreet válidas e os detalhes do projeto *Região, Caminho da pasta de entrega e Nome da pasta de entrega* da Dun & Bradstreet. Obterá [estas informações](#set-up-your-dun--bradstreet-project) do projeto Dun & Bradstreet.

1. Reveja e forneça o seu consentimento para a [Privacidade e conformidade dos dados](#data-privacy-and-compliance) selecionando **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Guardar**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Página de configuração de ligação à Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados à Dun & Bradstreet, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá estes dados após a sua instrução, mas fica responsável por assegurar que a Dun & Bradstreet cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.

## <a name="supported-countries-or-regions"></a>Países ou regiões suportados

Atualmente, suportamos as seguintes opções de país/região: Canadá (inglês) ou Estados Unidos (inglês).

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Melhorar os meus dados** no mosaico **Dados da empresa** para Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de ecrã do mosaico Dun & Bradstreet.":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione a ligação e confirme. Contacte um administrador, caso não esteja nenhuma disponível.

1. Selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar com os dados da empresa da Dun & Bradstreet. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

1. Defina que tipos de campos dos seus perfis unificados utilizar para corresponder dados de empresa da Dun & Bradstreet. Pelo menos, um dos campos **Nome e endereço**, **Telefone** ou **E-mail** é obrigatório.

1. Selecione **Seguinte**

1. Mapeie os campos para o dados da empresa a partir da Dun & Bradstreet. São necessários os campos **Número DUNS** ou **Nome da empresa** ou **País/Região**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Painel de mapeamento de campos da Dun & Bradstreet.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o melhoramento e o **Nome da entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

## <a name="enrichment-results"></a>Resultados do enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Próximos passos

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]

---
title: Personalizar as suas experiências com dados sobre utilizadores conhecidos e desconhecidos
description: Incorpore as informações sobre os utilizadores desconhecidos anteriormente quando conhece a sua identidade.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224309"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalizar as suas experiências com dados sobre utilizadores conhecidos e desconhecidos

A gestão de dados de clientes não é um novo desafio, mas está cada vez mais difícil à medida que os utilizadores navegam nas várias ofertas de canais digitais. Um utilizador conhecido (autenticado) num canal torna-se desconhecido (não autenticado) noutro se não tiver sessão iniciada. Frequentemente, o problema é que os utilizadores não autenticados (desconhecidos) não têm um ID comum. Poderia ser utilizado para associar atributos de perfil importantes e gerar perfis de cliente unificados. O Customer Insights ajuda a resolver este problema ao ingerir dados a partir de métodos de monitorização nos sistemas de origem. A consolidação de perfis desconhecidos e conhecidos proporciona às organizações uma vista completa dos perfis atualizados e das respetivas transações históricas, comportamentos e demografia das organizações. Vai um passo ainda mais longe ao fornecer resolução de identidades que lhe permite unificar a atividade dos clientes através de vários canais, incluindo o seu site, a compra na loja, programas de fidelização, entre outros.

## <a name="sample-scenario"></a>Cenário de exemplo

Pensemos numa cadeia de cafés, que tem uma vasta base de clientes que compra café e alimentos em lojas, e faz encomendas online. Muitas vezes, os visitantes online não são autenticados quando navegam nos produtos, tornando-os "utilizadores desconhecidos". É difícil a cadeia de cafés oferecer ofertas e experiências personalizadas se os utilizadores forem desconhecidos. Por outro lado, os clientes podem iniciar sessão nas respetivas contas e tornar-se "utilizadores conhecidos" junto da empresa ao juntarem-se a um sistema de fidelização que, por sua vez, permite experiências mais personalizadas. O Customer Insights pode ajudar a cadeia de cafés a obter informações sobre os utilizadores conhecidos e anteriormente desconhecidos.

Com o Customer Insights, a empresa pode combinar os perfis de cliente com dados de atividade das sessões não autenticadas (desconhecidas) depois de um utilizador iniciar sessão e se tornar conhecido. A cadeia de cafés pode aportar dados de outras origens de dados através de conectores integrados no Customer Insights para intercalar identidades para clientes de vários canais.

## <a name="prerequisites"></a>Pré-requisitos

- Os dados Web são recolhidos e contêm "IDs de visitante" para todos os visitantes.
- Os dados Web contêm "IDs de utilizador autenticados" para os visitantes com sessão iniciada. Estes IDs estão associados ao sistema de fidelização.
- Os dados de eventos de elevado valor, tais como "Vista Produto" e "Finalização da compra", são definidos e incluídos nos dados de origem, juntamente com o carimbo de data/hora do evento e um ID de evento.

A tabela seguinte mostra um exemplo simplificado de como os eventos Web de elevado valor podem ser capturados.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|5|07-23-2022 10:00:00|abc123|--|Vista do produto|
|2|07-23-2022 10:05:00|abc123|707|Início de sessão de fidelização|
|3|07-23-2022 10:10:00|abc123|707|Finalização da Compra|
|4|07-23-2022 10:20:00|xyz789|--|Vista do produto|

## <a name="data-ingestion"></a>Ingestão de dados

Os dados sobre os clientes podem ter origem no Web site como dados de eventos e podem ser armazenados nos seus próprios serviços de análise de dados internos ou de terceiros. Os dados Web contêm utilizadores conhecidos e desconhecidos se o Web site tiver um fluxo de autenticação que se integra com um serviço de autenticação. Por exemplo, um sistema de eCommerce que necessita que os utilizadores forneçam os respectivos detalhes completos para concluírem uma transação de compra. Ou um sistema de fidelização que necessita de autenticação para confirmar um destinatário válido dos descontos de recompensas.

Os dados de eventos no nosso exemplo acima contêm os IDs de perfil distintos dos utilizadores conhecidos e desconhecidos. Nos eventos 1 e 4, os utilizadores são desconhecidos, enquanto nos eventos 2 e 3 o utilizador com o ID abc123 inscreve-se num programa de fidelização.

:::image type="content" source="media/website-data-source.png" alt-text="Origens de dados, incluindo o Web site Contoso.":::

Para mais informações sobre as opções disponíveis para ingestão de dados, consulte [Descrição geral das origens de dados](data-sources.md).

## <a name="data-unification"></a>Unificação de dados

Convergir as identidades desconhecidas com as identidades conhecidas ajuda a permitir a personalização com base nos comportamentos dos utilizadores, independentemente do respectivo estado de perfil (conhecido ou desconhecido). O conteúdo personalizado para todos os utilizadores ajuda os clientes a obter rapidamente os produtos ou serviços mais relevantes em que estão interessados nesse momento.

Uma vez que alguns dos utilizadores nos nossos dados são conhecidos, podemos utilizar o Customer Insights para combinar esses dados com o perfil do utilizador. Para mais informações sobre como unificar os perfis de cliente, consulte [Descrição geral da unificação de dados](data-unification.md).

1. Selecione os campos de origem a partir da entidade de dados Web. Utilize os dados de perfil armazenados nos seus dados Web e selecione os campos que representam IDs com dados demográficos.

   :::image type="content" source="media/website-source-fields.png" alt-text="Campos de origem para a origem de dados Web.":::

1. Adicione regras para intercalar registos duplicados. Para os dados Web, escolha os dados mais preenchidos.

1. Configure as regras e as condições de correspondência. Os dados de eventos de perfis Web neste exemplo serão correspondidos em IDs com os perfis das outras origem de dados que contêm informações dos clientes. Configure as regras de correspondência exatas nos IDs como regras separadas, com cada uma das outras entidades de perfil que tenham uma chave primária ou ID correspondente. No exemplo, os dados do perfil de evento Web são utilizados como a última entidade correspondente, de modo a que os outros dados do perfil seja combinados primeiro.
   1. Não selecionar **Incluir todos os registos** cria perfis unificados para utilizadores conhecidos e inclui os IDs de utilizador desconhecidos correspondentes. É útil nos cenários em que está interessado em ver as atividades comportamentais passadas dos utilizadores conhecidos quando ainda eram desconhecidos.
   1. Selecionar **Incluir todos os dados** cria registos de perfil separados para utilizadores desconhecidos. Os utilizadores desconhecidos obtêm um ID de cliente exclusivo. No futuro, quando um perfil conhecido está associado nos dados do perfil de eventos Web, o percurso do utilizador recém-conhecido também pode ser visualizado e utilizado para personalização com base nos dados comportamentais desconhecidos.

:::image type="content" source="media/website-match-rule.png" alt-text="Regra de correspondência para a entidade de origem de dados do Web site.":::

## <a name="get-insights"></a>Obter informações

Se os perfis de cliente forem criados para os utilizadores desconhecidos e conhecidos, os dados de eventos Web de elevado valor podem ser utilizados como [atividades](activities.md). Estas atividades podem ser utilizadas para criar mais informações. Por exemplo, os clientes que visitaram um Web site há seis meses (quando ainda eram desconhecidos) ou os clientes que não tenham um ID de fidelização nunca concluíram uma finalização de compra.

:::image type="content" source="media/website-known-unknown.png" alt-text="Captura de ecrã da página de cliente com clientes conhecidos e desconhecidos.":::

[Melhore](enrichment-hub.md) os seus dados, crie [medidas](measures.md) e crie [segmentos](segments.md) para aumentar a ativação.

Por exemplo, pode criar segmentos de utilizadores conhecidos que viram alguns produtos mas que nunca finalizaram a compra.

Para mais informações, consulte [Descrição geral dos segmentos](segments.md).

## <a name="activate-insights"></a>Ativar informações

Existem várias formas de exportar os seus dados e tomar medidas com base nas informações subjacentes.

Para mais informações, consulte [Descrição geral das exportações](export-destinations.md).

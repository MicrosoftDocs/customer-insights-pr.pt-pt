---
title: Utilizar perfis unificados no Dynamics 365 Marketing
description: Aprenda a integrar perfis e segmentos unificados com o Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054446"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Utilizar unified customer profiles no Dynamics 365 Marketing

O [Dynamics 365 Marketing](/dynamics365/marketing/overview) eleva as experiências dos clientes, permitindo-lhe orquestrar percursos personalizados em todos os pontos de contacto para fortalecer relações e ganhar fidelidade. A aplicação Dynamics 365 Marketing funciona de forma totalmente integrada com o Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams e outros produtos e permite-lhe tomar decisões mais rápidas e melhores utilizando o poder dos dados e da IA.

Ao ligar dados do Customer Insights ao Marketing, pode:

- Foque-se em perfis e segmentos de clientes do unificados. Isto permite-lhe cativar todos os clientes, independentemente da localização do dados do cliente.
- Conteúdo dinâmico base (como tokens personalizados) em e-mails, SMS e notificações push em medidas, como o estado de fidelização, data de renovação da subscrição, conta principal ou qualquer outra medida que tenha capturado no perfil unificado do Customer Insights.
- Carregue dados do Marketing para o Customer Insights e combine-os com dados de clientes de outras origens.
- Aplique ferramentas de limpeza, melhoramento e correspondência difusa de dados do Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Utilizar perfis avançados de clientes em marketing em tempo real

O marketing em tempo real permite-lhe criar [acionadores personalizados](/dynamics365/marketing/real-time-marketing-custom-triggers) que iniciam o percurso do cliente com base em qualquer ação personalizada. Quanto mais personalizados os dados, mais relevantes e personalizados serão os seus percursos. É isto que torna a combinação do Marketing e do Customer Insights tão poderosa. Pode [unificar dados](data-unification.md) de qualquer origem e, em seguida, utilizá-los para iniciar percursos do cliente hiperpersonalizados.

Saber mais: [Utilizar perfis e segmentos do Customer Insights em marketing em tempo real](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Utilizar segmentos unificados com percursos do cliente de saída

O Customer Insights permite-lhe refinar dados a partir de muitas origens e combiná-los em segmentos de clientes agregados. Ao [ligar o Customer Insights a marketing de saída](export-dynamics365-marketing.md), estes segmentos irão aparecer automaticamente *e* serão automaticamente atualizados no estruturador do percurso do cliente.

Mais informações: [Utilizar segmentos do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Extrair dados do seu próprio Azure Data Lake Storage

Não está limitado ao armazenamento na nuvem se pretender utilizar dados do Customer Insights com Marketing. Se já tiver a sua própria configuração do Azure Data Lake Storage, pode ligar ao Customer Insights e, em seguida, partilhar os dados com a aplicação Marketing, da mesma forma que o faria com uma configuração baseada na cloud.

Mais informações: [Ativar a partilha de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)

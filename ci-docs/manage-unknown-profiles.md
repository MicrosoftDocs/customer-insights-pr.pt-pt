---
title: Gerir perfis desconhecidos com o Customer Insights
description: Trabalhar com perfis de cliente desconhecidos criados e geridos no Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776835"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Gerir perfis desconhecidos com o Customer Insights

Os utilizadores da Internet são, frequentemente, não identificados ou anónimos online. Até os clientes mais leais poderão aparecer como "desconhecidos" se não tiverem sessão iniciada em diferentes dispositivos. Para muitos marcas, utilizadores conhecidos ou autenticados, são a minoria, apesar das expetativas crescentes dos clientes em relação à personalização. Com o futuro de cookies de terceiros em questão, em vez disso, a gestão de preferências de utilizador baseadas em dados proprietários é crucial para obter experiências personalizadas diferenciadas.

A personalização memorável depende de quão bem conhece o seu cliente e o Customer Insights ajudam-no a consegui-lo através da monitorização de todos os clientes.  Não é preciso limitar nem parar a utilização dos dados recolhidos no início do percurso do cliente. O Customer Insights permite-lhe trazer os seus próprios dados para criar um perfil de cliente para utilizadores desconhecidos. Em seguida, poderá utilizar esse perfil para mais ações, apesar das informações de contacto em falta. Importar dados proprietários a partir de origens como sistemas Web, móveis ou CRM para o Customer Insights para enriquecer continuamente os perfis do cliente. À medida que unifica mais interações, [transforme o cliente *desconhecido* num cliente *conhecido*](unknown-to-known.md).

## <a name="sample-scenario"></a>Cenário de Amostra

Assume que um utilizador utiliza o dispositivo móvel para navegar no seu site de comércio eletrónico. O site atribui o visitante "mobile_guest123" como um identificador exclusivo e as pessoas começam a recolher atividades comportamentais com base na atividade online dele. Por exemplo, que páginas visitou, quanto tempo passou nessas páginas ou em que ligações clicou. Não sabe o nome dele, nem o endereço de e-mail, mas esses dados podem ajudar a fornecer informações úteis às marcas sobre este utilizador específico. Por sua vez, pode utilizar essas informações da próxima vez que esse utilizador visitar o site. Consulte o Customer Insights para o "mobile_guest123" para obter a lista de segmentos do utilizador, tais como "orgânico", "clientes móveis de pré-encomenda", "clientes de importância elevada", etc. ou obtenha o perfil para criar experiências Web personalizadas. Também pode exportar os dados para que qualquer sistema de ativação o faça.

## <a name="prerequisites"></a>Pré-requisitos

- Ingerir dados proprietários no Customer Insights
- Cada entidade tem um ID exclusivo que é definido como a chave primária
- Cada entidade com uma chave primária para personalização é unificada
- O sistema de gestão de conteúdos do seu site pode utilizar APIs (para personalização Web com base em comunicação direta com o Customer Insights)

A tabela seguinte mostra um exemplo simplificado de como os eventos Web de elevado valor podem ser capturados.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|5|15-09-2022 9:00:00|abc123|CookieID1|Vista do produto|
|2|18-09-2022 10:05:00|abc123|CookieID1|Vista do produto|
|3|18-09-2022 10:10:00|abc123|CookieID1|Adicionar ao carrinho|
|4|21-09-2022 09:05:00|abc123|CookieID1|Vista do produto|

## <a name="data-ingestion"></a>Ingestão de dados

Para mais informações sobre as opções disponíveis para ingestão de dados, consulte [Descrição geral das origens de dados](data-sources.md).

## <a name="data-unification"></a>Unificação de dados

Para mais informações sobre como unificar os perfis de cliente, consulte [Descrição geral da unificação de dados](data-unification.md).

## <a name="get-insights"></a>Obter informações

[Melhore](enrichment-hub.md) os seus dados, crie [medidas](measures.md) e crie [segmentos](segments.md) para aumentar a ativação.

Por exemplo, pode criar segmentos de utilizadores desconhecidos que navegaram nas mesmas páginas de produto, mas que nunca finalizaram a compra.

## <a name="activation"></a>Ativação

Com os seus dados no Customer Insights e as suas informações preparadas para trabalhar, pode utilizar o Customer Insights para personalização:

1. Utilize a [API OData](apis.md) para obter uma associação de segmentos ou perfil de cliente. Para mais exemplos, consulte [Exemplos de consulta de OData para APIs do Customer Insights](odata-examples.md).

1. [Exporte](export-destinations.md) os seus dados para os sistemas de ativação.

Exemplo: um utilizador desconhecido visita um site várias vezes e visita páginas de produtos com vários modelos sapatos de couro. Com esses dados disponíveis no Customer Insights, pode incluir o utilizador desconhecido no segmento de pessoas que estão interessadas em sapatos de couro. Utilize este segmento para informar a personalização do seu site para visitantes que regressem. Na visita seguinte, o site reconhece o utilizador desconhecido e pode oferecer-lhe um cupão de desconto de 10% em sapatos de couro.

[!INCLUDE [footer-include](includes/footer-banner.md)]

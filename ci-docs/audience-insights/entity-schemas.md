---
title: Esquema de entidades do Customer Insights no Common Data Model
description: Trabalhar com entidades no Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2cf01029ef6b64fe566022d09ce65bca3603189c
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643922"
---
# <a name="entity-schemas-in-common-data-model"></a>Esquema de entidades no Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

O [Common Data Model](https://docs.microsoft.com/common-data-model/) é uma especificação declarativa e uma definição de entidades padrão que representam as atividades e os conceitos frequentemente utilizados em várias aplicações de negócio e produtividade. Este modelo também está a ser alargado para dados de observação e analíticos. O Common Data Model fornece entidades de negócio bem definidas, modulares e expansíveis – tais como Conta, Unidade de Negócio, Incidente, Contacto, Oportunidade Potencial, Oportunidade e Produto – bem como oferece interações com fornecedores, trabalhadores e clientes, tais como atividades e contratos de nível de serviço. Qualquer pessoa pode desenvolver e expandir definições do Common Data Model para capturar ideias adicionais específicas da empresa.

Este modelo de dados partilhados que permite que os integradores de dados e aplicações colaborem mais facilmente fornecendo uma definição unificada dos dados. O Common Data Model inclui um sistema de metadados rico com entidades, relações, hierarquias, características padrão e muito mais. Provém de aplicações do Dynamics 365 e é aberto com origem no GitHub com mais de 260 entidades padrão. Um grande sistema de parceiros internos e externos contribui com conceitos específicos do setor para o Common Data Model.

Vários sistemas e plataformas implementam o Common Data Model hoje em dia, incluindo os fluxos de dados do Power BI e os Serviços de Dados do Azure. Esta já é suportada no Common Data Service, Dynamics 365, Power Apps, Power BI e no futuro Azure Data Services adicionando valor diretamente à [Iniciativa de Dados Abertos](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Esquemas de entidades do Customer Insights

Para estabelecer uma vista de 360 graus do cliente e disponibilizar os modelos do Customer Insights no Common Data Model para extensibilidade, publicámos os seguintes esquemas de entidade:

| Entidade | Descrição |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Uma atividade efetuada por um utilizador com valor de observação para a empresa. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Uma pessoa ou organização que tenha efetuado ou que tem o potencial de participar em atividades de negócio. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definição de KPIs particionados por zero ou mais dimensões (tal como, Utilizadores Ativos Mensais, Gasto Total por Cliente, Custo Médio da Aquisição de Clientes) |
|[Segmento](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Define um grupo de membros com características comuns. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Membros que participam num determinado segmento. |

Para mais informações, consulte a documentação sobre os [Esquemas de entidade no Customer Insights no Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Ver entidades utilizando o Navegador de Entidades do Common Data Model

Pode visualizar entidades no [Navegador de Entidades do Common Data Model](https://microsoft.github.io/CDM/). Selecione o botão **Carregar a partir do GitHub!** e navegue para **foundationCommon** > **crmCommon** > **solutions** > **customerInsights** onde encontrará a lista de entidades do Customer Insights e as respetivas definições.
> [!div class="mx-imgBorder"]
> ![Navegador de Entidades do CDM que mostra a entidade CustomerActivity](media/CDM-entity-navigator.png "Navegador de Entidades do CDM que mostra a entidade CustomerActivity")

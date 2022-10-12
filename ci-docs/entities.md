---
title: Entidades no Customer Insights
description: Ver dados na página Entidades.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610112"
---
# <a name="entities-in-customer-insights"></a>Entidades no Customer Insights

Depois de [configurar as suas origens de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos. As entidades são consideradas conjuntos de dados. Múltiplas capacidades de Dynamics 365 Customer Insights são construídas em torno destas entidades. A sua análise aprofundada poderá ajudar a validar a saída dessas funcionalidades.

À medida que trabalha no Customer Insights a melhorar os seus dados ou a criar segmentos, medidas e atividades, as entidades criadas a partir dessas ações são apresentadas na página **Entidades**.

## <a name="view-a-list-of-entities"></a>Ver uma lista de entidades

Vá para **Dados** > **Entidades** para ver uma lista de entidades. São apresentadas as seguintes informações para cada entidade:

- **Nome**: o nome da entidade de dados. Se for apresentado um símbolo de aviso junto a um nome de entidade, significa que os dados dessa entidade não foram carregados com êxito.
- **Origem**: tipo de origem de dados que ingeriu a entidade.
- **Atualizado**: hora a que a entidade foi atualizada pela última vez.
- **Estado**: detalhes sobre a última atualização da entidade.

## <a name="explore-a-specific-entitys-data"></a>Explorar os dados de uma entidade específica

1. Aceda a **Dados** > **Entidades**.
1. Selecione uma entidade para abrir a página de detalhes.  
1. Explore os diferentes campos e registos incluídos para essa entidade.

- O separador **Atributos** está selecionado por predefinição e mostra os detalhes para a entidade selecionada, tais como nomes de campo, tipos de dados e tipos. A coluna **Tipo** mostra os tipos associados do Common Data Model, que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos utilizadores. Estes tipos são tipos semânticos que podem diferir dos tipos de dados dos atributos. Por exemplo, o campo *Email* abaixo tem um tipo de dados *Cadeia*, mas o seu tipo de Common Data Model (semântico) pode ser *Email*, *EmailAddress* ou *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabela de campos.":::

   > [!NOTE]
   > Esta página mostra apenas uma amostra dos dados da sua entidade. Para ver o conjunto de dados completo, vá para a página **Origens de dados**, selecione uma entidade, selecione **Editar** e, em seguida, veja os dados desta entidade com o editor do Power Query, tal como explicado em [Origens de dados](data-sources.md).

   Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características de dados importantes, tais como os valores nulos, os valores em falta, os valores exclusivos, as contagens e as distribuições, conforme aplicável aos seus dados. Selecione o ícone de gráfico para ver o resumo dos dados.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabela de resumo de dados.":::

- O separador **Dados** mostra os detalhes sobre os registos individuais da entidade. Os detalhes listados dependem do tipo de dados da entidade.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Selecione uma entidade.":::

- O separador **Relatórios** (disponível para algumas entidades) permite visualizar os seus dados ao criar um relatório, que inclui as seguintes colunas:

  - **Nome do relatório**: o nome do relatório.
  - **Criado por**: nome da pessoa que criou a entidade.
  - **Criado**: data e hora da criação da entidade.
  - **Editado por**: nome da pessoa que modificou a entidade.
  - **Editado**: data e hora da modificação da entidade.

[!INCLUDE [footer-include](includes/footer-banner.md)]

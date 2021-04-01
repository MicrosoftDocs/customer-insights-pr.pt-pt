---
title: Entidades e conjuntos de dados
description: Ver dados na página Entidades.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596421"
---
# <a name="entities-in-audience-insights"></a>Entidades em insight da audiência

Depois de [configurar as suas origens de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos. As entidades são consideradas conjuntos de dados. Múltiplas capacidades de Dynamics 365 Customer Insights são construídas em torno destas entidades. A sua análise aprofundada poderá ajudar a validar a saída dessas funcionalidades.

A página **Entidades** lista as entidades e inclui várias colunas:

- **Nome**: o nome da sua entidade de dados. Se for apresentado um símbolo de aviso junto a um nome de entidade, significa que os dados dessa entidade não foram carregados com êxito.
- **Origem**: o tipo de origem de dados que ingeriu a entidade
- **Criado por**: nome da pessoa que criou a entidade
- **Criado**: data e hora da criação da entidade
- **Atualizado por**: nome da pessoa que atualizou a entidade
- **Última atualização**: data e hora da última atualização da entidade
- **Última atualização**: data e hora da última atualização de dados

## <a name="exploring-a-specific-entitys-data"></a>Explorar os dados de uma entidade específica

Selecione uma entidade para explorar os diferentes campos e registos incluídos nessa entidade.

> [!div class="mx-imgBorder"]
> ![Selecionar uma entidade](media/data-manager-entities-data.png "Selecionar uma entidade")

- O separador **Dados** é selecionado por predefinição e mostra uma tabela a listar os detalhes sobre os registos individuais da entidade.

> [!div class="mx-imgBorder"]
> ![Tabela de campos](media/data-manager-entities-fields.PNG "Tabela de campos")

- O separador **Campos** mostra uma tabela para rever os detalhes da entidade selecionada, como os nomes dos campos, os tipos de dados e os tipos. A coluna **Tipo** mostra os tipos associados do Common Data Model, que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos utilizadores. Estes são tipos semânticos que podem ser diferentes dos tipos de dados dos atributos. Por exemplo, o campo *E-mail* abaixo tem um tipo de dados *Texto*, mas o respetivo tipo (semântico) de Common Data Model pode ser *E-mail* ou *Endereço de E-mail*.

> [!NOTE]
> Ambas as tabelas mostram apenas um exemplo dos dados da sua entidade. Para ver o conjunto de dados completo, vá para a página **Origens de dados**, selecione uma entidade, selecione **Editar** e, em seguida, veja os dados desta entidade com o editor do Power Query, tal como explicado em [Origens de dados](data-sources.md).

Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características importantes dos dados, tais como os valores nulos, os valores em falta, os valores exclusivos, as contagens e as distribuições, conforme aplicável aos seus dados.

Selecione o ícone de gráfico para ver o resumo dos dados.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumo](media/data-manager-entities-summary.png "Tabela de resumo de dados")

### <a name="next-step"></a>Passo seguinte

Consulte o tópico [Unificar](data-unification.md) para saber mais sobre como *mapear*, *corresponder* e *intercalar* os dados ingeridos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
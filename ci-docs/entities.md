---
title: Entidades e conjuntos de dados
description: Ver dados na página Entidades.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: c1094bc2f6d137087b317ed20d0615289d6f1187
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646948"
---
# <a name="entities-in-customer-insights"></a>Entidades no Customer Insights

Depois de [configurar as suas origens de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos. As entidades são consideradas conjuntos de dados. Múltiplas capacidades de Dynamics 365 Customer Insights são construídas em torno destas entidades. A sua análise aprofundada poderá ajudar a validar a saída dessas funcionalidades.

A página **Entidades** lista as entidades e inclui estas colunas:

- **Nome**: o nome da entidade de dados. Se for apresentado um símbolo de aviso junto a um nome de entidade, significa que os dados dessa entidade não foram carregados com êxito.
- **Origem**: tipo de origem de dados que ingeriu a entidade.
- **Atualizado**: hora a que a entidade foi atualizada pela última vez.
- **Estado**: detalhes sobre a última atualização da entidade.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Explorar os dados de uma entidade específica

1. Aceda a **Dados** > **Entidades**.
1. Na página **Entidades**, selecione uma entidade para abrir a página de detalhes.  
1. Explore os diferentes campos e registos incluídos para essa entidade.

- Por predefinição, o separador **Atributos** está selecionado e mostra uma tabela para obter detalhes para a entidade selecionada, tais como nomes de campo, tipos de dados e tipos. A coluna **Tipo** mostra os tipos associados do Common Data Model, que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos utilizadores. Estes tipos são tipos semânticos que podem diferir dos tipos de dados dos atributos. Por exemplo, o campo *E-mail* abaixo tem um *Texto* tipo de dados, mas o seu tipo de Common Data Model (semântico) pode ser *Email* ou *EmailAddress*.

> [!div class="mx-imgBorder"]
> ![Tabela de campos.](media/data-manager-entities-fields.PNG "Tabela de campos")

> [!NOTE]
> Esta página mostra apenas uma amostra dos dados da sua entidade. Para ver o conjunto de dados completo, vá para a página **Origens de dados**, selecione uma entidade, selecione **Editar** e, em seguida, veja os dados desta entidade com o editor do Power Query, tal como explicado em [Origens de dados](data-sources.md).

Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características importantes dos dados, tais como os valores nulos, os valores em falta, os valores exclusivos, as contagens e as distribuições, conforme aplicável aos seus dados. Selecione o ícone de gráfico para ver o resumo dos dados.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumo.](media/data-manager-entities-summary.png "Tabela de resumo de dados")

- O separador **Dados** mostra uma tabela que lista detalhes sobre registos individuais da entidade. Os detalhes listados dependem do tipo de dados da entidade.

> [!div class="mx-imgBorder"]
> ![Selecione uma entidade.](media/data-manager-entities-data.png "Selecione uma entidade")

- O separador **Relatórios** (disponível para algumas entidades) permite visualizar os seus dados ao criar um relatório, e inclui as seguintes colunas:

  - **Nome do relatório**: o nome do relatório.
  - **Criado por**: nome da pessoa que criou a entidade.
  - **Criado**: data e hora da criação da entidade.
  - **Editado por**: nome da pessoa que modificou a entidade.
  - **Editado**: data e hora da modificação da entidade. 

## <a name="entity-specific-information"></a>Informações específicas de entidade

A secção seguinte fornece informações sobre algumas entidades criadas pelo sistema.

### <a name="corrupted-data-sources"></a>Origens de dados danificadas

Campos de uma origem de dados ingerida podem conter dados danificados. Os registos com campos danificados estão expostos em entidades criadas pelo sistema. Conhecer registos danificados ajuda a identificar que dados rever e atualizar no sistema de origem. Após a próxima atualização da origem de dados, os registos corrigidos são ingeridos para o Customer Insights e transmitidos para processos a jusante. 

Por exemplo, uma coluna de "aniversário" tem o tipo de dados definido como "data". Um registo de cliente tem o seu aniversário introduzido como "01/01/19777". O sistema vai sinalizar este registo como danificado. Alguém pode agora mudar o aniversário no sistema de origem para "1977". Após uma atualização automatizada de origens de dados, o campo tem agora um formato válido e o registo será removido da entidade danificada. 

Aceda a **Dados** > **Entidades** e procure as entidades danificadas na secção **Sistema**. Nomeação de esquema de entidades danificadas: "DataSourceName_EntityName_corrupt". Selecione uma entidade corrompida para identificar todos os campos corrompidos e a razão a nível de registo individual.
> [!div class="mx-imgBorder"]
> ![Razão do corrompimento.](media/corruption-reason.png "Razão do Corrompimento")

O Customer Insights ainda processa registos danificados. No entanto, podem causar problemas ao trabalhar com os dados unificados.

As verificações que se seguem são executadas nos dados ingeridos para expor registos danificados: 

- O valor de um campo não corresponde ao tipo de dados da sua coluna.
- Os campos contêm carateres que fazem com que as colunas não correspondam ao esquema esperado. Por exemplo: aspas mal formatadas, aspas não fechadas ou carateres de nova linha.
- Se existirem as colunas datetime/date/datetimeoffset, o respetivo formato terá de ser especificado no modelo se não seguir o formato ISO padrão.


[!INCLUDE [footer-include](includes/footer-banner.md)]
---
title: Atualização incremental para o Power Query e origens de dados do Azure Data Lake
description: Atualize dados novos e atualizados para origens de dados grandes com base em origens de dados do Power Query ou do Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207151"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Atualização incremental para o Power Query e origens de dados do Azure Data Lake

A atualização incremental para origens de dados baseada no Power Query ou no Azure Data Lake oferece as seguintes vantagens:

- **Atualizações mais rápidas** – apenas os dados alterados são atualizados. Por exemplo, poderá atualizar apenas os últimos cinco dias de um conjunto de dados histórico.
- **Maior fiabilidade** – com atualizações menores, não é necessário manter ligações com sistemas de origem voláteis por tanto tempo, reduzindo o risco de problemas de ligação.
- **Consumo de recursos reduzida** – a atualização de apenas um subconjunto de dados proporciona uma utilização mais eficiente dos recursos informáticos e reduz a pegada ambiental.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configurar a atualização incremental para origens de dados baseadas no Power Query

O Customer Insights permite uma atualização incremental para origens de dados importadas através do Power Query que suportam ingestão incremental. Por exemplo, bases de dados SQL do Azure com campos de data e hora, que indicam quando os registos de dados foram atualizados pela última vez.

1. [Criar uma nova origem de dados baseada no Power Query](connect-power-query.md).

1. Selecione uma origem de dados que suporte a atualização incremental, tal como a [base de dados do Azure SQL](/power-query/connectors/azuresqldatabase).

1. Selecione as entidades ou tabelas a ingerir.

1. Conclua os passos de transformação e selecione **Seguinte**.

1. Na caixa de diálogo **Configurar atualização incremental**, selecione **Configurar** para abrir as **Definições de atualização incremental**. Se selecionar **Ignorar**, a origem de dados irá atualizar todo o conjunto de dados.
   > [!TIP]
   > Também pode aplicar a atualização incremental mais tarde editando uma origem de dados existente.

1. Nas **Definições de atualização incremental**, irá configurar a atualização incremental para todas as entidades que tiver selecionado ao criar a origem de dados.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurar definições de atualização incremental.":::

1. Selecione uma entidade e forneça os seguintes detalhes:

   - **Definir a chave primária**: selecione uma chave primária para a entidade ou tabela.
   - **Definir o campo "última atualização"**: este campo só irá apresentar atributos do tipo data ou hora. Selecione um atributo que indique quando os registos foram atualizados pela última vez. Será usado para identificar os registos que se enquadram no intervalo de tempo de atualização incremental.
   - **Pesquisar atualizações a cada**: especifique o intervalo de tempo pretendido da atualização incremental.

1. Selecione **Guardar** para concluir a criação do origem de dados. A atualização de dados inicial será uma atualização completa. Posteriormente, a atualização de dados incremental acontece conforme configurado no passo anterior.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configurar atualização incremental para origens de dados do Azure Data Lake

O Customer Insights permite a atualização incremental para origens de dados ligadas ao Azure Data Lake Storage. Para utilizar a gestão incremental e atualizar para uma entidade, configure essa entidade ao adicionar a origem de dados do Azure Data Lake ou, mais tarde, quando editar a origem de dados. A pasta de dados da entidade tem de conter as seguintes pastas:

- **FullData**: pasta com ficheiros de dados que contêm registos iniciais
- **IncrementalData**: pasta com pastas de hierarquia de data/hora no formato **aaaa/mm/dd/hh** que contêm as atualizações incrementais. **hh** representa a hora UTC das atualizações e contém as pastas **Upserts** e **Eliminações**. **Upserts** contém ficheiros de dados com atualizações para registos existentes ou registos novos. **Eliminações** contém ficheiros de dados com os registos a remover.

1. Quando adicionar ou editar uma origem de dados, navegue para o painel **Atributos** da entidade.

1. Reveja os atributos. Certifique-se de que um atributo de data criado ou atualizado pela última vez está configurado com um **Formato de dados** de *dateTime* e um **Tipo de semântica** de *Calendar.Date*. Edite o atributo, se necessário, e selecione **Concluído**.

1. No painel **Selecionar Entidades**, edite a entidade. A caixa de verificação **Ingestão incremental** está selecionada.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurar entidades numa origem de dados para atualização incremental.":::

   1. Navegue para a pasta raiz que contém os ficheiros .csv ou .parquet para dados completos, upserts de dados incrementais e eliminações de dados incrementais.
   1. Introdução à extensão para os dados completos e ambos os ficheiros incrementais (\.csv ou \.parquet).
   1. Para os ficheiro .csv, selecione o delimitador de colunas e, se quiser que a primeira linha do ficheiro seja um cabeçalho de coluna.
   1. Selecione **Guardar**.

1. Para **Última atualização**, selecione o atributo de data carimbo de data/hora.

1. Se a **Chave primária** não estiver selecionada, selecione a chave primária. A chave primária é um atributo exclusivo da entidade. Para que um atributo seja uma chave primária válida, não deve incluir valores duplicados, valores em falta ou valores nulos. Os atributos de cadeia, número inteiro e tipo de dados GUID são suportados como chaves primárias.

1. Selecione **Fechar** para guardar e fechar o painel.

1. Continue a adicionar ou a editar a origem de dados.

[!INCLUDE [footer-include](includes/footer-banner.md)]

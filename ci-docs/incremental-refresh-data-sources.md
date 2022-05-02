---
title: Atualização incremental para Power Query baseado em origens de dados
description: Atualizar dados novos e atualizados para grandes origens de dados com base no Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647184"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Atualização incremental para origens de dados baseadas no Power Query

Este artigo aborda a forma de configurar a atualização incremental para origens de dados baseada no Power Query.

A atualização incremental para origens de dados fornece as seguintes vantagens:

- **Atualizações mais rápidas** – apenas os dados alterados são atualizados. Por exemplo, poderá atualizar apenas os últimos cinco dias de um conjunto de dados histórico.
- **Maior fiabilidade** – com atualizações menores, não é necessário manter ligações com sistemas de origem voláteis por tanto tempo, reduzindo o risco de problemas de ligação.
- **Consumo de recursos reduzida** – a atualização de apenas um subconjunto de dados proporciona uma utilização mais eficiente dos recursos informáticos e reduz a pegada ambiental.

## <a name="configure-incremental-refresh"></a>Configurar a atualização incremental

O Customer Insights permite uma atualização incremental para origens de dados importadas através do Power Query que suportam ingestão incremental. Por exemplo, bases de dados SQL do Azure com campos de data e hora, que indicam quando os registos de dados foram atualizados pela última vez.

1. [Criar uma nova origem de dados baseada no Power Query](connect-power-query.md).

1. Forneça um **Nome** para a origem de dados.

1. Selecione uma origem de dados que suporte a atualização incremental, tal como a [base de dados do Azure SQL](/power-query/connectors/azuresqldatabase).

1. Selecione as entidades ou tabelas a ingerir.

1. Conclua os passos de transformação e selecione **Seguinte**.

1. Na caixa de diálogo **Configurar atualização incremental**, selecione **Configurar** para abrir as **Definições de atualização incremental**. Se selecionar **Ignorar**, a origem de dados irá atualizar todo o conjunto de dados.
   > [!TIP]
   > Também pode aplicar a atualização incremental mais tarde editando uma origem de dados existente.

1. Nas **Definições de atualização incremental**, irá configurar a atualização incremental para todas as entidades que tiver selecionado ao criar a origem de dados.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurar entidades numa origem de dados para atualização incremental.":::

1. Selecione uma entidade e forneça os seguintes detalhes:

   - **Definir a chave primária**: selecione uma chave primária para a entidade ou tabela.
   - **Definir o campo "última atualização"**: este campo só irá apresentar atributos do tipo data ou hora. Selecione um atributo que indique quando os registos foram atualizados pela última vez. Será usado para identificar os registos que se enquadram no intervalo de tempo de atualização incremental.
   - **Pesquisar atualizações a cada**: especifique o intervalo de tempo pretendido da atualização incremental.

1. Selecione **Guardar** para concluir a criação do origem de dados. A atualização de dados inicial será uma atualização completa. Posteriormente, a atualização de dados incremental acontece conforme configurado no passo anterior.


[!INCLUDE [footer-include](includes/footer-banner.md)]

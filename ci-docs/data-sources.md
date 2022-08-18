---
title: Descrição geral das origens de dados
description: Saiba como importar ou ingerir dados a partir de várias origens.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245663"
---
# <a name="data-sources-overview"></a>Descrição geral das origens de dados

O Dynamics 365 Customer Insights fornece ligações para recolher dados de um vasto conjunto de origens. A ligação a um origem de dados é frequentemente referida como o processo de *ingestão de dados*. Depois de ingerir os dados, pode [unificar](data-unification.md), gerar informações e ativar os dados para criar experiências personalizadas.

## <a name="add-or-edit-data-sources"></a>Adicionar ou editar origens de dados

É possível anexar ou importar origens de dados para o Customer Insights. As ligações abaixo fornecem instruções sobre como adicionar ou editar origens de dados.

**Anexar uma origem de dados**

Se tiver dados preparados num dos serviços de dados do Azure da Microsoft, o Customer Insights pode ligar-se facilmente à origem de dados sem que tenha de voltar a ingerir os dados. Selecione uma das seguintes opções:
- [Azure Data Lake Storage (ficheiros csv ou parquet numa pasta do Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (bases de dados do Lake)](connect-synapse.md)
- [Data lake do Microsoft Dataverse](connect-dataverse-managed-lake.md)

**Importar e transformar**

Se utilizar origens de dados no local, a Microsoft ou dados de terceiros, importe e transforme os dados utilizando conectores do Power Query.
- [Conectores do Power Query](connect-power-query.md)

## <a name="review-data-sources"></a>Rever origens de dados

Se o ambiente foi configurado para utilizar o armazenamento do Customer Insights e utilizar as origens de dados no local, utilizará os fluxos de dados do Power Platform. Com os fluxos de dados do Power Platform, pode ver as origens de dados partilhadas e as origens de dados geridas por outros. A página **Origens de Dados** lista as origens de dados em três secções:
- **Partilhado**: as origens de dados que podem ser geridas por todos os admins do Customer Insights. Os fluxos de dados do Power Platform, a sua própria conta de armazenamento e anexar a um data lake gerido pelo Dataverse são exemplos de origens de dados partilhadas.
- **Gerido por mim**: fluxos de dados do Power Platform criados e geridos apenas por si. Outros admins do Customer Insights só podem ver estes fluxos de dados, mas não os podem editar, atualizar ou eliminar.
- **Gerido por outros**: fluxos de dados do Power Platform criados por outros admins. Só os pode ver. Enumera o proprietário do fluxo de dados a contactar para qualquer assistência.
> [!NOTE]
> Todas as entidades podem ser vistas e utilizadas por outros utilizadores. Apesar de as origens de dados serem propriedade do utilizador que as criou, as entidades resultantes da ingestão de dados podem ser utilizadas por cada utilizador do Customer Insights.

Se o ambiente não utilizar fluxos de dados do Power Platform, a página **Origens de Dados** contém apenas uma lista de todas as origens de dados. Não são apresentadas quaisquer secções.

## <a name="manage-existing-data-sources"></a>Gerir origens de dados existentes

Aceda a **Dados** > **Origens de Dados** para ver o nome de cada origem de dados ingerida, o respetivo estado e a última vez que os dados foram atualizados para essa origem. Pode ordenar a lista de origens de dados por qualquer coluna ou utilizar a caixa de pesquisa para localizar a origem de dados que pretende gerir.

Selecione uma origem de dados para ver as ações disponíveis.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Origem de dados adicionada.":::

- [**Editar**](#add-or-edit-data-sources) a origem de dados para alterar as respetivas propriedades.
- [**Atualizar**](#refresh-data-sources) a origem de dados para incluir os dados mais recentes.
- [**Melhorar**](data-sources-enrichment.md) a origem de dados antes da unificação.
- **Eliminar** a origem de dados. Uma origem de dados só pode ser eliminada se os dados não forem utilizados em qualquer processamento, tal como unificação, informações ativações ou exportações.

## <a name="refresh-data-sources"></a>Atualizar origens de dados

As origens de dados podem ser atualizadas com agendamento automático ou atualizadas manualmente a pedido. As [origens de dados no local](connect-power-query.md#add-data-from-on-premises-data-sources) atualizam-se nas próprias agendas, que são configuradas durante a ingestão de dados. Para as origens de dados anexadas, a ingestão de dados consome os dados mais recentes disponíveis dessa origem de dados.

Aceda a **Admin** > **Sistema** > [**Agenda**](schedule-refresh.md) para configurar atualizações agendadas pelo sistema das suas origens de dados ingeridas.

Para atualizar uma origem de dados a pedido:

1. Aceda a **Dados** > **Origens de dados**.

1. Selecione os origem de dados que pretende atualizar e selecione **Atualizar**. A origem dos dados é agora ativada para uma atualização manual. Atualizar uma origem de dados irá atualizar tanto o esquema da entidade como os dados para todas as entidades especificadas na origem de dados.

1. Selecione o estado para abrir o painel **Detalhes do progresso** e ver o progresso. Para cancelar a tarefa, selecione **Cancelar tarefa** na parte inferior do painel.

[!INCLUDE [footer-include](includes/footer-banner.md)]

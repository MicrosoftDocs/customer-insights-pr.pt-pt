---
title: Atualizar as definições de unificação
description: Atualizar regras de duplicação, regras de correspondência ou campos unificados nas definições de unificação.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755604"
---
# <a name="update-the-unification-settings"></a>Atualizar as definições de unificação

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Para rever ou alterar quaisquer definições de unificação após a criação de um perfil unificado, execute os seguintes passos.

1. Vá para **Dados** > **Unificar**.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de ecrã da página Unificação de dados após a unificação dos dados.":::

   > [!TIP]
   > O mosaico **Condições de correspondência** só é apresentado se várias entidades tiverem sido selecionadas.

1. Escolha o que pretende atualizar:
   - [Campos de origem](#edit-source-fields) para adicionar entidades ou atributos ou alterar tipos de atributo.
   - [Registos duplicados](#manage-deduplication-rules) para gerir regras de eliminação de duplicados ou unir preferências.
   - [Condições de correspondência](#manage-match-rules) para atualizar regras de correspondência em duas ou mais entidades.
   - [Campos de clientes unificados](#manage-unified-fields) para combinar ou excluir campos. Também pode agrupar perfis relacionados em clusters.

1. Depois de efetuar as alterações, escolha a sua próxima opção:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Captura de ecrã da página Unificar Dados com as opções de União realçadas.":::

   - Para atualizar o unified customer profile (com ou sem dependências), consulte [Executar atualizações para o perfil de cliente](#run-updates-to-the-unified-customer-profile).
   - Para avaliar a qualidade das condições correspondentes sem atualizar o perfil unificado, consulte [Executar condições de correspondência](#run-matching-conditions). A opção **Executar condições de correspondência apenas** não é apresentada para uma única entidade.

## <a name="edit-source-fields"></a>Editar campos de origem

Não é possível remover um atributo ou uma entidade se os atributos já foram unificados.

1. Selecione **Editar** no mosaico **Campos de origem**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de ecrã da página Campos de Origem que mostram o número de chaves primárias, campos mapeados e não mapeados":::

   O número de campos mapeados e não mapeados apresentados.

1. Selecione **Selecionar entidades e campos** para adicionar outros atributos ou entidades. Utilize a pesquisa ou percorra para encontrar e selecionar os seus atributos e entidades de interesse. Selecione **Aplicar**.

1. Opcionalmente, pode alterar a chave primária de uma entidade, os tipos de atributo e ativar ou desativar o **mapeamento Inteligente**. Para mais informações, consulte [Selecionar chave primária e tipo de semântica para atributos](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Selecione **Seguinte** para efetuar alterações às regras de eliminação de duplicados ou selecione **Guardar e fechar** para voltar a [Atualizar as definições de unificação](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Gerir regras de eliminação de duplicados

1. Selecione **Editar** no mosaico **Registos duplicados**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de ecrã da página Registos Duplicados, que mostra o número de registos duplicados" lightbox="media/m3_duplicates_edit.png":::

   O número de registos duplicados encontrados é apresentado em **Duplicados**. A coluna **Eliminação de registos duplicados** mostra as entidades que tinham dados duplicados e a percentagem de dados duplicados.

1. Se adicionou uma entidade enriquecida, selecione **Utilizar entidades enriquecidas**. Para obter mais informações, consulte [Melhoramento para origens de dados](data-sources-enrichment.md).

1. Para gerir regras de eliminação de duplicados, escolha qualquer uma das seguintes opções:
   - **Criar uma nova regra**: Selecione **Adicionar regra** na entidade apropriada. Para obter mais informações, consulte [Definir regras de eliminação de duplicados](remove-duplicates.md#define-deduplication-rules).
   - **Alterar condições de regra**: Selecione a regra e, depois, **Editar**. Alterar campos, adicionar ou remover condições ou adicionar ou remover exceções.
   - **Pré-visualização**: Selecione a regra e, depois, **Pré-visualização** para ver os resultados da última execução desta regra.
   - **Desativar uma regra**: Selecione a regra e, depois, **Desative** para manter uma regra de eliminação de duplicados enquanto a exclui do processo de correspondência.
   - **Duplicar uma regra**: Selecione a regra e, depois, **Duplicar** para criar uma regra semelhante com modificações.
   - **Eliminar uma regra**: Selecione a regra e, depois, **Eliminar**.

1. Para alterar as preferências de união, selecione a entidade. Só pode alterar as preferências se for criada uma regra.
   1. Selecione **Editar preferências de união** e altere o **Registo para manter** opção.
   1. Para alterar as preferências de união em atributos individuais de uma entidade, selecione **Avançadas** e efetue as alterações necessárias.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Captura de ecrã de preferências de união avançadas que mostram o e-mail mais recente e o endereço mais completo":::

   1. Selecionar **Concluído**.

1. Selecione **Seguinte** para efetuar alterações às condições de correspondência ou selecione **Guardar e fechar** para voltar a [Atualizar as definições de unificação](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Gerir regras de correspondência

Pode reconfigurar e aperfeiçoar a maioria dos parâmetros de correspondência. Não pode adicionar ou eliminar entidades. As regras de correspondência não se aplicam a uma única entidade.

1. Selecione **Editar** no mosaico **Condições de correspondência**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de ecrã da página Regras e condições de correspondência com estatísticas." lightbox="media/m3_match_edit.png":::

   A página apresenta a ordem de correspondência e as regras definidas, bem como as seguintes estatísticas:
   - **Registos de origem exclusivos** mostra o número de registos de origem individuais que foram processados na última execução de correspondência.
   - **Registos correspondidos e não correspondidos** destaca quantos registos únicos permanecem após o processamento das regras de correspondência.
   - **Apenas registos correspondidos** mostra o número de correspondências em todos os seus pares de correspondências.

1. Para ver os resultados de todas as regras e a respetivas pontuações, selecione **Ver última execução**. Os resultados são apresentados, incluindo os IDs de contacto alternativos. Pode transferir os resultados.

1. Para ver os resultados e pontuações de uma determinada regra, selecione a regra e, depois, **Pré-visualizar**. Os resultados são apresentados. Pode transferir os resultados.

1. Para ver os resultados de uma determinada condição de uma regra, selecione a regra e, depois, **Editar**. No painel Editar, selecione **Pré-visualizar** na condição. Pode transferir os resultados.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Representação gráfica de dados sem e com correspondências, incluindo uma lista dos dados.":::

1. Se adicionou uma entidade enriquecida, selecione **Utilizar entidades enriquecidas**. Para obter mais informações, consulte [Melhoramento para origens de dados](data-sources-enrichment.md).

1. Para gerir regras, escolha qualquer uma das seguintes opções:
   - **Criar uma nova regra**: Selecione **Adicionar regra** na entidade apropriada. Para mais informações, consulte [Definir regras para pares de correspondência](match-entities.md#define-rules-for-match-pairs).
   - **Altere a ordem das regras** se tiver definido várias regras: arraste e largue as regras pela ordem que pretende. Para obter mais informações, consulte [Especificar a ordem de correspondência](match-entities.md#specify-the-match-order).
   - **Alterar condições de regra**: Selecione a regra e, depois, **Editar**. Alterar campos, adicionar ou remover condições ou adicionar ou remover exceções.
   - **Desativar uma regra**: Selecione a regra e, depois, **Desative** para manter uma regra de correspondência de duplicados enquanto a exclui do processo de correspondência.
   - **Duplicar uma regra**: Selecione a regra e, depois, **Duplicar** para criar uma regra semelhante com modificações.
   - **Eliminar uma regra**: Selecione a regra e, depois, **Eliminar**.

1. Selecione **Seguinte** para efetuar alterações a campos unificados ou selecione **Guardar e fechar** para voltar a [Atualizar as definições de unificação](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Gerir campos unificados

1. Selecione **Editar** no mosaico **Campos de cliente unificados**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de ecrã dos campos de cliente unificados":::

1. Reveja os campos combinados e excluídos e efetue quaisquer alterações necessárias. Adicione ou edite a chave CustomerID ou agrupe perfis em clusters. Para mais informações, consulte [Perfis de cliente unificados](merge-entities.md).

1. Selecione **Seguinte** para rever as definições de unificação e [atualizar o perfil unificado e as dependências](#run-updates-to-the-unified-customer-profile), ou selecione **Guardar e fechar** para voltar a [Atualizar as definições de unificação](#update-the-unification-settings) para efetuar mais alterações.

## <a name="run-matching-conditions"></a>Executar condições de correspondência

1. Na página **Dados** > **Unificar**, selecione **Executar condições de correspondência apenas**.

   Os mosaicos **Duplicar registos** e **Condições de correspondência** mostram **Fila** ou **Atualização**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Quando o processo correspondente estiver concluído, selecione **Editar** no mosaico **Condições de correspondência**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de ecrã recortada das métricas-chave na página Corresponder com números e detalhes.":::

1. Para efetuar alterações, consulte [Gerir regras de eliminação de duplicados](#manage-deduplication-rules) ou [Gerir regras de correspondência](#manage-match-rules).

1. Execute novamente o processo de correspondência ou [execute atualizações ao perfil de cliente](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Executar atualizações para o unified customer profile

1. Na página **Dados** > **Unificar**, selecione:

   - **Unificar perfis de clientes**: Atualiza a entidade unified customer profile sem afetar dependências (tais como enriquecimentos, segmentos ou medidas). Os processos dependentes não são executados, mas serão atualizados conforme [definido na agenda de atualização](system.md#schedule-tab).

   - **Unificar perfis de cliente e dependências**: Atualiza o perfil unificado e todas as dependências. Todos os processos voltam a ser executados automaticamente. Depois de concluídos todos os processos a jusante, o perfil de cliente reflete os dados atualizados.

   Os mosaicos **Duplicar registos**, **Condições de correspondência** e **Campos de cliente unificados** mostram **Fila** ou **Atualização**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

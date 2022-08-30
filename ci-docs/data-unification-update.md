---
title: Atualizar definições de cliente, conta ou unificação de contactos
description: Atualize regras de duplicação, regras de correspondência ou campos unificados nas definições de unificação de clientes ou contas.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304349"
---
# <a name="update-unification-settings"></a>Atualizar definições de unificação

Para rever ou alterar quaisquer definições de unificação após a criação de um perfil unificado, execute os seguintes passos.

1. Vá para **Dados** > **Unificar**.

   Para clientes individuais (B2C), a página **Unificar** apresenta o número de perfis de clientes e mosaicos unificados para cada um dos passos de unificação.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de ecrã da página Unificação de dados após a unificação dos dados." lightbox="media/m3_unified.png":::

   Para contas empresariais (B2C), a página **Unificar** apresenta o número de perfis de contas e mosaicos unificados para cada um dos passos de unificação de contas. Se os contactos foram unificados, são apresentados o número de perfis de contactos e mosaicos unificados para cada um dos passos de unificação de contactos. Escolha o mosaico apropriado por baixo de **Unificar contas** ou **Unificar contactos (pré-visualização)** dependendo da atualização que pretende fazer.

   :::image type="content" source="media/b2b_unified.png" alt-text="Captura de ecrã da página Unificação de dados após a unificação de dados de conta e contactos." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > O mosaico **Condições de correspondência** só é apresentado se várias entidades tiverem sido selecionadas.

1. Escolha o que pretende atualizar:
   - [Campos de origem](#edit-source-fields) para adicionar entidades ou atributos ou alterar tipos de atributo.
   - [Registos duplicados](#manage-deduplication-rules) para gerir regras de eliminação de duplicados ou unir preferências.
   - [Condições de correspondência](#manage-match-rules) para atualizar regras de correspondência em duas ou mais entidades.
   - [Campos de clientes unificados](#manage-unified-fields) para combinar ou excluir campos. Também pode agrupar perfis relacionados em clusters.
   - [Campos semânticos](#manage-semantic-fields-for-unified-contacts) para gerir tipos semânticos para campos de contacto unificados.
   - [Relações](#manage-contact-and-account-relationships) para gerir o contacto para relação de conta.

1. Depois de efetuar as alterações, escolha a sua próxima opção:

   - [Executar condições de correspondência](#run-matching-conditions) para avaliar rapidamente a qualidade das condições de correspondência (regras de correspondência e de eliminação de duplicados) sem atualizar o perfil unificado. A opção **Executar condições de correspondência apenas** não é apresentada para uma única entidade.
   - [Unificar perfis](#run-updates-to-the-unified-profile) para executar condições de correspondência e atualizar a entidade de perfil unificada sem afetar dependências (tais como melhoramentos, segmentos ou medidas). Os processos dependentes não são executados, mas serão atualizados conforme [definido na agenda de atualização](schedule-refresh.md).
   - [Unificar perfis e dependências](#run-updates-to-the-unified-profile) para executar condições de correspondência, atualizar a entidade de perfil unificado e atualizar todas as dependências (tais como melhoramentos, segmentos ou medidas). Todos os processos voltam a ser executados automaticamente. No B2B, a unificação é executada nas entidades de conta e de contacto, atualizando os perfis unificados.

## <a name="edit-source-fields"></a>Editar campos de origem

Não é possível remover um atributo ou uma entidade se os atributos já foram unificados.

1. Selecione **Editar** no mosaico **Campos de origem**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de ecrã da página Campos de Origem que mostram o número de chaves primárias, campos mapeados e não mapeados":::

   O número de campos mapeados e não mapeados apresentados.

1. Para adicionar outros atributos ou entidades, selecione **Selecionar entidades e campos**.

1. Opcionalmente, pode alterar a chave primária de uma entidade, os tipos de atributo e ativar ou desativar o **mapeamento Inteligente**. Para mais informações, consulte [Selecionar campos de origem](map-entities.md).

1. Selecione **Seguinte** para efetuar alterações às regras de deduplicação ou selecione **Guardar e fechar** para voltar a [Atualizar as definições de unificação](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Gerir regras de eliminação de duplicados

1. Selecione **Editar** no mosaico **Registos duplicados**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de ecrã da página Registos Duplicados, que mostra o número de registos duplicados" lightbox="media/m3_duplicates_edit.png":::

   O número de registos duplicados encontrados é apresentado em **Duplicados**. A coluna **Eliminação de registos duplicados** mostra as entidades que tinham dados duplicados e a percentagem de dados duplicados.

1. Para utilizar uma entidade enriquecida, selecione **Utilizar entidades enriquecidas**. Para obter mais informações, consulte [Melhoramento para origens de dados](data-sources-enrichment.md).

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

   1. Selecionar **Concluído**.

1. Selecione **Seguinte** para efetuar alterações às condições de correspondência ou selecione **Guardar e fechar** para voltar a [Atualizar definições de unificação](#update-unification-settings).

## <a name="manage-match-rules"></a>Gerir regras de correspondência

Pode reconfigurar e aperfeiçoar a maioria dos parâmetros de correspondência. Não pode adicionar ou eliminar entidades. As regras de correspondência não se aplicam a uma única entidade.

1. Selecione **Editar** no mosaico **Condições de correspondência**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de ecrã da página Regras e condições de correspondência com estatísticas." lightbox="media/m3_match_edit.png":::

   A página apresenta a ordem de correspondência e as regras definidas, bem como as seguintes estatísticas:
   - **Registos de origem exclusivos** mostra o número de registos de origens individuais que foram processados na última execução de correspondência.
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

1. Selecione **Seguinte** para efetuar alterações a campos unificados ou selecione **Guardar e fechar** para voltar a [Atualizar definições de unificação](#update-unification-settings).

## <a name="manage-unified-fields"></a>Gerir campos unificados

1. Selecione **Editar** no mosaico **Campos de cliente unificados**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de ecrã dos campos de cliente unificados":::

1. Reveja os campos combinados e excluídos e efetue quaisquer alterações necessárias. Adicione ou edite a chave CustomerID ou agrupe perfis em clusters. Para mais informações, consulte [Perfis de cliente unificados](merge-entities.md).

1. Para clientes ou contas, selecione **Seguinte** para rever e [atualizar o perfil unificado e dependências](#run-updates-to-the-unified-profile). Ou selecione **Guardar e fechar** para voltar a [Atualizar definições de unificação](#update-unification-settings) para efetuar mais alterações.

   Para contactos, selecione **Seguinte** para gerir campos semânticos. Ou selecione **Guardar e fechar** para voltar a [Atualizar definições de unificação](#update-unification-settings) para efetuar mais alterações.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Gerir campos semânticos para contactos unificados

1. Selecione **Editar** no mosaico **Campos semânticos**.

1. Para alterar o tipo semântico para um campo unificado, selecione um novo tipo. Para mais informações, consulte [Definir os campos semânticos para contactos unificados](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Selecione **Seguinte** para gerir a relação de conta e contacto ou selecione **Guardar e fechar** para voltar a [Atualizar definições de unificação](#update-unification-settings).

## <a name="manage-contact-and-account-relationships"></a>Gerir relações de contacto e conta

1. Selecione **Editar** no mosaico **Relações**.

1. Para alterar a relação de contacto e conta, altere qualquer uma das seguintes informações:

   - **Chave externa a partir da entidade de contacto**: escolha o atributo que liga a sua entidade de contacto à conta.
   - **Para a entidade de conta**: escolha a entidade de conta associada ao contacto.

1. Selecione **Seguinte** para rever as definições de unificação e [atualizar o perfil unificado e dependências](#run-updates-to-the-unified-profile), ou selecione **Guardar e fechar** para voltar a [Atualizar definições de unificação](#update-unification-settings) para efetuar mais alterações.

## <a name="run-matching-conditions"></a>Executar condições de correspondência

A execução de condições de correspondência executa apenas regras de correspondência e eliminação de duplicados e atualiza as entidades *Deduplication_* e *ConflationMatchPair*.

1. Na página **Dados** > **Unificar**, selecione **Executar condições de correspondência apenas**.

   Os mosaicos **Duplicar registos** e **Condições de correspondência** mostram o estado **Na fila** ou **Em atualização**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Quando o processo correspondente estiver concluído, selecione **Editar** no mosaico **Condições de correspondência**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de ecrã recortada das métricas-chave na página Corresponder com números e detalhes.":::

1. Para efetuar alterações, consulte [Gerir regras de eliminação de duplicados](#manage-deduplication-rules) ou [Gerir regras de correspondência](#manage-match-rules).

1. Execute novamente o processo de correspondência ou [execute atualizações ao perfil](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Executar atualizações ao perfil unificado

- Para executar condições de correspondência e atualizar a entidade de perfil unificada *sem* afetar dependências (tais como cartões de cliente, melhoramentos, segmentos ou medidas), selecione **Unificar perfis de cliente**. Para contas, seleccione **Unificar contas** > **Unificar perfis**. Para contactos, seleccione **Unificar contactos (pré-visualização)** > **Unificar perfis**. Os processos dependentes não são executados, mas serão atualizados conforme [definido na agenda de atualização](schedule-refresh.md).
- Para executar condições de correspondência, atualizar o perfil unificado e executar todas as dependências, selecione **Unificar perfis de cliente e dependências**. Todos os processos voltam a ser executados automaticamente. Para contas e contactos, selecione **Unificar contas** > **Unificar perfis e dependências**. São executadas condições de correspondência para contas e contactos, atualizando tanto perfis unificados e todas as outras dependências executadas.

Todos os mosaicos, exceto **Campos de origem**, apresentam **Em fila de espera** ou **A atualizar**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Os resultados de uma apresentação de execução com êxito na página **Unificar** mostram o número de perfis unificados.

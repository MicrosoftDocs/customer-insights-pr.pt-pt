---
title: Criar um perfil de contacto unificado (pré-visualização)
description: Passe pelo processo de unificação de dados para criar um único conjunto de dados principal de contactos.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305048"
---
# <a name="create-a-unified-contact-profile-preview"></a>Criar um perfil de contacto unificado (pré-visualização)

Depois de [unificar contas empresariais](map-entities.md), pode, opcionalmente, unificar os contactos dessas contas e ligar os contactos unificados às contas unificadas. O processo de unificação dos contactos mapeia dados de contactos a partir de várias origens de dados, remove duplicados, faz corresponder dados entre entidades, configura mapeamentos semânticos, cria relações entre contactos e contas e, em seguida, cria um perfil de contacto unificado.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Os primeiros passos são idênticos aos passos de unificação de contas.

## <a name="prerequisites"></a>Pré-requisitos

Os registos de contas e contactos devem ter uma chave exclusiva (chamada chave externa) que os liga. Por exemplo, um ID de conta que existe no registo de conta e de contacto que associa a conta e o contacto.

## <a name="preview-limitations"></a>Limitações de pré-visualização

- Os contactos sem uma ligação a uma conta são dispensados.
- Se uma conta for deduplicada, é identificado um registo vencedor com base nas preferências de união. Não são selecionados registo perdedores, pelo que são dispensados. Os contactos associados à perda de dados são dispensados.
- Uma conta pode ter vários contactos, mas um contacto está associado a uma única conta.
- Os atributos de contacto mapeados no passo de mapeamento semântico são os únicos atributos que podem ser apresentados no Cartão de cliente. No entanto, estão disponíveis 17 atributos.

## <a name="select-source-fields"></a>Selecionar campos de origem

1. Por baixo de **Unificar contactos (pré-visualização)**, selecione **Começar**.

1. [Selecione as entidades e os campos](map-entities.md) para as origens de dados dos seus contactos, incluindo as chaves primárias e os tipos de atributo.

1. Selecione **Seguinte**.

## <a name="remove-duplicate-records"></a>Remover registos duplicados

1. Opcionalmente, [defina as regras de deduplicação](remove-duplicates.md) para as entidades selecionadas.

1. Selecione **Seguinte**.

## <a name="match-conditions"></a>Condições de correspondência

1. [Defina a ordem e regras de correspondência](match-entities.md) para a correspondência cruzada de entidades.

1. Selecione **Seguinte**.

## <a name="unify-contact-fields"></a>Unificar campos de contacto

1. [Combine e exclua campos de contacto](merge-entities.md).

1. Selecione **Seguinte**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definir os campos de semântica para contactos unificados

Este passo no processo de unificação mapeia os campos de contacto unificados para tipos semânticos. No B2B, os cartões de cliente mostram contas. Quando o cartão está selecionado, são apresentados todos os contactos associados à conta. Os campos que mapear neste passo são os campos que serão apresentados nos cartões.

1. Selecione o tipo semântico que mapeia cada campo unificado. Selecione **Nenhum** se não estiver disponível um tipo semântico.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Captura de ecrã da página Campos semânticos para definir os tipos semânticos." lightbox="media/semantic_mapping.png":::

1. Depois de mapear todos os campos unificados, selecione **Seguinte**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Definir a relação entre contactos e contas

Este passo no processo de unificação liga os seus dados de contacto aos dados de conta correspondentes.

1. Para cada entidade, introduza a seguinte informação:

   - **Chave externa a partir da entidade de contacto**: escolha o atributo que liga a sua entidade de contacto à conta.
   - **Para a entidade de conta**: escolha a entidade de conta associada ao contacto.

   :::image type="content" source="media/contact_relationship.png" alt-text="Captura de ecrã da página Relação para ligar as entidades de contacto e conta.":::

1. Selecione **Seguinte**.

## <a name="review-contact-unification"></a>Rever a unificação de contactos

Reveja o resumo das alterações, crie o perfil unificado e reveja os resultados.

### <a name="review-and-create-contact-profiles"></a>Rever e criar perfis de contacto

Este último passo no processo de unificação mostra um resumo dos passos no processo e oferece uma oportunidade de efetuar alterações antes de criar o perfil de contacto.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Captura de ecrã de Rever e criar perfis de contacto.":::

1. Selecione **Editar** em qualquer um dos passos de unificação de contactos para rever e efetuar quaisquer alterações.

1. Se estiver satisfeito com as suas seleções, selecione **Criar perfis de contacto**. A página **Unificar** é apresentada durante a criação do perfil de contacto unificado.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Captura de ecrã da página Unificar contactos com mosaicos a mostrar Em fila de espera ou A atualizar.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificação demora algum tempo a ser concluído e não pode alterar a configuração enquanto não for concluído.

### <a name="view-the-results-of-contact-unification"></a>Ver os resultados da unificação de contactos

Após a conclusão da unificação, a página **Dados** > **Unificar** mostra o número de perfis de contacto unificados. Os resultados de cada passo no processo de unificação são apresentados em cada mosaico. Por exemplo, **Campos de origem** mostra o número de atributos mapeados (campos) e **Registos duplicados** mostram o número de registos duplicados encontrados.

:::image type="content" source="media/unified_contacts.png" alt-text="Captura de ecrã da página Unificação de dados após a unificação de contactos.":::

> [!TIP]
> O mosaico **Condições de correspondência** só é apresentado se várias entidades tiverem sido selecionadas.

Recomendamos que reveja os resultados, particularmente a qualidade das [regras de correspondência](data-unification-update.md#manage-match-rules) refina-as se necessário.

Sempre que necessário, [efetue alterações às definições de unificação de contactos](data-unification-update.md) e execute novamente o perfil unificado.

### <a name="verify-output-entities-from-data-unification"></a>Verificar entidades de saída a partir da unificação de dados

Aceda a **Dados** > **Entidades** para verificar as entidades de saída.

A entidade de perfil de contacto unificado, denominada *ContactProfile*, é apresentada na secção **Entidades semânticas**. A primeira execução de unificação realizada com êxito cria a entidade *ContactProfile* unificada. Todas as execuções subsequentes expandem essa entidade.

A entidade *ContactsCustomer* (pré-visualização) é criada e apresentada na secção **Perfis**. Esta entidade contém os dados de contacto sem as ligações às contas. Esta entidade é utilizada como entrada no mapeamento semântico e nos passos de relação da unificação de contactos.

As entidades de deduplicação e conflação são criadas e apresentadas na secção **Sistema**. Uma entidade deduplicada para cada entidade de origem é criada com o nome **Deduplication_DataSource_Entity**. A entidade **ContactsConflationMatchPairs** contém informações sobre correspondências cruzadas de entidades.

Uma entidade de saída de eliminação de duplicados contém as seguintes informações:
- IDs / Chaves
  - Campos Chave primária e ID Alternativo. O campo de ID alternativo é composto por todos os IDs alternativos identificados num registo.
  - O campo Deduplication_GroupId mostra o grupo ou o cluster identificado dentro de uma entidade que agrupa todos os registos semelhantes com base nos campos de eliminação de duplicados especificados. É utilizado para fins de processamento do sistema. Se não existirem regras de eliminação de duplicados manuais especificadas e se aplicarem regras de eliminação de duplicados definidas pelo sistema, poderá não encontrar este campo na entidade de saída de eliminação de duplicados.
  - Deduplication_WinnerId: este campo contém o ID de vencedor dos grupos ou clusters identificados. Se Deduplication_WinnerId é o mesmo que o valor da Chave primária para um registo, significa que o registo é o registo vencedor.
- Campos usados para definir as regras de eliminação de duplicados.
- Campos Regra e Pontuação para denotar quais as regras de eliminação de duplicados foram aplicadas e a pontuação devolvida pelo algoritmo correspondente.

## <a name="next-step"></a>Passo Seguinte

Configure [atividades](activities.md), [melhoramento](enrichment-hub.md) ou [relações](relationships.md) para obter mais informações sobre os seus contactos.

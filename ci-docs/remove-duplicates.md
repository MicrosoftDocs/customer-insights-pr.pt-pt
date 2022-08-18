---
title: Remover duplicados antes de unificar dados
description: O segundo passo no processo de unificação é selecionar que registos manter quando são encontrados duplicados.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 7f4829cfc14af623f724c6594e834f3fac1c15a9
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213641"
---
# <a name="remove-duplicates-before-unifying-data"></a>Remover duplicados antes de unificar dados

Este passo opcional na unificação permite configurar as regras para eliminar registos duplicados **dentro** de uma entidade. A eliminação de duplicados identifica vários registos para um cliente e seleciona o melhor registo a manter (com base nas preferências de intercalação básicas) ou intercala os registos num só (baseado nas preferências de intercalação avançadas). Os registos de origem ligam-se ao registo intercalado com ID alternativos. Se não forem configuradas regras, aplicam-se as regras definidas pelo sistema.

## <a name="default-deduplication"></a>Eliminação de duplicados predefinida

As regras definições pelo sistema são aplicáveis se não forem adicionadas quaisquer regras de eliminação de duplicados.

- São eliminados os duplicados da chave primária.
  Para quaisquer registos com a mesma chave primária, o registo **Mais preenchido** (o que tem o menor número de valores nulos) é o vencedor.
- Quaisquer regras de correspondência entre entidades são aplicadas à entidade.
  Por exemplo: no passo de correspondência, se a entidade A for correspondida com a entidade B em *FullName* e *DateofBirth*, também são eliminados os duplicados da entidade A por *FullName* e *DateofBirth*. Como *FullName* e *DateofBirth* são chaves válidas para identificar um cliente na entidade A, estas chaves também são válidas para identificar clientes duplicados na entidade A.

## <a name="include-enriched-entities-preview"></a>Incluir entidades melhoradas (pré-visualização)

Se tiver melhorado entidades ao nível origem de dados para ajudar a melhorar os resultados de unificação, selecione-as. Para obter mais informações, consulte [Melhoramento para origens de dados](data-sources-enrichment.md).

1. Na página **Registos duplicados**, selecione **Utilizar entidades melhoradas** na parte superior da página.

1. A partir do painel **Utilizar entidades melhoradas**, escolha uma ou mais entidades melhoradas.

1. Selecionar **Concluído**.

## <a name="define-deduplication-rules"></a>Definir regras de eliminação de duplicados

1. Na página **Registos duplicados**, selecione uma entidade e selecione **Adicionar regra** para definir as regras de eliminação de duplicados.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Captura de ecrã de páginas Registos duplicados com Mostrar mais destacado":::

   1. No painel **Adicionar regra**, introduza as seguintes informações:
      - **Selecionar campo**: escolha a partir da lista de campos disponíveis na entidade que pretende verificar a existência de duplicados. Escolha os campos que sejam provavelmente únicos para cada cliente. Por exemplo, um endereço de e-mail ou a combinação de nome, cidade e número de telefone.
      - **Normalizar**: selecione a partir das seguintes opções de normalização para os atributos selecionados.
        - **Números**: converte outros sistemas numéricos, como a numeração romana em algarismos árabes. *VIII* torna-se *8*.
        - **Símbolos**: remove todos os símbolos e caracteres especiais. *Head&Shoulder* torna-se *HeadShoulder*.
        - **Texto para minúscula: converte todos os caracteres em minúsculas**. *TODAS MAIÚSCULAS e Título* torna-se *todas maiúsculas e título*.
        - **Tipo (Telefone, Nome, Endereço, Organização)**: padroniza nomes, títulos, números de telefone, endereços, etc.
        - **Unicode para ASCII**: converte a notação unicode para caracteres ASCII. */u00B2* torna-se *2*.
        - **Espaço em branco**: remove todos os espaços. *Olá   Mundo* torna-se *OláMundo*.
      - **Precisão**: defina o nível de precisão para aplicar esta condição.
        - **Básico**: escolha entre *Baixo (30%)*, *Médio (60%)*, *Alto (80%)* e *Exato (100%)*. Selecione **Exato** para corresponder apenas registos que correspondam a 100 por cento.
        - **Personalizar**: defina uma percentagem que os registos têm de corresponder. O sistema só vai corresponder os registos que ultrapassam este limiar.
      - **Nome**: nome da regra.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Captura de ecrã do painel Adicionar regra para remover duplicados.":::

   1. Opcionalmente, selecione **Adicionar** > **Adicionar condição** para adicionar mais condições à regra. As condições estão ligadas a um operador E lógico e, portanto, só são executadas se todas as condições forem satisfeitas.

   1. Opcionalmente, **Adicionar** > **Adicionar exceção** para [adicionar exceções à regra](match-entities.md#add-exceptions-to-a-rule). As exceções são utilizadas para resolver casos raros de falsos positivos e falsos negativos.

   1. Selecione **Concluído** para criar a regra.

1. Opcionalmente, [adicione mais regras](#define-deduplication-rules).

1. Selecione uma entidade e, em seguida, **Editar preferências de união**.

1. No painel **Unir preferências**:
   1. Escolha uma de três opções para determinar que registo manter se forem encontrados duplicados:
      - **Mais preenchido**: identifica o registo com os campos de atributos mais povoados como registo vencedor. É a opção de intercalação predefinida.
      - **Mais recentes**: Identifica o registo vencedor com base no mais recente. Requer uma data ou um campo numérico para definir a atualidade.
      - **Menos recente**: Identifica o registo vencedor com base no menos recente. Requer uma data ou um campo numérico para definir a atualidade.
      
      No caso de empate, o registo vencedor é aquele com o MAX(PK) ou valor da chave primária maior.
      
   1. Opcionalmente, para definir as preferências de união em atributos individuais de uma entidade, selecione **Avançadas** na parte inferior do painel. Por exemplo, pode optar por manter o e-mail mais recente e o endereço mais completo de diferentes registos. Expanda a entidade para ver todos os seus atributos e definir que opção utilizar para atributos individuais. Se escolher uma opção baseada em recência, também precisa de especificar um campo de data/hora que defina a recência.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Preferências de união avançadas que mostram e-mails recentes e endereços completos":::

   1. Selecione **Concluído** para aplicar preferências de união

1. Depois de definir as regras de eliminação de duplicados e as preferências de união selecione **Seguinte**.
  
> [!div class="nextstepaction"]
> [Passo seguinte para uma única entidade: Unificar campos](merge-entities.md)

> [!div class="nextstepaction"]
> [Passo seguinte para várias entidades: Condições de correspondência](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Saída de eliminação de duplicados como uma entidade

O processo de eliminação de duplicados cria uma nova entidade sem duplicados para cada uma das entidades de origem. Estas entidades podem ser encontradas juntamente com **ConflationMatchPairs:CustomerInsights** na secção **Sistema** na página **Entidades**, com o nome **Deduplication_DataSource_Entity**.

Uma entidade de saída de eliminação de duplicados contém as seguintes informações:

- IDs / Chaves
  - Campos Chave primária e ID Alternativo. O campo de ID alternativo é composto por todos os IDs alternativos identificados num registo.
  - O campo Deduplication_GroupId mostra o grupo ou o cluster identificado dentro de uma entidade que agrupa todos os registos semelhantes com base nos campos de eliminação de duplicados especificados. É utilizado para fins de processamento do sistema. Se não existirem regras de eliminação de duplicados manuais especificadas e se aplicarem regras de eliminação de duplicados definidas pelo sistema, poderá não encontrar este campo na entidade de saída de eliminação de duplicados.
  - Deduplication_WinnerId: este campo contém o ID de vencedor dos grupos ou clusters identificados. Se Deduplication_WinnerId é o mesmo que o valor da Chave primária para um registo, significa que o registo é o registo vencedor.
- Campos usados para definir as regras de eliminação de duplicados.
- Campos Regra e Pontuação para denotar quais as regras de eliminação de duplicados foram aplicadas e a pontuação devolvida pelo algoritmo correspondente.

[!INCLUDE[footer-include](includes/footer-banner.md)]

---
title: Criar segmentos complexos com o construtor de segmentos
description: Utilize o construtor de segmentos para criar segmentos de clientes ao agrupá-los com base em vários atributos.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304763"
---
# <a name="create-complex-segments-with-segment-builder"></a>Criar segmentos complexos com o construtor de segmentos

Defina filtros complexos em torno do cliente unificado ou contacto unificado e as suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registos de cliente ou contacto que pode exportar e sobre os quais pode agir.

> [!TIP]
> Os segmentos baseados em **clientes individuais** incluem automaticamente informações de contacto disponíveis para os membros do segmento. Nas **contas empresariais**, se [unificou](data-unification.md) contas e contactos, escolha se o segmento se baseia em contas ou contactos empresariais. Para exportar para um destino que espera informação de contacto, utilize um segmento de contactos. Para exportar para um destino que espera informação de conta, utilize um segmento de contas.

## <a name="segment-builder"></a>Construtor de segmentos

A imagem a seguir ilustra os vários aspetos do construtor de segmentos. Mostra um segmento que resulta num grupo de clientes. Os clientes encomendaram bens num intervalo de tempo específico e recolheram pontos de recompensa ou gastaram uma certa quantia em dinheiro.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do criador de segmentos." lightbox="media/segment-builder-overview.png":::

1. Organize o seu segmento com regras e sub-regras. Cada regra ou subregra consiste de condições. Combine as condições com os operadores lógicos.

1. Escolha o [caminho de relação](relationships.md) entre entidades que se aplica a uma regra. O caminho da relação determina quais os atributos que podem ser usados numa condição.

1. Faça a gestão de regras e sub-regras. Altere a posição de uma regra ou elimine-a.

1. Adicione condições e crie o nível certo de aninhamento utilizando sub-regras.

1. Aplique operações de conjuntos a regras ligadas.

1. Utilize o painel de atributos para adicionar atributos de entidade disponíveis ou criar condições com base em atributos. O painel mostra a lista de entidades e atributos, com base no caminho da relação selecionada, que estão disponíveis para a regra selecionada.

1. Adicione condições com base em atributos às regras e sub-regras existentes ou adicione-as a uma nova regra.

1. Anule e refaça alterações enquanto cria o segmento.

O exemplo acima ilustra a capacidade de segmentação. Definimos um segmento para clientes que compraram pelo menos 500 $ de bens online *e* que têm interesse no desenvolvimento de software.

## <a name="create-a-new-segment-with-segment-builder"></a>Criar um novo segmento com o construtor de segmentos

1. Aceda a **Segmentos**.

1. Selecione **Novo** > **Criar o seu próprio**. Na página de construtores de segmentos, define ou compõe regras. Uma regra é composta por uma ou mais condições que definem um conjunto de clientes.

   > [!NOTE]
   > Para ambientes baseados em contas empresariais, selecione **Novo** > **Segmento de contas** ou **Segmento de contactos (pré-visualização)** com base no tipo de segmento que pretende criar. Se uma [hierarquia de contas](relationships.md#set-up-account-hierarchies) tiver sido definida e pretende criar regras para filtrar dados com base na relação de elemento principal e subordinado, selecione **Utilizar hierarquia? (pré-visualização)**, selecione a hierarquia e, em seguida, **Aplicar**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Painel de seleção do segmento de hierarquia de conta.":::

1. Selecione **Editar detalhes** junto de Segmento sem título. Forneça um nome para o seu segmento e atualize o **Nome da entidade de saída** sugerido para o segmento. Opcionalmente, adicione uma descrição e [etiquetas](work-with-tags-columns.md#manage-tags) ao segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Caixa de diálogo Editar detalhes.":::

1. Na secção **Regra1**, escolha um atributo de uma entidade pela qual pretende filtrar clientes. Existem duas formas de escolher atributos:
   - Reveja a lista de entidades e atributos disponíveis no painel **Adicionar à Regra** e selecione o ícone **+** ao lado do atributo a adicionar. Escolha se deseja adicionar o atributo a uma regra existente ou usá-lo para criar uma nova regra.
   - Digite o nome do atributo na secção da regra para ver sugestões correspondentes.

1. Escolha os operadores para especificar os valores correspondentes da condição. O atributo pode ter um dos quatro tipos de dados como valor: numérico, cadeia, data ou booleano. Dependendo do tipo de dados do atributo, diferentes operadores estão disponíveis para especificar a condição.

1. Selecione **Adicionar condição** para adicionar mais condições a uma regra. Para criar uma regra sob a regra atual, selecione **Adicionar sub-regra**.

1. Se uma regra utilizar outras entidades para além da entidade *Cliente* (ou a entidade *ContactProfile* para B2B), selecione **Definir caminho de relação** para mapear a entidade selecionada para a entidade de cliente unificada. Se existir apenas um caminho de relação possível, o sistema seleciona-o automaticamente. Diferentes [caminhos de relações](relationships.md#relationship-paths) podem produzir resultados diferentes. Cada regra pode ter o seu próprio caminho de relação.

   :::image type="content" source="media/relationship-path.png" alt-text="Caminho de relação potencial ao criar uma regra baseada numa entidade mapeada para a entidade de cliente unificado.":::

1. Se tiver várias condições numa regra, escolha o operador lógico que as liga.  
   - Operador **E**: todas as condições devem ser satisfeitas para incluir um registo no segmento. Utilize esta opção quando define condições em diferentes entidades.
   - Operador **OU**: qualquer uma das condições deve ser satisfeita para incluir um registo no segmento. Utilize esta opção quando define múltiplas condições para a mesma entidade.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regra com duas condições E.":::

   Ao utilizar o operador OU, todas as condições tem de se basear em entidades incluídas no caminho da relação.

1. Para criar diferentes conjuntos de registos de clientes, crie múltiplas regras. Para incluir os clientes necessários para o seu caso de negócio combine os grupos. Especificamente, se não puder incluir uma entidade numa regra por causa do caminho da relação especificado, crie uma nova regra da qual escolher os atributos.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Adicionar uma nova regra a um segmento e escolher o operador definido.":::

   1. Selecione **Adicionar regra**.
   1. Selecione um dos operadores definidos: **União**, **Intersetar** ou **Exceto**.

      - **União** une os dois grupos.
      - **Interseção** sobrepõe os dois grupos. Apenas os dados *comuns* a ambos os grupos permanecem no grupo unificado.
      - **Exceto** combina os dois grupos. Apenas são mantidos os dados do grupo A que *não são comuns* aos dados do grupo B.

1. Por predefinição, a entidade de saída conterá automaticamente todos os atributos de perfis de cliente que correspondem aos filtros definidos. No B2B, quando utiliza a entidade *ContactProfile*, o ID da conta é incluído automaticamente. Se um segmento se basear no outras entidades que não a entidade *Cliente* ou para incluir mais atributos a partir de *ContactProfile*, selecione **Atributos de projeto** para adicionar mais atributos destas entidades à entidade de saída.
 
   Por exemplo: um segmento baseia-se numa entidade que contém dados de compra, que estão relacionados com a entidade *Cliente*. O segmento procura todos os clientes de Espanha que compraram bens no ano atual. Pode optar por anexar atributos como o preço dos bens ou a data de compra de todos os registos de clientes correspondentes na entidade de saída. Estas informações podem ser úteis para analisar as correlações sazonais com o total de despesas.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplo de atributos de projeto selecionados no painel lateral a adicionar à entidade de saída.":::
 
   Um resultado de um exemplo de um segmento baseado em contas empresariais com atributos projetados de contactos poderia ser assim:

   |ID  |Nome da conta  |Receitas  |Nome do contacto  | Função do contacto|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [CEO, Gestor de aprovisionamento]

   > [!NOTE]
   > - **Atributos de projeto** só funciona para entidades que têm uma relação de um para muitos com a entidade *Cliente* ou *ContactProfile*. Por exemplo, um cliente pode ter várias subscrições.
   > - Se o atributo que pretende projetar estiver a mais de um salto de distância da entidade *Cliente* ou *ContactProfile*, como definido pela relação, esse atributo deve ser utilizado em todas as regras da consulta de segmento que está a criar.
   > - Se o atributo que pretende projetar estiver apenas a um salto de distância da entidade *Cliente* ou *ContactProfile*, esse atributo não precisa de estar presente em todas as regras da consulta de segmento que está a criar.
   > - Os **atributos projetados** são contabilizados quando utiliza operadores definidos.

1. Selecione **Executar** para criar o segmento. Selecione **Guardar** se pretender manter a configuração atual e executar o segmento mais tarde. A página **Segmentos** é apresentada.

### <a name="segment-builder-tips"></a>Sugestões para o construtor de segmentos

Ao criar um segmento utilizando o construtor de segmentos, tenha em atenção as seguintes sugestões:

- O construtor de segmentos não sugerirá valores válidos das entidades ao definir os operadores para as condições. Pode ir a **Dados** > **Entidades** e transferir os dados da entidade para ver quais os valores disponíveis.
- As condições baseadas nas datas permitem alternar entre datas fixas e um intervalo de datas flutuante.
- Se tiver várias regras para o seu segmento, a regra que está a editar tem uma linha azul vertical ao lado.
- Pode mover regras e condições para outros lugares na definição de segmento. Selecione as reticências verticais (&vellip;) junto de uma regra ou condição e escolha como e para onde a mover.
- Os controlos **Anular** e **Refazer** permitem-lhe reverter as alterações.
- Depois de criar um segmento, alguns segmentos permitem-lhe [monitorizar a utilização do segmento](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Próximos passos

[Exporte um segmento](export-destinations.md) e explore a [integração do Cartão de Cliente](customer-card-add-in.md) para utilizar segmentos noutras aplicações.

[!INCLUDE [footer-include](includes/footer-banner.md)]

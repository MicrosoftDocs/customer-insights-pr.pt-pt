---
title: Criar segmentos complexos com o construtor de segmentos
description: Utilize o construtor de segmentos para criar segmentos de clientes ao agrupá-los com base em vários atributos.
ms.date: 03/25/2022
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
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170649"
---
# <a name="create-complex-segments-with-segment-builder"></a>Criar segmentos complexos com o construtor de segmentos

Defina filtros complexos em torno da entidade de cliente unificado e as suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registos de clientes que pode exportar e tomar medidas.

> [!TIP]
> Os segmentos baseados em **clientes individuais** incluem automaticamente informações de contacto disponíveis para os membros do segmento. Em ambientes para **contas empresariais**, os segmentos baseiam-se em contas (empresas ou subsidiárias). Para incluir informações de contacto num segmento, utilize a funcionalidade **Projetar atributos** no construtor de segmentos. Certifique-se de que as origens de dados de contacto são [semanticamente mapeadas para a entidade ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

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

1. Selecione **Editar detalhes** junto de Segmento sem título. Forneça um nome para o seu segmento e atualize o **Nome da entidade de saída** sugerido para o segmento. Opcionalmente, adicione uma descrição e [etiquetas](work-with-tags-columns.md#manage-tags) ao segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Caixa de diálogo Editar detalhes.":::

1. Na secção **Regra1**, escolha um atributo de uma entidade pela qual pretende filtrar clientes. Existem duas formas de escolher atributos:
   - Reveja a lista de entidades e atributos disponíveis no painel **Adicionar à Regra** e selecione o ícone **+** ao lado do atributo a adicionar. Escolha se deseja adicionar o atributo a uma regra existente ou usá-lo para criar uma nova regra.
   - Digite o nome do atributo na secção da regra para ver sugestões correspondentes.

1. Escolha os operadores para especificar os valores correspondentes da condição. O atributo pode ter um dos quatro tipos de dados como valor: numérico, cadeia, data ou booleano. Dependendo do tipo de dados do atributo, diferentes operadores estão disponíveis para especificar a condição. Para segmentos com contas empresariais, estão disponíveis dois operadores especiais para incluir potenciais hierarquias entre as contas ingeridas. Utilize os operadores *subordinado de* e *principal de* para incluir contas relacionadas.

1. Selecione **Adicionar condição** para adicionar mais condições a uma regra. Para criar uma regra sob a regra atual, selecione **Adicionar sub-regra**.

1. Se uma regra utilizar outras entidades para além da entidade *Cliente*, selecione **Definir caminho da relação** para mapear a entidade selecionada para a entidade de cliente unificada. Se existir apenas um caminho de relação possível, o sistema seleciona-o automaticamente. Diferentes [caminhos de relações](relationships.md#relationship-paths) podem produzir resultados diferentes. Cada regra pode ter o seu próprio caminho de relação.

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

1. Por predefinição, a entidade de saída conterá automaticamente todos os atributos de perfis de cliente que correspondem aos filtros definidos. Se um segmento se basear noutras entidades diferentes da entidade *Cliente*, selecione **Atributos do projeto** para adicionar mais atributos destas entidades à entidade de saída.

   > [!IMPORTANT]
   > Para os segmentos baseados em contas empresariais, os detalhes de um ou mais contactos de cada conta da entidade *ContactProfile* têm de ser incluídos no segmento para permitir que esse segmento seja ativado ou exportado para destinos que exijam informações de contacto. Para obter mais informações sobre a entidade *ContactProfile*, consulte [Mapeamentos semânticos](semantic-mappings.md).
   > Um resultado de um exemplo de um segmento baseado em contas empresariais com atributos projetados de contactos poderia ser assim:
   >
   > |ID  |Nome da conta  |Receitas  |Nome do contacto  | Função do contacto|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [CEO, Gestor de aprovisionamento]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplo de atributos de projeto selecionados no painel lateral a adicionar à entidade de saída.":::
  
   Por exemplo: um segmento baseia-se numa entidade que contém dados de compra, que estão relacionados com a entidade *Cliente*. O segmento procura todos os clientes de Espanha que compraram bens no ano atual. Pode optar por anexar atributos como o preço dos bens ou a data de compra de todos os registos de clientes correspondentes na entidade de saída. Estas informações podem ser úteis para analisar as correlações sazonais com o total de despesas.

   > [!NOTE]
   > - A opção **Projetar atributos** só funciona para entidades que têm uma relação de um para muitos com a entidade do cliente. Por exemplo, um cliente pode ter várias subscrições.
   > - Se o atributo que pretende projetar estiver a mais de um salto de distância da entidade *Cliente*, tal como definido pela relação, esse atributo deve ser utilizado em todas as regras da consulta de segmento que está a criar.
   > - Se o atributo que pretende projetar estiver apenas a um salto de distância da entidade *Cliente*, esse atributo não precisa de estar presente em todas as regras da consulta de segmento que está a criar.
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

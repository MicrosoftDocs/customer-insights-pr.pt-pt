---
title: Criar segmentos
description: Criar segmentos de clientes para os agrupar com base em vários atributos utilizando o construtor de segmentos ou segmentos rápidos.
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
ms.openlocfilehash: b99d9575d3b6af91758d80eb04170773b08cc9ab
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053986"
---
# <a name="create-segments"></a>Criar segmentos

Defina filtros complexos em torno da entidade de cliente unificado e as suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registos de clientes que pode exportar e tomar medidas. Os segmentos são geridos na página **Segmentos**. Pode [criar novos segmentos](#create-a-new-segment) utilizando o construtor de segmentos ou [criar segmentos rápidos](#quick-segments) a partir de outras áreas da aplicação.

> [!TIP]
> - Os segmentos rápidos só são suportados em ambientes para **clientes individuais**.
> - Os segmentos baseados em **clientes individuais** incluem automaticamente informações de contacto disponíveis para os membros do segmento. Em ambientes para **contas empresariais**, os segmentos baseiam-se em contas (empresas ou subsidiárias). Para incluir informações de contacto num segmento, utilize a funcionalidade **Projetar atributos** no construtor de segmentos. Certifique-se de que as origens de dados de contacto são [semanticamente mapeadas para a entidade ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Construtor de segmentos

A imagem a seguir ilustra os vários aspetos do construtor de segmentos. Mostra um segmento que resulta num grupo de clientes. Os clientes encomendaram bens num intervalo de tempo específico e recolheram pontos de recompensa ou gastaram uma certa quantia em dinheiro.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do criador de segmentos." lightbox="media/segment-builder-overview.png":::

1. Organize o seu segmento com regras e sub-regras. Cada regra ou subregra consiste de condições. Combine as condições com os operadores lógicos

1. Escolha o [caminho de relação](relationships.md) entre entidades que se aplica a uma regra. O caminho da relação determina quais os atributos que podem ser usados numa condição.

1. Faça a gestão de regras e sub-regras. Altere a posição de uma regra ou elimine-a.

1. Adicione condições e crie o nível certo de aninhamento utilizando sub-regras.

1. Aplique operações de conjuntos a regras ligadas.

1. Utilize o painel de atributos para adicionar atributos de entidade disponíveis ou criar condições com base em atributos. O painel mostra a lista de entidades e atributos, com base no caminho da relação selecionada, que estão disponíveis para a regra selecionada.

1. Adicione condições com base em atributos às regras e sub-regras existentes ou adicione-as a uma nova regra.

1. Anule e refaça alterações enquanto cria o segmento.

O exemplo acima ilustra a capacidade de segmentação. Definimos um segmento para clientes que compraram pelo menos 500 $ de bens online *e* que têm interesse no desenvolvimento de software.

## <a name="create-a-new-segment"></a>Criar um novo segmento

Existem várias formas de criar um novo segmento. Esta secção descreve como criar o seu próprio segmento a partir do zero. Também pode criar um *segmento rápido* baseado em entidades existentes ou fazer uso de modelos de aprendizagem automática para obter *segmentos sugeridos*. Para mais informações, consulte [Descrição geral dos segmentos](segments.md).

Ao criar um segmento, pode guardar um rascunho. Na fase de rascunho, um segmento é guardado como um segmento inativo. Quando concluir a configuração do segmento, execute-a para ativar o segmento. Também pode **Ativar** um segmento a partir da página **Todos os segmentos**.

1. Ir para a página **Segmentos**.

1. Selecione **Novo** > **Criar o seu próprio**.

1. Na página de construtores de segmentos, define ou compõe regras. Uma regra é composta por uma ou mais condições que definem um conjunto de clientes.

1. Na secção **Regra1**, escolha um atributo de uma entidade pela qual pretende filtrar clientes. Existem duas formas de escolher atributos:
   - Reveja a lista de entidades e atributos disponíveis no painel **Adicionar à Regra** e selecione o ícone **+** ao lado do atributo a adicionar. Escolha se deseja adicionar o atributo a uma regra existente ou usá-lo para criar uma nova regra.
   - Digite o nome do atributo na secção da regra para ver sugestões correspondentes.

1. Escolha os operadores para especificar os valores correspondentes da condição. O atributo pode ter um dos quatro tipos de dados como valor: numérico, cadeia, data ou booleano. Dependendo do tipo de dados do atributo, diferentes operadores estão disponíveis para especificar a condição. Para segmentos com contas empresariais, estão disponíveis dois operadores especiais para incluir potenciais hierarquias entre as contas ingeridas. Utilize os operadores *subordinado de* e *principal de* para incluir contas relacionadas.

1. Selecione **Adicionar condição** para adicionar mais condições a uma regra. Para criar uma regra sob a regra atual, selecione **Adicionar sub-regra**.

1. Se uma regra utilizar outras entidades que não a entidade *Cliente*, tem de definir o caminho da relação. O caminho da relação é necessário para informar o sistema sobre que relações pretende que acedam à entidade de cliente unificado. Selecione **Definir caminho da relação** para mapear a entidade selecionada para a entidade de cliente unificado. Se houver apenas um caminho de relação possível, o sistema irá selecioná-lo automaticamente. Diferentes caminhos de relações podem produzir resultados diferentes. Cada regra pode ter o seu próprio caminho de relação.

   :::image type="content" source="media/relationship-path.png" alt-text="Caminho de relação potencial ao criar uma regra baseada numa entidade mapeada para a entidade de cliente unificado.":::

   Por exemplo, a entidade *eCommerce_eCommercePurchases* na captura de ecrã tem quatro opções para mapear para a entidade de *Cliente*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Cliente
   - eCommerce_eCommercePurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente: Ao escolher a última opção, podemos incluir atributos de todas as entidades listadas nas condições de regra. Provavelmente teremos menos resultados porque os registos de clientes correspondentes precisam de fazer parte de todas as entidades. Neste exemplo, compraram bens através de comércio eletrónico (*eCommerce_eCommercePurchases*) num ponto de venda (*POS_posPurchases*) e participar no nosso programa de fidelização (*loyaltyScheme_loyCustomers*). Ao escolher a segunda opção, só podemos escolher atributos de *eCommerce_eCommercePurchases* e da entidade *Cliente*. Isto provavelmente resulta em perfis de clientes mais resultantes.

1. Se tiver várias condições numa regra, pode escolher qual o operador lógico que as liga.  
   - Operador **E**: todas as condições devem ser satisfeitas para incluir um registo no segmento. Esta opção é mais útil quando define condições em diferentes entidades.
   - Operador **OU**: qualquer uma das condições deve ser satisfeita para incluir um registo no segmento. Esta opção é mais útil quando define múltiplas condições para a mesma entidade.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regra com duas condições E.":::

   Ao utilizar o operador OU, todas as condições tem de se basear em entidades incluídas no caminho da relação.

   - Pode criar várias regras para criar diferentes conjuntos de registos de clientes. Pode combinar grupos para incluir os clientes necessários para o seu caso de negócio. Para criar uma nova regra, selecione **Adicionar regra**. Especificamente, se não puder incluir e entidade numa regra por causa do caminho da relação especificado, tem de criar uma nova regra para escolher os atributos que a formem.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Adicionar uma nova regra a um segmento e escolher o operador definido.":::

   - Selecione um dos operadores definidos: **União**, **Intersetar** ou **Exceto**.

      - **União** une os dois grupos.
      - **Interseção** sobrepõe os dois grupos. Apenas os dados *comuns* a ambos os grupos permanecem no grupo unificado.
      - **Exceto** combina os dois grupos. Apenas são mantidos os dados do grupo A que *não são comuns* aos dados do grupo B.

1. Por predefinição, os segmentos geram a entidade de saída contendo todos os atributos de perfis de cliente que correspondem aos filtros definidos. Se um segmento se basear noutras entidades diferentes da entidade *Cliente*, pode adicionar mais atributos destas entidades à entidade de saída. Selecione **Atributos do projeto** para escolher os atributos que serão acrescentados à entidade de saída.

   > [!IMPORTANT]
   > Para segmentos baseados em contas empresariais, os detalhes de um ou mais contactos de cada conta da entidade *ContactProfile* devem ser incluídos no segmento para permitir que esse segmento seja ativado ou exportado para destinos que exijam informações de contacto. Para obter mais informações sobre a entidade *ContactProfile*, consulte [Mapeamentos semânticos](semantic-mappings.md).
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

1. Selecione **Editar detalhes** junto de Segmento sem título. Forneça um nome para o seu segmento e atualize o **Nome da entidade de saída** sugerido para o segmento. Opcionalmente, adicione uma descrição e [etiquetas](work-with-tags-columns.md#manage-tags) ao segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Caixa de diálogo Editar detalhes.":::

1. Selecione **Executar** para guardar o segmento, ative-o e comece a processar o seu segmento com base em todas as regras e condições. Caso contrário, será guardado como um segmento inativo.

1. Selecione **Regressar a segmentos** para regressar à página **Segmentos**.

1. Por predefinição, o segmento é criado como um segmento dinâmico. Significa que o segmento é atualizado durante as atualizações do sistema. Para [parar a atualização automática](segments.md#manage-existing-segments), selecione o segmento e escolha a opção **Tornar estáticos**. Os segmentos estáticos podem ser [atualizados manualmente](segments.md#refresh-segments) a qualquer momento.

> [!TIP]
> - O construtor de segmentos não sugerirá valores válidos das entidades ao definir os operadores para as condições. Pode ir a **Dados** > **Entidades** e transferir os dados da entidade para ver quais os valores disponíveis.
> - As condições baseadas nas datas permitem alternar entre datas fixas e um intervalo de datas flutuante.
> - Se tiver várias regras para o seu segmento, a regra que está a editar tem uma linha azul vertical ao lado.
> - Pode mover regras e condições para outros lugares na definição de segmento. Selecione as reticências verticais (&vellip;) junto de uma regra ou condição e escolha como e para onde a mover.
> - Os controlos **Anular** e **Refazer** permitem-lhe reverter as alterações.
> - Depois de criar um segmento, alguns segmentos permitem-lhe [monitorizar a utilização do segmento](segments.md#track-usage-of-a-segment).

## <a name="quick-segments"></a>Segmentos rápidos

Segmentos rápidos permitem criar segmentos simples com um único operador rapidamente para informações mais rápidas.

1. Na página **Segmentos**, selecione **Novo** > **Criar de**.
   - Selecione a opção **Perfis** para criar um segmento baseado na entidade de *cliente unificado*.
   - Selecione a opção **Medidas** para criar um segmento em torno das medidas que criou anteriormente.
   - Selecione a opção **Inteligência** para criar um segmento à volta de uma das entidades de saída geradas com as capacidades **Predições** ou **Modelos Personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo na lista pendente **Campo**.

3. O sistema irá fornecer mais informações que o ajudarão a criar melhores segmentos dos seus clientes.
   - Para campos categóricos, mostraremos as 10 melhores contagens de clientes. Escolha um **Valor** e selecione **Rever**.
   - Para um atributo numérico, o sistema mostrará que valor do atributo se situa no percentil de cada cliente. Escolha um **Operador** e um **Valor** e, em seguida, selecione **Rever**.

4. O sistema fornecerá um **Tamanho do segmento estimado**. Poderá selecionar se pretende gerar ou não o segmento que definiu ou, primeiro, revisitá-lo para obter um tamanho de segmento diferente.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nome e estimativa para um segmento rápido.":::

5. Forneça um **Nome** e **Nome de entidade de saída** para o seu segmento. Opcionalmente, adicione [etiquetas](work-with-tags-columns.md#manage-tags).

6. Selecione **Guardar** para criar o segmento.

7. Depois de concluído o processamento do segmento, poderá vê-lo como qualquer outro segmento que tenha criado.

## <a name="next-steps"></a>Passos seguintes

[Exporte um segmento](export-destinations.md) e explore a [integração do Cartão de Cliente](customer-card-add-in.md) para utilizar segmentos noutras aplicações.

[!INCLUDE [footer-include](includes/footer-banner.md)]

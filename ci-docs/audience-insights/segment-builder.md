---
title: Criar segmentos com o construtor de segmentos
description: Crie segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494516"
---
# <a name="create-segments"></a>Criar segmentos

Defina filtros complexos em torno da entidade de cliente unificado e as suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registos de clientes que pode exportar e tomar medidas. Os segmentos são geridos na página **Segmentos**. Pode [criar novos segmentos](#create-a-new-segment) utilizando o [construtor de segmentos](#segment-builder) ou [criar segmentos rápidos](#quick-segments) a partir de outras áreas da aplicação.

## <a name="segment-builder"></a>Construtor de segmentos

A imagem a seguir ilustra os vários aspetos do construtor de segmentos. Mostra um segmento que resulta num grupo de clientes. Os clientes encomendaram bens num período de tempo específico e obtiveram uma série de pontos de recompensa ou gastaram uma certa quantia de dinheiro. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do criador de segmentos." lightbox="media/segment-builder-overview.png":::

1 – Organize o seu segmento com regras e subregras. Cada regra ou subregra consiste de condições. Combine as condições com os operadores lógicos

2 – Escolha o [caminho de relação](relationships.md) entre entidades que se aplica a uma regra. O caminho da relação determina quais os atributos que podem ser usados numa condição.

3 – Faça a gestão de regras e subregras. Altere a posição de uma regra ou elimine-a.

4 – Adicione condições e crie o nível certo de aninhamento utilizando subregras.

5 – Aplique operações de conjuntos a regras ligadas.

6 – Utilize o painel de atributos para adicionar atributos de entidade disponíveis ou criar condições com base em atributos. O painel mostra a lista de entidades e atributos, com base no caminho da relação selecionada, que estão disponíveis para a regra selecionada.

7 – Adicione condições com base em atributos às regras e subregras existentes ou adicione-as a uma nova regra.

8 – Anule e refaça alterações enquanto cria o segmento.

O exemplo acima ilustra a capacidade de segmentação. Definimos um segmento para clientes que compraram pelo menos 500 $ de bens online *e* que têm interesse no desenvolvimento de software.

## <a name="create-a-new-segment"></a>Criar um novo segmento

Existem várias formas de criar um novo segmento. Esta secção descreve como criar o seu próprio segmento a partir do zero. Também pode criar um *segmento rápido* baseado em entidades existentes ou fazer uso de modelos de aprendizagem automática para obter *segmentos sugeridos*. Mais informações: [Descrição geral de segmentos](segments.md).

Ao criar um segmento, pode guardar um rascunho. Será guardado como um segmento inativo e não pode ser ativado se terminado com uma configuração válida.

1. Ir para a página **Segmentos**.

1. Selecione **Novo** > **Criar o seu próprio**.

1. Na página do construtor de segmentos, define a primeira regra. Uma regra consiste numa ou mais condições e define um conjunto de clientes.

1. Na secção **Regra1**, escolha um atributo de uma entidade por quem pretenda filtrar clientes. Existem duas formas de escolher atributos: 
   - Reveja a lista de entidades e atributos disponíveis no painel **Adicionar à Regra** e selecione o ícone **+** ao lado do atributo a adicionar. Escolha se deseja adicionar o atributo a uma regra existente ou usá-lo para criar uma nova regra.
   - Digite o nome do atributo na secção da regra para ver sugestões correspondentes.

1. Escolha os operadores para especificar os valores correspondentes da condição. O atributo pode ter um dos quatro tipos de dados como valor: numérico, cadeia, data ou booleano. Dependendo do tipo de dados do atributo, diferentes operadores estão disponíveis para especificar a condição. 

1. Selecione **Adicionar condição** para adicionar mais condições a uma regra. Para criar uma regra sob a regra atual, selecione **Adicionar sub-regra**.

1. Se uma regra utilizar outras entidades que não a entidade *Cliente*, tem de definir o caminho da relação. O caminho da relação é necessário para informar o sistema sobre que relações pretende que acedam à entidade de cliente unificado. Selecione **Definir caminho da relação** para mapear a entidade selecionada para a entidade de cliente unificado. Se houver apenas um caminho de relação possível, o sistema irá selecioná-lo automaticamente. Diferentes caminhos de relações podem produzir resultados diferentes. Cada regra pode ter o seu próprio caminho de relação.

   :::image type="content" source="media/relationship-path.png" alt-text="Caminho de relação potencial ao criar uma regra baseada numa entidade mapeada para a entidade de cliente unificado.":::

   Por exemplo, a entidade *eCommerce_eCommercePurchases* na captura de ecrã tem quatro opções para mapear para a entidade de *Cliente*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Cliente
   - eCommerce_eCommercePurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente: Ao escolher a última opção, podemos incluir atributos de todas as entidades listadas nas condições de regra. Provavelmente, teremos menos resultados porque os registos de cliente correspondentes precisam de fazer parte de todas as entidades. Neste exemplo, compraram bens através de e-commerce (*eCommerce_eCommercePurchases*), num ponto de venda (*POS_posPurchases*) e participar no nosso programa de fidelização (*loyaltyScheme_loyCustomers*). Ao escolher a segunda opção, só podemos escolher atributos de *eCommerce_eCommercePurchases* e da entidade *Cliente*. Isto provavelmente resulta em perfis de clientes mais resultantes.

1. Se tiver várias condições numa regra, pode escolher qual o operador lógico que as liga.

   - Operador **E**: todas as condições devem ser satisfeitas para incluir um registo no segmento. Esta opção é mais útil quando define condições em diferentes entidades.

   - Operador **OU**: qualquer uma das condições deve ser satisfeita para incluir um registo no segmento. Esta opção é mais útil quando define múltiplas condições para a mesma entidade.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regra com duas condições E.":::

   Ao utilizar o operador OU, todas as condições tem de se basear em entidades incluídas no caminho da relação.

   1. Pode criar várias regras para criar diferentes conjuntos de registos de clientes. Pode combinar grupos para incluir os clientes necessários para o seu caso de negócio. Para criar uma nova regra, selecione **Adicionar regra**. Especificamente, se não puder incluir uma entidade numa regra devido ao caminho da relação especificado, tem de criar uma nova regra para escolher atributos que a formem.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Adicionar uma nova regra a um segmento e escolher o operador definido.":::

   1. Selecione um dos operadores definidos: **União**, **Intersetar** ou **Exceto**.

   - **União** une os dois grupos.

   - **Interseção** sobrepõe os dois grupos. Apenas os dados que *são comuns* a ambos os grupos são mantidos no grupo unificado.

   - **Exceto** combina os dois grupos. Apenas os dados do grupo A que *não são comuns* aos dados do grupo B são mantidos.

1. Por predefinição, os segmentos geram a entidade de saída contendo todos os atributos de perfis de cliente que correspondem aos filtros definidos. Se um segmento se basear noutras entidades diferentes da entidade *Cliente*, pode adicionar mais atributos destas entidades à entidade de saída. Selecione **Atributos do projeto** para escolher os atributos que serão acrescentados à entidade de saída.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplo de atributos de projeto selecionados no painel lateral a adicionar à entidade de saída.":::
  
   Exemplo: Um segmento baseia-se numa entidade que contém dados de compra, que estão relacionados com a entidade *Cliente*. O segmento procura todos os clientes de Espanha que compraram bens no ano atual. Pode optar por anexar atributos como o preço dos bens ou a data de compra de todos os registos de clientes correspondentes na entidade de saída. Estas informações podem ser úteis para analisar as correlações sazonais com o total de despesas.

   > [!NOTE]
   > - Os atributos projetados só funcionam para entidades que têm uma relação de um-para-muitos com a entidade de cliente. Por exemplo, um cliente pode ter várias subscrições.
   > - Só é possível projetar atributos de uma entidade que é usada em todas as regras de consultas de segmentos que está a criar.
   > - Os atributos projetados são contabilizados quando utiliza operadores definidos.

1. Antes de guardar e executar o segmento, selecione **Editar detalhes** junto do nome do segmento. Forneça um nome para o seu segmento e atualize o **Nome da entidade de saída** sugerido para o segmento. Também pode adicionar uma descrição ao segmento.

1. Selecione **Executar** para guardar e processar o seu segmento se todos os requisitos forem validados. Caso contrário, será guardado como um rascunho de segmento inativo.

1. Selecione **Regressar a segmentos** para regressar à página **Segmentos**.

> [!TIP]
> - O construtor de segmentos não sugerirá valores válidos das entidades ao definir os operadores para as condições. Pode ir a **Dados** > **Entidades** e transferir os dados da entidade para ver quais os valores disponíveis.
> - As condições baseadas nas datas permitem alternar entre datas fixas e um intervalo de datas flutuante.
> - Se tiver várias regras para o seu segmento, encontra uma barra azul em torno da regra que está a editar.
> - Pode mover regras e condições para outros lugares na definição de segmento. Selecione [...] ao lado de uma regra ou condição e escolha como e para onde movê-la.
> - Os controlos **Anular** e **Refazer** na barra de comandos permitem-lhe reverter alterações.

## <a name="quick-segments"></a>Segmentos rápidos

Segmentos rápidos permitem criar segmentos simples com um único operador rapidamente para informações mais rápidas.

1. Na página **Segmentos**, selecione **Novo** > **Criar de**.

   - Selecione a opção **Perfis** para criar um segmento baseado na entidade de *cliente unificado*.
   - Selecione a opção **Medidas** para criar um segmento em torno de medidas que criou anteriormente.
   - Selecione a opção **Inteligência** para criar um segmento à volta de uma das entidades de saída geradas com as capacidades **Predições** ou **Modelos Personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo na lista pendente **Campo**.

3. O sistema irá fornecer mais informações que o ajudarão a criar melhores segmentos dos seus clientes.
   - Para campos categóricos, mostraremos as 10 melhores contagens de clientes. Escolha um **Valor** e selecione **Rever**.

   - Para um atributo numérico, o sistema mostrará que valor do atributo se situa no percentil de cada cliente. Escolha um **Operador** e um **Valor** e, em seguida, selecione **Rever**.

4. O sistema fornecerá um **Tamanho do segmento estimado**. Poderá selecionar se pretende gerar ou não o segmento que definiu ou, primeiro, revisitá-lo para obter um tamanho de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nome e estimativa para um segmento rápido.](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")

5. Indique um **Nome** para o seu segmento. Opcionalmente, indique um **Nome a apresentar**.

6. Selecione **Guardar** para criar o segmento.

7. Depois de concluído o processamento do segmento, poderá vê-lo como qualquer outro segmento que tenha criado.

## <a name="next-steps"></a>Passos seguintes

[Exporte um segmento](export-destinations.md) e explore a [integração do Cartão de Cliente](customer-card-add-in.md) para utilizar segmentos noutras aplicações.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

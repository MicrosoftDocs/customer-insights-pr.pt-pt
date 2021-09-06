---
title: Criar e gerir segmentos
description: Crie segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377802"
---
# <a name="create-and-manage-segments"></a>Criar e gerir segmentos

> [!IMPORTANT]
> Há várias alterações a serem lançadas para a experiência de criação de segmentos em setembro de 2021: 
> - O construtor de segmentos será ligeiramente diferente com elementos remodelados e um melhor fluxo de utilizador.
> - Novos operadores datetime e um seletor de datas melhorado estão ativados no construtor de segmentos.
> - Poderá adicionar ou remover condições e regras dos segmentos. 
> - As regras aninhadas que começam com uma condição OR ficarão disponíveis. Já não precisa de uma condição AND na camada mais externa.
> - Um painel lateral para selecionar atributos estará constantemente disponível.
> - Uma opção para selecionar caminhos de relação de entidade.
> Para experimentar o novo construtor de segmentos, envie um e-mail com o assunto "Request to enable the new segment builder" ("Pedido para ativar o novo construtor de segmentos") para cihelp [at] microsoft.com. Inclua o nome da sua organização e o ID do ambiente de sandbox.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do criador de segmentos." lightbox="media/segment-builder-overview.png":::
>
> 1 – Organize o seu segmento com regras e subregras. Cada regra ou subregra consiste de condições. Combine as condições com os operadores lógicos
>
> 2 – Escolha o [caminho de relação](relationships.md) entre entidades que se aplica a uma regra. O caminho da relação determina quais os atributos que podem ser usados numa condição.
>
> 3 – Faça a gestão de regras e subregras. Altere a posição de uma regra ou elimine-a.
>
> 4 – Adicione condições e crie o nível certo de aninhamento utilizando subregras.
>
> 5 – Aplique operações de conjuntos a regras ligadas.
>
> 6 – Utilize o painel de atributos para adicionar atributos de entidade disponíveis ou criar condições com base em atributos. O painel mostra a lista de entidades e atributos, com base no caminho da relação selecionada, que estão disponíveis para a regra selecionada.
>
> 7 – Adicione condições com base em atributos às regras e subregras existentes ou adicione-as a uma nova regra.
>
> 8 – Anule e refaça alterações enquanto cria o segmento.

Defina filtros complexos em torno da entidade de cliente unificado e as suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registos de clientes que pode exportar e tomar medidas. Os segmentos são geridos na página **Segmentos**. 

O exemplo seguinte ilustra a capacidade de segmentação. Definimos um segmento para os clientes que encomendaram pelo menos 500 $ de bens nos últimos 90 dias *e* que estavam envolvidos numa chamada de suporte ao cliente que foi escalada.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de ecrã da IU do construtor de segmentos com dois grupos que especificam um segmento de cliente.":::

## <a name="create-a-new-segment"></a>Criar um novo segmento

Existem várias formas de criar um novo segmento. Esta secção descreve como criar um *segmento em branco* a partir do zero. Também pode criar um *segmento rápido* baseado em entidades existentes ou fazer uso de modelos de aprendizagem automática para obter *segmentos sugeridos*. Mais informações: [Descrição geral de segmentos](segments.md).

Ao criar um segmento, pode guardar um rascunho. Será guardado como um segmento inativo e não pode ser ativado se terminado com uma configuração válida.

1. Ir para a página **Segmentos**.

1. Selecione **Novo** > **Segmento em branco**.

1. No painel **Novo segmento**, escolha um tipo de segmento:

   - **Segmentos dinâmicos** [atualizam-se](segments.md#refresh-segments) numa agenda recorrente.
   - **Segmentos estáticos** são executados uma vez quando os cria.

1. Forneça um **Nome de entidade de saída** para o segmento. Opcionalmente, forneça um nome a apresentar e uma descrição que ajude a identificar o segmento.

1. Selecione **Seguinte** para ir para a página **Construtor de segmentos** onde define um grupo. Um grupo é um conjunto de clientes.

1. Escolha a entidade que inclui o atributo pelo qual pretende segmentar.

1. Escolha o atributo pelo qual pretende segmentar. Este atributo pode ter um de quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.

1. Escolha um operador e um valor para o atributo selecionado.

   > [!div class="mx-imgBorder"]
   > ![Filtro de grupo personalizado.](media/customer-group-numbers.png "Filtro de grupo do cliente")

   |Número |Definição  |
   |---------|---------|
   |5     |Entity          |
   |2     |Atributo          |
   |3    |Operador         |
   |4    |valor         |

   1. Para adicionar mais condições a um grupo, poderá utilizar dois operadores lógicos:

      - Operador **AND**: ambas as condições têm de ser satisfeitas como parte do processo de segmentação. Esta opção é mais útil quando define condições em diferentes entidades.

      - Operador **OR**: qualquer uma das condições tem de ser satisfeita como parte do processo de segmentação. Esta opção é mais útil quando define múltiplas condições para a mesma entidade.

      > [!div class="mx-imgBorder"]
      > ![Operador OR onde qualquer condição tem de ser satisfeita.](media/segmentation-either-condition.png "Operador OR onde qualquer condição tem de ser satisfeita")

      Atualmente, é possível aninhar um operador **OR** num operador **AND**, mas não o contrário.

   1. Cada grupo corresponde a um conjunto de clientes. Pode combinar grupos para incluir os clientes necessários para o seu caso de negócio.    
   Selecione **Adicionar Grupo**.

      > [!div class="mx-imgBorder"]
      > ![Grupo de clientes – adicionar grupo.](media/customer-group-add-group.png "Grupo de clientes - adicionar grupo")

   1. Selecione um dos operadores definidos: **União**, **Intersetar** ou **Exceto**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de clientes – adicionar união.](media/customer-group-union.png "Grupo de clientes - adicionar união")

   - **União** une os dois grupos.

   - **Interseção** sobrepõe os dois grupos. Apenas os dados que *são comuns* a ambos os grupos são mantidos no grupo unificado.

   - **Exceto** combina os dois grupos. Apenas os dados do grupo A que *não são comuns* aos dados do grupo B são mantidos.

1. Se a entidade estiver ligada à entidade de cliente unificada através das [relações](relationships.md), terá de definir o caminho da relação para criar um segmento válido. Adicione as entidades a partir do caminho da relação até poder selecionar a entidade **Customer : CustomerInsights** a partir da lista pendente. Em seguida, escolha **Todos os registos** para cada passo.

   > [!div class="mx-imgBorder"]
   > ![Caminho da relação durante a criação do segmento.](media/segments-multiple-relationships.png "Caminho da relação durante a criação do segmento")

1. Por predefinição, os segmentos geram uma entidade de saída que contém todos os atributos dos perfis de cliente que correspondem aos filtros definidos. Se um segmento se basear noutras entidades diferentes da entidade *Cliente*, pode adicionar mais atributos destas entidades à entidade de saída. Selecione **Atributos do projeto** para escolher os atributos que serão acrescentados à entidade de saída.  
  
   Exemplo: Um segmento baseia-se numa entidade que contém os dados de atividade do cliente que estão relacionados com a entidade *Cliente*. O segmento procura todos os clientes que ligaram para o suporte técnico nos últimos 60 dias. Pode optar por acrescentar a duração da chamada e o número de chamadas a todos os registos de clientes correspondentes na entidade de saída. Esta informação pode ser útil para enviar um e-mail com ligações úteis para artigos de ajuda online e FAQs aos clientes que ligaram com frequência.

   > [!NOTE]
   > - Os atributos projetados só funcionam para entidades que têm uma relação de um-para-muitos com a entidade de cliente. Por exemplo, um cliente pode ter várias subscrições.
   > - Só é possível projetar atributos de uma entidade que é utilizada em todos os grupos de consultas de segmento que está a criar.
   > - Os atributos projetados são contabilizados quando utiliza operadores definidos.

1. Selecione **Guardar** para guardar o segmento. O seu segmento será guardado e processado se todos os requisitos forem validados. Caso contrário, será guardado como rascunho.

1. Selecione **Regressar a segmentos** para regressar à página **Segmentos**.



## <a name="quick-segments"></a>Segmentos rápidos

Segmentos rápidos permitem criar segmentos simples com um único operador rapidamente para informações mais rápidas.

1. Na página **Segmentos**, selecione **Novo** > **Criar de**.

   - Selecione a opção **Perfis** para criar um segmento baseado na entidade de *cliente unificado*.
   - Selecione a opção **Medidas** para criar um segmento em torno de medidas que criou anteriormente.
   - Selecione a opção **Inteligência** para criar um segmento à volta de uma das entidades de saída geradas com as capacidades **Predições** ou **Modelos Personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo na lista pendente **Campo**.

3. O sistema fornecerá algumas informações adicionais que o ajudam a criar melhores segmentos dos seus clientes.
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

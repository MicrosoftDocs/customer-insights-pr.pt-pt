---
title: Criar e gerir segmentos
description: Crie segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270370"
---
# <a name="create-and-manage-segments"></a>Criar e gerir segmentos

Os segmentos permitem-lhe agrupar os seus clientes com base em atributos demográficos, transacionais, ou comportamentais. Pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para alcançar os seus objetivos de negócio.

Poderá definir filtros complexos à volta da entidade Perfil de Cliente e das entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registos de clientes que pode exportar e tomar medidas. Aplicam-se alguns [limites de serviço](service-limits.md).

Salvo indicação em contrário, todos os segmentos são **Segmentos dinâmicos**, que são atualizados num horário recorrente.

O exemplo seguinte ilustra a capacidade de segmentação. Definimos um segmento para os clientes que encomendaram pelo menos 500 $ de bens nos últimos 90 dias *e* que estavam envolvidos numa chamada de suporte ao cliente que foi escalada.

> [!div class="mx-imgBorder"]
> ![Múltiplos grupos](media/segmentation-group1-2.png "Múltiplos grupos")

## <a name="create-a-new-segment"></a>Criar um novo segmento

Os segmentos são geridos na página **Segmentos**.

1. Nas informações de audiência, vá à página **Segmentos**.

2. Selecione **Novo** > **Segmento em branco**.

3. No painel **Novo segmento**, escolha um tipo de segmento e atribua um **Nome**.

   Opcionalmente, forneça um nome a apresentar e uma descrição que ajude a identificar o segmento.

4. Selecione **Seguinte** para ir para a página **Construtor de segmentos** onde define um grupo. Um grupo é um conjunto de clientes.

5. Escolha a entidade que inclui o atributo pelo qual pretende segmentar.

6. Escolha o atributo pelo qual pretende segmentar. Este atributo pode ter um de quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.

7. Escolha um operador e um valor para o atributo selecionado.

   > [!div class="mx-imgBorder"]
   > ![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo do cliente")

   |Número |Definição  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atributo          |
   |3    |Operador         |
   |4    |valor         |

8. Se a entidade estiver ligada à entidade de cliente unificada através das [relações](relationships.md), terá de definir o caminho da relação para criar um segmento válido. Adicione as entidades a partir do caminho da relação até poder selecionar a entidade **Customer : CustomerInsights** a partir da lista pendente. Em seguida, escolha **Todos os registos** para cada condição.

   > [!div class="mx-imgBorder"]
   > ![Caminho da relação durante a criação do segmento](media/segments-multiple-relationships.png "Caminho da relação durante a criação do segmento")

9. Selecione **Guardar** para guardar o segmento. O seu segmento será guardado e processado se todos os requisitos forem validados. Caso contrário, será guardado como rascunho.

10. Selecione **Regressar a segmentos** para regressar à página **Segmentos**.

## <a name="manage-existing-segments"></a>Gerir segmentos existentes

Na página **Segmentos**, pode ver todos os segmentos guardados e geri-los.

Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.

Pode ordenar os segmentos numa coluna ao selecionar o cabeçalho da coluna.

Utilize a caixa de **Pesquisa** no canto superior direito para filtrar os segmentos.

> [!div class="mx-imgBorder"]
> ![Opções para gerir um segmento existente](media/segments-selected-segment.png "Opções para gerir um segmento existente")

A seguinte ação está disponível quando seleciona um segmento:

- **Ver** os detalhes do segmento, incluindo a tendência da contagem de membros e uma pré-visualização dos membros do segmento.
- **Editar** o segmento para alterar as respetivas propriedades.
- **Atualizar** o segmento para incluir os dados mais recentes.
- **Ativar** ou **desativar** o segmento. Os segmentos têm dois estados possíveis – ativos ou inativos. Estes estados são úteis ao editar um segmento. Para segmentos inativos, a definição de segmento existe, mas ainda não contém nenhum cliente. Quando ativa um segmento, o seu estado muda de "inativo" para "ativo" e começa a procurar clientes que correspondam à definição do segmento. Se uma [atualização agendada](system.md#schedule-tab) for configurada, os segmentos inativos têm o **Estado** listado como **Ignorado** indicando que uma atualização nem sequer foi tentada. Quando um segmento inativo é ativado, ele irá atualizar e será incluído em atualizações agendadas.
  Em alternativa, pode utilizar a funcionalidade **Agendar mais tarde** no menu pendente **Ativar/Desativar** para especificar uma data e hora futuras para ativação e desativação de um determinado segmento.
- **Mudar nome** do segmento.
- **Transferir** a lista de membros como um ficheiro .CSV.
- A opção **Adicionar a** envia a lista de IDs do cliente no segmento para processamento noutra aplicação.
- **Eliminar** o segmento.

## <a name="refresh-segments"></a>Atualizar segmentos

Pode atualizar todos os segmentos de uma só vez selecionando **Atualizar tudo** na página **Segmentos** ou pode atualizar um ou vários segmentos quando os seleciona e escolher **Atualizar** nas opções. Em alternativa, poderá configurar uma atualização recorrente em **Administração** > **Sistema** > **Agendar**.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="download-and-export-segments"></a>Transferir e exportar segmentos

Poderá transferir os seus segmentos para um ficheiro CSV ou exportá-los para o Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Transferir segmentos para um ficheiro CSV

1. Nas informações de audiência, vá à página **Segmentos**.

2. Selecione as reticências no mosaico de um segmento específico.

3. Selecione **Transferir como CSV** na lista pendente de ações.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportar segmentos para o Dynamics 365 Sales

Antes de exportar os segmentos para o Dynamics 365 Sales, um administrador precisa de [criar o destino de exportação](export-destinations.md) para o Dynamics 365 Sales.

1. Nas informações de audiência, vá à página **Segmentos**.

2. Selecione as reticências no mosaico de um segmento específico.

3. Selecione **Adicionar a** na lista pendente de ações e selecione o destino de exportação para o qual pretende enviar os dados.

## <a name="draft-mode-for-segments"></a>Modo Rascunho para segmentos

Se nem todos os requisitos para processar um segmento forem satisfeitos, pode guardar o segmento como rascunho e aceder ao mesmo na página **Segmentos**.

Será guardado como um segmento inativo e não poderá ser ativado enquanto não for válido.

## <a name="add-more-conditions-to-a-group"></a>Adicionar mais condições a um grupo

Para adicionar mais condições a um grupo, poderá utilizar dois operadores lógicos:

- Operador **AND**: ambas as condições têm de ser satisfeitas como parte do processo de segmentação. Esta opção é mais útil quando define condições em diferentes entidades.

- Operador **OR**: qualquer uma das condições tem de ser satisfeita como parte do processo de segmentação. Esta opção é mais útil quando define múltiplas condições para a mesma entidade.

   > [!div class="mx-imgBorder"]
   > ![Operador OR onde qualquer condição tem de ser satisfeita](media/segmentation-either-condition.png "Operador OR onde qualquer condição tem de ser satisfeita")

Atualmente, é possível aninhar um operador **OR** num operador **AND**, mas não o contrário.

## <a name="combine-multiple-groups"></a>Combinar múltiplos grupos

Cada grupo produz um conjunto de clientes específico. Poderá combinar estes grupos para incluir os clientes necessários para o seu caso de negócio.

1. Nas informações de audiência, aceda à página **Segmentos** e selecione um segmento.

2. Selecione **Adicionar Grupo**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de clientes - adicionar grupo](media/customer-group-add-group.png "Grupo de clientes - adicionar grupo")

3. Selecione um dos seguintes operadores de definição: **União**, **Interseção** ou **Exceto**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de clientes - adicionar união](media/customer-group-union.png "Grupo de clientes - adicionar união")

   Selecione um operador de definição para definir um novo grupo. Guardar diferentes grupos para determinar que dados são retidos:

   - **União** une os dois grupos.

   - **Interseção** sobrepõe os dois grupos. Apenas os dados que *são comuns* a ambos os grupos são mantidos no grupo unificado.

   - **Exceto** combina os dois grupos. Apenas os dados do grupo A que *não são comuns* aos dados do grupo B são mantidos.

## <a name="view-processing-history-and-segment-members"></a>Ver histórico de processamento e membros do segmento

Poderá ver os dados consolidados sobre um segmento ao analisar os respetivos detalhes.

Na página **Segmentos**, selecione o segmento que pretende analisar.

A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros. Passe o rato sobre os pontos de dados para ver a contagem de membros numa data específica.

Poderá atualizar o intervalo de tempo da visualização.

> [!div class="mx-imgBorder"]
> ![Intervalo de tempo do segmento](media/segment-time-range.png "Intervalo de tempo do segmento")

A parte inferior contém uma lista dos membros do segmento.

> [!NOTE]
> Os campos apresentados nesta lista baseiam-se nos atributos das entidades do segmento.
>
>A lista é uma pré-visualização dos membros do segmento correspondente e mostra os primeiros 100 registos do seu segmento para poder avaliá-lo rapidamente e rever as definições, se for necessário. Para ver todos os registos correspondentes, tem de [exportar o segmento](export-destinations.md).

## <a name="quick-segments"></a>Segmentos rápidos

Para além do construtor de segmentos, há outro caminho para a criação de segmentos. Os segmentos rápidos permitem criar segmentos simples (com um único operador) rapidamente e com informações instantâneas.

1. Na página **Segmentos**, selecione **Novo** > **Criar rapidamente a partir de**.

   - Selecione a opção **Perfis** para criar um segmento baseado na entidade Cliente unificado.
   - Selecione a opção **Medidas** para criar um segmento à volta de cada tipo de Atributo de Cliente das medidas que criou anteriormente na página **Medidas**.
   - Selecione a opção **Inteligência** para criar um segmento à volta de uma das entidades de saída geradas com as capacidades **Predições** ou **Modelos Personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo na lista pendente **Campo**.

3. O sistema fornecerá algumas informações adicionais que o ajudam a criar melhores segmentos dos seus clientes.
   - Para campos categóricos, mostraremos as 10 melhores contagens de clientes. Escolha um **Valor** e selecione **Rever**.

   - Para um atributo numérico, o sistema mostrará que valor do atributo se situa no percentil de cada cliente. Escolha um **Operador** e um **Valor** e, em seguida, selecione **Rever**.

4. O sistema fornecerá um **Tamanho do segmento estimado**. Poderá selecionar se pretende gerar ou não o segmento que definiu ou, primeiro, revisitá-lo para obter um tamanho de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nome e estimativa para um segmento rápido](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")

5. Indique um **Nome** para o seu segmento. Opcionalmente, indique um **Nome a apresentar**.

6. Selecione **Guardar** para criar o segmento.

7. Depois de concluído o processamento do segmento, poderá vê-lo como qualquer outro segmento que tenha criado.

Para os cenários seguintes, recomendamos a utilização do construtor de segmentos em vez da funcionalidade de segmentos recomendada:

- Criar segmentos com filtros em campos categóricos onde o operador é diferente do operador **É**
- Criar segmentos com filtros em campos numéricos onde o operador é diferente dos operadores **Entre**, **Maior que** e **Menor que**
- Criar segmentos com filtros nos campos de tipo de data

## <a name="next-steps"></a>Passos seguintes

[Exportar um segmento](export-destinations.md) e explore a [Ficha de Cliente](customer-card-add-in.md) e [Conectores](export-power-bi.md) para obter informações a nível do cliente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
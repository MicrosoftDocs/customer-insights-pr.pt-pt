---
title: Criar e editar medidas
description: Defina medidas relacionadas com os clientes para analisar e refletir o desempenho de determinadas áreas de negócio.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406648"
---
# <a name="define-and-manage-measures"></a>Definir e gerir medidas

**Medidas** representa os indicadores de desempenho-chave (KPIs) que refletem o desempenho e o estado de áreas de negócio específicas. As informações da audiência proporcionam uma experiência intuitiva para a construção de diferentes tipos de medidas, utilizando um construtor de questões que não exige que codifique ou valide manualmente as suas medidas. Pode monitorizar as medidas de negócio na **Home** page, ver as medidas para clientes específicos na **Ficha de Cliente** e utilizar medidas para definir segmentos de clientes na página **Segmentos**.

## <a name="create-a-measure"></a>Criar uma medida

Esta secção orienta-o ao longo da criação de uma medida de raiz. Pode criar medidas com dados de várias origens de dados que estão ligadas através da entidade Cliente. Aplicam-se alguns [limites de serviço](service-limits.md).

1. Nas informações de audiência, vá a **Medidas**.

2. Selecione **Nova medida**.

3. Escolha a medida **Tipo**:

   - **Atributo de cliente**: um único campo por cliente que reflete uma classificação, valor ou estado para o cliente. Os atributos de cliente são criados como atributos numa nova entidade gerada pelo sistema denominada **Medida de Cliente**.

   - **Medida de cliente**: informações sobre o comportamento do cliente discriminadas pelas dimensões selecionadas. É gerada uma nova entidade para cada medida, potencialmente com vários registos por cliente.

   - **Medida de negócio**: monitoriza o desempenho e o estado do negócio. As medidas de negócio podem ter duas saídas diferentes: uma saída numérica que é mostrada na **Home** ou uma nova entidade que está disponível na página **Entidades**.

4. Forneça um **Nome** e um **Nome a apresentar** opcional e, depois, selecione **Seguinte**.

5. Na secção **Entidades**, selecione a primeira entidade na lista pendente. Neste ponto, deve decidir se são necessárias entidades adicionais como parte da definição da medida.

   > [!div class="mx-imgBorder"]
   > ![Definição da medida](media/measure-definition.png "Definição da medição")

   Para adicionar mais entidades, selecione **Adicionar entidade** e selecione as entidades que pretende utilizar para a medida.

   > [!NOTE]
   > Só pode selecionar as entidades que tenham relações com a entidade inicial. Para mais informações sobre como definir relações, consulte [Relações](relationships.md).

6. Opcionalmente, pode configurar variáveis. Na secção **Variáveis**, selecione **Nova variável**.

   As variáveis são cálculos efetuados em cada um dos registos selecionados. Por exemplo, somar as vendas do ponto de venda (POS) e online para cada um dos registos dos seus clientes.

7. Forneça um **Nome** para a variável.

8. Na área **Expressão**, escolha um campo com o qual iniciar o cálculo.

9. Introduza uma expressão na área **Expressão** ao mesmo tempo que escolhe mais campos a incluir no cálculo.

   > [!NOTE]
   > Atualmente, apenas as expressões aritméticas são suportadas. Além disso, o cálculo da variável não é suportado para as entidades de diferentes [caminhos de entidade](relationships.md).

10. Selecione **Concluído**.

11. Na secção **Definição da medida**, defina como as entidades escolhidas e as variáveis calculadas são agregadas num novo atributo ou entidade de medida.

12. Selecione **Nova dimensão**. Pode encarar uma dimensão como uma função *agrupar por*. A saída de dados do seu atributo ou entidade Medida será agrupada por todas as suas dimensões definidas.

    > [!div class="mx-imgBorder"]
    > ![Escolher ciclo agregado](media/measures-businessreport-measure-definition2.png "Escolher ciclo agregado")

    Selecione ou introduza as seguintes informações como parte da definição da sua dimensão:

    - **Entidade**: se definir uma entidade Medida, deverá incluir pelo menos um atributo. Se definir um atributo Medida, incluirá apenas um atributo por predefinição. Esta seleção pretende escolher a entidade que inclui esse atributo.
    - **Campo**: escolha o atributo específico a incluir no atributo ou entidade Medida.
    - **Registo**: escolha se pretende agregar dados numa base diária, mensal ou anual. Trata-se de uma seleção necessária apenas se tiver selecionado um atributo de Tipo de data.
    - **Como**: define o nome do novo campo.
    - **Nome a apresentar**: define o nome a apresentar do campo.

    > [!NOTE]
    > A medida de negócio será guardada como uma entidade de número único e será apresentada na **Home** page, a menos que adicione mais dimensões à medida. Depois de adicionar mais dimensões, a medida *não* será mostrada na **Home** page.

13. Opcionalmente, adicione funções de agregação. Qualquer agregação que crie resulta num novo valor no atributo ou entidade Medidas. As funções de agregação suportadas são: **Mín**, **Máx**, **Média**, **Mediana**, **Soma**, **Contagem Exclusiva**, **Primeiro** (assume o primeiro registo de um valor de dimensão) e **Último** (assume o último registo adicionado a um valor de dimensão).

14. Selecione **Guardar** para aplicar as alterações à medida.

## <a name="manage-your-measures"></a>Gerir as medidas

Depois de criar pelo menos uma medida, verá uma lista de medidas na página **Medidas**.

Encontrará informações sobre o tipo de medida, o criador, a data e hora de criação, a data e hora da última edição, o estado (se a medida está ativa, inativo ou com falhas), e a data e hora da última atualização. Quando selecionar uma medida a partir da lista, poderá ter uma pré-visualização da respetiva saída.

Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.

> [!div class="mx-imgBorder"]
> ![Ações para gerir medidas únicas](media/measure-actions.png "Ações para gerir medidas únicas")

Em alternativa, selecione uma medida a partir da lista e execute uma das seguintes ações:

- Selecione o nome da medida para ver os respetivos detalhes.
- **Edite** a configuração da medida.
- **Mude o nome** da medida.
- **Elimine** a medição.
- Selecione as reticências (...) e, em seguida, **Atualizar** para iniciar o processo de atualização para a medida.
- Selecione as reticências (...) e, em seguida, **Transferir** para obter um ficheiro CSV da medida.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="next-step"></a>Passo seguinte

Pode utilizar as medidas existentes para criar o seu primeiro segmento de cliente na página **Segmentos**. Para mais informações, consulte [Segmentos](segments.md).

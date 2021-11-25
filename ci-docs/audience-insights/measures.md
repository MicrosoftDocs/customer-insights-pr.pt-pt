---
title: Criar e gerir medidas
description: Defina medidas para analisar e refletir o desempenho do seu negócio.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f6be11bd97be71bc0c3a58eaee4d8ed45f535877
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732740"
---
# <a name="define-and-manage-measures"></a>Definir e gerir medidas

As medidas ajudam-no a compreender melhor os comportamentos dos clientes e o desempenho do negócio. Olham para os valores relevantes dos [perfis unificados](data-unification.md). Por exemplo, uma empresa quer ver o *gasto total por cliente* para entender o histórico de compras de um cliente individual ou medir as *vendas totais da empresa* para entender a receita ao nível agregado de todo o negócio.  

As medidas são criadas utilizando o criador de medidas, uma plataforma de consulta de dados com vários operadores e opções simples de mapeamento. Permite filtrar os dados, agrupar os resultados, detetar [caminhos de relações entres entidades](relationships.md) e pré-visualizar a saída.

Utilize o criador de medidas para planear as atividades empresariais consultando os dados dos clientes e extraindo informações. Por exemplo, criar uma medida de *gasto total por cliente* e *devoluções totais por cliente* ajuda a identificar um grupo de clientes com elevado gasto mas com elevadas devoluções também. Pode [criar um segmento](segments.md) para impulsionar as próximas melhores ações. 

## <a name="build-your-own-measure-from-scratch"></a>Criar a sua própria medida de raiz

Esta secção acompanha-o através da criação de uma nova medida a partir do zero. Pode criar uma medida com atributos de dados de entidades de dados que tenham uma relação configurada para se ligar à entidade do perfil do cliente unificado.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

1. Nas informações de audiência, vá a **Medidas**.

1. Selecione **Nova** e escolha **Criar a sua própria**.

1. Selecione **Editar nome** e forneça um **Nome** para a medida. 

1. Na área de configuração, escolha a função de agregação no menu pendente **Selecionar Função**. As funções de agregação incluem: 
   - **Sum**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máx.**
   - **Min**
   - **Primeiro:** pega no primeiro valor do registo de dados
   - **Último**: pega no último valor que foi adicionado ao registo de dados

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.
   
   1. Selecione o separador **Atributos**. 
   1. Entidade de dados: escolha a entidade que inclui o atributo que pretende medir. 
   1. Atributo de dados: escolha o atributo que pretende utilizar na função agregação para calcular a medida. Só pode selecionar um atributo de cada vez.
   1. Também pode selecionar um atributo de dados a partir de uma medida existente selecionando o separador **Medidas**, ou pode procurar uma entidade ou um nome de medida. 
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecionar um atributo a usar em cálculos.":::

1. Para criar medidas mais complexas, pode adicionar mais atributos ou utilizar operadores de matemática na sua função de medida.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Criar uma medida complexa com operadores de matemática.":::

1. Para adicionar filtros, selecione **Filtro** na área de configuração. 
  
   1. Na secção **Adicionar atributo** do painel **Filtros**, selecione o atributo que pretende utilizar para criar filtros.
   1. Defina os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Para adicionar dimensões, selecione **Dimensão** na área de configuração. Dimensões mostrarão como colunas na entidade de saída da medida.
 
   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais pretende agrupar os valores da medida. Por exemplo, cidade ou sexo. Por predefinição, a dimensão *CustomerID* é selecionada para criar *medidas ao nível do cliente*. Pode remover a dimensão predefinida se pretender criar *medidas ao nível do negócio*.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores nos seus dados que precisa de substituir por um número inteiro, selecione **Regras**. Configure a regra e certifique-se de que escolhe apenas números inteiros como substitutos. Por exemplo, substitua *nulo* por *0*.

1. Se existirem múltiplos caminhos entre a entidade de dados que mapeou e a entidade *Cliente*, tem de escolher um dos [caminhos de relação entre entidades identificados](relationships.md). Os resultados da medida podem variar dependendo do caminho selecionado. 
   
   1. Selecione **Caminho da relação** e escolha o caminho da entidade que deve ser utilizado para identificar a sua medida. Se houver apenas um único caminho para a entidade *Cliente*, este controlo não aparecerá.
   1. Selecione **Concluído** para aplicar a sua seleção. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecionar o caminho da entidade para a medida.":::

1. Para adicionar mais cálculos para a medida, selecione **Novo cálculo**. Só é possível utilizar entidades no mesmo caminho da entidade para novos cálculos. Mais cálculos mostrarão como novas colunas na entidade de saída da medida.

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Pré-visualização**, verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A pré-visualização reage dinamicamente a alterações na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Guardar e fechar** se pretender manter a configuração atual e executar a medida mais tarde.

1. Vá a **Medidas** para ver a nova medida criada na lista.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

1. Nas informações de audiência, vá a **Medidas**.

1. Selecione **Nova** e escolha **Criar a sua própria**.

1. Selecione **Editar nome** e forneça um **Nome** para a medida. 

1. Na área de configuração, escolha a função de agregação no menu pendente **Selecionar Função**. As funções de agregação incluem: 
   - **Sum**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máx.**
   - **Min**
   - **Primeiro:** pega no primeiro valor do registo de dados
   - **Último**: pega no último valor que foi adicionado ao registo de dados

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.
   
   1. Selecione o separador **Atributos**. 
   1. Entidade de dados: escolha a entidade que inclui o atributo que pretende medir. 
   1. Atributo de dados: escolha o atributo que pretende utilizar na função agregação para calcular a medida. Só pode selecionar um atributo de cada vez.
   1. Também pode selecionar um atributo de dados a partir de uma medida existente selecionando o separador **Medidas**, ou pode procurar uma entidade ou um nome de medida. 
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecionar um atributo a usar em cálculos.":::

1. Para criar medidas mais complexas, pode adicionar mais atributos ou utilizar operadores de matemática na sua função de medida.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Criar uma medida complexa com operadores de matemática.":::

1. Para adicionar filtros, selecione **Filtro** na área de configuração. 
  
   1. Na secção **Adicionar atributo** do painel **Filtros**, selecione o atributo que pretende utilizar para criar filtros.
   1. Defina os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Para adicionar dimensões, selecione **Dimensão** na área de configuração. Dimensões mostrarão como colunas na entidade de saída da medida.
 
   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais pretende agrupar os valores da medida. Por exemplo, cidade ou sexo. Por predefinição, a dimensão *CustomerID* é selecionada para criar *medidas ao nível do cliente*. Pode remover a dimensão predefinida se pretender criar *medidas ao nível do negócio*.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores nos seus dados que precisa de substituir por um número inteiro, selecione **Regras**. Configure a regra e certifique-se de que escolhe apenas números inteiros como substitutos. Por exemplo, substitua *nulo* por *0*.

1. Pode utilizar o seletor **Fazer rollup de subcontas** se [utilizar contas com hierarquias](relationships.md#set-up-account-hierarchies).
   - Se estiver definido como **Desligado**, a medida é calculada para cada conta. Cada conta obtém o seu próprio resultado.
   - Se estiver definido como **Ligado**, selecione **Editar** para escolher a hierarquia de contas de acordo com as hierarquias ingeridas. A medida produzirá apenas um resultado porque está agregada a subcontas.

1. Se existirem múltiplos caminhos entre a entidade de dados que mapeou e a entidade *Cliente*, tem de escolher um dos [caminhos de relação entre entidades identificados](relationships.md). Os resultados da medida podem variar dependendo do caminho selecionado. 
   
   1. Selecione **Caminho da relação** e escolha o caminho da entidade que deve ser utilizado para identificar a sua medida. Se houver apenas um único caminho para a entidade *Cliente*, este controlo não aparecerá.
   1. Selecione **Concluído** para aplicar a sua seleção. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecionar o caminho da entidade para a medida.":::

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Pré-visualização**, verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A pré-visualização reage dinamicamente a alterações na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Guardar e fechar** se pretender manter a configuração atual e executar a medida mais tarde.

1. Vá a **Medidas** para ver a nova medida criada na lista.

---

## <a name="use-a-template-to-build-a-measure"></a>Utilize um modelo para criar uma medida

Pode utilizar modelos predefinidos de medidas utilizadas frequentemente para criá-las. Descrições detalhadas dos modelos e uma experiência guiada ajudam-no com a criação de medidas eficientes. Os modelos são criados a partir de dados mapeados da entidade de *Atividade Unificada*. Por isso, certifique-se de que configurou [atividades de cliente](activities.md) antes de criar uma medida a partir de um modelo.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Pode utilizar modelos predefinidos de medidas utilizadas frequentemente para criá-las. Descrições detalhadas dos modelos e uma experiência guiada ajudam-no com a criação de medidas eficientes. Os modelos são criados a partir de dados mapeados da entidade de *Atividade Unificada*. Por isso, certifique-se de que configurou [atividades de cliente](activities.md) antes de criar uma medida a partir de um modelo.

Modelos de medidas disponíveis: 
- Valor médio da transação (ATV)
- Valor total das transações
- Receita média diária
- Receita média anual
- Contagem de transações
- Pontos de fidelização ganhos
- Pontos de fidelização resgatados
- Saldo de pontos de fidelização
- Período de tempo ativo do cliente
- Duração da adesão à fidelidade
- Tempo desde a última compra

O procedimento a seguir descreve os passos para criar uma nova medida utilizando um modelo.

1. Nas informações de audiência, vá a **Medidas**.

1. Selecione **Novo** e, em seguida, selecione **Escolher um modelo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de ecrã do menu pendente ao criar uma nova medida com destaque no modelo.":::

1. Encontre o modelo que se adequa à sua necessidade e selecione **Escolher modelo**.

1. Reveja os dados necessários e selecione **Começar** se tiver todos os dados preparados.

1. No painel **Editar nome**, defina o nome da sua medida e a entidade de saída. 

1. Selecione **Concluído**.

1. Na secção **Definir período de tempo**, defina o período de tempo dos dados a utilizar. Escolha se pretende que a nova medida cubra todo o conjunto de dados selecionando **Sempre** ou se pretende que a medida se concentre num **Período de tempo específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de ecrã a mostrar a secção do período de tempo ao configurar uma medida a partir de um modelo.":::

1. Na secção seguinte, selecione **Adicionar dados** para escolher as atividades e mapear os dados correspondentes da sua entidade *Atividade Unificada*.

    1. Passo 1 de 2: sob **Tipo de atividade**, escolha o tipo de entidade que pretende utilizar. Para **Atividades**, selecione as entidades que pretende mapear.
    1. Passo 2 de 2: escolha o atributo da entidade *Atividade Unificada* para o componente exigido pela fórmula. Por exemplo, para o valor de transação Médio, é o atributo que representa o valor da Transação. Para **Carimbo data/hora da atividade**, escolha o atributo da entidade Atividade Unificada que representa a data e a hora da atividade.
   
1. Quando o mapeamento de dados for bem sucedido, pode ver o estado como **Concluído** e o nome das atividades e atributos mapeados.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de ecrã de uma configuração de modelo de medida concluída.":::

1. Agora pode selecionar **Executar** para calcular os resultados da medida. Para refiná-la mais tarde, selecione **Guardar rascunho**.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Esta funcionalidade apenas está disponível para medidas criadas em ambientes com clientes individuais como a audiência alvo principal.

---

## <a name="manage-your-measures"></a>Gerir as medidas

Pode encontrar a lista de medidas na página **Medidas**.

Encontrará informações sobre o tipo de medida, o criador, data de criação e estado. Quando selecionar uma medida da lista, pode pré-visualizar a saída e transferir um ficheiro CSV.

Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.

> [!div class="mx-imgBorder"]
> ![Ações para gerir medidas únicas.](media/measure-actions.png "Ações para gerir medidas únicas.")

Selecione uma medida da lista para as seguintes opções:

- Selecione o nome da medida para ver os respetivos detalhes.
- **Edite** a configuração da medida.
- **Atualize** a medida com base nos dados mais recentes.
- **Mude o nome** da medida.
- **Elimine** a medição.
- **Ativar** ou **Desativar**. As medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Próximo passo

Pode utilizar as medidas existentes para criar [um segmento de cliente](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]

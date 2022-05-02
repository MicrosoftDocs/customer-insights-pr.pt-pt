---
title: Criar novas medidas com o construtor de medidas
description: Criar medidas de raiz para analisar métricas chave sobre o seu negócio.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647284"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Utilizar o construtor de medidas para criar medidas de raiz

Este artigo explica como deve criar uma nova [medida](measures.md) de raiz. O construtor de medidas permite definir cálculos usando operadores de matemática, funções de agregação e filtros. Pode construir uma medida com atributos de entidades relacionadas com a entidade de *Cliente* unificado.

A criação de medidas em ambientes B2C e B2B funciona da mesma forma. No entanto, se o seu ambiente B2B [utilizar contas com hierarquias](relationships.md#set-up-account-hierarchies), pode optar por agregar a medida através de subcontas relacionadas.

Também pode criar uma medida de forma rápida, escolhendo a partir de um conjunto de medidas habitualmente usadas e predefinidas. Para obter mais informações, consulte [Utilizar um modelo para construir uma medida](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Pode criar medidas ao nível de clientes individuais (atributo do cliente, medida do cliente) ou ao nível da empresa/organização (medida de negócio). O atributo do cliente e a medida do cliente são dois tipos que lhe permitem monitorizar o desempenho por cliente. Por exemplo, o total gasto por cada cliente. As medidas de negócio permitem-lhe monitorizar o desempenho por negócio. Por exemplo, o total de receitas da empresa.

- Atributo do cliente: gera a saída como um novo atributo, que é guardado como uma nova coluna na entidade gerada pelo sistema chamada *Customer_Measure*. Ao atualizar um atributo do cliente, todos os outros atributos do cliente na entidade *Customer_Measure* são atualizados simultaneamente. Além disso, os atributos do cliente são apresentados no cartão de perfil do cliente. Uma vez executado ou guardado o atributo do cliente, o utilizador não pode alterá-lo para uma medida do cliente.

- Medida do cliente: gera a saída como a sua entidade própria e o utilizador não pode alterá-la para um atributo do cliente, uma vez executado ou guardado. As medidas do cliente não aparecem no cartão de perfil do cliente.

- Medida de negócio: gera a saída como a sua entidade própria e mostra na página inicial do seu ambiente Customer Insights.

1. Va a **Medidas**.

1. Selecione **Nova** e escolha **Criar a sua própria**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Ecrã de configuração vazio para uma medida B2C. " lightbox="media/measure-b2c.png":::

1. Para monitorizar o desempenho ao nível do negócio, mude o comutador **Tipo de medida** para **Nível do negócio**. Por predefinição, está selecionado **Nível do cliente**. **Nível de cliente** adiciona automaticamente o atributo *CustomerId* a Dimensões, enquanto o **Nível do negócio** remove-o automaticamente.

1. Na área de configuração, escolha a função de agregação no menu pendente **Selecionar função**. As funções de agregação incluem:
   - **Sum**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máx.**
   - **Min**
   - **Primeiro:** pega no primeiro valor do registo de dados
   - **Último**: pega no último valor que foi adicionado ao registo de dados
   - **ArgMax**: encontra o registo de dados dando o valor máximo de uma função de destino
   - **ArgMin**: encontra o registo de dados dando o valor mínimo de uma função de destino

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.

   1. Selecione o separador **Atributos**.
   1. Entidade de dados: escolha a entidade que inclui o atributo que pretende medir.
   1. Atributo de dados: escolha o atributo que pretende utilizar na função agregação para calcular a medida. Só pode selecionar um atributo de cada vez.
   1. Também pode selecionar um atributo de dados a partir de uma medida existente selecionando o separador **Medidas**, ou pode procurar uma entidade ou um nome de medida.
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

1. Para criar medidas mais complexas, pode adicionar mais atributos ou utilizar operadores de matemática na sua função de medida.

1. Para adicionar filtros, selecione **Filtro** na área de configuração. A aplicação de filtros utilizará apenas os registos que correspondam aos filtros para calcular a medida.
  
   1. Na secção **Adicionar atributo** do painel **Filtros**, selecione o atributo que pretende utilizar para criar filtros.
   1. Defina os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Selecione **Dimensão** para escolher mais campos que são adicionados como colunas à entidade de saída da medida.

   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais pretende agrupar os valores da medida. Por exemplo, cidade ou sexo.
   > [!TIP]
   > Se tiver selecionado **Nível do cliente** como o **Tipo de Medida**, o atributo *CustomerId* foi já adicionado. Se remover o atributo, o comutador **Tipo de medida** muda para **Nível do negócio**.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores nos seus dados que precisa de substituir por um número inteiro, selecione **Regras**. Configure a regra e certifique-se de que escolhe apenas números inteiros como substitutos. Por exemplo, substitua *nulo* por *0*.

1. Se existirem múltiplos caminhos entre a entidade de dados que mapeou e a entidade *Cliente*, tem de escolher um dos [caminhos de relação entre entidades identificados](relationships.md). Os resultados da medida podem variar dependendo do caminho selecionado.

   1. Selecione **Caminho da relação** e escolha o caminho da entidade que deve ser utilizado para identificar a sua medida. Se houver apenas um único caminho para a entidade *Cliente*, este controlo não aparecerá.
   1. Selecione **Concluído** para aplicar a sua seleção.

1. Para adicionar mais cálculos para a medida, selecione **Novo cálculo**. Só é possível utilizar entidades no mesmo caminho da entidade para novos cálculos. Mais cálculos mostrarão como novas colunas na entidade de saída da medida.

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Pré-visualização**, verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A pré-visualização reage dinamicamente a alterações na configuração.

1. Selecione **Editar detalhes** junto de Medida sem título. Forneça um nome para a medida. Opcionalmente, adicione [etiquetas](work-with-tags-columns.md#manage-tags) à medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Caixa de diálogo Editar detalhes.":::

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Guardar e fechar** se pretender manter a configuração atual e executar a medida mais tarde.

1. Vá a **Medidas** para ver a nova medida criada na lista.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Pode criar medidas ao nível de contas individuais (medida do cliente) ou ao nível de todas as contas (medida de negócio).

- Medida do cliente: gera a saída como a sua entidade própria. As medidas do cliente não aparecem no cartão de perfil do cliente.

- Medida de negócio: gera a saída como a sua entidade própria e mostra na página inicial do seu ambiente Customer Insights.

1. Va a **Medidas**.

1. Selecione **Novo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Ecrã de configuração vazio para uma medida B2B. ":::

1. Na área de configuração, escolha a função de agregação no menu pendente **Selecionar função**. As funções de agregação incluem:
   - **Sum**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máx.**
   - **Min**
   - **Primeiro:** pega no primeiro valor do registo de dados
   - **Último**: pega no último valor que foi adicionado ao registo de dados

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.

   1. Selecione o separador **Atributos**.
   1. Entidade de dados: escolha a entidade que inclui o atributo que pretende medir.
   1. Atributo de dados: escolha o atributo que pretende utilizar na função agregação para calcular a medida. Só pode selecionar um atributo de cada vez.
   1. Também pode selecionar um atributo de dados a partir de uma medida existente selecionando o separador **Medidas**, ou pode procurar uma entidade ou um nome de medida.
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

1. Para criar medidas mais complexas, pode adicionar mais atributos ou utilizar operadores de matemática na sua função de medida.

1. Para adicionar filtros, selecione **Filtro** na área de configuração. A aplicação de filtros utilizará apenas os registos que correspondam aos filtros para calcular a medida.
  
   1. Na secção **Adicionar atributo** do painel **Filtros**, selecione o atributo que pretende utilizar para criar filtros.
   1. Defina os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Selecione **Dimensão** para escolher mais campos que são adicionados como colunas à entidade de saída da medida.

   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais pretende agrupar os valores da medida. Por exemplo, cidade ou sexo.
      > [!TIP]
      > Se tiver selecionado **Nível do cliente** como o **Tipo de Medida**, o atributo *CustomerId* foi já adicionado. Se remover o atributo, **Tipo de medida** muda para **Nível do negócio**.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores nos seus dados que precisa de substituir por um número inteiro, selecione **Regras**. Configure a regra e certifique-se de que escolhe apenas números inteiros como substitutos. Por exemplo, substitua *nulo* por *0*.

1. Pode utilizar o seletor **Fazer rollup de subcontas** se [utilizar contas com hierarquias](relationships.md#set-up-account-hierarchies).
   - Se estiver definido como **Desligado**, a medida é calculada para cada conta. Cada conta obtém o seu próprio resultado.
   - Se estiver definido como **Ligado**, selecione **Editar** para escolher a hierarquia de contas de acordo com as hierarquias ingeridas. A medida produzirá apenas um resultado porque está agregada a subcontas.

1. Se existirem múltiplos caminhos entre a entidade de dados que mapeou e a entidade *Cliente*, tem de escolher um dos [caminhos de relação entre entidades identificados](relationships.md). Os resultados da medida podem variar dependendo do caminho selecionado.

   1. Selecione **Caminho da relação** e escolha o caminho da entidade que deve ser utilizado para identificar a sua medida. Se houver apenas um único caminho para a entidade *Cliente*, este controlo não aparecerá.
   1. Selecione **Concluído** para aplicar a sua seleção.

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Pré-visualização**, verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A pré-visualização reage dinamicamente a alterações na configuração.

1. Selecione **Editar detalhes** junto de Medida sem título. Forneça um nome para a medida. Opcionalmente, adicione [etiquetas](work-with-tags-columns.md#manage-tags) à medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Caixa de diálogo Editar detalhes.":::

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Guardar e fechar** se pretender manter a configuração atual e executar a medida mais tarde.

1. Vá a **Medidas** para ver a nova medida criada na lista.

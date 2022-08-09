---
title: Criar medidas com o construtor de medidas
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
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170877"
---
# <a name="create-measures-with-measure-builder"></a>Criar medidas com o construtor de medidas

O construtor de medidas permite definir cálculos usando operadores de matemática, funções de agregação e filtros. Defina as medidas com os atributos de entidades relacionadas com a entidade *Cliente* unificada.

A criação de medidas em ambientes B2C e B2B funciona da mesma forma. No entanto, se o seu ambiente B2B [utilizar contas com hierarquias](relationships.md#set-up-account-hierarchies), escolha se quer agregar a medida através de subcontas relacionadas.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Crie medidas ao nível de clientes individuais (atributo do cliente, medida do cliente) ou ao nível da empresa/organização (medida de negócio). O atributo do cliente e a medida do cliente permitem monitorizar o desempenho por cliente. Por exemplo, o total gasto por cada cliente. As medidas de negócio monitorizam o desempenho por negócio. Por exemplo, o total de receitas da empresa.

- Atributo do cliente: gera a saída como um novo atributo, que é guardado como uma nova coluna na entidade gerada pelo sistema chamada *Customer_Measure*. Ao atualizar um atributo do cliente, todos os outros atributos do cliente na entidade *Customer_Measure* são atualizados simultaneamente. Além disso, os atributos do cliente são apresentados no cartão de perfil do cliente. Uma vez executado ou guardado, não pode alterar um atributo de cliente para uma medida do cliente.

- Medida do cliente: gera a saída como a sua entidade própria e o utilizador não pode alterá-la para um atributo do cliente, uma vez executado ou guardado. As medidas do cliente não aparecem no cartão de perfil do cliente.

- Medida de negócio: gera a saída como a sua entidade própria e mostra na página inicial do seu ambiente Customer Insights.

1. Va a **Medidas**.

1. Selecione **Novo** > **Criar o seu próprio**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Ecrã de configuração vazio para uma medida B2C. " lightbox="media/measure-b2c.png":::

1. Selecione **Editar detalhes** junto de Medida sem título. Forneça um nome para a medida. Opcionalmente, adicione [etiquetas](work-with-tags-columns.md#manage-tags) à medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Caixa de diálogo Editar detalhes.":::

1. Selecionar **Concluído**.

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

1. Selecione **Adicionar atributo** para selecionar os dados para criar esta medida.

   1. Selecione o separador **Atributos**.
   1. Entidade de dados: escolha a entidade que inclui o atributo que pretende medir.
   1. Atributo de dados: escolha o atributo que pretende utilizar na função agregação para calcular a medida. Só pode selecionar um atributo de cada vez.
   1. Opcionalmente, escolha um atributo de dados a partir de uma medida existente selecionando o separador **Medidas**, ou procure uma entidade ou um nome de medida.
   1. Selecione **Adicionar**.

1. Para criar medidas mais complexas, adicione mais atributos ou utilize operadores de matemática na sua função de medida.

1. Para adicionar filtros, selecione **Filtro** na área de configuração. A aplicação de filtros utilizará apenas os registos que correspondam aos filtros para calcular a medida.
  
   1. Na secção **Adicionar atributo** do painel **Filtros**, selecione o atributo que pretende utilizar para criar filtros.
   1. Defina os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar**.

1. Selecione **Dimensão** para escolher mais campos a adicionar como colunas à entidade de saída da medida.

   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais pretende agrupar os valores da medida. Por exemplo, cidade ou sexo.
      > [!TIP]
      > Se tiver selecionado **Nível do cliente** como o **Tipo de Medida**, o atributo *CustomerId* foi já adicionado. Se remover o atributo, o comutador **Tipo de medida** muda para **Nível do negócio**.
   1. Selecionar **Concluído**.

1. Se existirem valores nos seus dados que têm de ser substituídos por um número inteiro, selecione **Regras**. Configure a regra e certifique-se de que escolhe apenas números inteiros como substitutos. Por exemplo, substitua *nulo* por *0*.

1. Se existirem múltiplos caminhos entre a entidade de dados que mapeou e a entidade *Cliente*, escolha um dos [caminhos de relação entre entidades identificados](relationships.md). Os resultados da medida podem variar dependendo do caminho selecionado.

   1. Selecione **Caminho da relação** e escolha o caminho da entidade que deve ser utilizado para identificar a sua medida. Se houver apenas um único caminho para a entidade *Cliente*, este controlo não aparecerá.
   1. Selecionar **Concluído**.

1. Para adicionar mais cálculos para a medida, selecione **Novo cálculo**. Utilize apenas entidades no mesmo caminho da entidade para novos cálculos. Mais cálculos mostrarão como novas colunas na entidade de saída da medida. Opcionalmente, selecione **Editar nome** para criar um nome para o cálculo.

1. Selecione as reticências verticais (&vellip;) no cálculo para **Duplicar** ou **Remover** um cálculo de uma medida.

1. Na área **Pré-visualização**, verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A pré-visualização reage dinamicamente a alterações na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Guardar e fechar** se pretender manter a configuração atual e executar a medida mais tarde. É apresentada a página **Medidas**.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Crie medidas a nível de contas individuais (medida do cliente) ou ao nível de todas as contas (medida de negócio).

- Medida do cliente: gera a saída como a sua entidade própria. As medidas do cliente não aparecem no cartão de perfil do cliente.

- Medida de negócio: gera a saída como a sua entidade própria e mostra na página inicial do seu ambiente Customer Insights.

1. Va a **Medidas**.

1. Selecione **Novo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Ecrã de configuração vazio para uma medida B2B. ":::

1. Selecione **Editar detalhes** junto de Medida sem título. Forneça um nome para a medida. Opcionalmente, adicione [etiquetas](work-with-tags-columns.md#manage-tags) à medida. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Caixa de diálogo Editar detalhes.":::

1. Selecionar **Concluído**.

1. Na área de configuração, escolha a função de agregação no menu pendente **Selecionar função**. As funções de agregação incluem:
   - **Sum**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máx.**
   - **Min**
   - **Primeiro:** pega no primeiro valor do registo de dados
   - **Último**: pega no último valor que foi adicionado ao registo de dados

1. Selecione **Adicionar atributo** para selecionar os dados para criar esta medida.

   1. Selecione o separador **Atributos**.
   1. Entidade de dados: escolha a entidade que inclui o atributo que pretende medir.
   1. Atributo de dados: escolha o atributo que pretende utilizar na função agregação para calcular a medida. Só pode selecionar um atributo de cada vez.
   1. Opcionalmente, escolha um atributo de dados a partir de uma medida existente selecionando o separador **Medidas**, ou procure uma entidade ou um nome de medida.
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

1. Para criar medidas mais complexas, adicione mais atributos ou utilize operadores de matemática na sua função de medida.

1. Para adicionar filtros, selecione **Filtro** na área de configuração. A aplicação de filtros utilizará apenas os registos que correspondam aos filtros para calcular a medida.
  
   1. Na secção **Adicionar atributo** do painel **Filtros**, selecione o atributo que pretende utilizar para criar filtros.
   1. Defina os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Selecione **Dimensão** para escolher mais campos a adicionar como colunas à entidade de saída da medida.

   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais pretende agrupar os valores da medida. Por exemplo, cidade ou sexo.
      > [!TIP]
      > O atributo *CustomerId* já foi adicionado, o que indica que este é um tipo de medida a nível do cliente. Se remover o atributo, o tipo de medida é alterado a nível do negócio.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se existirem valores nos seus dados que têm de ser substituídos por um número inteiro, selecione **Regras**. Configure a regra e certifique-se de que escolhe apenas números inteiros como substitutos. Por exemplo, substitua *nulo* por *0*.

1. Se [utilizar contas com hierarquias](relationships.md#set-up-account-hierarchies), reveja **Fazer rollup de subcontas**.
   - Se estiver definido como **Desligado**, a medida é calculada para cada conta. Cada conta obtém o seu próprio resultado.
   - Se estiver definido como **Ligado**, selecione **Editar** para escolher a hierarquia de contas de acordo com as hierarquias ingeridas. A medida produzirá apenas um resultado porque está agregada a subcontas.

1. Se existirem múltiplos caminhos entre a entidade de dados que mapeou e a entidade *Cliente*, escolha um dos [caminhos de relação entre entidades identificados](relationships.md). Os resultados da medida podem variar dependendo do caminho selecionado.

   1. Selecione **Caminho da relação** e escolha o caminho da entidade que deve ser utilizado para identificar a sua medida. Se houver apenas um único caminho para a entidade *Cliente*, este controlo não aparecerá.
   1. Selecione **Concluído** para aplicar a sua seleção.

1. Selecione as reticências verticais (&vellip;) no cálculo para **Duplicar** ou **Remover** um cálculo de uma medida.

1. Na área **Pré-visualização**, verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A pré-visualização reage dinamicamente a alterações na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Guardar e fechar** se pretender manter a configuração atual e executar a medida mais tarde. É apresentada a página **Medidas**.

---

## <a name="next-step"></a>Próximo passo

Utilize as medidas existentes para criar [um segmento de cliente](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

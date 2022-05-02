---
title: Predição de recomendação de produtos
description: Preveja que produtos um cliente é provável que compre ou com os quais interaja.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: fe6c0e8ba8236243682a4105535a0026c4343c3d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647359"
---
# <a name="product-recommendation-prediction"></a>Predição de recomendação de produtos

O modelo de recomendação de produtos cria conjuntos de recomendações de produtos preditivas. As recomendações baseiam-se em comportamentos de compra anteriores e clientes com padrões de compra semelhantes. Pode criar novas predições de recomendação de produtos na página **Inteligência** > **Predições**. Selecione **Minhas previsões** para ver outras previsões que criou.

As recomendações de produto podem estar sujeitas às leis e regulamentos locais e às expetativas dos clientes, o que o modelo não foi criado para ter especificamente em conta.  Como utilizador desta capacidade preditiva, **tem de rever as recomendações antes de as entregar aos seus clientes** para garantir que está em conformidade com quaisquer leis ou regulamentos aplicáveis e expetativas de clientes para o que possa recomendar. 

Além disso, a saída deste modelo irá dar-lhe recomendações com base no ID do produto. O seu mecanismo de entrega terá de mapear os IDs de produto previstos para o conteúdo apropriado para que os seus clientes tenham em conta a localização, conteúdo de imagem e outros conteúdos ou comportamentos específicos do negócio.

## <a name="sample-guide"></a>Guia de Exemplo

Se estiver interessado em experimentar esta funcionalidade mas não tiver dados para completar os requisitos abaixo, pode [criar uma implementação de exemplo](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.

- Conhecimento do negócio para compreender diferentes tipos de produtos para o seu negócio e como os seus clientes interagem com eles. Suportamos a recomendação de produtos que tenham sido previamente comprados pelos seus clientes ou recomendações para novos produtos.

- Dados sobre transações, compras e o respetivo histórico:
    - Identificadores de transações para distinguir compras ou transações.
    - Identificadores de clientes para mapear transações para os seus clientes.
    - Datas do evento da transação que especificam as datas em que a transação ocorreu.
    - Informações de ID de Produtos para a transação.
    - (Opcional) Uma entidade de dados do catálogo de produtos para utilizar um filtro de produto.
    - (Opcional) Se uma transação é uma devolução ou não.
    - O esquema de dados semânticos requer as seguintes informações:
        - **ID da transação:** Um identificador único de uma compra ou transação.
        - **Data da transação:** A data da compra ou transação.
        - **Valor da transação:** o valor numérico da compra ou transação.
        - **ID exclusivo do produto:** o ID do produto ou serviço comprado se os seus dados estiverem a um nível de item de linha.
        - (Opcional) **Compra ou devolução:** um campo booleano onde o valor *true* identifica que uma transação foi uma devolução. Se os dados de Compra ou Devolução não forem fornecidos o modelo e o **Valor da transação** for negativo, também usaremos estas informações para inferir uma devolução.
- Características de dados sugeridos:
    - Dados históricos suficientes: pelo menos, um ano de dados transacionais, de preferência de dois a três anos para incluir alguma sazonalidade.
    - Compras múltiplas por cliente: três ou mais transações por ID de Cliente
    - Número de clientes: pelo menos, 100 clientes, de preferência mais de 10.000 clientes. O modelo falhará com menos de 100 clientes.

> [!NOTE]
> - O modelo requer o histórico de transações dos seus clientes. A definição de uma transação é bastante flexível. Quaisquer dados que descrevam uma interação entre utilizador e produto pode funcionar como uma entrada. Por exemplo, comprar um produto, ter uma aula ou assistir a um evento.
> - Atualmente, apenas uma entidade de histórico de transações pode ser configurada. Se existirem várias entidades de compra, pode uni-las no Power Query antes de começar a ingestão de dados.
> - Se a encomenda e os detalhes da encomenda forem entidades diferentes, una-as antes de usar no modelo. O modelo não funciona apenas com um ID de encomenda ou ID de recibo numa entidade.


## <a name="create-a-product-recommendation-prediction"></a>Criar uma predição de recomendação de produtos

1. No Customer Insights, aceda a **Inteligência** > **Predições**.

1. Selecione o mosaico **Modelo de recomendações de produtos** e selecione **Utilizar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Mosaico do modelo Recomendação de Produtos com o botão Utilizar este modelo.](media/product-recommendation-usethismodel.PNG "Mosaico do modelo Recomendação de Produtos com o botão Utilizar este modelo")

1. Reveja as informações sobre os requisitos do modelo. Se tiver os dados obrigatórios, selecione **Começar**.

### <a name="name-model"></a>Atribuir nome ao modelo

1. Forneça um nome para o modelo para distingui-lo de outros modelos.

1. Insira um nome para a entidade de saída usando apenas letras e números, sem espaços. É o nome que a entidade modelo vai usar. Em seguida, selecione **Seguinte**.

### <a name="define-product-recommendation-configuration"></a>Definir a configuração de recomendação de produtos

1. Defina o **Número de produtos** que pretende recomendar a um cliente. Este valor depende de como o seu método de entrega preenche os dados. Se puder recomendar três produtos, defina este valor em conformidade.
   
   >[!TIP]
   > Pode selecionar **Guardar rascunho** a qualquer momento para guardar a predição como rascunho. Vai encontrar a predição de rascunho no separador **A minhas predições**.

1. Escolha se pretende incluir produtos que os clientes compraram recentemente no campo **Compras repetidas esperadas**.

1. Defina a **Janela de histórico**. Esta definição especifica o período de tempo que o modelo considera antes de recomendar o produto ao utilizador novamente. Por exemplo, indica que um cliente compra um portátil de dois em dois anos. Esta janela irá olhar para o histórico de compras dos últimos dois anos e, se encontrarem um item, o item será filtrado das recomendações.

1. Selecione **Seguinte**

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** e escolha o tipo de atividade no painel lateral que contém as informações de histórico de transação ou de compra necessárias.

1. Em **Escolher atividades**, escolha as atividades específicas da atividade selecionada em que gostaria que o cálculo se focasse.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Painel lateral a mostrar a escolha de atividades específicas sob o tipo semântico.":::

1. Se ainda não mapeou a atividade para um tipo semântico, selecione **Editar** para o fazer. A experiência guiada para mapear atividades semânticas é aberto. Mapeie os seus dados para os campos correspondentes no tipo de atividade selecionado.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Tipo de atividade de definição de página.":::

1. Depois de mapear a atividade para o tipo semântico correspondente, selecione **Seguinte** para prosseguir 
 
1. Mapear os atributos semânticos para os campos que são necessários para executar o modelo.

1. Selecione **Guardar**.

1. Selecione **Seguinte**.


### <a name="configure-product-filters"></a>Configurar filtros de produtos

Por vezes, apenas determinados produtos são benéficos ou adequados para o tipo de predição que cria. Os filtros de produtos permitem identificar um subconjunto de produtos com características específicas a recomendar aos seus clientes. O modelo utilizará todos os produtos disponíveis para aprender padrões, mas utilizará apenas os produtos correspondentes ao filtro do produto na sua saída.

1. No passo **Adicionar informações do produto**, adicione o seu catálogo de produtos com informações para cada produto. Mapear as informações necessárias e selecione **Seguinte**.

3. No passo **Filtros de produtos**, escolha de entre as seguintes opções.

   * **Sem filtros**: utilize todos os produtos na predição de recomendação de produtos.

   * **Definir filtros específicos de produtos**: utilize produtos específicos na predição de recomendação de produtos.

1. Selecione **Seguinte**.

1. Se optar por definir um filtro de produtos, tem de o definir agora. No painel **Atributos do catálogo de produtos**, selecione os atributos da *entidade do Catálogo de Produtos* que pretende incluir no filtro.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Painel lateral a mostrar atribuído na entidade do catálogo de produtos para selecionar para filtros de produtos.":::

1. Escolha se deseja que o filtro de produtos use conectores **and** ou **or** para combinar logicamente a sua seleção de atributos do catálogo de produtos.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Configuração de exemplo de filtros de produtos combinada com conectores lógicos AND.":::

1. Selecione **Seguinte**.

### <a name="set-update-schedule-and-review-configuration"></a>Definir agenda de atualização e rever configuração

1. Defina uma frequência para reeducar o modelo. Esta definição é importante para atualizar a precisão das previsões à medida que novos dados são importados para o Customer Insights. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.

1. Rever a configuração. Pode voltar a qualquer parte da configuração de previsão selecionando **Editar** por abaixo do valor indicado. Ou pode selecionar um passo de configuração a partir do indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Guardar e executar** para iniciar o processo de previsão. No separador **Minhas previsões**, pode ver o estado das suas previsões. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Rever um estado de previsão e resultados

1. Vá para o separador **Minhas previsões** em **Informações** > **Previsões**.
   > [!div class="mx-imgBorder"]
   > ![Vista da página Minhas Previsões.](media/product-recommendation-mypredictions.PNG "Vista da página Minhas Previsões")

1. Selecione a predição que pretende rever.
   - **Nome da previsão:** O nome da previsão fornecida ao criá-la.
   - **Tipo de previsão:** O tipo de modelo utilizado para a previsão
   - **Entidade de saída:** Nome da entidade para armazenar a saída da previsão. Pode encontrar uma entidade com este nome em **Dados** > **Entidades**.    
      A *Pontuação* na entidade de saída é uma medida quantitativa da recomendação. O modelo recomenda produtos com uma pontuação mais elevada sobre produtos com uma pontuação mais baixa.
   - **Campo previsto:** este campo é preenchido apenas para alguns tipos de predições e não é utilizado na predição de Recomendação de Produtos.
   - **Estado:** O estado atual da execução da previsão.
        - **Em fila:** a previsão está neste momento à espera que outros processos sejam executados.
        - **Atualização:** A previsão está atualmente a executar a fase de processamento "pontuação" para produzir resultados que fluirão para a entidade de saída.
        - **Falhada:** a previsão falhou. Selecione **Registos** para obter mais detalhes.
        - **Bem sucedida:** a previsão foi bem sucedida. Selecione **Ver** por baixo das reticências verticais para rever a previsão
   - **Editada:** A data da em que a configuração para a previsão foi alterada.
   - **Última atualização:** A data em que a previsão foi atualizada resulta na entidade de saída.

1. Selecione as reticências verticais ao lado da previsão que pretende rever os resultados e selecione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista das opções no menu de reticências verticais para uma previsão, incluindo Editar, Atualizar, Ver, Registos e Eliminar.](media/product-recommendation-verticalellipses.PNG "Vista das opções no menu de reticências verticais para uma previsão, incluindo Editar, Atualizar, Ver, Registos e Eliminar")

1. Existem cinco secções primárias de dados dentro da página de resultados:
    1. **Desempenho do modelo de preparação:** A, B ou C são possíveis pontuações. Esta pontuação indica o desempenho da previsão, e pode ajudá-lo a tomar a decisão de usar os resultados armazenados na entidade de saída.
        - As pontuações são determinadas com base nas seguintes regras:
            - **A** O modelo será considerado de qualidade **A** se a métrica "Sucesso @ K" for, pelo menos, 10% mais a linha de base. 
            - **B** O modelo será considerado de qualidade **B** se a métrica "Sucesso @ K" for 0% a 10% mais do que a linha de base.
            - **C** O modelo será considerado de qualidade **C** se a métrica "Sucesso @ K" for menor que a linha de base.
               
               > [!div class="mx-imgBorder"]
               > ![Vista do resultado do desempenho do modelo.](media/product-recommendation-modelperformance.PNG "Vista do resultado do desempenho do modelo")
            - **Linha de base**: o modelo considera os produtos mais recomendados pela contagem de compras entre todos os clientes e utiliza regras aprendidas identificadas pelo modelo para criar um conjunto de recomendações para os clientes. As predições são então comparadas com os produtos principais, como calculado pelo número de clientes que tinham comprado o produto. Se um cliente tiver, pelo menos, um produto nos seus produtos recomendados que também foi visto nos principais produtos comprados, são considerados uma parte da linha de base. Se houvesse 10 destes clientes que tivessem um produto recomendado comprado de 100 clientes totais, a linha de base seria de 10%.
            - **Sucesso @ K**: utilizando um conjunto de períodos de tempo de validação de transações, são criadas recomendações para todos os clientes e comparadas com o conjunto de transações de validação. Por exemplo, num período de 12 meses, o mês 12 pode ser reservado como um conjunto de dados de validação. Se o modelo prevê, pelo menos, uma coisa que compraria no mês 12 com base no que aprendeu com os 11 meses anteriores, o cliente aumentaria a métrica "Sucesso @ K".
    
    1. **Produtos mais sugeridos (com contagem):** os cinco principais produtos que foram previstos para os seus clientes.
       > [!div class="mx-imgBorder"]
       > ![Grafo que mostra os principais 5 produtos mais recomendados.](media/product-recommendation-topproducts.PNG "Gráfico que mostra os principais 5 produtos mais recomendados")
    
    1. **Principais fatores de recomendação:** o modelo utiliza o histórico de transações dos clientes para fazer recomendações de produtos. Aprende padrões com base em compras anteriores e encontra semelhanças entre clientes e produtos. Estas semelhanças são então utilizadas para gerar recomendações de produtos.
    Seguem-se os fatores que podem influenciar uma recomendação de produtos gerada pelo modelo. 
        - **Transações anteriores**: os padrões de compra no passado foram utilizados pelo modelo para gerar recomendações de produtos. Por exemplo, o modelo pode recomendar um _Surface Arc Mouse_ se alguém comprou recentemente um _Surface Book 3_ e uma _Caneta para Surface_. O modelo aprendeu que, historicamente, muitos clientes tinham comprado um _Surface Arc Mouse_ depois de comprarem um _Surface Book 3_ e uma _Caneta para Surface_.
        - **Semelhança de clientes**: um produto recomendado foi historicamente comprado por outros clientes que apresentam padrões de compra semelhantes. Por exemplo, John foi recomendado o _Auscultadores Surface 2_ porque Lara e Brad compraram recentemente _Auscultadores Surface 2_. O modelo acredita que John é semelhante a Lara e a Brad porque historicamente têm padrões de compra semelhantes.
        - **Semelhança de produtos**: um produto recomendado é semelhante a outros produtos que o cliente comprou anteriormente. O modelo considera que dois produtos são semelhantes se forem comprados juntos ou por clientes semelhantes. Por exemplo, alguém obtém uma recomendação para uma _Unidade de Armazenamento USB_ porque comprou anteriormente um _Adaptador USB-C para USB_ e o modelo acredita que a _Unidade de Armazenamento USB_ é semelhante a _Adaptador USB-C para USB_ com base em padrões históricos de compra.

        Cada recomendação de produtos é influenciada por um ou mais destes fatores. A percentagem de recomendações em que cada fator influenciador desempenhou um papel é visualizada num gráfico. No exemplo seguinte, 100% das recomendações foram influenciadas por transações passadas, 60% pela semelhança de clientes e 22% pela semelhança de produtos. Paire sobre as barras no gráfico para ver a percentagem exata onde os fatores influenciadores contribuíram.

        > [!div class="mx-imgBorder"]
        > ![Principais fatores de recomendação.](media/product-recommendation-keyrecommendationfactors.png "Principais fatores de recomendação aprendidos pelo modelo para gerar recomendações de produtos")
       
     
   1. **Estatísticas de dados**: dá uma descrição geral do número de transações, clientes e produtos considerados pelo modelo. Baseia-se nos dados de entrada que foram usados para aprender padrões e gerar recomendações de produtos.

      > [!div class="mx-imgBorder"]
      > ![Estatísticas de dados.](media/product-recommendation-datastatistics.png "Estatísticas de dados em torno de dados de entrada utilizados pelo modelo para aprender padrões")

      Esta secção mostra estatísticas em torno dos pontos de dados que foram usados pelo modelo para aprender padrões e gerar recomendações de produtos. A filtragem, como configurada na configuração do modelo, aplicar-se-á na saída gerada pelo modelo. No entanto, o modelo utiliza todos os dados disponíveis para aprender padrões. Portanto, se utilizar a filtragem de produtos na configuração do modelo, esta secção mostrará o número total de produtos que o modelo analisou para aprender padrões, o que pode diferir do número de produtos que correspondem aos critérios de filtragem definidos.

   1. **Recomendações de alta confiança no produto:** um exemplo de recomendações fornecidas aos seus clientes que o modelo acredita serem suscetíveis de serem adquiridas pelo cliente.    
      Se for adicionado um catálogo de produtos, os IDs de produtos são substituídos por nomes de produtos. Os nomes dos produtos fornecem informações mais acionáveis e intuitivas sobre as predições.
       > [!div class="mx-imgBorder"]
       > ![Lista que mostra sugestões de alta confiança para um conjunto selecionado de clientes individuais.](media/product-recommendation-highconfidence.PNG "Lista que mostra sugestões de alta confiança para um conjunto selecionado de clientes individuais")

## <a name="manage-predictions"></a>Gerir predições

É possível otimizar, resolver problemas, atualizar ou eliminar predições. Reveja um relatório de capacidade de utilização de dados de entrada para saber como tornar uma predição mais rápida e fiável. Para mais informações, consulte [Gerir predições](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]

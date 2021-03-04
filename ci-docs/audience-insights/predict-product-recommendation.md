---
title: Predição de recomendação de produtos
description: Preveja que produtos um cliente é provável que compre ou com os quais interaja.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270523"
---
# <a name="product-recommendation-prediction-preview"></a>Predição de recomendação de produtos (pré-visualização)

O modelo de recomendação de produtos cria conjuntos de recomendações de produtos preditivas. As recomendações baseiam-se em comportamentos de compra anteriores e clientes com padrões de compra semelhantes. Pode criar novas predições de recomendação de produtos na página **Inteligência** > **Predições**. Selecione **Minhas previsões** para ver outras previsões que criou.

As recomendações de produtos podem estar sujeitas às leis e regulamentos locais, bem como às expetativas dos clientes, o que o modelo não foi criado para ter em conta especificamente.  Como utilizador desta capacidade preditiva, **tem de rever as recomendações antes de as entregar aos seus clientes** para garantir que está a cumprir quaisquer leis ou regulamentos aplicáveis, bem como as expetativas dos clientes relativamente ao que pode recomendar. 

Além disso, a saída deste modelo irá dar-lhe recomendações com base no ID do produto. O seu mecanismo de entrega terá de tomar os IDs do produto previstos e mapeá-los para conteúdo apropriado para que os seus clientes sejam responsáveis pela localização, conteúdo de imagem e outros conteúdos ou comportamentos específicos do negócio.

## <a name="sample-guide"></a>Guia de Exemplo

Se estiver interessado em experimentar esta funcionalidade mas não tiver dados para completar os requisitos abaixo, pode [criar uma implementação de exemplo](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.
- Conhecimento do negócio para compreender diferentes tipos de produtos para o seu negócio e como os seus clientes interagem com eles. Suportamos a recomendação de produtos que tenham sido previamente comprados pelos seus clientes ou recomendações para novos produtos.
- Dados sobre transações, compras e o respetivo histórico:
    - Identificadores de transações para distinguir compras ou transações.
    - Identificadores de clientes para mapear transações para os seus clientes.
    - Datas do evento da transação que especificam as datas em que a transação ocorreu.
    - (Opcional) Informações de ID do Produto para a transação.
    - (Opcional) Se uma transação é uma devolução ou não.
    - O esquema de dados semânticos requer as seguintes informações:
        - **ID da transação:** Um identificador único de uma compra ou transação.
        - **Data da transação:** a data da compra ou transação.
        - **Valor da transação:** o valor numérico da compra ou transação.
        - **ID exclusivo do produto:** o ID do produto ou serviço comprado se os seus dados estiverem a um nível de item de linha.
        - (Opcional) **Compra ou devolução:** um campo true/false que identifica se a transação foi ou não uma devolução. Se o **Valor da transação** é negativo, também utilizaremos esta informação para inferir uma devolução.


## <a name="create-a-product-recommendation-prediction"></a>Criar uma predição de recomendação de produtos

1. No Customer Insights, aceda a **Inteligência** > **Predições**.

1. Selecione o mosaico **Modelo de recomendações de produtos (pré-visualização)** e selecione **Utilizar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Mosaico do modelo Recomendação de Produtos com o botão Utilizar este modelo](media/product-recommendation-usethismodel.PNG "Mosaico do modelo Recomendação de Produtos com o botão Utilizar este modelo")

1. Reveja as informações sobre os requisitos do modelo. Se tiver os dados obrigatórios, selecione **Começar**.

### <a name="name-model"></a>Atribuir nome ao modelo

1. Forneça um nome para o modelo para distingui-lo de outros modelos.

1. Insira um nome para a entidade de saída usando apenas letras e números, sem espaços. É o nome que a entidade modelo vai usar. Em seguida, selecione **Seguinte**.

### <a name="define-product-recommendation-configuration"></a>Definir a configuração de recomendação de produtos

1. Defina o **Número de produtos** que pretende recomendar a um cliente. Este valor depende de como o seu método de entrega preenche os dados. Se puder recomendar três produtos, defina este valor em conformidade.
   
   >[!TIP]
   > Pode selecionar **Guardar e fechar** a qualquer momento para guardar a previsão como rascunho. Vai encontrar a predição de rascunho no separador **A minhas predições**.

1. Escolha se pretende **Sugerir produtos que os clientes compraram recentemente**.

1. Se tiver selecionado *não* recomendar produtos comprados recentemente, defina a **Janela de recuo**. Esta definição especifica o período de tempo que o modelo considera antes de recomendar o produto ao utilizador novamente. Por exemplo, indique um cliente compra um portátil a cada 2 anos. Esta janela irá olhar para o histórico de compras dos últimos 2 anos e, se encontrar um item, o item será filtrado das recomendações.

1. Selecione **Seguinte**

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** para o **Histórico de transações do cliente** e escolha a entidade que fornece as informações do histórico de transações/compras, conforme descrito nos [pré-requisitos](#prerequisites).

1. Mapear os campos semânticos a atributos dentro da sua entidade de histórico de compras e selecione **Seguinte**. Para descrições dos campos, veja os [pré-requisitos](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definir A relação entre entidades](media/product-recommendation-purchasehistorymapping.PNG "Página de histórico de compras que mostra atributos semânticos que são mapeados para campos na entidade do histórico de compras selecionada")

1. Se os campos não estiverem preenchidos, configure a relação da sua entidade de histórico de compras para a entidade *Cliente*.
    1. Selecione a **Entidade de histórico de compras**.
    1. Selecione o **Campo** que identifica o cliente na entidade do histórico de compras. Tem de se relacionar com o ID do cliente primário da sua entidade *Cliente*.
    1. Selecione a **entidade Cliente** que corresponde à sua entidade principal de cliente.
    1. Introduza um nome que descreva a relação.
       > [!div class="mx-imgBorder"]
       > ![Página de histórico de compras que mostra a criação de uma relação com o cliente](media/model-purchase-join.png "Página de histórico de compras que mostra a criação de uma relação com o cliente")

1. Selecione **Guardar**.

1. Selecione **Seguinte**.

### <a name="set-schedule-and-review-configuration"></a>Definir agenda e rever configuração

1. Defina uma frequência para reeducar o modelo. Esta definição é importante para atualizar a precisão das previsões à medida que novos dados são importados para o Customer Insights. A maioria das empresas pode reeducar uma vez por mês e obter uma boa precisão para a sua previsão.

1. Selecione **Seguinte**.

1. Rever a configuração. Pode voltar a qualquer parte da configuração de previsão selecionando **Editar** por abaixo do valor indicado. Ou pode selecionar um passo de configuração a partir do indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Guardar e executar** para iniciar o processo de previsão. No separador **Minhas previsões**, pode ver o estado das suas previsões. O processo pode demorar várias horas a ser concluído dependendo da quantidade de dados utilizados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Rever um estado de previsão e resultados

1. Vá para o separador **Minhas previsões** em **Informações** > **Previsões**.
   > [!div class="mx-imgBorder"]
   > ![Vista da página Minhas Previsões](media/product-recommendation-mypredictions.PNG "Vista da página Minhas Previsões")

1. Selecione a predição que pretende rever.
   - **Nome da previsão:** O nome da previsão fornecida ao criá-la.
   - **Tipo de previsão:** O tipo de modelo utilizado para a previsão
   - **Entidade de saída:** Nome da entidade para armazenar a saída da previsão. Pode encontrar uma entidade com este nome em **Dados** > **Entidades**.
   - **Campo da predição:** Este campo é povoado apenas para alguns tipos de predições, e não é usado na predição de abandono.
   - **Estado:** O estado atual da execução da previsão.
        - **Em fila:** a previsão está neste momento à espera que outros processos sejam executados.
        - **Atualização:** A previsão está atualmente a executar a fase de processamento "pontuação" para produzir resultados que fluirão para a entidade de saída.
        - **Falhada:** a previsão falhou. Selecione **Registos** para obter mais detalhes.
        - **Bem sucedida:** a previsão foi bem sucedida. Selecione **Ver** por baixo das reticências verticais para rever a previsão
   - **Editada:** A data da em que a configuração para a previsão foi alterada.
   - **Última atualização:** A data em que a previsão foi atualizada resulta na entidade de saída.

1. Selecione as reticências verticais ao lado da previsão que pretende rever os resultados e selecione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista das opções no menu de reticências verticais para uma previsão, incluindo Editar, Atualizar, Ver, Registos e Eliminar](media/product-recommendation-verticalellipses.PNG "Vista das opções no menu de reticências verticais para uma previsão, incluindo Editar, Atualizar, Ver, Registos e Eliminar")

1. Existem três secções primárias de dados dentro da página de resultados:
    1. **Desempenho do modelo de preparação:** A, B ou C são possíveis pontuações. Esta pontuação indica o desempenho da previsão, e pode ajudá-lo a tomar a decisão de usar os resultados armazenados na entidade de saída.
        - As pontuações são determinadas com base nas seguintes regras:
            - **A** O modelo será considerado de qualidade **A** se a métrica "Sucesso @ K" for, pelo menos, 10% mais a linha de base. 
            - **B** O modelo será considerado de qualidade **B** se a métrica "Sucesso @ K" for 0% a 10% mais do que a linha de base.
            - **C** O modelo será considerado de qualidade **C** se a métrica "Sucesso @ K" for inferior à linha de base.
               
               > [!div class="mx-imgBorder"]
               > ![Vista do resultado do desempenho do modelo](media/product-recommendation-modelperformance.PNG "Vista do resultado do desempenho do modelo")
            - **Linha de base**: o modelo considera os produtos mais recomendados pela contagem de compras entre todos os clientes e utiliza regras aprendidas identificadas pelo modelo para criar um conjunto de recomendações para os clientes. As predições são então comparadas com os produtos principais, como calculado pelo número de clientes que tinham comprado o produto. Se um cliente tiver, pelo menos, um produto nos seus produtos recomendados que também foi visto nos principais produtos comprados, são considerados uma parte da linha de base. Se houvesse 10 destes clientes que tivessem um produto recomendado comprado de 100 clientes totais, a linha de base seria de 10%.
            - **Sucesso @ K**: utilizando um conjunto de períodos de tempo de validação de transações, são criadas recomendações para todos os clientes e comparadas com o conjunto de transações de validação. Por exemplo, num período de 12 meses, o mês 12 pode ser reservado como um conjunto de dados de validação. Se o modelo prevê, pelo menos, uma coisa que compraria no mês 12 com base no que aprendeu com os 11 meses anteriores, o cliente aumentaria a métrica "Sucesso @ K".
    
    1. **Produtos mais sugeridos (com contagem):** os 5 principais produtos que foram previstos para os seus clientes.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que mostra os principais 5 produtos mais recomendados](media/product-recommendation-topproducts.PNG "Gráfico que mostra os principais 5 produtos mais recomendados")
    
    1. **Recomendações de alta confiança no produto:** um exemplo de recomendações fornecidas aos seus clientes que o modelo acredita serem suscetíveis de serem adquiridas pelo cliente.
       > [!div class="mx-imgBorder"]
       > ![Lista que mostra sugestões de alta confiança para um conjunto selecionado de clientes individuais](media/product-recommendation-highconfidence.PNG "Lista que mostra sugestões de alta confiança para um conjunto selecionado de clientes individuais")

## <a name="fix-a-failed-prediction"></a>Corrigir uma previsão falhada

1. Vá para o separador **Minhas previsões** em **Informações** > **Previsões**.

1. Selecione a previsão para visualizar registos de erros e selecione **Registos**.

1. Rever todos os erros. Existem vários tipos de erros que podem ocorrer, e estes descrevem que condição causou o erro. Por exemplo, um erro que não há dados suficientes para prever com precisão é, normalmente, resolvido carregando dados adicionais no Customer Insights.

## <a name="refresh-a-prediction"></a>Atualizar uma previsão

As predições atualizam-se automaticamente na mesma [agenda em que os seus dados são atualizados](system.md#schedule-tab), como configurados nas definições.

1. Vá para o separador **Minhas previsões** em **Informações** > **Previsões**.

1. Selecione as reticências verticais ao lado da previsão que pretende atualizar.

1. Selecione **Atualizar**.

## <a name="delete-a-prediction"></a>Eliminar uma previsão

A eliminação de uma predição também removerá a sua entidade de saída.

1. Vá para o separador **Minhas previsões** em **Informações** > **Previsões**.

1. Selecione as reticências verticais ao lado da previsão que pretende eliminar.

1. Selecione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
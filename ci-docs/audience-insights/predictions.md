---
title: Dados parciais completos utilizando previsões
description: Utilizar previsões para preencher os dados incompletos dos clientes.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6ce72486faa97e6f630a991044ca5e6d4714d0b8b8395a60fad12f3e3a49fa29
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032449"
---
# <a name="complete-your-partial-data-with-predictions"></a>Concluir os seus dados parciais com predições

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

As predições permitem criar facilmente valores previstos que podem melhorar a sua compreensão de um cliente. Na página **Inteligência** > **Predições**, pode selecionar **As minhas predições** para ver as predições que configurou noutras partes das informações de audiência, e pode personalizá-las ainda mais.

> [!NOTE]
> Não poderá utilizar esta funcionalidade se o seu ambiente utilizar o armazenamento do Azure Data Lake Gen 2.
>
> A funcionalidade de predições utiliza meios automatizados para avaliar os dados e efetuar predições com base nesses dados e, por conseguinte, tem a capacidade de ser utilizada como método de criação de perfis, nos termos em que esse termo for definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD"). A utilização desta funcionalidade por parte do Cliente para tratar os dados pode estar sujeita aos RGPD ou a outras leis ou regulamentos. O utilizador é responsável por garantir que a sua utilização do Dynamics 365 Customer Insights, incluindo predições, cumpre com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas com a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

## <a name="prerequisites"></a>Pré-requisitos

Antes de a sua organização poder utilizar a funcionalidade de predições, devem ser cumpridos os seguintes pré-requisitos:

1. A sua organização tem uma instância [configurada no Microsoft Dataverse](/ai-builder/build-model#prerequisites) e está na mesma organização que o Customer Insights.

2. O seu ambiente de informações de audiência está ligado à sua instância do Dataverse.

Se [criar um novo ambiente](get-started-paid.md), configure-o na caixa de diálogo **Criar um ambiente** e selecione **Avançadas**. Se já tiver criado um ambiente, aceda às respetivas definições e **selecione** avançado. De qualquer forma, na secção **Usar predições**, introduza a o URL da instância do Dataverse a que deseja anexar o seu ambiente.

## <a name="create-a-prediction-in-the-customer-entity"></a>Criar uma predição na entidade de Cliente

1. Nas informações de audiência, vá a **Dados** > **Entidades**.

2. Selecione a entidade **Cliente**.

3. Na entidade **Cliente: CustomerInsights**, selecione o separador **Campos**.

4. Localize o nome do atributo para o qual pretende prever os valores e, em seguida, no ícone **Descrição Geral** na coluna **Resumo**.
   > [!div class="mx-imgBorder"]
   > ![Ícone Descrição Geral.](media/intelligence-overviewicon.png "Ícone Descrição Geral")

5. Se existir uma taxa elevada de valores em falta para o atributo, selecione **Prever valores em falta** para continuar com a sua predição.
   > [!div class="mx-imgBorder"]
   > ![Estado da descrição geral a mostrar o botão Prever valores em falta.](media/intelligence-overviewpredictmissingvalues.png "Estado da descrição geral a mostrar o botão Prever valores em falta")

6. Forneça um **Nome a Apresentar** e um **Nome da entidade de saída** para obter os resultados da predição.

7. Será aqui mostrada uma lista de opções preenchida previamente onde poderá mapear os valores para uma categoria prevista. Neste caso, as únicas opções de categoria serão 0 ou 1, uma vez que são mapeadas para a natureza verdadeiro/falso, ou binária, da predição. Na coluna Categoria, mapeie os valores de campo que pretende que sejam classificados como "0" na predição final como "0" e os itens que pretende que sejam classificados como "1" na predição final como "1".
   > [!div class="mx-imgBorder"]
   > ![Exemplo a mostrar valores de campos mapeados para categorias.](media/intelligence-categorymapping.png "Exemplo a mostrar valores de campos mapeados para categorias")

8. Selecione **Concluído** e a predição será processada. O processamento irá demorar algum tempo, consoante o tamanho e a complexidade dos dados. Os resultados estarão disponíveis numa nova entidade baseada no **Nome da entidade de saída** da predição que criou.

## <a name="create-a-prediction-while-creating-a-segment"></a>Criar uma predição durante a criação de um segmento

A predição dos valores em falta para um atributo específico à escolha também é possível ao criar um segmento. Especificamente, quando cria rapidamente um segmento baseado na entidade Cliente unificado ou na entidade Customer_Measure.

Como parte deste fluxo, irá escolher um atributo específico onde basear o segmento, como Satisfação do Cliente ou Montante de Compra. Após a criação do segmento, o sistema irá sugerir um método para prever quaisquer valores em falta para este atributo.

1. Nas informações de audiência, aceda a **Segmentos** e selecione o mosaico **Perfis**. 

2. Escolha um **Campo** onde criar um segmento e selecione um **Operador** e, em seguida selecione **Rever**.

3. Forneça um **Nome** e um **Nome a apresentar** para o segmento.

4. Selecione **Guardar**.

5. Se o segmento que criar tiver dados incompletos no campo de origem, poderá optar por prever os valores em falta.
   > [!div class="mx-imgBorder"]
   > ![Botão Predição.](media/segments-predictoption.png "Botão Predição")

6. Forneça um **Nome a Apresentar** e um **Nome da entidade de saída** para obter os resultados da predição.

7. Selecione **Concluído**. A sua predição será gerada em breve numa nova entidade com o nome fornecido para o **Nome da entidade de saída**.

## <a name="view-a-prediction"></a>Ver uma predição

1. Nas informações de audiência, vá a **Inteligência** > **Predições** > **As minhas predições**.

2. Selecione a predição que pretende rever.

3. Selecione as reticências na coluna **Ações** e escolha **Ver**.

4. Verá vários pontos de dados na vista da sua predição.
   > [!div class="mx-imgBorder"]
   > ![Página Predições.](media/intelligence-predictionsviewpage.png "Página Predições")

   - Os **valores previstos** mostram o mapeamento criado durante a fase de mapeamento do valor Campo para Categoria. São valores no conjunto de dados que foram mapeados para uma categoria específica.
   -**Principais influenciadores** são os fatores existentes no seu conjunto de dados com maior probabilidade de influenciar a confiança da predição do valor Campo que está a ser mapeado para uma categoria específica..
   - **Desempenho** indica a forma como as predições estão a ser efetuadas. Selecione a ligação para saber mais.
   - **Pré-visualizar** mostra exemplos do conjunto de dados de saída da sua predição, bem como a probabilidade, ou nossa confiança, do valor previsto, em que 0 é incerteza e 1 é certo.

## <a name="update-a-prediction"></a>Atualizar uma predição

1. Nas informações de audiência, vá a **Inteligência** > **Predições** > **As minhas predições**.

2. Selecione a predição que pretende atualizar e selecione o ícone **Atualizar**.

3. A predição será agendada para processamento. Pode ver a hora da última atualização na coluna **Atualizado** da página **Predições**.

## <a name="edit-a-prediction"></a>Editar uma predição

Depois de ter criado uma predição, pode personalizar o modelo no AI Builder para aumentar a eficácia do seu modelo.  

1. Nas informações de audiência, vá a **Inteligência** > **Predições** > **As minhas predições**.

2. Selecione a predição que pretende editar.

3. Selecione as reticências na coluna **Ações** e escolha **Ver**.

4. Selecione **Personalizar no AI Builder**.

5. Atualize o seu modelo no AI Builder. [Saiba mais informações sobre como gerir os modelos no AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

A execução seguinte da sua predição utilizará o modelo atualizado que criou.

> [!NOTE]
> Os novos modelos criados no AI Builder não serão exibidos em informações de audiência, a menos que o modelo tenha sido criado a partir das experiências listadas acima.

## <a name="remove-a-prediction"></a>Remover uma predição

1. Nas informações de audiência, vá a **Inteligência** > **Predições** > **As minhas predições**.

2. Selecione a predição que pretende eliminar.

3. Selecione as reticências na coluna **Ações** e escolha **Eliminar**.

4. Confirme a eliminação.

## <a name="troubleshooting"></a>Resolução de Problemas

Se não conseguir concluir o processo de anexação do Dataverse devido a um erro, poderá tentar concluir o processo manualmente. Existem dois problemas conhecidos que podem ocorrer no processo de anexação:

- A solução Suplemento Ficha de Cliente não está instalada.
    1. Conclua as instruções para [instalar e configurar a solução](customer-card-add-in.md).

- Não são concedidas permissões da aplicação.
    1. Ir para o [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Selecionar **Ambientes**.
    1. Selecione as reticências junto do ambiente ao qual pretende adicionar a permissão e selecione **Definições**.
    1. Expanda **Utilizadores + permissões** e selecione **Utilizadores**.
    1. Selecione **+ Novo** e selecione **Utilizador**.
    1. Selecione **Utilizador da Aplicação** se ainda não estiver selecionado e introduza as seguintes informações:
        - **Nome de Utilizador:** cihelp@microsoft.com
        - **ID da Aplicação:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Nome Próprio:** Cliente
        - **Apelido:** Informações
        - **E-mail Principal:** cihelp@microsoft.com
    1. Selecione **Guardar e Fechar**.
    1. Selecione o utilizador que criou.
    1. Selecione **Gerir Funções** na barra de menus superior.
    1. Selecione **Administrador de Sistema** e selecione **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
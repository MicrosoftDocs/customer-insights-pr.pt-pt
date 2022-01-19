---
title: Ingerir dados através de um conector do Power Query (contém vídeo)
description: Conectores para origens de dados com base no Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934992"
---
# <a name="connect-to-a-power-query-data-source"></a>Ligue-se a uma origem de dados do Power Query

O Power Query oferece um vasto conjunto de conectores para ingerir dados. A maioria destes conectores são suportados pelo Dynamics 365 Customer Insights. 

Normalmente, a adição de origens de dados baseada em conectores do Power Query segue os passos descritos nesta secção. No entanto, dependendo do conector que utiliza, são necessárias informações diferentes. Para saber mais, consulte a documentação sobre os conectores individuais na [Referência do conector do Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Criar uma nova origem de dados

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Selecione **Microsoft Power Query** e, depois, selecione **Seguinte**.

1. Forneça um **Nome** para a origem de dados e selecione **Seguinte** para criar a origem de dados.

1. Escolha um dos [conectores disponíveis](#available-power-query-data-sources). Neste exemplo, selecionamos o conector **Text/CSV**.

1. Introduza os detalhes requeridos nas **Definições de ligação** para o conector selecionado e selecione **Seguinte** para ver uma pré-visualização dos dados.

1. Selecione **Transformar dados**. Neste passo, vai adicionar entidades à sua origem de dados. As entidades são conjuntos de dados. Se tiver uma base de dados que inclua vários conjuntos de dados, cada conjunto é a sua própria entidade.

1. A caixa de diálogo **Power Query – Editar consultas** permite-lhe rever e refinar os dados. As entidades que os sistemas identificaram na sua origem de dados ligada aparecem no painel esquerdo.

   > [!div class="mx-imgBorder"]
   > ![Diálogo Editar consultas.](media/data-manager-configure-edit-queries.png "Diálogo Editar consultas")

1. Também pode transformar os seus dados. Selecione uma entidade para edição ou transformação. Utilize as opções na janela do Power Query para aplicar transformações. Cada transformação é listada em **Passos aplicados**. O Power Query fornece inúmeras opções de transformação pré-criadas. Para obter mais informações, veja [Transformações do Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Poderá adicionar entidades adicionar à sua origem de dados ao selecionar **Obter dados** na caixa de diálogo **Editar consultas**.

   Recomendamos que utilize as seguintes transformações:

   - Se estiver a ingerir dados a partir de um ficheiro CSV, a primeira linha contém frequentemente cabeçalhos. Aceda a **Tabela de transformar** e selecione **Utilizar os cabeçalhos como primeira linha**.
   - Certifique-se de que o tipo de dados está definido de forma adequada.

1. Selecione **Guardar** no final da janela do Power Query para guardar as transformações. Depois de guardar, encontrará a sua origem de dados em **Dados** > **Origens de dados**.

1. Na página **Origens de dados**, vai notar que a nova origem de dados está em estado **A atualizar**.

## <a name="available-power-query-data-sources"></a>Origens de dados do Power Query disponíveis

Consulte a [Referência do conector do Power Query](/power-query/connectors/) para obter uma lista de conectores que poderá utilizar para importar dados para o Customer Insights. 

Os conectores com uma marca de verificação na coluna **Customer Insights (Fluxos de dados)** estão disponíveis para criar novas origens de dados com base no Power Query. Reveja a documentação de um conector específico para saber mais sobre os seus pré-requisitos, limitações e outros detalhes.

## <a name="edit-power-query-data-sources"></a>Editar origens de dados do Power Query

> [!NOTE]
> Poderá não ser possível efetuar alterações às origens de dados que estão atualmente a ser utilizadas num dos processos da aplicação (*segmentação*, *corresponder* ou *intercalar*, por exemplo). 
>
> Na página **Definições**, pode monitorizar o progresso de cada um dos processos ativos. Quando um processo é concluído, pode regressar à página **Origens de Dados** e efetuar as suas alterações.

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

2. Selecione as reticências verticais junto da origem de dados que pretende alterar e selecione **Editar** no menu pendente.

   > [!div class="mx-imgBorder"]
   > ![Opção Editar.](media/edit-option-data-sources.png "Opção Editar")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Aplique as suas alterações e transformações no diálogo **Power Query – Editar consultas** como descrito na secção [Criar uma nova origem de dados](#create-a-new-data-source).

4. Selecione **Guardar** no Power Query depois de completar as suas edições para guardar as suas alterações.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

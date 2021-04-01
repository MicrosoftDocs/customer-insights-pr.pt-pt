---
title: Ingerir dados através de um conector Power Query
description: Conectores para origens de dados com base no Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596927"
---
# <a name="connect-to-a-power-query-data-source"></a>Ligue-se a uma origem de dados do Power Query

O Power Query oferece um vasto conjunto de conectores para ingerir dados. A maioria destes conectores são suportados pelo Dynamics 365 Customer Insights. A adição de origens de dados com base em conectores Power Query geralmente segue os passos descritos na secção seguinte. No entanto, dependendo do conector que utiliza, são necessárias informações diferentes. Para obter mais informações, consulte a documentação sobre os conectores individuais na [referência do conector Power Query](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Criar uma nova origem de dados

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Escolha o método **Importação de dados** e selecione **Seguinte**.

1. Forneça um **Nome** para a origem de dados e selecione **Seguinte** para criar a origem de dados. Nomear diretrizes: 
   - Comece com uma letra.
   - Utilize apenas letras e números. Não são permitidos carateres especiais e espaços.
   - Utilize entre 3 e 64 carateres.

1. Escolha um dos [conectores disponíveis](#available-power-query-data-sources). Para este exemplo, selecionamos o conector **Texto/CSV**.

1. Introduza os detalhes requeridos nas **Definições de ligação** para o conector selecionado e selecione **Seguinte** para ver uma pré-visualização dos dados.

1. Selecione **Transformar dados**. Neste passo, vai adicionar entidades à sua origem de dados. As entidades são conjuntos de dados. Se tiver uma base de dados que inclua vários conjuntos de dados, cada conjunto é a sua própria entidade.

1. A caixa de diálogo **Power Query – Editar consultas** permite-lhe rever e refinar os dados. As entidades que os sistemas identificaram na sua origem de dados ligada aparecem no painel esquerdo.

   > [!div class="mx-imgBorder"]
   > ![Diálogo Editar consultas](media/data-manager-configure-edit-queries.png "Diálogo Editar consultas")

1. Também pode transformar os seus dados. Selecione uma entidade para edição ou transformação. Utilize as opções na janela do Power Query para aplicar transformações. Cada transformação é listada em **Passos aplicados**. O Power Query fornece inúmeras opções de transformação pré-criadas. Para obter mais informações, veja [Transformações do Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Poderá adicionar entidades adicionar à sua origem de dados ao selecionar **Obter dados** na caixa de diálogo **Editar consultas**.

   Estas transformações são altamente recomendadas:

   - Se estiver a ingerir dados a partir de um ficheiro CSV, a primeira linha contém frequentemente cabeçalhos. Aceda a **Tabela de transformar** e selecione **Utilizar os cabeçalhos como primeira linha**.
   - Certifique-se de que o tipo de dados está definido de forma adequada.

1. Selecione **Guardar** no final da janela do Power Query para guardar as transformações. Depois de guardar, encontrará a sua origem de dados em **Dados** > **Origens de dados**.

1. Na página **Origens de dados**, vai notar que a nova origem de dados está em estado **A atualizar**.

## <a name="available-power-query-data-sources"></a>Origens de dados do Power Query disponíveis

Consulte a [referência do conector Power Query](/power-query/connectors/) para obter uma lista atualizada de conectores que pode selecionar para importar dados para o Customer Insights. 

Os conectores com uma marca de verificação na coluna **Customer Insights (Fluxos de dados)** estão disponíveis para criar novas origens de dados com base no Power Query. Reveja a documentação de um conector específico para saber mais sobre os seus pré-requisitos, limitações e outros detalhes.

## <a name="edit-power-query-data-sources"></a>Editar origens de dados do Power Query

> [!NOTE]
> Poderá não ser possível efetuar alterações às origens de dados que estão atualmente a ser utilizadas num dos processos da aplicação (*segmentação*, *corresponder* ou *intercalar*, por exemplo). 
>
> A utilização da página **Definições** permite monitorizar o progresso de cada um dos processos ativos. Quando um processo é concluído, pode regressar à página **Origens de Dados** e efetuar as suas alterações.

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

2. Selecione as reticências verticais junto à origem de dados que pretende alterar e selecione **Editar** a partir do menu pendente.

   > [!div class="mx-imgBorder"]
   > ![Opção Editar](media/edit-option-data-sources.png "Opção Editar")

3. Aplique as suas alterações e transformações no diálogo **Power Query – Editar consultas** como descrito na secção [Criar uma nova origem de dados](#create-a-new-data-source).

4. Selecione **Guardar** no Power Query depois de completar as suas edições para guardar as suas alterações.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
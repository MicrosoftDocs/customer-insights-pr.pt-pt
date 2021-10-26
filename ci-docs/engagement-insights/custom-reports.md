---
title: Acerca de relatórios personalizados
description: Saiba como criar e personalizar relatórios.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582891"
---
# <a name="create-and-edit-custom-reports"></a>Criar e editar relatórios personalizados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Além dos relatórios predefinidos (OOB), é possível criar um relatório personalizado com visualizações de gráficos e tabelas para o ajudar a compreender o comportamento dos utilizadores. Este artigo explica como criar um relatório com os dados de que necessita usando visualizações de tabelas e gráficos. Para obter informações sobre relatórios OOB, consulte [Ver relatórios](view-reports.md).

## <a name="create-a-custom-report"></a>Criar um relatório personalizado

1. Vá a **Analisar** > **Personalizado** para aceder à lista de relatórios personalizados.

1. Selecione **Novo relatório** para começar a criar um relatório personalizado.

   :::image type="content" source="media/new-custom-report.png" alt-text="Novos relatórios personalizados.":::

1. Decida o tipo de relatório que pretende construir:

    - Selecione **Adicionar visual** na barra de comando para criar uma visualização de tabela predefinida.
    - Ou, selecione uma coluna, barra, linha, área, tarte, donut ou visualização de tabela do painel de **Editor de relatório**.

1. Na secção **Dados** do painel **Editor de visualização**, escolha uma das opções disponíveis (por exemplo, vistas de página) a partir do menu pendente **Métrica**. Também pode adicionar **Dimensões** (por exemplo, país) para mostrar na visualização. Para mais informações, consulte [Ver e criar métricas](metrics.md) e [Ver e criar dimensões](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Escolha uma métrica para o seu relatório.":::

1. Selecione a secção **Design** do painel **Editor de visualização** para adicionar **Texto do título** e ativar e desativar o **Título**.  Também pode alterar o tipo de visualização selecionando outro gráfico, como **gráfico circular**.

1. Para alterar o tamanho e a posição de uma visualização:
   - Selecione a visualização e, em seguida, arraste um dos cantos ou bordas para ajustar o seu tamanho.
   - Selecione a visualização e mova-a para uma nova posição. Também pode utilizar as teclas de seta para alterar a posição.
1. Para adicionar outra visualização, selecione **Adicionar visual** na barra de comando.
1. Depois de adicionar as visualizações que pretende para o relatório, selecione **Guardar** na barra de comandos.

1. Forneça um nome para o relatório personalizado e selecione **Guardar** para o criar.
 
## <a name="filter-a-custom-report"></a>Filtrar um relatório personalizado

Pode selecionar o intervalo de tempo ou de datas num relatório personalizado para se concentrar num valor ou período de tempo.

Para selecionar um intervalo de tempo, no canto superior direito da vista do relatório, selecione um valor da lista pendente do relatório. Também pode escolher um **Intervalo de datas fixo*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtre por intervalo de tempo ou datas.":::

Para a maioria dos relatórios, selecione **+ Adicionar condição**, para escolher uma dimensão ou um segmento para filtrar o relatório. Para mais informações, consulte [Ver e criar segmentos](segments.md).

## <a name="edit-a-custom-report"></a>Editar um relatório personalizado

1. Vá a **Analisar** > **Personalizado** para aceder à lista de relatórios personalizados.

1. Na lista de relatórios personalizados, selecione **Mais [...]** 

1. Escolha **Editar nome** para alterar o nome do relatório.

1. Selecione o nome do relatório e utilize as opções de **+ Adicionar elemento visual** e **Editar** para adicionar, remover, reposicionar ou redimensionar as visualizações.

1. Para alterar as propriedades de uma visualização, selecione o elemento visual, selecione **...** e, em seguida, **Editar elemento visual**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Propriedades de gráfico de edição para relatórios personalizados.":::

1. Depois de editar o relatório, selecione **Guardar** para aplicar as suas alterações. 

## <a name="delete-a-custom-report"></a>Eliminar um relatório personalizado

1. Vá a **Analisar** > **Personalizado** para aceder à lista de relatórios personalizados.

1. Na lista de relatórios personalizados, selecione **...**

1. Escolha **Eliminar** para remover o relatório.

1. Confirme a sua eliminação para remover o relatório permanentemente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

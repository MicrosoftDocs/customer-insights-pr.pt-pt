---
title: Relatórios do funil
description: Como usar relatórios de funil para entender como a audiência toma decisões.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7c6b7b7285556f8a531ce9e29f0d1de162562be6fb43dd826a65fd9e00d87b30
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032269"
---
# <a name="create-and-manage-funnel-reports"></a>Criar e gerir relatórios de funil

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um relatório de funil recolhe informações sobre os passos que ocorrem durante um percurso do cliente através do seu site ou aplicação móvel. Ajuda-o a compreender como uma audiência progride através de um processo e identifica pontos de entrega. Por exemplo, pode usar um relatório de funil para identificar caminhos que os seus clientes tomam antes de fazerem uma compra. Um relatório de funil fornece dados para informar as decisões e identificar áreas para otimização e melhorias de processos.

## <a name="create-a-funnel-report"></a>Criar um relatório de funil

Para criar o relatório de funil, especifique os passos que pretende incluir e a atividade para cada passo. Uma atividade é um [evento](glossary.md) que representa o comportamento do utilizador. O relatório do funil apresenta o número de utilizadores que completaram cada passo definido. 

1. Vá a **Funis** e selecione **+Novo funil** para iniciar um relatório de funil.

1. No **Editor de funil**, em **Passos** selecione **+Adicionar passo.** 

1. Introduzir um nome no **Título do passo**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Novo relatório do funil.":::

1. Selecione uma **Atividade**. Uam atividade regista quando um utilizador vê uma página (atividade **Ver**) ou interage com conteúdo (atividade **Ação**).

1. Utilize **Critérios de passo** para especificar a dimensão da atividade. [Dimensões](dimensions.md) são atributos que podem descrever, filtrar ou agrupar dados.

1. Opcionalmente, pode configurar passos de funil com múltiplas condições. Selecione **Adicionar condição** para especificar mais dimensões num passo. Os critérios adicionais têm de utilizar o mesmo tipo de atividade. Pode escolher se várias condições estão ligadas a um operador AND ou OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor de funil a mostrar a configuração do passo com passos de múltiplas condições.":::

1. Selecione **Adicionar passo** até completar todos os passos que deseja no relatório.

1. Selecione **Guardar**, nomeie o relatório e **Guarde** novamente. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Exemplo: Relatório de funil da empresa Fourth Coffee

O seguinte cenário demonstra uma forma de utilizar um relatório de funil. Um analista da empresa Fourth Coffee quer entender a influência de uma promoção recente nas taxas de subscrição. O analista cria um relatório de funil para identificar a atividade do cliente. Começa quando os clientes chegam à página inicial da empresa até usarem o código de promoção de subscrição. O analista cria um relatório de funil com os seguintes passos:

Passo 1: Clientes que aterram na página inicial   
Passo 2: Clientes que fazem uma compra   
Passo 3: Clientes que usam o código de promoção para obter um desconto numa subscrição   
Passo 4: Assinatura de subscrição   

:::image type="content" source="media/funnel-report-example.png" alt-text="Exemplo de relatório funil.":::
  
Este funil permite-lhe ver o número de utilizadores que usaram o código de promoção após uma compra única para se inscrever no programa de subscrição.

### <a name="configure-advanced-settings"></a>Configurar definições avançadas 

Os relatórios de funil permitem definir um limite para o tempo que demora a concluir um funil. Por exemplo, pode definir o tempo de conclusão do funil para quatro dias. Esta definição contará apenas inscrições de subscrição bem sucedidas que ocorreram no prazo de quatro dias após a visita de um utilizador à página inicial.

1. Vá aos **funis** para abrir a **biblioteca de funis**.

1. Selecione um nome para abrir o relatório. 

1. No painel **Editor de Funil**, selecione **Definições avançadas**. 

1. Defina Limitar tempo de conclusão do funil como **Ligado**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor de funil a mostrar a definição avançada e opções para limitar o tempo para conclusão de um funil.":::

1. Escolha a hora em que o funil tem de ter sido preenchido na lista pendente **Definir limite para**.

1. Selecione **Guardar** para aplicar as alterações.


## <a name="cross-channel-funnel-reports"></a>Relatórios de funil entre canais 

As informações de cativação também podem recolher dados de comportamento do cliente na sua aplicação móvel. Uma vez instrumentalizada a sua aplicação móvel com o [SDK Android](get-started-android.md) ou [SDK iOS](get-started-ios.md) de informações de cativação, pode criar relatórios de funil entre canais. 

### <a name="create-a-cross-channel-funnel-report"></a>Criar um relatório de funil entre canais 

1. Siga os passos para [criar um relatório de funil](#create-a-funnel-report).    

1. Para monitorizar como os seus clientes estão a interagir com a sua marca através do seu site e aplicação móvel ou vários sites, use o comutador de área de trabalho para criar passos de funil com dados de outras áreas de trabalho. No **Editor de Funil** sob **Passos**, selecione de que área de trabalho devem vir os dados para o seu passo de funil.

## <a name="manage-funnel-reports"></a>Gerir relatórios de funil

Pode rever relatórios de funil para analisar dados, rastrear o desempenho e recolher informações.

> [!NOTE]
> - Os relatórios de funil de cativação suportam atualmente cenários em que todos os utilizadores do funil são anónimos ou todos os utilizadores são autenticados. 
> - Os dados históricos em relatórios de funil estão disponíveis nos últimos 30 dias.

### <a name="view-funnel-reports"></a>Ver relatórios do funil

1. Vá aos **funis** para abrir a **biblioteca de funis**.
1. Selecione um nome para abrir o relatório.    

### <a name="see-the-data-collected-for-a-report"></a>Consulte os dados recolhidos para um relatório   

Para ver informações sobre uma fase

- Aponte para um passo no relatório.

:::image type="content" source="media/funnel-step-data.png" alt-text="Dados de funil.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Alterar o intervalo de datas para o relatório do funil

1. Vá aos **funis** para abrir a **biblioteca de funis**.

1. Selecione um nome para abrir o relatório.

1. Abra o **intervalo de tempo** e selecione um novo período de tempo a partir da lista ou **Intervalo de datas fixas** para especificar um intervalo de datas.

## <a name="edit-or-delete-funnel-reports"></a>Editar ou eliminar relatórios de funil

Pode alterar o nome de um relatório de funil, eliminá-lo ou modificar os passos do relatório.

### <a name="rename-or-delete-a-funnel-report"></a>Renomear ou eliminar um relatório de funil

1. Vá aos **funis** para abrir a **biblioteca de funis**. 

1. Selecione **Mais** ao lado do relatório que pretende alterar e escolha **Editar nome** ou **Eliminar**.

### <a name="edit-a-funnel-step"></a>Editar um passo de funil  

1. Vá aos **funis** para abrir a **biblioteca de funis**. 

1. Selecione um nome para abrir o relatório.

1. Selecione o passo que pretende editar.

1. Selecione **Editar**.

1. No **Editor de funil**, atualize as informações que pretende alterar.  

1. Selecione **Guardar**.

### <a name="reorder-a-funnel-step"></a>Reordenar um passo de funil

1. Vá aos **funis** para abrir a **biblioteca de funis**. 

1. Selecione um nome para abrir o relatório.

1. Selecione o passo que pretende reordenar.

1. Selecione **Mover** e depois **Cima**, **Baixo**, **Para o topo** ou **Para baixo** para mover o passo.

### <a name="delete-a-funnel-step"></a>Eliminar um passo de funil

1. Vá aos **funis** para abrir a **biblioteca de funis**. 

1. Selecione um nome para abrir o relatório.

1. Selecione o passo que pretende remover e selecione **Eliminar**.


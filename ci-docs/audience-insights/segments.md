---
title: Segmentos nas informações de audiência
description: Descrição geral de segmentos e como criar e geri-los.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111401"
---
# <a name="segments-overview"></a>Descrição geral dos segmentos

Os segmentos permitem-lhe agrupar os seus clientes com base em atributos demográficos, transacionais, ou comportamentais. Pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para alcançar os seus objetivos de negócio.

Os perfis de cliente que correspondem aos filtros de uma definição de segmento são referidos como *membros* de um segmento. Aplicam-se alguns [limites de serviço](service-limits.md).

## <a name="create-a-new-segment"></a>Criar um novo segmento

Existem várias formas de criar um novo segmento: 

- Segmento complexo com criador de segmentos: [Segmento em branco](segment-builder.md#create-a-new-segment)
- Segmentos simples com um operador: [Segmento rápido](segment-builder.md#quick-segments)
- Forma de encontrar clientes semelhantes com tecnologia de IA: [Clientes Semelhantes](find-similar-customer-segments.md)
- Sugestões com tecnologia de IA baseadas em medidas ou atributos: [Segmentos sugeridos para melhorar medidas](suggested-segments.md)
- Sugestões baseadas em atividades: [Segmentos sugeridos baseados em atividades de cliente](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Gerir segmentos existentes

Vá à página **Segmentos**, para ver todos os seus segmentos guardados e geri-los.

Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selecionado com lista pendente de opções e opções disponíveis.":::

A seguinte ação está disponível quando seleciona um segmento:

- **Ver** os detalhes do segmento, incluindo a tendência da contagem de membros e uma pré-visualização dos membros do segmento.
- **Editar** o segmento para alterar as respetivas propriedades.
- **Criar duplicado** de um segmento. Pode optar por editar as suas propriedades imediatamente ou simplesmente guardar o duplicado.
- **Atualizar** o segmento para incluir os dados mais recentes.
- **Ativar** ou **desativar** o segmento. Os segmentos têm dois estados possíveis – ativos ou inativos. Estes estados são úteis ao editar um segmento. Para segmentos inativos, a definição de segmento existe, mas ainda não contém nenhum cliente. Quando ativa um segmento, o seu estado muda de "inativo" para "ativo" e começa a procurar clientes que correspondam à definição do segmento. Se uma [atualização agendada](system.md#schedule-tab) for configurada, os segmentos inativos têm o **Estado** listado como **Ignorado** indicando que uma atualização nem sequer foi tentada. Quando um segmento inativo é ativado, ele irá atualizar e será incluído em atualizações agendadas.
  Em alternativa, pode utilizar a funcionalidade **Agendar mais tarde** no menu pendente **Ativar/Desativar** para especificar uma data e hora futuras para ativação e desativação de um determinado segmento.
- **Mudar nome** do segmento.
- **Transferir** a lista de membros como um ficheiro .CSV.
- **Faça a gestão de exportações** para ver o segmento relacionado com as exportações e geri-las. [Saber mais sobre exportações.](export-destinations.md)
- **Eliminar** o segmento.

## <a name="refresh-segments"></a>Atualizar segmentos

Pode atualizar todos os segmentos de uma só vez selecionando **Atualizar tudo** na página **Segmentos** ou pode atualizar um ou vários segmentos quando os seleciona e escolher **Atualizar** nas opções. Em alternativa, poderá configurar uma atualização recorrente em **Administração** > **Sistema** > **Agendar**.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="export-segments"></a>Exportar segmentos

Pode exportar um segmento a partir da página de segmentos ou da [página de exportações](export-destinations.md). 

1. Ir para a página **Segmentos**.

1. Selecione **Mostrar mais [...]** para o segmento que pretende exportar.

1. Selecione **Gerir exportações** na lista pendente de ações.

1. A página **Exportações (pré-visualização) para segmento** abre-se. Pode ver todas as exportações configuradas agrupadas por exportações que contêm o segmento atual ou não o contêm.

   1. Para adicionar o segmento selecionado a uma exportação, selecione a exportação na lista e selecione **Adicionar segmento**.

   1. Para criar uma nova exportação com o segmento selecionado, selecione **Adicionar exportação**. Para mais informações sobre a criação de exportações, consulte [Configurar uma nova exportação](export-destinations.md#set-up-a-new-export).

1. Selecione **Anterior** para a regressar à página principal para segmentos.

## <a name="view-processing-history-and-segment-members"></a>Ver histórico de processamento e membros do segmento

Poderá ver os dados consolidados sobre um segmento ao analisar os respetivos detalhes.

Na página **Segmentos**, selecione o segmento que pretende analisar.

A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros. Passe o rato sobre os pontos de dados para ver a contagem de membros numa data específica.

Poderá atualizar o intervalo de tempo da visualização.

> [!div class="mx-imgBorder"]
> ![Intervalo de tempo do segmento](media/segment-time-range.png "Intervalo de tempo do segmento")

A parte inferior contém uma lista dos membros do segmento.

> [!NOTE]
> Os campos apresentados nesta lista baseiam-se nos atributos das entidades do segmento.
>
>A lista é uma pré-visualização dos membros do segmento correspondente e mostra os primeiros 100 registos do seu segmento para poder avaliá-lo rapidamente e rever as definições, se for necessário. Para ver todos os registos correspondentes, tem de [exportar o segmento](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 

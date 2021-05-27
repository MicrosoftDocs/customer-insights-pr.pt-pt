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
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034026"
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

## <a name="get-insights-on-existing-segments"></a>Obter informações sobre segmentos existentes

Descubra informações adicionais em torno dos segmentos existentes com [Informações de segmentos](segment-insights.md). Descubra o que diferencia dois segmentos ou o que têm em comum.

## <a name="find-similar-customers"></a>Encontrar clientes semelhantes

Encontre clientes semelhantes aos membros de um segmento selecionado com a ajuda de inteligência artificial. Para mais informações, consulte [clientes semelhantes](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Gerir segmentos existentes

Vá à página **Segmentos**, para ver todos os seus segmentos guardados e geri-los.

Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.

> [!div class="mx-imgBorder"]
> ![Opções para gerir um segmento existente](media/segments-selected-segment.png "Opções para gerir um segmento existente")

A seguinte ação está disponível quando seleciona um segmento:

- **Ver** os detalhes do segmento, incluindo a tendência da contagem de membros e uma pré-visualização dos membros do segmento.
- **Editar** o segmento para alterar as respetivas propriedades.
- **Criar duplicado** de um segmento. Pode optar por editar as suas propriedades imediatamente ou simplesmente guardar o duplicado.
- **Atualizar** o segmento para incluir os dados mais recentes.
- **Ativar** ou **desativar** o segmento. Os segmentos têm dois estados possíveis – ativos ou inativos. Estes estados são úteis ao editar um segmento. Para segmentos inativos, a definição de segmento existe, mas ainda não contém nenhum cliente. Quando ativa um segmento, o seu estado muda de "inativo" para "ativo" e começa a procurar clientes que correspondam à definição do segmento. Se uma [atualização agendada](system.md#schedule-tab) for configurada, os segmentos inativos têm o **Estado** listado como **Ignorado** indicando que uma atualização nem sequer foi tentada. Quando um segmento inativo é ativado, ele irá atualizar e será incluído em atualizações agendadas.
  Em alternativa, pode utilizar a funcionalidade **Agendar mais tarde** no menu pendente **Ativar/Desativar** para especificar uma data e hora futuras para ativação e desativação de um determinado segmento.
- **Mudar nome** do segmento.
- **Transferir** a lista de membros como um ficheiro .CSV.
- A opção **Adicionar a** envia a lista de IDs do cliente no segmento para processamento noutra aplicação.
- **Eliminar** o segmento.

## <a name="refresh-segments"></a>Atualizar segmentos

Pode atualizar todos os segmentos de uma só vez selecionando **Atualizar tudo** na página **Segmentos** ou pode atualizar um ou vários segmentos quando os seleciona e escolher **Atualizar** nas opções. Em alternativa, poderá configurar uma atualização recorrente em **Administração** > **Sistema** > **Agendar**.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

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

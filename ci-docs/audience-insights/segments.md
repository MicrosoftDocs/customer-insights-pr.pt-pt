---
title: Segmentos nas informações de audiência
description: Descrição geral de segmentos e como criar e geri-los.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 740d293b21f43b50201f23fcba109318823ef3af
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978073"
---
# <a name="segments-overview"></a>Descrição geral dos segmentos

Os segmentos permitem-lhe agrupar os seus clientes com base em atributos demográficos, transacionais, ou comportamentais. Pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para alcançar os seus objetivos de negócio.

Os perfis de cliente que correspondem aos filtros de uma definição de segmento são referidos como *membros* de um segmento. Aplicam-se alguns [limites de serviço](service-limits.md).

## <a name="create-a-new-segment"></a>Criar um novo segmento

Existem várias formas de criar um novo segmento: 

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- Segmento complexo com construtor de segmentos: [Criar o nosso próprio](segment-builder.md#create-a-new-segment) 
- Segmentos simples com um operador: [Segmento rápido](segment-builder.md#quick-segments) 
- Forma de encontrar clientes semelhantes com tecnologia de IA: [Clientes Semelhantes](find-similar-customer-segments.md) 
- Sugestões com tecnologia de IA baseadas em medidas ou atributos: [Segmentos sugeridos para melhorar medidas](suggested-segments.md) 
- Sugestões baseadas em atividades: [Segmentos sugeridos baseados em atividades de cliente](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- Segmento complexo com construtor de segmentos: [Criar o nosso próprio](segment-builder.md#create-a-new-segment)

---

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Pode exportar um segmento a partir da página de segmentos ou da [página de exportações](export-destinations.md). 

1. Ir para a página **Segmentos**.

1. Selecione **Mostrar mais [...]** para o segmento que pretende exportar.

1. Selecione **Gerir exportações** da lista pendente de ações.

1. A página **Exportações (pré-visualização) para segmento** abre-se. Pode ver todas as exportações configuradas agrupadas pelo facto de conterem ou não o segmento atual.

   1. Para adicionar o segmento selecionado a uma exportação, **Edite** a respetiva exportação para selecionar o segmento correspondente e, em seguida, guarde. Em ambientes para clientes individuais pode, em vez disso, selecionar a exportação na lista e selecionar **Adicionar segmento** para obter o mesmo resultado.

   1. Para criar uma nova exportação com o segmento selecionado, selecione **Adicionar exportação**. Para mais informações sobre a criação de exportações, consulte [Configurar uma nova exportação](export-destinations.md#set-up-a-new-export).

1. Selecione **Anterior** para a regressar à página principal para segmentos.

## <a name="view-processing-history-and-segment-members"></a>Ver histórico de processamento e membros do segmento

Poderá ver os dados consolidados sobre um segmento ao analisar os respetivos detalhes.

Na página **Segmentos**, selecione o segmento que pretende analisar.

A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros. Passe o rato sobre os pontos de dados para ver a contagem de membros numa data específica.

Poderá atualizar o intervalo de tempo da visualização.

> [!div class="mx-imgBorder"]
> ![Intervalo de tempo do segmento.](media/segment-time-range.png "Intervalo de tempo do segmento")

A parte inferior contém uma lista dos membros do segmento.

> [!NOTE]
> Os campos apresentados nesta lista baseiam-se nos atributos das entidades do segmento.
>
>A lista é uma pré-visualização dos membros do segmento correspondente e mostra os primeiros 100 registos do seu segmento para poder avaliá-lo rapidamente e rever as definições, se for necessário. Para ver todos os registos correspondentes, tem de [exportar o segmento](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)] 

---
title: Segmentos no Customer Insights
description: Descrição geral de segmentos e como criar e geri-los.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800756"
---
# <a name="segments-overview"></a>Descrição geral dos segmentos

Os segmentos permitem-lhe agrupar os seus clientes com base em atributos demográficos, transacionais, ou comportamentais. Pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para alcançar os seus objetivos de negócio.

Os perfis de cliente que correspondem aos filtros de uma definição de segmento são referidos como *membros* de um segmento. Aplicam-se alguns [limites de serviço](/dynamics365/customer-insights/service-limits).

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

Vá à página **Segmentos** para ver todos os seus segmentos guardados e geri-los.

Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selecionado com lista pendente de opções e opções disponíveis." lightbox="media/segments-selected-segment.png":::

As seguintes ações estão disponíveis quando seleciona um segmento:

- **Ver** os detalhes do segmento, incluindo a tendência da contagem de membros e uma pré-visualização dos membros do segmento.
- **Transferir** a lista de membros como um ficheiro .CSV.
- **Editar** o segmento para alterar as respetivas propriedades.
- **Criar duplicado** de um segmento. Pode optar por editar de imediato as respetivas propriedades ou guardar o duplicado.
- **Atualizar** o segmento para incluir os dados mais recentes.
- **Ativar** ou **desativar** o segmento. Para segmentos inativos, a definição de segmento existe, mas ainda não contém nenhum cliente. Um segmento ativo procura por clientes que correspondem à definição do segmento. Se uma [atualização agendada](system.md#schedule-tab) for configurada, os segmentos inativos têm o **Estado** listado como **Ignorado** indicando que uma atualização nem sequer foi tentada. Quando um segmento inativo é ativado, ele irá atualizar e será incluído em atualizações agendadas.
  Em alternativa, pode utilizar a funcionalidade **Agendar mais tarde** no menu pendente **Ativar/Desativar** para especificar uma data e hora futuras para ativação e desativação de um determinado segmento.
- **[Encontre clientes semelhantes](find-similar-customer-segments.md)** a partir do segmento.
- **Mudar nome** do segmento.
- **Etiqueta** para [gerir etiquetas](work-with-tags-columns.md#manage-tags) para o segmento.
- **Transferir** a lista de membros como um ficheiro .CSV.
- **Faça a gestão de exportações** para ver o segmento relacionado com as exportações e geri-las. [Saber mais sobre exportações.](export-destinations.md)
- **Eliminar** o segmento.
- **Colunas** para [personalizar as colunas](work-with-tags-columns.md#customize-columns) que são apresentadas.
- **Filtrar** para [filtrar em etiquetas](work-with-tags-columns.md#filter-on-tags).
- **Pesquisar nome** para pesquisar por nome de segmento.

## <a name="refresh-segments"></a>Atualizar segmentos

Pode atualizar todos os segmentos de uma só vez selecionando **Atualizar tudo** na página **Segmentos** ou pode atualizar um ou vários segmentos quando os seleciona e escolher **Atualizar** nas opções. Em alternativa, poderá configurar uma atualização recorrente em **Administração** > **Sistema** > **Agendar**. Quando uma atualização recorrente é configurada, aplicam-se as seguintes regras:

- Todos os segmentos com o tipo **Dinâmico** ou **Expansão** serão automaticamente atualizados na cadência definida. Assim que a atualização estiver concluída, o **Estado** indica se houve quaisquer problemas na atualização do segmento. A **Última atualização** mostra um carimbo de data/hora da última atualização bem sucedida. Se ocorrer um erro, selecione o erro para ver os detalhes sobre o que aconteceu.
- Os segmentos com o tipo **Estático** *não* serão atualizados automaticamente. A **Última atualização** mostra um carimbo de data/hora da última vez que os segmentos estáticos foram executados ou atualizados manualmente.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Pode exportar um segmento a partir da página de segmentos ou da [página de exportações](export-destinations.md). 

1. Ir para a página **Segmentos**.

1. Selecione as reticências verticais (&vellip;) do segmento que pretende exportar.

1. Selecione **Gerir exportações** da lista pendente de ações.

1. A página **Exportações (pré-visualização) para segmento** abre-se. Pode ver todas as exportações configuradas agrupadas pelo facto de conterem ou não o segmento atual.

   1. Para adicionar o segmento selecionado a uma exportação, **Edite** a respetiva exportação para selecionar o segmento correspondente e, em seguida, guarde. Em ambientes para clientes individuais pode, em vez disso, selecionar a exportação na lista e selecionar **Adicionar segmento** para obter o mesmo resultado.

   1. Para criar uma nova exportação com o segmento selecionado, selecione **Adicionar exportação**. Para mais informações sobre a criação de exportações, consulte [Configurar uma nova exportação](export-destinations.md#set-up-a-new-export).

1. Selecione **Anterior** para a regressar à página principal para segmentos.

## <a name="track-usage-of-a-segment"></a>Monitorizar a utilização de um segmento

Se utilizar segmentos em aplicações, as quais são baseadas na mesma organização do Microsoft Dataverse que está ligada ao Customer Insights, poderá monitorizar a utilização de um segmento. Para [Segmentos do Customer Insights utilizados em percursos do cliente do Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), o sistema informa-o sobre a utilização desse segmento.

Quando edita um segmento que está a ser utilizado no ambiente do Customer Insights ou num percurso do cliente no Marketing, uma faixa no [construtor de segmentos](segment-builder.md) informa-o sobre as dependências. Pode inspecionar os detalhes da dependência diretamente a partir da faixa ou selecionando **Utilização** no construtor de segmentos.

O painel **Utilização de segmentos** mostra os detalhes sobre a utilização deste segmento nas aplicações baseadas do Dataverse. No caso de segmentos utilizados em percursos do cliente, encontrará uma ligação para inspecionar o percurso no Marketing, onde este segmento é utilizado. Se tiver permissões para aceder à aplicação Marketing, poderá aceder a mais detalhes aí.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Painel lateral com detalhes da utilização do segmento no construtor de segmentos.":::

O sistema informa-o sobre a utilização de um segmento monitorado quando tenta eliminá-lo. Se o segmento que está prestes a eliminar for utilizado num percurso do cliente no Marketing, esse percurso vai parar para todos os utilizadores do segmento. Se o percurso fizer parte de uma campanha de marketing, a eliminação irá afetar a própria campanha. No entanto, ainda pode eliminar o segmento, apesar dos avisos.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Caixa de diálogo para confirmar a eliminação do segmento quando um segmento é utilizado numa aplicação do Dataverse.":::

### <a name="supported-apps"></a>Aplicações suportadas

A utilização é monitorizada atualmente nas seguintes aplicações baseadas no Dataverse:

- [Percursos do cliente no Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

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

[!INCLUDE [footer-include](includes/footer-banner.md)]

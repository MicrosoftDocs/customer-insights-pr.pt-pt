---
title: Descrição geral dos segmentos
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
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246307"
---
# <a name="segments-overview"></a>Descrição geral dos segmentos

Os segmentos permitem-lhe agrupar os seus clientes com base em atributos demográficos, transacionais, ou comportamentais. Pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para alcançar os seus objetivos de negócio.

Os perfis de cliente que correspondem aos filtros de uma definição de segmento são referidos como *membros* de um segmento. Aplicam-se alguns [limites de serviço](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Criar um segmento

Escolha como criar um segmento baseado na audiência de destino.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- Segmentos complexos com construtor de segmentos: [Criar o seu próprio](segment-builder.md)
- Segmentos simples com um operador: [Segmento rápido](segment-quick.md)
- Forma de encontrar clientes semelhantes com tecnologia de IA: [Clientes semelhantes](find-similar-customer-segments.md)
- Sugestões com tecnologia de IA baseadas em medidas ou atributos: [Segmentos sugeridos baseado nas medidas](suggested-segments.md)
- Sugestões baseadas em atividades: [Segmentos sugeridos baseados em atividades de cliente](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- Segmentos simples ou complexos com construtor de segmentos: [Criar o seu próprio](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Gerir segmentos existentes

Vá para a página **Segmentos** para ver os segmentos que criou, o seu estado e estatuto, o número de membros e a última vez que os dados foram atualizados. Pode ordenar a lista de segmentos por qualquer coluna ou utilizar a caixa de pesquisa para encontrar o segmento que pretende gerir.

Selecione um segmento para ver as ações disponíveis.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selecionado com lista pendente de opções e opções disponíveis." lightbox="media/segments-selected-segment.png":::

- [**Ver**](#view-segment-details) os detalhes do segmento, incluindo a tendência da contagem de membros e uma pré-visualização dos membros do segmento.
- **Transferir** a lista de membros como um ficheiro .CSV.
- **Editar** o segmento para alterar as respetivas propriedades.
- **Criar duplicado** de um segmento. Pode optar por editar de imediato as respetivas propriedades ou guardar o duplicado.
- [**Atualizar**](#refresh-segments) o segmento para incluir os dados mais recentes.
- **Ativar** ou **desativar** o segmento. Os segmentos inativos não serão atualizadas durante uma [atualização agendada](schedule-refresh.md) e têm o **Estado** listado como **Ignorado** indicando que uma atualização nem sequer foi tentada. Os segmentos ativos são atualizados com base no respetivo tipo: estático ou dinâmico.
- **Tornar estáticos** ou **Tornar dinâmicos** o tipo de segmento. Os segmentos estáticos têm de ser atualizados manualmente. Os segmentos dinâmicos são atualizados de forma dinâmica durante as atualizações do sistema.
- [**Encontre clientes semelhantes**](find-similar-customer-segments.md) a partir do segmento.
- **Mudar nome** do segmento.
- **Etiqueta** para [gerir etiquetas](work-with-tags-columns.md#manage-tags) para o segmento.
- [**Gerir exportações**](#export-segments) para ver os segmentos relacionados com a exportação e geri-los. [Saber mais sobre exportações.](export-destinations.md)
- **Eliminar** o segmento.
- **Colunas** para [personalizar as colunas](work-with-tags-columns.md#customize-columns) que são apresentadas.
- **Filtrar** para [filtrar em etiquetas](work-with-tags-columns.md#filter-on-tags).
- **Pesquisar nome** para pesquisar por nome de segmento.

## <a name="view-segment-details"></a>Ver detalhes do segmento

Na página **Segmentos**, selecione um segmento para ver o histórico de processamentos e os membros do segmento.

A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros. Passe o rato sobre os pontos de dados para ver a contagem de membros numa data específica. Altere o intervalo de tempo da visualização.

:::image type="content" source="media/segment-time-range.png" alt-text="Intervalo de tempo do segmento.":::

A parte inferior contém uma lista dos membros do segmento.

> [!NOTE]
> Os campos apresentados nesta lista baseiam-se nos atributos das entidades do segmento.
>
>A lista é uma pré-visualização dos membros do segmento correspondente e mostra os primeiros 100 registos do seu segmento para poder avaliá-lo rapidamente e rever as definições, se for necessário. Para ver todos os registos correspondentes, [exporte o segmento](export-destinations.md).

## <a name="refresh-segments"></a>Atualizar segmentos

Os segmentos podem ser atualizados com um agendamento automático ou atualizadas manualmente a pedido. Para atualizar manualmente um ou mais segmentos, selecione-os e escolha **Atualizar**.

Para [agendar uma atualização automática](schedule-refresh.md), aceda a **Admin** > **Sistema** > **Agendar**. Aplicam-se as seguintes regras:

- Todos os segmentos com o tipo **Dinâmico** ou **Expansão** serão automaticamente atualizados na cadência definida. Assim que a atualização estiver concluída, o **Estado** indica se houve quaisquer problemas na atualização do segmento. A **Última atualização** mostra um carimbo de data/hora da última atualização bem sucedida. Se ocorrer um erro, selecione o erro para ver os detalhes sobre o que aconteceu.
- Os segmentos com o tipo **Estático** *não* serão atualizados automaticamente. A **Última atualização** mostra um carimbo de data/hora da última vez que o segmento estático foi executado ou atualizado manualmente.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Exporte os segmentos para outras aplicações para continuar a utilizar os dados. Exporte um segmento a partir da página de segmentos ou da [página de exportações](export-destinations.md).

1. Vá para **Segmentos** e selecione o segmento que pretende exportar.

1. Selecione **Gerir exportações**. A página **Exportações (pré-visualização) para segmento** abre-se. Veja todas as exportações configuradas agrupadas pelo facto de conterem ou não o segmento atual.

   1. Para adicionar o segmento selecionado a uma exportação, **Edite** a respetiva exportação para selecionar o segmento correspondente e, em seguida, guarde. Em ambientes para clientes individuais,selecione a exportação na lista e selecione **Adicionar segmento** para obter o mesmo resultado.

   1. Para criar uma nova exportação com o segmento selecionado, selecione **Adicionar exportação**. Para mais informações sobre a criação de exportações, consulte [Configurar uma nova exportação](export-destinations.md#set-up-a-new-export).

1. Selecione **Anterior** para a regressar à página principal para segmentos.

## <a name="track-usage-of-a-segment"></a>Monitorizar a utilização de um segmento

Se utilizar segmentos em aplicações, as quais são baseadas na mesma organização do Microsoft Dataverse que está ligada ao Customer Insights, poderá monitorizar a utilização de um segmento. Para [Segmentos do Customer Insights utilizados em percursos do cliente do Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), o sistema informa-o sobre a utilização desse segmento.

Quando edita um segmento que está a ser utilizado no ambiente do Customer Insights ou num percurso do cliente no Marketing, uma faixa no [construtor de segmentos](segment-builder.md) informa-o sobre as dependências. Inspecione os detalhes da dependência diretamente a partir da faixa ou selecionando **Utilização** no construtor de segmentos.

O painel **Utilização de segmentos** mostra os detalhes sobre a utilização deste segmento nas aplicações baseadas do Dataverse. No caso de segmentos utilizados em percursos do cliente, encontrará uma ligação para inspecionar o percurso no Marketing, onde este segmento é utilizado. Se tiver permissões para aceder à aplicação Marketing, Veja mais detalhes aí.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Painel lateral com detalhes da utilização do segmento no construtor de segmentos.":::

O sistema informa-o sobre a utilização de um segmento monitorado quando tenta eliminá-lo. Se o segmento que está prestes a eliminar for utilizado num percurso do cliente no Marketing, esse percurso vai parar para todos os utilizadores do segmento. Se o percurso fizer parte de uma campanha de marketing, a eliminação irá afetar a própria campanha. No entanto, ainda pode eliminar o segmento, apesar dos avisos.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Caixa de diálogo para confirmar a eliminação do segmento quando um segmento é utilizado numa aplicação do Dataverse.":::

### <a name="supported-apps"></a>Aplicações suportadas

A utilização é monitorizada atualmente nas seguintes aplicações baseadas no Dataverse:

- [Percursos do cliente no Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]

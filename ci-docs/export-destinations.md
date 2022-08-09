---
title: Descrição geral de exportações (pré-visualização)
description: Gerir exportações para partilhar dados.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194982"
---
# <a name="exports-preview-overview"></a>Descrição geral de exportações (pré-visualização)

 As exportações permitem partilhar dados específicos com várias aplicações. Podem incluir perfis de clientes, entidades, esquemas e detalhes de mapeamento. Cada exportação requer uma [ligação, configurada por um administrador, para gerir a autenticação e o acesso](connections.md). A página **Exportações** mostra todas as exportações configuradas.

## <a name="export-types"></a>Tipos de exportação

Existem dois tipos principais de exportação:  

- As **exportações de saída de dados** permitem exportar qualquer tipo de entidade disponível no Customer Insights. As entidades que seleciona para exportação são exportadas com todos os campos de dados, metadados, esquemas e detalhes de mapeamento.
- **Exportações de segmentos**: exporte entidades de segmentos do Customer Insights. Os segmentos representam uma lista de perfis de clientes. Ao configurar a exportação, selecione os campos de dados incluídos, dependendo do sistema de destino para o qual está a exportar dados.

### <a name="export-segments"></a>Exportar segmentos

**Exportar segmentos em ambientes para contas empresariais (B2B) ou consumidores individuais (B2C)**  
A maioria das opções de exportação suportam ambos os tipos de ambientes. A exportação de segmentos para vários sistemas de destino tem requisitos específicos. 

**Exportações de segmentos em ambientes para consumidores individuais (B2C)**  
- Os segmentos no contexto de ambientes para clientes individuais são baseados na entidade *perfil do cliente unificado*. Todos os segmentos que satisfaçam os requisitos dos sistemas de destino (por exemplo, um endereço de e-mail) podem ser exportados.

**Ambientes de exportação de segmentos para contas empresariais (B2B)**  
- Os segmentos no contexto de ambientes para contas empresariais são baseados na entidade *conta*. Para exportar segmentos de contas como está, o sistema de destino precisa de suportar segmentos de contas completos. É o caso do [LinkedIn](export-linkedin-ads.md) quando escolhe a opção **empresa** enquanto define a exportação.
- Todos os outros sistemas de destino requerem campos da entidade de contacto. Para garantir que os segmentos de contas podem obter dados de contactos relacionados, a definição do segmento precisa de projetar atributos da entidade de contacto. Saiba mais sobre como [configurar segmentos e projetar atributos](segment-builder.md).

**Limites às exportações de segmentos**  
- Os sistemas de destino de terceiros podem limitar o número de perfis de clientes que pode exportar. 
- Para clientes individuais, verá o número real de membros do segmento quando seleciona um segmento para exportação. Obterá um aviso se um segmento for muito grande. 
- Para contas empresariais, verá o número de contas num segmento; no entanto, o número de contactos que podem ser projetados não é apresentado. Em alguns casos, isto poderia levar a que o segmento exportado realmente contenha mais perfis de clientes do que o sistema de destino aceita. Se os limites do sistema de destino tiver excedido, a exportação é ignorada.

## <a name="set-up-a-new-export"></a>Configurar uma nova exportação

Para configurar ou editar uma exportação, precisa das ligações certas disponíveis para si. As ligações dependem da sua [função de utilizador](permissions.md):
- Os **administradores** têm acesso a todas as ligações. Podem também criar novas ligações ao configurar uma exportação.
- Os **contribuidores** podem ter acesso a ligações específicas. Dependem dos administradores para configurar e partilhar ligações. A lista de exportações mostra aos contribuidores se podem editar ou apenas ver uma exportação na coluna **As suas permissões**. Para mais informações, aceda a [Permitir que os contribuidores utilizem uma ligação para as exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os **visualizadores** só podem ver as exportações existentes, mas não podem criá-las.

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação** para criar um nova exportação.

1. No painel **Configurar exportação**, selecione a [ligação](connections.md) a utilizar.

1. Forneça os detalhes necessários e selecione **Guardar** para criar a exportação. Para obter os detalhes necessários, consulte a documentação do Customer Insights para a exportação específica.

## <a name="manage-existing-exports"></a>Gerir exportações existentes

Vá para **Dados** > **Exportações** para ver as exportações, o respetivo nome de ligação, o tipo de ligação e o estado. Todas as funções de utilizador podem ver exportações configuradas. Pode ordenar a lista de exportações por qualquer coluna ou utilizar a caixa de pesquisa para encontrar a exportação que pretende gerir.

Selecione uma exportação para ver as ações disponíveis.

:::image type="content" source="media/exports_showmore.png" alt-text="Página Exportações.":::

- **Ver** ou **Editar** a exportação. Os utilizadores sem permissões de edição selecionam **Ver** em vez de **Editar** para ver os detalhes da exportação.
- **Executar** a exportação para exportar os dados mais recentes.
- **Criar duplicado** de uma exportação.
- **[Agendar](#schedule-and-run-exports)** a exportação.
- **Desanexar ligação** para remover a ligação para esta exportação. Desanexar não remove a ligação, mas desativa a exportação. A coluna **Ligação utilizada** apresenta Sem Ligação.
- **Remover** a exportação.

## <a name="schedule-and-run-exports"></a>Agendar e executar exportações

Cada exportação que configura tem uma agenda de atualização. Durante uma atualização, o sistema procura dados novos ou atualizados a incluir numa exportação. Por predefinição, as exportações são executadas como parte de cada [atualização de sistema agendada](system.md#schedule-tab). Pode personalizar a agenda de atualização ou desativá-la para executar exportações manualmente.

As agendas de exportação dependem do estado do seu ambiente. Se houver atualizações em curso sobre as [dependências](system.md#refresh-processes) quando uma exportação agendada deveria começar, o sistema completará primeiro as atualizações e, em seguida, executará a exportação. A coluna **Atualizada** mostra quando uma exportação foi atualizada pela última vez.

### <a name="schedule-exports"></a>Agendar exportações

Defina agendas de atualização personalizadas para exportações individuais ou várias exportações ao mesmo tempo. A agenda atualmente definida está listada na coluna **Agenda** da lista de exportação. A permissão para alterar a agenda é a mesma que para [editar e definir exportações](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Selecione a exportação que pretende agendar.

1. Selecione **Agendar**.

1. No painel **Agendar exportação**, defina **Agendar execução** para **Ativada** para executar a exportação automaticamente. Defina-a como **Desativada** para a atualizar manualmente.

1. Para exportações automaticamente atualizadas, escolha um valor de **Periodicidade** e especifique os respetivos detalhes. O tempo definido aplica-se a todas as instâncias de periodicidade. É o momento em que uma exportação deve começar a atualizar.

1. Selecione **Guardar**.

Ao editar a agenda para várias exportações, faça uma seleção em **Manter ou substituir agendas**:

- **Manter agendas individuais**: mantenha a agenda previamente definida para as exportações selecionadas e apenas as desativa ou ativa.
- **Definir nova agenda para todas as exportações selecionadas**: substitui as agendas existentes das exportações selecionadas.

### <a name="run-exports-on-demand"></a>Executar exportações a pedido

Para exportar dados sem esperar por uma atualização agendada, vá a **Dados** > **Exportações**.

- Para executar todas as exportações, selecione **Executar todas** na barra de comandos. Só as exportações que tenham uma agenda ativa são executadas. Para executar uma exportação que não está ativa, execute uma única exportação.
- Para executar uma única exportação, selecione-a na lista e selecione **Executar** na barra de comandos.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]

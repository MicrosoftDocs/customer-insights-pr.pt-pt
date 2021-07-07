---
title: Exportar dados do Customer Insights
description: Gerir exportações para partilhar dados.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305492"
---
# <a name="exports-preview-overview"></a>Descrição geral de exportações (pré-visualização)

A página **Exportações** mostra todas as exportações configuradas. As exportações partilham dados específicos com várias aplicações. Podem incluir perfis de clientes ou entidades, esquemas e detalhes de mapeamento. Cada exportação requer uma [ligação, configurada por um administrador, para gerir a autenticação e o acesso](connections.md).

Vá a **Dados** > **Exportações** para ver a página de exportações. Todas as funções de utilizador podem ver exportações configuradas. Utilize o campo de pesquisa na barra de comando para encontrar exportações pelo nome, nome da ligação ou tipo de ligação.

## <a name="set-up-a-new-export"></a>Configurar uma nova exportação

Para configurar ou editar uma exportação, precisa de ter ligações disponíveis para si. As ligações dependem da sua [função de utilizador](permissions.md):
- Os administradores têm acesso a todas as ligações. Podem também criar novas ligações ao configurar uma exportação.
- Os contribuidores podem ter acesso a ligações específicas. Dependem dos administradores para configurar e partilhar ligações. A lista de exportações mostra aos contribuidores se podem editar ou apenas ver uma exportação na coluna **As suas permissões**. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os visualizadores só podem ver exportações existentes, mas não criá-las.

### <a name="define-a-new-export"></a>Definir uma nova exportação

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação** para criar um nova exportação.

1. No painel **Configurar exportação**, selecione que ligação utilizar. As [Ligações](connections.md) são geridas por administradores. 

1. Forneça os detalhes necessários e selecione **Guardar** para criar a exportação.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Defina uma nova exportação com base numa exportação existente

1. Aceda a **Dados** > **Exportações**.

1. Na lista de exportações, selecione a exportação que pretende duplicar.

1. Selecione **Criar duplicado** na barra de comandos para abrir o painel **Configurar exportação** com os detalhes da exportação selecionada.

1. Reveja e adapte a exportação e selecione **Guardar** para criar uma nova exportação.

### <a name="edit-an-export"></a>Editar uma exportação

1. Aceda a **Dados** > **Exportações**.

1. Na lista de exportações, selecione a exportação que pretende editar.

1. Selecione **Editar** na barra de comandos.

1. Altere os valores que pretende atualizar e selecione **Guardar**.

## <a name="view-exports-and-export-details"></a>Ver exportações e detalhes da exportação

Depois de criar destinos de exportação, são listados em **Dados** > **Exportações**. Todos os utilizadores podem ver que dados são partilhados e o respetivo estado mais recente.

1. Aceda a **Dados** > **Exportações**.

1. Os utilizadores sem permissões de edição selecionam **Ver** em vez de **Editar** para ver os detalhes da exportação.

1. O painel lateral mostra a configuração de uma exportação. Sem permissões de edição, não é possível alterar valores. Selecione **Fechar** para regressar à página de exportações.

## <a name="schedule-and-run-exports"></a>Agendar e executar exportações

Cada exportação que configura tem uma agenda de atualização. Durante uma atualização, o sistema procura dados novos ou atualizados a incluir numa exportação. Por predefinição, as exportações são executadas como parte de cada [atualização de sistema agendada](system.md#schedule-tab). Pode personalizar a agenda de atualização ou desativá-la para executar exportações manualmente.

As agendas de exportação dependem do estado do seu ambiente. Se houver atualizações em curso sobre as [dependências](system.md#refresh-policies) quando uma exportação agendada deveria começar, o sistema completará primeiro as atualizações e, em seguida, executará a exportação. Pode ver quando uma exportação foi atualizada pela última vez na coluna **Atualizadas**.

### <a name="schedule-exports"></a>Agendar exportações

Pode definir agendas de atualização personalizadas para exportações individuais ou várias exportações ao mesmo tempo. A agenda atualmente definida está listada na coluna **Agenda** da lista de exportação. A permissão para alterar a agenda é a mesma que para [editar e definir exportações](export-destinations.md#set-up-a-new-export). 

1. Aceda a **Dados** > **Exportações**.

1. Selecione a exportação que pretende agendar.

1. Selecione **Agendar** na barra de comandos.

1. No painel **Agendar exportação**, defina **Agendar execução** para **Ativada** para executar a exportação automaticamente. Defina-a como **Desativada** para a atualizar manualmente.

1. Para exportações automaticamente atualizadas, escolha um valor de **Periodicidade** e especifique os respetivos detalhes. O tempo definido aplica-se a todas as instâncias de periodicidade. É o momento em que uma exportação deve começar a atualizar.

1. Aplique e ative as suas alterações selecionando **Guardar**.

Ao editar a agenda para várias exportações, precisa de fazer uma seleção sob **Manter ou substituir agendas**:
- **Manter agendas individuais**: persiste a agenda previamente definida para as exportações selecionadas e apenas as desativa ou ativa.
- **Definir nova agenda para todas as exportações selecionadas**: substitui as agendas existentes das exportações selecionadas.

### <a name="run-exports-on-demand"></a>Executar exportações a pedido

Para exportar dados sem esperar por uma atualização agendada, vá a **Dados** > **Exportações**.

- Para executar todas as exportações, selecione **Executar todas** na barra de comandos. Esta ação só irá executar exportações que tenham uma agenda ativa.
- Para executar uma única exportação, selecione-a na lista e selecione **Executar** na barra de comandos. É assim que se executam exportações sem agenda ativa. 

## <a name="remove-an-export"></a>Remover uma Exportação

1. Aceda a **Dados** > **Exportações**.

1. Selecione a exportação que deseja remover.

1. Selecione **Remover** na barra de comandos.

1. Confirme a remoção selecionando **Remover** no ecrã de confirmação.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

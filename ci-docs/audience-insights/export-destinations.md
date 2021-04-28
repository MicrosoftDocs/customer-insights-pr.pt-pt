---
title: Exportar dados do Customer Insights
description: Gerir exportações para partilhar dados.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896157"
---
# <a name="exports-preview-overview"></a>Descrição geral de exportações (pré-visualização)

A página **Exportações** mostra todas as exportações configuradas. As exportações partilham dados específicos com várias aplicações. Podem incluir perfis de clientes ou entidades, esquemas e detalhes de mapeamento. Cada exportação requer uma [ligação, configurada por um administrador, para gerir a autenticação e o acesso](connections.md).

> [!NOTE]
> Até março de 2021, as exportações criaram automaticamente uma ligação ao serviço correspondente. As exportações exigem agora uma [ligação, criada e partilhada por um administrador](connections.md) antes de as poder criar.

Vá a **Dados** > **Exportações** para ver a página de exportações. Todas as funções de utilizador têm acesso a ver exportações configuradas. Utilização do campo de pesquisa na barra de comandos para encontrar exportações pelo nome, nome da ligação ou tipo de ligação.

## <a name="set-up-a-new-export"></a>Configurar uma nova exportação

Para configurar ou editar uma exportação, precisa de ter ligações disponíveis para si. As ligações dependem da sua [função de utilizador](permissions.md):
- Os administradores têm acesso a todas as ligações. Podem também criar novas ligações ao configurar uma exportação.
- Os contribuidores podem ter acesso a ligações específicas. Dependem dos administradores para configurar e partilhar ligações. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os visualizadores só podem ver exportações existentes, mas não criá-las.

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação** para criar um novo destino de exportação.

1. No painel **Configurar exportação**, selecione que ligação utilizar. As [Ligações](connections.md) são geridas por administradores. 

1. Forneça os detalhes necessários e selecione **Guardar** para criar a exportação.

### <a name="edit-an-export"></a>Editar uma exportação

1. Selecione as reticências verticais do destino de exportação que pretende editar.

1. Selecione **Editar** no menu pendente.

1. Altere os valores que pretende atualizar e selecione **Guardar**.

## <a name="view-exports-and-export-details"></a>Ver Exportações e detalhes da exportação

Depois de criar destinos de exportação, são listados em **Dados** > **Exportações**. Todos os utilizadores podem ver que dados são partilhados e o respetivo estado mais recente.

1. Aceda a **Dados** > **Exportações**.

1. Os utilizadores sem permissões de edição selecionam **Ver** em vez de **Editar** para ver os detalhes da exportação.

1. Este painel lateral mostra a configuração desta exportação. Sem permissões de edição, não é possível alterar valores. Selecione **Fechar** para regressar à página de exportações.

## <a name="run-exports-on-demand"></a>Executar exportações a pedido

Depois de configurar uma exportação, será executada a cada [atualização agendada](system.md#schedule-tab), desde que tenha uma ligação funcional.

Para exportar dados sem esperar por uma atualização agendada, vá a **Dados** > **Exportações**. Tem duas opções:

- Para executar todas as exportações, selecione **Executar todas** na barra de comandos. 
- Para executar uma única exportação, selecione as reticências (...) num item de lista e, em seguida, escolha **Executar**.

## <a name="remove-an-export"></a>Remover uma Exportação

1. Aceda a **Dados** > **Exportações**.

1. Selecione as reticências verticais da Exportação que pretende remover.

1. Selecione **Remover** no menu pendente.

1. Confirme a remoção selecionando **Remover** no ecrã de confirmação.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

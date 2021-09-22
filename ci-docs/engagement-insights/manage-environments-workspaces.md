---
title: Gerir áreas de trabalho e ambientes
description: Como criar, renomear e eliminar áreas de trabalho e ambientes.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034056"
---
# <a name="manage-environments-and-workspaces"></a>Gerir ambientes e áreas de trabalho

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Descrição geral

Uma área de trabalho é um espaço para armazenar e gerir eventos e relatórios. É onde pode ver a atividade do utilizador em tempo real. Quando cria uma área de trabalho, seleciona o tipo de dados a enviar para a área de trabalho. Atualmente, os dados Web e as aplicações móveis são suportados.

Um ambiente é um espaço onde gere as suas áreas de trabalho e ligações. A forma como utiliza ambientes depende da sua organização e do seu caso de utilização. Por exemplo, pode criar:

-   Um único ambiente.
-   Ambientes separados para teste e produção.
-   Ambientes separados para equipas ou departamentos específicos da sua organização que contenham eventos relevantes para cada audiência.
-   Ambientes separados para diferentes ramificações globais da sua empresa.
-   Ligações a capacidade de informações de audiência do Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Escolha um ambiente e crie uma área de trabalho 

Todas as áreas de trabalho precisam de estar num ambiente. Pode selecionar um ambiente pré-existente ou fazer um novo quando criar uma área de trabalho. Em seguida, pode optar por adicionar membros da área de trabalho e começar a recolher dados.

**Para criar a sua primeira área de trabalho**

1. Em informações de cativação, selecione **Novo** a partir do comutador de área de trabalho. 

   :::image type="content" source="media/New-workspace.png" alt-text="Seletor de área de trabalho da página do Customer Insights.":::

1. Escolha um ambiente na lista ou selecione **Criar novo ambiente**.

1. Introduza um nome em **Nome de área de trabalho**. 

1. Selecione o tipo de ambiente que pretende criar, dependendo se pretende medir o que acontece num site ou numa aplicação móvel. 

1. Pode adicionar membros e atribuir o seu nível de permissão na lista de **Funções**. Em seguida, selecione **Terminar** para criar a área de trabalho ou **Seguinte** para instalar código. 

1. Instale o fragmento de código para começar a receber dados e, em seguida, selecione **Concluído**. 

## <a name="manage-a-workspace"></a>Gerir uma área de trabalho

Pode manter várias áreas de trabalho simultaneamente num ambiente. A sua [função](user-roles.md) determina como pode trabalhar nelas. 

 - Tem de ser um administrador do ambiente ou um administrador da área de trabalho para gerir a área de trabalho.
 - Como administrador da área de trabalho, pode mudar o nome de áreas de trabalho existentes ou eliminá-las. 

### <a name="edit-a-workspace-name"></a>Editar um nome da área de trabalho

1. Ir a **Administrador** > **Área de trabalho** e selecionar **Definições**.

1. Na caixa **Nome da área de trabalho** introduza um novo nome.

1. Selecione **Guardar** para aplicar as alterações.

### <a name="delete-a-workspace"></a>Eliminar uma área de trabalho

A eliminação de uma área de trabalho removerá permanentemente todo o respetivo conteúdo, dados, definições e permissões. Não é possível anular esta ação.

1. Ir a **Administrador** > **Área de trabalho** e selecionar **Definições**.

1. Selecione **Eliminar área de trabalho**. 

1. Na caixa de diálogo **Eliminar área de trabalho**, introduza **CONFIRMAR ELIMINAÇÃO**. 

1. Selecione **Eliminar** para eliminar permanentemente a área de trabalho.

### <a name="manage-workspace-members"></a>Gerir membros da área de trabalho

1. Ir a **Administrador** > **Área de trabalho** e selecionar **Membros**.

1. Selecione **Adicionar membros** para dar acesso e [atribuir funções](user-roles.md). Atualmente, apenas **Administrador de área de trabalho** está disponível.

1. Se configurar uma [ligação para informações de audiência](configure-connections.md), pode selecionar **Permitir o acesso aos dados do perfil** para permitir que o membro veja relatórios baseados nos [perfis do utilizador](profile-reports.md).

1. Selecione **Adicionar membros** para os adicionar à sua área de trabalho.

## <a name="manage-an-environment"></a>Gerir um ambiente

Como administrador do Ambiente, pode aceder a um ambiente a partir do painel de navegação à esquerda. Pode configurar configurações de ambiente, outros administradores de ambiente, áreas de trabalho e [ligações a informações de audiência](configure-connections.md). Selecione separadores para se mover entre diferentes áreas no centro de administração.

:::image type="content" source="media/New-environment.png" alt-text="Centro de administração do ambiente.":::

### <a name="create-an-environment"></a>Criar um ambiente

1. No seletor da área de trabalho, selecione **+Nova**.

1. Na experiência guiada, abra o menu pendente **Ambiente** e selecione **Criar novo ambiente**. 

1. Forneça um **Nome do ambiente**.

   :::image type="content" source="media/create-environment.png" alt-text="Passo na experiência guiada para especificar os detalhes do ambiente.":::

1. Escolha a **Região** e selecione **Seguinte**. 

1. Forneça um nome da Área de trabalho e escolha que tipo de área de trabalho pretende criar. 

1.  Opcionalmente, adicione membros e copie o fragmento de código para concluir o processo de criação.

### <a name="rename-an-environment"></a>Renomear um ambiente

1. Ir a **Administrador** > **Ambiente** e selecionar **Definições**.

1. Atualize o **Nome de ambiente** e selecione **Guardar** para aplicar as suas alterações.

### <a name="manage-environment-members"></a>Gerir membros do ambiente

1. Ir a **Administrador** > **Ambiente** e selecionar **Membros**.

1. Selecione **Adicionar membros** para atualizar membros e [atribuir funções](user-roles.md). Atualmente, apenas **Administrador de ambiente** está disponível.

1. Se configurar uma [ligação para informações de audiência](configure-connections.md), pode selecionar **Permitir o acesso aos dados do perfil** para permitir que o membro veja relatórios baseados nos [perfis do utilizador](profile-reports.md).

1. Selecione **Adicionar membros** para os adicionar ao seu ambiente.

### <a name="delete-an-environment"></a>Eliminar um ambiente

Os admins de ambientes podem eliminar ambientes. Antes de eliminar um ambiente, tem de remover todas as áreas de trabalho abaixo dele.

1. Ir a **Administrador** > **Ambiente** e selecionar **Definições**.

1. Selecione **Eliminar ambiente**. 

1. Na caixa de diálogo **Eliminar área de trabalho**, introduza **CONFIRMAR ELIMINAÇÃO**. 

1. Selecione **Eliminar** para eliminar permanentemente o ambiente.

## <a name="manage-connections"></a>Gerir ligações

Estabelecer ligações com informações de audiência permite-lhe ver relatórios em informações de cativação baseados em perfis de clientes unificados. 

Para obter mais informações, ver [Configure ligações](configure-connections.md).

## <a name="manage-personal-data"></a>Gerir dados pessoais

Para proteger os dados pessoais do seu cliente, pode eliminar ou exportar dados identificáveis do utilizador final.

Para mais informações, ver [Eliminar e exportar dados de eventos contendo informações pessoais](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

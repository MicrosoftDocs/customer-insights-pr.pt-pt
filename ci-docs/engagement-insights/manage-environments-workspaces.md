---
title: Gerir áreas de trabalho e ambientes
description: Como criar, renomear e eliminar áreas de trabalho e ambientes.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673811"
---
# <a name="manage-environments-and-workspaces"></a>Gerir ambientes e áreas de trabalho

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Descrição geral

Este tópico discute como gerir áreas de trabalho e ambientes uma vez que já foram criados. 

- Uma *área de trabalho* é um espaço para armazenar e gerir eventos e relatórios. É onde pode ver a atividade do utilizador em tempo real. Quando cria uma área de trabalho, seleciona o tipo de dados a enviar para a área de trabalho. Atualmente, os dados Web e as aplicações móveis são suportados. Para obter mais informações, consulte [Criar uma nova área de trabalho e adicionar membros](create-workspace.md).

- Um *ambiente* é um espaço onde gere as suas áreas de trabalho e ligações. Para obter mais informações, consulte [Criar um novo ambiente](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Gerir uma área de trabalho existente

Pode manter várias áreas de trabalho simultaneamente num ambiente. A sua [função](user-roles.md) determina como pode trabalhar nelas. 

 - Tem de ser um administrador do ambiente ou um administrador da área de trabalho para gerir a área de trabalho.
 - Como administrador da área de trabalho, pode mudar o nome de áreas de trabalho existentes ou eliminá-las. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centro de administração da área de trabalho.":::

### <a name="edit-a-workspace-name"></a>Editar um nome da área de trabalho

1. Ir a **Administrador** > **Área de trabalho** e selecionar **Definições**.

1. Na caixa **Nome da área de trabalho** introduza um novo nome.

1. Selecione **Guardar** para aplicar as alterações.

### <a name="delete-a-workspace"></a>Eliminar uma área de trabalho

A eliminação de uma área de trabalho remove permanentemente todo o respetivo conteúdo, dados, definições e permissões. Não é possível anular esta ação.

1. Ir a **Administrador** > **Área de trabalho** e selecionar **Definições**.

1. Selecione **Eliminar área de trabalho**. 

1. No diálogo **Eliminar área de trabalho**, introduza **CONFIRMAR ELIMINAÇÃO** totalmente em maiúsculas. 

1. Selecione **Eliminar** para eliminar permanentemente a área de trabalho.

### <a name="manage-workspace-members"></a>Gerir membros da área de trabalho

1. Ir a **Administrador** > **Área de trabalho** e selecionar **Membros**.

1. Selecione **Adicionar membros** para dar acesso e [atribuir funções](user-roles.md). Atualmente, apenas **Administrador de área de trabalho** está disponível.

1. Selecione **Adicionar membros** para os adicionar à sua área de trabalho.

## <a name="manage-an-existing-environment"></a>Gerir um ambiente existente

Como administrador do ambiente, pode aceder a um ambiente a partir do painel de navegação à esquerda. Pode configurar definições de ambiente, outros admins de ambiente e áreas de trabalho. Selecione separadores para se mover entre diferentes áreas no centro de administração.

:::image type="content" source="media/environment-edit.png" alt-text="Centro de administração do ambiente.":::

### <a name="edit-an-environment-name"></a>Editar um nome do ambiente

1. Ir a **Administrador** > **Ambiente** e selecionar **Definições**.

1. Atualize o **Nome de ambiente** e selecione **Guardar** para aplicar as suas alterações.

### <a name="delete-an-environment"></a>Eliminar um ambiente

Os admins de ambientes podem eliminar ambientes. Antes de eliminar um ambiente, tem de remover todas as áreas de trabalho abaixo dele.

1. Ir a **Administrador** > **Ambiente** e selecionar **Definições**.

1. Selecione **Eliminar ambiente**. 

1. No diálogo **Eliminar área de trabalho**, introduza **CONFIRMAR ELIMINAÇÃO** totalmente em maiúsculas. 

1. Selecione **Eliminar** para eliminar permanentemente o ambiente.

### <a name="manage-environment-members"></a>Gerir membros do ambiente

1. Ir a **Administrador** > **Ambiente** e selecionar **Membros**.

1. Selecione **Adicionar membros** para atualizar membros e [atribuir funções](user-roles.md). Atualmente, apenas **Administrador de ambiente** está disponível.

1. Selecione **Adicionar membros** para os adicionar ao seu ambiente.

## <a name="manage-connections"></a>Gerir ligações

Estabelecer ligações com informações de audiência permite-lhe ver relatórios em informações de cativação baseados em perfis de clientes unificados. 

Para mais informações, consulte [Criar uma ligação entre as informações de audiência e as informações de cativação](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Gerir dados pessoais

Para proteger os dados pessoais do seu cliente, pode eliminar ou exportar dados identificáveis do utilizador final.

Para mais informações, ver [Eliminar e exportar dados de eventos contendo informações pessoais](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]

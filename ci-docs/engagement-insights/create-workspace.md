---
title: Criar uma nova área de trabalho
description: A finalidade de uma área de trabalho e como criar uma nova.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673507"
---
# <a name="create-a-new-workspace-and-add-members"></a>Criar uma nova área de trabalho e adicionar membros

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Uma área de trabalho é como pode ver a atividade do utilizador em tempo real para entender melhor a sua audiência. É onde se armazena e gere eventos e relatórios.

Quando cria uma área de trabalho, seleciona o tipo de dados em que se pretende focar. Pode adicionar outros utilizadores ou membros a uma área de trabalho existente a qualquer momento. 

## <a name="create-a-new-workspace"></a>Criar uma nova área de trabalho

O processo de criação de uma área de trabalho inclui a criação do *ambiente* para organizar a sua área de trabalho. Um ambiente é um espaço que pode conter uma ou mais áreas de trabalho. Pode utilizar um ambiente para gerir as suas áreas de trabalho e ligações à capacidade de informações de audiência.

1. Selecione **+Novo** no comutador de área de trabalho.

   :::image type="content" source="media/new-workspace.png" alt-text="Página do Customer Insights com chamada no painel de navegação e descrição.":::

1. No painel **Área de trabalho**, introduza um **Nome da área de trabalho**.

   :::image type="content" source="media/workspace-name.png" alt-text="Digite um nome da área de trabalho.":::

1. Escolha o tipo de plataforma (Web ou móvel) que pretende medir.

1. Selecione **Mostrar definições avançadas** para ativar ou desativar estas definições opcionais:

   - Alterne **Desconhecido para conhecido** como "ativado" para associar eventos Web a utilizadores que foram anteriormente autenticados. Para mais informações, consulte [Reconhecer eventos Web de visitantes anteriormente autenticados](unknown-to-known.md)
   - Alterne **Filtrar tráfego de bots** para "ativado" para remover o tráfego Web por bots para esta área de trabalho. 

1. Selecione **Concluído** quando tiver concluído. 

1. Instale o fragmento de código para começar a receber dados e, em seguida, selecione **Concluir** para criar a área de trabalho. Para mais informações, consulte [Descrição geral para programadores](developer-resources.md).

> [!NOTE]
> Agora pode adicionar membros e atribuir o seu nível de permissão na lista **Função**. Para obter mais informações, veja [Funções e permissões](user-roles.md). 

Para obter mais informações, consulte [Gerir ambientes e áreas de trabalho](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

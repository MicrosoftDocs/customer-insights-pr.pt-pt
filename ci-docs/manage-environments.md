---
title: 'Como: gerir ambientes'
description: Saiba como gerir ambientes do Customer Insights existentes como um admin."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fc3b3f404cf0ac84c782778414494289c803babe
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081671"
---
# <a name="how-to-manage-environments"></a>Como: gerir ambientes

Os administradores [criam](create-environment.md) e gerem ambientes. Podem alterar algumas definições em ambientes existentes. As definições de negócio, tipo, região, opção de armazenamento e Dataverse são fixas após a criação do ambiente. Se quiser alterar estas definições, reponha o ambiente ou crie um novo ambiente.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Pode editar alguns dos detalhes de ambientes existentes.

1. Selecione o seletor **Ambiente** no cabeçalho da aplicação.

1. Selecione o ícone **Editar**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ícone para editar as definições do ambiente.":::

1. Na caixa **Editar ambiente**, pode atualizar as definições do ambiente.

Para começar com um novo ambiente, consulte [Criar um novo ambiente.](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Alterar o proprietário de um ambiente

Vários utilizadores podem ter permissões de admin, mas apenas um utilizador é o proprietário de um ambiente. Por predefinição, é o administrador quem cria inicialmente um ambiente. Como administrador de um ambiente, pode atribuir a propriedade a outro utilizador com permissões de administrador.

1. Selecione o seletor **Ambiente** no cabeçalho da aplicação.

1. Selecione o ícone **Editar**.

1. Na caixa de **Editar ambiente**, vá para o passo **Informações básicas**.

1. No campo **Alterar proprietário do ambiente**, escolha o novo proprietário do ambiente.  

1. Selecione **Rever e concluir** e, em seguida, **Atualizar** para aplicar as alterações.

## <a name="claim-ownership-of-an-environment"></a>Reclamar a propriedade de um ambiente

Se a conta de utilizador do proprietário for eliminada ou suspensa, o ambiente não terá proprietário. Todos os utilizadores administradores podem reclamar a propriedade e tornar-se o novo proprietário. Pode continuar a ser o proprietário do ambiente ou [alterar a propriedade para outro administrador](#change-the-owner-of-an-environment).

Para reclamar a propriedade, selecione o botão **Assumir propriedade** que é apresentado no início de cada página no Customer Insights quando o proprietário original deixou a organização.

## <a name="reset-an-existing-environment-preview"></a>Repor um ambiente existente (Pré-visualização)

Como proprietário de um ambiente, pode repor um ambiente para um estado vazio se quiser eliminar todas as configurações e remover os dados ingeridos.

1. Selecione o seletor **Ambiente** no cabeçalho da aplicação.

1. Selecione o ambiente que pretende repor e selecione as reticências verticais (&vellip;).

1. Escolha a opção **Repor**.

   :::image type="content" source="media/reset-environment.png" alt-text="Controlo para repor um ambiente.":::

1. Escolha se pretende repor o ambiente completo, tudo, exceto as origens de dados, ou qualquer coisa que esteja configurada em cima do Unified customer profile.

1. Para confirmar, introduza o nome do ambiente e selecione **Repor**.

## <a name="delete-an-existing-environment"></a>Eliminar um ambiente existente

Como proprietário de um ambiente, pode eliminar um ambiente que administra.

1. Selecione o seletor **Ambiente** no cabeçalho da aplicação.

1. Selecione o ambiente que pretende repor e selecione as reticências verticais (&vellip;). 

1. Escolha a opção **Eliminar**.

   :::image type="content" source="media/delete-environment.png" alt-text="Controlo para eliminar o ambiente.":::

1. Para confirmar a eliminação, introduza o nome do ambiente e selecione **Eliminar**.

> [!IMPORTANT]
> A eliminação de um ambiente não remove a ligação a um ambiente do Dataverse. Se pretende ligar o mesmo ambiente do Dataverse a um novo ambiente do Customer Insights no futuro, tem de remover essa ligação [Saiba como remover uma ligação existente a um ambiente do Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]

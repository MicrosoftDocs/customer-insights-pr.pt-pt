---
title: Criar um novo ambiente
description: A finalidade de um ambiente e como criar um novo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f82ff588c2ffbe82c3ee7df2498ac2cca2bad31
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225461"
---
# <a name="create-a-new-environment"></a>Criar um novo ambiente 

## <a name="overview"></a>Descrição geral

Um ambiente é um espaço onde gere as suas áreas de trabalho e ligações. A forma como utiliza ambientes depende da sua organização e do seu caso de utilização. Por exemplo, pode criar:

- Um único ambiente.
- Ambientes separados para teste e produção.
- Ambientes separados para equipas ou departamentos específicos da sua organização que contenham eventos relevantes para cada audiência.
- Ambientes separados para diferentes ramificações globais da sua empresa.
- Ligações a capacidade de informações de audiência do Customer Insights.

## <a name="create-a-new-environment"></a>Criar um novo ambiente

1. No lado direito da faixa principal, selecione o seletor de ambientes e, em seguida, **+Novo**.

   :::image type="content" source="media/environment-picker.png" alt-text="Selecione o seletor de ambientes.":::

1. No painel **Configuração**, digite **Nome do ambiente**.

1. Escolha o **Tipo** de conta, dependendo do seu tipo de plano.

1. Escolha a **Região** e selecione **Seguinte**. 

1. Digite **Nome da área de trabalho**, que lhe permite recolher dados para aplicações ou sites específicos. Para obter mais informações, consulte [Criar uma área de trabalho](create-workspace.md).

1. Escolha o **Tipo de área de trabalho** (Web ou móvel) que pretende criar. 

1. Selecione **Mostrar definições avançadas** para ativar ou desativar estas definições opcionais:

   - Alterne **Desconhecido para conhecido** como "ativado" para associar eventos Web a utilizadores que foram anteriormente autenticados. Para mais informações, consulte [Reconhecer eventos Web de visitantes anteriormente autenticados](unknown-to-known.md).
   - Alterne **Filtrar tráfego de bots** para "ativado" para remover o tráfego Web por bots para esta área de trabalho. 

1. Selecione **Concluído** quando tiver concluído. 

1. Instale o fragmento de código para começar a receber dados e, em seguida, selecione **Concluir** para criar a área de trabalho. Para mais informações, consulte [Descrição geral para programadores](developer-resources.md).

> [!NOTE]
> Agora pode adicionar membros e atribuir o seu nível de permissão na lista **Função**. Para obter mais informações, veja [Funções e permissões](user-roles.md). 

Para obter mais informações, consulte [Gerir ambientes e áreas de trabalho](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Trabalhar com o seu novo ambiente

- [Criar uma área de trabalho](../engagement-insights/create-workspace.md) e adicionar membros.
- [Adicione o código ao seu site](../engagement-insights/instrument-website.md) ou à [aplicação móvel](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Veja um [relatório em tempo real](../engagement-insights/view-reports.md) ou crie [relatórios personalizados](../engagement-insights/custom-reports.md).
- [Criar eventos refinados](../engagement-insights/refined-events.md) para exportação.
- [Exporte os dados](../engagement-insights/export-events.md) para o Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

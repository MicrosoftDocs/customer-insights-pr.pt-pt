---
title: Funções e permissões
description: Visão geral das funções e permissões disponíveis para membros da área de trabalho.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036707"
---
# <a name="roles-and-permissions"></a>Funções e permissões

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Uma área de trabalho é a forma como armazena e gere eventos e relatórios. Um membro é um utilizador que pode aceder a uma área de trabalho. Pode atribuir membros à sua área de trabalho e definir as suas funções e permissões. As funções de administrador gerem áreas de trabalho e ambientes e configuram informações de cativação para outros utilizadores. As funções de contribuidor são direcionadas para analistas que não precisam de configurar informações de cativação, mas querem criar os seus próprios relatórios, funis ou segmentos.

## <a name="permissions"></a>Permissões
  
O gráfico que se segue identifica permissões para cada função. 

| Permissão | Administrador do ambiente | Administrador da área de trabalho | Contribuidor do ambiente | Contribuidor da área de trabalho | 
|--|--|--|--|--|
| Criar ambientes (o criador torna-se automaticamente administrador do ambiente) | X* | X* | X* | X* |  
| Configure ambiente (membros do ambiente, eliminar ambiente) | X |  |  |  |  
| Criar áreas de trabalho | X |  |  |  |  
| Configurar áreas de trabalho (membros da área de trabalho, eliminar área de trabalho) | X | X |  |  |  
| Configurar eventos e eventos refinados | X | X | |  |  
| Ver eventos de área de trabalho e eventos refinados | X | X | |  |  
| Ver recursos da área de trabalho (relatórios, segmentos e métrica)| X | X | X | X |  
| Criar relatórios e funis personalizados | X | X | X | X |  
| Criar métricas e dimensões base| X | X |  |  |  
| Criar segmentos| X | X | X | X |  

*Só pode criar ambientes experimentais na pré-visualização. 

## <a name="add-members"></a>Adicionar membros

Pode adicionar e remover membros de áreas de trabalho e ambientes. Para obter mais informações, consulte [Ambientes e áreas de trabalho](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Funções e permissões
description: Visão geral das funções e permissões disponíveis para membros da área de trabalho.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227553"
---
# <a name="roles-and-permissions"></a>Funções e permissões

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Uma área de trabalho é o local onde armazena e gere eventos e relatórios. Para obter mais informações, consulte [Criar uma área de trabalho e adicionar membros](create-workspace.md). 

Uma área de trabalho pode incluir as seguintes funções e permissões:

- As funções de *membro* são os utilizadores que podem aceder a uma área de trabalho. Pode atribuir membros à sua área de trabalho e definir as suas funções e permissões. 
- As funções de *administrador* gerem áreas de trabalho e ambientes e configuram informações de cativação para outros utilizadores. 
- As funções de *contribuidor* são direcionadas para os analistas que não precisam de configurar informações de cativação, mas que querem criar os seus próprios relatórios, funis ou segmentos.

## <a name="permissions"></a>Permissões
  
A tabela seguinte identifica as permissões para cada função. 

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

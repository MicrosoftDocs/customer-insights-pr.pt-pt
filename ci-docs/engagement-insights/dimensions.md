---
title: Ver e criar dimensões
description: Como criar, editar e eliminar dimensões.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d35c72f73d2f3e202ae3c5a5ef26e9db89360084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226321"
---
# <a name="view-and-create-dimensions"></a>Ver e criar dimensões

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Uma dimensão é um atributo de um evento que pode descrever, filtrar ou agrupar dados. Se estiver a realizar uma promoção de marketing no seu site, pode usar dimensões para ordenar visitantes por utilizadores novos e de regresso.  

As informações de cativação incluem dimensões fornecidas com o programa (OOB) para propriedades de eventos. Os exemplos incluem:

- Nome do browser
- Nome de página
- Modelo do dispositivo
- Sistema operativo
- País/região

## <a name="view-dimensions"></a>Ver dimensões

As dimensões baseiam-se nas propriedades de eventos existentes. Quando utiliza o código de monitorização para informações de cativação, as dimensões do sistema são criadas automaticamente.

1. Aceda a **Dados** no painel de navegação esquerdo. 
1. Selecione **Dimensões** para ver uma lista de todas as dimensões na área de trabalho. 
   > [!NOTE]
   > As dimensões geradas pelo sistema são apenas de leitura. Não é possível editá-las. Só é possível criar e editar dimensões personalizadas.

## <a name="create-a-dimension"></a>Criar uma dimensão

Além das dimensões geradas pelo sistema, os admins de ambientes e de áreas de trabalho podem criar dimensões personalizadas. As dimensões personalizadas baseiam-se em propriedades predefinidas de eventos base ou podem usar [propriedades personalizadas de um evento](advanced-SDK-implementation.md).

1. Aceda a **Dados** > **Dimensões**.
1. Selecione **Nova dimensão**.

   :::image type="content" source="media/add-dimension.png" alt-text="Adicionar uma dimensão a um evento.":::

1. No painel **Criar uma dimensão**, selecione uma propriedade em que basear a dimensão. A lista de propriedades mostrará todas as propriedades na área de trabalho não atribuídas a uma dimensão.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Crie uma nova dimensão.":::
      
3. Introduza um nome na caixa **Nome a apresentar**. Opcionalmente, pode adicionar uma **Descrição**.
4. Selecione **Criar** para guardar a dimensão. Pode demorar até um minuto antes que possa utilizar a dimensão num [relatório personalizado](custom-reports.md) ou [segmento](segments.md). 

## <a name="edit-a-dimension"></a>Editar uma dimensão

Pode alterar o nome e a descrição de uma dimensão. Só pode editar dimensões criadas pelo utilizador, mas não é possível editar dimensões do sistema.


1. Aceda a **Dados** > **Dimensões**.
1. Selecione a dimensão que pretende eliminar.
1. No painel **Editar dimensão**, atualize a dimensão.
1. Selecione **Aplicar** para guardar as alterações.

## <a name="delete-a-dimension"></a>Eliminar uma dimensão

Só é possível eliminar dimensões criadas por utilizadores, mas não é possível remover as dimensões de sistema.

Eliminar uma dimensão é uma ação permanente. Os relatórios e segmentos que utilizam uma dimensão eliminada deixarão de funcionar. 

1. Aceda a **Dados** > **Dimensões**.
1. Selecione a dimensão que pretende eliminar.
1. No painel **Editar dimensão**, selecione **Eliminar dimensão**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Eliminar uma dimensão de um evento.":::

1. Introduza **CONFIRMAR ELIMINAÇÃO** (em maiúsculas) para confirmar a eliminação. 
1. Selecione **Eliminar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

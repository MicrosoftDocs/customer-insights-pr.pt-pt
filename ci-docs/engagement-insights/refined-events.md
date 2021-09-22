---
title: Criar e modificar eventos refinados
description: Como criar e modificar eventos refinados.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034788"
---
# <a name="create-and-modify-refined-events"></a>Criar e modificar eventos refinados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Um evento são dados que representam o comportamento do utilizador, como a atividade num site.

- Um evento *base* regista quando um utilizador vê uma página (ver evento) ou interage com conteúdo (evento de ação).
- Um evento *refinado* é uma visão virtual de um evento base. Define eventos refinados removendo e adicionando propriedades ou filtrando eventos com base em valores de propriedade.

Utilize eventos refinados para reduzir o âmbito de um evento base para [exportação](export-events.md) ou para remover propriedades que não sejam necessárias para exposição ou exportação.

## <a name="create-refined-events"></a>Criar evento refinados

Há três maneiras de criar um evento refinado a partir de um evento base. 

1. Vá a **Dados**> **Eventos** e escolha uma das seguintes opções:
    - Selecione **novos eventos** e, em seguida, selecione **Criar eventos refinados**.
    - Selecione um evento base para abrir uma vista detalhada e selecione **Criar eventos refinados** a partir do menu superior.
    - Selecione **Mais [...]** para abrir o menu de atalho para um evento base. Em seguida, selecione **Criar eventos refinados**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opções para criar eventos refinados.":::

1. Na caixa de diálogo **Criar eventos refinados**, insira as seguintes informações:

- Selecione um evento a partir do menu suspenso de **Eventos base** se estiver a criar um novo evento.
- Introduza um nome na caixa **Nome a apresentar de eventos refinados**.
- Opcionalmente, atualize o **nome real** sugerido sem utilizar espaços.

3. Selecione **Criar** para aplicar as suas definições.

1. Na visão detalhada do seu evento refinado, selecione **Adicionar e remover propriedades** para abrir o painel de **Editar propriedades**. 

1. Utilize as caixas de verificação para selecionar as propriedades que pretende mostrar e as que pretende esconder. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editar propriedades para eventos refinados.":::

1. Selecione **Confirmar** para aplicar a sua seleção.

1. Selecione **Guardar** para guardar a configuração.

## <a name="edit-refined-events"></a>Editar eventos refinados

Pode alterar o nome e as propriedades de um evento refinado.

### <a name="edit-event-name"></a>Editar nome de evento

1. Vá a **Dados** > **Eventos**. 
1. Selecione **Mais [...]** para um evento e selecione **Editar nome**.
1. Atualize o nome do evento e selecione **Renomear**.

### <a name="edit-selected-properties"></a>Editar propriedades selecionadas

1. Vá a **Dados** > **Eventos** e selecione os eventos refinados para abrir a vista detalhada.
1. Selecione **Adicionar e remover propriedades**. 
1. Editar a seleção das caixas de verificação.
1. Selecione **Confirmar** e, em seguida, **Guarde** para aplicar as alterações.

Para obter informações sobre eventos de exportação, consulte [Exportar eventos](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]

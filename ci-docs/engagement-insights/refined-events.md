---
title: Criar e modificar eventos
description: Como criar e modificar eventos.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606253"
---
# <a name="create-and-modify-events"></a>Criar e modificar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um evento são dados que representam o comportamento do utilizador, como a atividade num site.

- Um evento *base* regista quando um utilizador vê uma página (ver evento) ou interage com conteúdo (evento de ação).
- Um evento *refinado* é uma visão virtual de um evento base. Define eventos refinados removendo e adicionando propriedades ou filtrando eventos com base em valores de propriedade.

## <a name="prerequisites"></a>Pré-requisitos

Para obter eventos, os dados do seu site precisam de ser ligados, em primeiro lugar, às informações de cativação com um fragmento de código. Para mais informações, consulte [Instalar o SDK Web num site](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Ligue os dados em primeiro lugar.":::

## <a name="create-refined-events"></a>Criar eventos refinados

Utilize eventos refinados para reduzir o âmbito de um evento base para [exportação](export-events.md) ou para remover propriedades que não sejam necessárias para exposição ou exportação.

> [!NOTE]
> Assim que adicionar o SDK Web ao seu site, pode ver os seus eventos base e criar eventos refinados. 

Para ver os seus eventos base:

1. Aceda a **Dados** no painel de navegação esquerdo.

1. Selecione **Eventos** para ver uma lista de todos os eventos na área de trabalho.

    :::image type="content" source="media/data-events.png" alt-text="Veja os eventos.":::

Para criar um evento refinado a partir de um evento base: 

1. Vá para **Dados** > **Eventos** e selecione **+ Novos eventos** na parte superior do ecrã.

1. No diálogo **Novos eventos**, selecione **Criar eventos refinados** e, em seguida, selecione **Seguinte**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Assistente de novos eventos.":::
     
1. No diálogo **Novos eventos**, introduza as seguintes informações:

   - Selecione um evento a partir do menu pendente **Eventos base**.
   - Introduza um nome na caixa **Nome a apresentar de eventos refinados**.
   - Opcionalmente, atualize o **nome real** sugerido sem utilizar espaços.

1. Selecione **Criar** para aplicar as suas definições.

O evento refinado aparece agora na sua lista de **Eventos**.

### <a name="edit-event-name"></a>Editar nome de evento

Pode alterar o nome e as propriedades de um evento base ou refinado.

1. Vá a **Dados** > **Eventos**. 

1. Selecione **Mais [...]** para um evento e selecione **Editar nome**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opções para criar eventos refinados.":::

3. Atualize o nome do evento e selecione **Renomear**.

### <a name="view-the-details-of-a-refined-event"></a>Veja os detalhes de um evento refinado:

1. Na lista de **Eventos**, selecione o seu evento base ou refinado. 

1. Selecione **Adicionar e remover propriedades** na parte superior do ecrã para abrir o painel **Editar propriedades**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Adicione e remova propriedades.":::

1. Utilize as caixas de verificação para selecionar as propriedades que pretende mostrar e as que pretende esconder. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editar propriedades para eventos refinados.":::

1. Selecione **Confirmar** para aplicar a sua seleção e, em seguida, selecione **Guardar**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Editar propriedades selecionadas para um evento refinado

1. Vá a **Dados** > **Eventos** e selecione os eventos refinados para abrir a vista detalhada.
1. Selecione **Adicionar e remover propriedades**. 
1. Editar a seleção das caixas de verificação.
1. Selecione **Confirmar** e, em seguida, **Guarde** para aplicar as alterações.

Para obter informações sobre eventos de exportação, consulte [Exportar eventos](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]

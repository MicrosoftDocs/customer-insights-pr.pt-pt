---
title: Atualização de dados de sistema
description: Agendar a hora a que o sistema deve ser atualizado
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610342"
---
# <a name="schedule-system-refresh"></a>Atualização de dados de sistema

Agende as atualizações automáticas de todas as suas [origens de dados ingeridas](data-sources.md). As atualizações automáticas ajudam a garantir que as atualizações das suas origens de dados são refletidas nos perfis de clientes unificados.

> [!NOTE]
> As origens de dados do Power Query geridas por si atualizam as suas próprias agendas. Para agendar a atualização de origens de dados do Power Query geridas por si, configure as definições de atualização nessa origem de dados específica na página **Origens de dados**. Alinhe a temporização com a agenda de atualização de dados a jusante para que as atualizações não ocorram todas ao mesmo tempo.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Definições de atualização do fluxo de dados.":::

## <a name="set-system-refresh-schedule"></a>Definir agendamento da atualização do sistema

1. Aceda a **Admin** > **Sistema** e selecione o separador **Agenda**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Separador Atualizar agendar da página Sistema.":::

1. O estado predefinido da atualização agendada é **Desativado**. Para ativar as atualizações agendadas, altere o botão de alternar na parte superior do ecrã para **Ativado**.

1. Escolha entre as atualizações **Semanal** (predefinição) e **Diária**. Se pretender agendar atualizações semanais, selecione um ou mais dias nos quais pretende executar a atualização.

1. Defina o seu **Fuso horário** e, em seguida, use a lista suspensa **Hora** para definir o tempo de atualização. Se pretende agendar várias atualizações num único dia, selecione **Adicionar outra hora**. Pode adicionar até quatro atualizações.

1. Selecione **Guardar** para aplicar as alterações.

[!INCLUDE [footer-include](includes/footer-banner.md)]

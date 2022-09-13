---
title: Atualização de dados de sistema
description: Agendar a hora a que o sistema deve ser atualizado
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395970"
---
# <a name="schedule-system-refresh"></a>Atualização de dados de sistema

Agende as atualizações automáticas de todas as suas [origens de dados ingeridas](data-sources.md). As atualizações automáticas ajudam a garantir que as atualizações das suas origens de dados são refletidas nos perfis de clientes unificados.

> [!NOTE]
> As origens de dados do Power Query geridas por si atualizam as suas próprias agendas. Para agendar a atualização de origens de dados do Power Query geridas por si, configure as definições de atualização nessa origem de dados específica na página **Origens de dados**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Definições de atualização do fluxo de dados.":::

## <a name="set-system-refresh-schedule"></a>Definir agendamento da atualização do sistema

1. Aceda a **Admin** > **Sistema** e selecione o separador **Agenda**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Separador Atualizar agendar da página Sistema.":::

1. O estado predefinido da atualização agendada é **Desativado**. Para ativar as atualizações agendadas, altere o botão de alternar na parte superior do ecrã para **Ativado**.

1. Escolha entre as atualizações **Semanal** (predefinição) e **Diária**. Se pretender agendar atualizações semanais, selecione um ou mais dias nos quais pretende executar a atualização.

1. Defina o seu **Fuso horário** e, em seguida, use a lista suspensa **Hora** para definir o tempo de atualização. Se pretende agendar várias atualizações num único dia, selecione **Adicionar outra hora**. Pode adicionar até quatro atualizações.

1. Selecione **Guardar** para aplicar as alterações.

[!INCLUDE [footer-include](includes/footer-banner.md)]

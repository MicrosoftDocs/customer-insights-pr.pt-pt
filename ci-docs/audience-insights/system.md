---
title: Configuração do sistema em informações de audiência
description: Saiba mais sobre as configurações do sistema na capacidade das informações de audiência do Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406649"
---
# <a name="system-configuration"></a>Configuração do sistema

A página **Sistema** inclui quatro separadores: **Estado**, **Agendar**, **Sobre** e **Geral**.

> [!div class="mx-imgBorder"]
> ![Página do sistema](media/system-tabs.png "Página do sistema")

## <a name="status-tab"></a>Separador Estado

O **separador Estado** permite monitorizar o progresso da ingestão de dados, exportações de dados e vários processos de produto importantes. Rever a informação neste separador para garantir a abrangência dos processos ativos.

Este separador inclui tabelas de estado para **Origens de dados**, **Processos do sistema** e **Preparação de dados**. Cada tabela monitoriza o **Nome** da tarefa e a sua entidade correspondente, o **Estado** da sua execução mais recente, e quando foi **Atualizada pela última vez**.

Ver os detalhes das últimas várias execuções das tarefas ao selecionar o respetivo nome.

### <a name="status-types"></a>Tipos de estado

Há seis tipos de estados para tarefas. Os seguintes tipos de estado também são mostrados nas páginas *Corresponder*, *Unir*, *Origens de dados*, *Segmentos*, *Medidas*, *Melhoramento*, *Atividades* e *Previsões*:

- **A processar:** a tarefa está em curso. O estado pode ser alterado para Com êxito ou Falha.
- **Com Êxito:** a tarefa foi concluída com êxito.
- **Ignorada:** A tarefa foi ignorada. Um ou mais dos processos a jusante de que esta tarefa depende estão a falhar ou foram ignorados.
- **Falha:** o processamento da tarefa falhou.
- **Cancelada:** o processamento foi cancelado pelo utilizador antes de ser concluído.
- **Em fila:** o processamento foi colocado em fila e será iniciado após a conclusão de todas as tarefas a jusante. Para mais informações, consulte [Políticas de atualização](#refresh-policies).

### <a name="refresh-policies"></a>Políticas de atualização

Esta lista mostra as políticas de atualização para cada um dos principais processos:

- **Origens de dados:** é executado de acordo com a [agenda configurada](#schedule-tab). Não depende de qualquer outro processo. A correspondência depende da conclusão com êxito deste processo.
- **Corresponder:** é executada de acordo com a [agenda configurada](#schedule-tab). Depende do processamento das origens de dados utilizadas na definição de correspondência. Unir depende da conclusão com êxito deste processo.
- **Unir:** é executada de acordo com a [agenda configurada](#schedule-tab). Depende da conclusão do processo de correspondência. Os segmentos, as medidas, o melhoramento, a pesquisa, as atividades, as previsões e a preparação de dados dependem da conclusão com êxito deste processo.
- **Segmentos**: a execução é feita manualmente (atualização única) e em conformidade com a [agenda configurada](#schedule-tab). Depende de Unir. As informações dependem do seu processamento.
- **Medidas**: a execução é feita manualmente (atualização única) e em conformidade com a [agenda configurada](#schedule-tab). Depende de Unir.
- **Atividades**: a execução é feita manualmente (atualização única) e em conformidade com a [agenda configurada](#schedule-tab). Depende de Unir.
- **Melhoramento**: a execução é feita manualmente (atualização única) e em conformidade com a [agenda configurada](#schedule-tab). Depende de Unir.
- **Pesquisa**: a execução é feita manualmente (atualização única) e em conformidade com a [agenda configurada](#schedule-tab). Depende de Unir.
- **Preparação de dados**: é executado de acordo com a [agenda configurada](#schedule-tab). Depende de Unir.
- **Informações**: a execução é feita manualmente (atualização única) e em conformidade com a [agenda configurada](#schedule-tab). Depende dos Segmentos.

Selecione o estado de uma tarefa para ver os detalhes do progresso de toda a tarefa em que se encontrava. As políticas de atualização anteriores podem ajudar a compreender o que pode fazer para abordar uma tarefa **Ignorada** ou **Em fila**.

## <a name="schedule-tab"></a>Separador Agenda

Use o separador **Agendar** para agendar atualizações automáticas de todos as suas [origens de dados ingeridas](data-sources.md). As atualizações automáticas ajudam a garantir que as atualizações das suas origens de dados são refletidas nos perfis de clientes unificados.

1. Nas informações de audiência, aceda a **Admin** > **Sistema** e selecione o separador **Agendar**.

2. O estado predefinido da atualização agendada é **Desativado**. Para ativar as atualizações agendadas, altere o botão de alternar na parte superior do ecrã para **Ativado**.

3. Escolha entre as atualizações **Semanal** (predefinição) e **Diária**. Se pretender agendar atualizações semanais, selecione um ou mais dias nos quais pretende executar a atualização.

4. Defina o seu **Fuso horário** e, em seguida, use a lista suspensa **Hora** para definir o tempo de atualização. Quando terminar, selecione **Definir**. Se pretende agendar várias atualizações num único dia, selecione **Adicionar outra hora**.

5. Selecione **Guardar** para aplicar as alterações.

## <a name="about-tab"></a>Separador Acerca de

O separador **Sobre** contém o **Nome a apresentar** da sua organização, o **ID do Ambiente** ativo, a **Região** e o seu **ID de Sessão**. Se tiver mais do que um ambiente de trabalho, deverá dar a cada um deles um nome a apresentar facilmente identificável.

## <a name="general-tab"></a>Separador Geral

Existem duas opções no separador **Geral**, **Idioma** e **Formato do País/Região**.

A aplicação [suporta diversos idiomas](supported-languages.md). Para alterar o idioma preferencial, escolha um **Idioma** na lista pendente.

Para alterar a formatação preferencial das datas, hora e números, utilize o menu pendente **País/Região**. É apresentada uma pré-visualização da formatação neste campo. O sistema irá sugerir automaticamente uma seleção quando escolher um novo idioma.

Selecione **Guardar** para confirmar as suas seleções.

## <a name="api-usage-tab"></a>Separador de utilização da API

Encontre detalhes sobre o uso da API em tempo real e veja quais os eventos que ocorreram num determinado intervalo de tempo. Para mais informações, consulte [Ingestão de dados em tempo real](real-time-data-ingestion.md).

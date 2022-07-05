---
title: Configuração do sistema
description: Saiba mais sobre as definições do sistema no Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 0ef84d8e286d8135eb8938e72f1319925e948bed
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050685"
---
# <a name="system-configuration"></a>Configuração do sistema

Para aceder a configurações do sistema, aceda a **Admin** > **Sistema** para ver uma lista de tarefas e processos do sistema.

A página **Sistema** inclui os seguintes separadores:
- [Estado](#status-tab)
- [Agenda](#schedule-tab)
- [Utilização da API](#api-usage-tab)
- [Acerca de](#about-tab)
- [Geral](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Separadores de definições na página do sistema.":::

## <a name="status-tab"></a>Separador Estado

O **separador Estado** permite-lhe monitorizar o progresso de tarefas, a ingestão de dados, as exportações de dados e vários outros processos importantes do produto. Reveja as informações sobre este separador para garantir a conclusão das suas tarefas e processos ativos.

Este separador inclui tabelas com informações de estado e processamento para vários processos. Cada tabela monitoriza o **Nome** da tarefa e a sua entidade correspondente, o **Estado** da sua execução mais recente, e quando foi **Atualizada pela última vez**. Pode ver os detalhes das últimas execuções selecionando a tarefa ou o nome do processo. 

Selecione o estado junto da tarefa ou do processo na coluna **Estado** para abrir o painel **Detalhes do progresso**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Painel de detalhes do progresso do sistema":::

### <a name="status-definitions"></a>Definições de estado

O sistema utiliza os seguintes estados para tarefas e processos:

|Estado  |Definição  |
|---------|---------|
|Cancelado |O processamento foi cancelado pelo utilizador antes de terminar.   |
|Com Falha   |A ingestão de dados encontrou erros.         |
|Falha  |O processamento falhou.  |
|Não iniciada   |A origem dos dados ainda não tem dados ingeridos ou ainda está em modo de rascunho.         |
|Em processamento  |A tarefa ou o processo estão em curso.  |
|A atualizar    |A ingestão de dados está em curso. Poderá cancelar esta operação ao selecionar **Parar de atualizar** na coluna **Ações**. Parar a atualização de um origem de dados irá revertê-lo para o último estado de atualização.       |
|Omitida  |A tarefa ou o processo foi ignorado. Um ou mais dos processos a jusante de que esta tarefa depende estão a falhar ou foram ignorados.|
|Êxito  |Tarefa ou processo concluído com êxito. Para as origens de dados, indica que os dados foram ingeridos com êxito se for mencionado um tempo na coluna **Atualizado**.|
|Em fila | O processamento está na fila e iniciará assim que todas as tarefas e processos de origem forem concluídos. Para mais informações, consulte [Atualizar processos](#refresh-processes).|

### <a name="refresh-processes"></a>Atualizar processos

A atualização de tarefas e processos é executada de acordo com a [agenda configurada](#schedule-tab). 

|Processo  |Descrição  |
|---------|---------|
|Atividade  |É executado manualmente (atualização única). Depende do processo de intercalação. As informações dependem do seu processamento.|
|Ligação da análise |É executado manualmente (atualização única). Depende dos segmentos.  |
|Preparação da análise |É executado manualmente (atualização única). Depende dos segmentos.  |
|Preparação de dados   |É necessária uma entidade em que executar. As entidades de origem de dados dependem da ingestão. As entidades melhoradas dependem de melhoramentos. A entidade Cliente depende da união.  |
|Origens de dados   |Não depende de qualquer outro processo. A correspondência depende da conclusão com êxito deste processo.  |
|Melhoramentos   |É executado manualmente (atualização única). Depende do processo de intercalação. |
|Destinos de exportação |É executado manualmente (atualização única). Depende dos segmentos.  |
|Informações |É executado manualmente (atualização única). Depende dos segmentos.  |
|Informações   |Depende da intercalação.   |
|Corresponder |Depende do processamento das origens de dados utilizadas na definição de correspondência.      |
|Medidas  |É executado manualmente (atualização única). Depende do processo de intercalação.  |
|Unir   |Depende da conclusão do processo de correspondência. Os segmentos, as medidas, o melhoramento, a pesquisa, as atividades, as previsões e a preparação de dados dependem da conclusão com êxito deste processo.   |
|Perfis   |É executado manualmente (atualização única). Depende do processo de intercalação. |
|Pesquisar   |É executado manualmente (atualização única). Depende do processo de intercalação. |
|Segmentos  |É executado manualmente (atualização única). Depende do processo de intercalação. As informações dependem do seu processamento.|
|Sistema   |Depende da conclusão do processo de correspondência. Os segmentos, as medidas, o melhoramento, a pesquisa, as atividades, as previsões e a preparação de dados dependem da conclusão com êxito deste processo.   |
|Utilizador  |É executado manualmente (atualização única). Depende das entidades.  |

Selecione o estado de um processo para ver os detalhes do progresso de toda a tarefa em que estava. Os processos de atualização acima podem ajudar a compreender o que pode fazer para abordar uma tarefa ou processo **Ignorado** ou **Em fila**.

## <a name="schedule-tab"></a>Separador Agenda

Use o separador **Agendar** para agendar atualizações automáticas de todos as suas [origens de dados ingeridas](data-sources.md). As atualizações automáticas ajudam a garantir que as atualizações das suas origens de dados são refletidas nos perfis de clientes unificados.

> [!NOTE]
> As origens de dados geridas por si atualizam as suas próprias agendas. Para agendar a atualização de origens de dados geridas por si, configure as definições de atualização nessa origem de dados específica na página de **origens de dados**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Definições de atualização do fluxo de dados.":::

1. Aceda a **Admin** > **Sistema** e selecione o separador **Agenda**.

2. O estado predefinido da atualização agendada é **Desativado**. Para ativar as atualizações agendadas, altere o botão de alternar na parte superior do ecrã para **Ativado**.

3. Escolha entre as atualizações **Semanal** (predefinição) e **Diária**. Se pretender agendar atualizações semanais, selecione um ou mais dias nos quais pretende executar a atualização.

4. Defina o seu **Fuso horário** e, em seguida, use a lista suspensa **Hora** para definir o tempo de atualização. Quando terminar, selecione **Definir**. Se pretende agendar várias atualizações num único dia, selecione **Adicionar outra hora**.

5. Selecione **Guardar** para aplicar as alterações.

## <a name="about-tab"></a>Separador Acerca de

O separador **Sobre** contém o **Nome a apresentar** da sua organização, o **ID do Ambiente** ativo, a **Região** e o seu **ID de Sessão**. Se tiver mais do que um ambiente de trabalho, deverá dar a cada um deles um nome a apresentar facilmente identificável.

## <a name="general-tab"></a>Separador Geral

Pode alterar o idioma e o formato de país/região no separador **Geral**.

O Customer Insights [suporta muitos idiomas](/dynamics365/get-started/availability). A aplicação usa a sua preferência de idioma para apresentar elementos como o menu, o texto da etiqueta e as mensagens do sistema no seu idioma preferencial.

Os dados importados e as informações que introduziu manualmente não são traduzidos.

### <a name="update-the-settings"></a>Atualizar as definições

Para alterar o idioma preferencial, escolha um **Idioma** na lista pendente.

Para alterar a formatação preferencial das datas, hora e números, utilize o menu pendente **País/Região**. É apresentada uma pré-visualização da formatação neste campo. O sistema irá sugerir automaticamente uma seleção quando escolher um novo idioma.

Selecione **Guardar** para confirmar as suas seleções.

## <a name="api-usage-tab"></a>Separador de utilização da API

Encontre detalhes sobre a utilização da API em tempo real e veja quais os eventos que ocorreram num dado período de tempo. Você escolhe o período de tempo no menu pendente **Selecionar um período de tempo**. 

A **Utilização da API** contém três secções: 
- **Chamadas à API** – um gráfico que visualiza o número agregado de chamadas à API no intervalo de tempo selecionado.

- **Transferência de dados** – um gráfico que mostra a quantidade de dados que foram transferidos através da API no intervalo de tempo selecionado.

-  **Operações** – uma tabela com filas para cada operação disponível da API e detalhes sobre a utilização das operações. Pode selecionar um nome de operação para ir [à referência API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   As operações que utilizam [a ingestão de dados em tempo real](real-time-data-ingestion.md) contêm um botão com um símbolo de binóculos para ver a utilização da API em tempo real. Selecione o botão para abrir um painel lateral contendo detalhes de utilização para a utilização da API em tempo real no ambiente atual.   
   Utilize a caixa **Agrupar por** no painel **Utilização da API em tempo real** para escolher como melhor apresentar as suas interações em tempo real. Pode agrupar os dados pelo método de API, nome qualificado de entidade (entidade ingerida), criado por (origem do evento), resultado (sucesso ou falha) ou códigos de erro. Os dados estão disponíveis como gráfico histórico e como tabela.


[!INCLUDE [footer-include](includes/footer-banner.md)]

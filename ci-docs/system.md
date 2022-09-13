---
title: Ver configuração do sistema
description: Saiba mais sobre as definições do sistema no Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396015"
---
# <a name="view-system-configuration"></a>Ver configuração do sistema

Ver informações do sistema, estado do sistema e utilização da API.

## <a name="view-api-usage"></a>Ver utilização da API

Veja os detalhes sobre a utilização da API em tempo real e veja quais os eventos que ocorreram num dado período de tempo.

1. Aceda a **Admin** > **Sistema** e selecione o separador **Utilização da API**.

1. **Selecione um intervalo de tempo** a ver.

   A página **Utilização da API** contém três secções:

   - **Chamadas à API** – um gráfico que visualiza o número agregado de chamadas à API no intervalo de tempo selecionado.
   - **Transferência de dados** – um gráfico que mostra a quantidade de dados que foram transferidos através da API no intervalo de tempo selecionado.
   - **Operações** – uma tabela com filas para cada operação disponível da API e detalhes sobre a utilização das operações. Selecione um nome de operação para ir para [a referência à API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Ver informações do sistema

Veja o nome a apresentar do ambiente, ID, região, tipo e ID de sessão.

1. Aceda a **Administrador** > **Sistema** e selecione o separador **Acerca de**.

1. Para ver o idioma e o país/região, selecione o separador **Geral**.

### <a name="update-preferred-language-or-countryregion"></a>Atualizar idioma ou país/região preferencial

O Customer Insights [suporta muitos idiomas](/dynamics365/get-started/availability). A aplicação usa a sua preferência de idioma para apresentar elementos como o menu, o texto da etiqueta e as mensagens do sistema no seu idioma preferencial.

Os dados importados e as informações que introduziu manualmente não são traduzidos.

1. Aceda a **Administrador** > **Sistema** e selecione o separador **Geral**.

1. Para alterar o idioma preferencial, escolha um **Idioma** na lista pendente.

1. Para alterar a formatação preferencial das datas, hora e números, utilize o menu pendente **País/Região**. É apresentada uma pré-visualização de formatação. O sistema sugere automaticamente uma seleção quando escolher um novo idioma.

1. Selecione **Guardar**.

## <a name="view-system-status"></a>Ver estado do sistema

Monitorize o progresso de tarefas, a ingestão de dados, as exportações de dados e vários outros processos importantes do produto. Reveja as informações para garantir a conclusão das suas tarefas e processos ativos.

1. Aceda a **Admin** > **Sistema** e selecione o separador **Estado**.

   São apresentadas as informações sobre o estado e o processamento para vários processos. Veja o **Nome** da tarefa, o **Estado** da sua execução mais recente, e quando foi **Atualizada pela última vez**.

1. Para ver os detalhes das últimas várias execuções, selecione a tarefa ou o nome do processo.

1. Para ver os detalhes do progresso para uma tarefa, selecione o estado. É apresentado o painel **Detalhes do progresso**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Painel de detalhes do progresso do sistema":::

1. Para ver os detalhes de progresso para todas as tarefas, selecione **Fluxo de trabalho completo**.

### <a name="status-definitions"></a>Definições de estado

O sistema utiliza os seguintes estados para tarefas e processos:

|Status  |Definição  |
|---------|---------|
|Cancelada |A tarefa ou o processo foi cancelado pelo utilizador antes de terminar.   |
|Com Falha   |A tarefa ou o processo executado encontrou erros.         |
|Falha  |A tarefa ou o processo falhou.  |
|Não iniciada   |A origem de dados ainda não tem dados ingeridos ou a tarefa ainda está em modo de rascunho.         |
|Em processamento  |A tarefa ou o processo estão em curso.  |
|A atualizar    |A tarefa ou o processo estão em curso. Para cancelar esta operação, selecione **A atualizar** e **Cancelar tarefa**. Parar a atualização de uma tarefa ou processo irá revertê-lo para o último estado de atualização.       |
|Omitida  |A tarefa ou o processo foi ignorado. Um ou mais dos processos a jusante de que esta tarefa depende estão a falhar ou foram ignorados.|
|Êxito  |Tarefa ou processo concluído com êxito. Para as origens de dados, indica que os dados foram ingeridos com êxito se for mencionado um tempo na coluna **Atualizado**.|
|Em fila | O processamento está na fila e iniciará assim que todas as tarefas e processos de origem forem concluídos. Para mais informações, consulte [Atualizar processos](#refresh-processes).|

### <a name="refresh-processes"></a>Atualizar processos

A atualização de tarefas e processos é executada de acordo com a [agenda configurada](schedule-refresh.md).

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


[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Configuração do sistema em informações de audiência
description: Saiba mais sobre as configurações do sistema na capacidade das informações de audiência do Dynamics 365 Customer Insights.
ms.date: 10/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3ce767939b8fedf676dc569ede47104ecfe930dd
ms.sourcegitcommit: cd9f9a9d3da71c5420ef5c4c6ead91bc820d17a9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651854"
---
# <a name="system-configuration"></a>Configuração do sistema

A página **Sistema** inclui os seguintes separadores:
- [Estado](#status-tab)
- [Agenda](#schedule-tab)
- [Utilização da API](#api-usage-tab)
- [Acerca de](#about-tab)
- [Geral](#general-tab)
- [Segurança](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Separadores de definições na página do sistema.":::

## <a name="status-tab"></a>Separador Estado

O separador **Estado** permite-lhe acompanhar o progresso da ingestão de dados, exportações de dados e vários outros processos importantes do produto. Rever a informação neste separador para garantir a abrangência dos processos ativos.

Este separador inclui tabelas com informações de estado e processamento para vários processos. Cada tabela monitoriza o **Nome** da tarefa e a sua entidade correspondente, o **Estado** da sua execução mais recente, e quando foi **Atualizada pela última vez**.

Ver os detalhes das últimas várias execuções das tarefas ao selecionar o respetivo nome.

### <a name="status-types"></a>Tipos de estado

Há seis tipos de estados para tarefas. Os seguintes tipos de estado também são mostrados nas páginas *Corresponder*, *Unir*, *Origens de dados*, *Segmentos*, *Medidas*, *Melhoramento*, *Atividades* e *Previsões*:

- **A processar:** a tarefa está em curso. O estado pode ser alterado para Com êxito ou Falha.
- **Com Êxito:** a tarefa foi concluída com êxito.
- **Ignorada:** A tarefa foi ignorada. Um ou mais dos processos a jusante de que esta tarefa depende estão a falhar ou foram ignorados.
- **Falha:** o processamento da tarefa falhou.
- **Cancelada:** o processamento foi cancelado pelo utilizador antes de ser concluído.
- **Em fila:** o processamento está em fila e começará assim que todas as tarefas a montante estiverem concluídas. Para mais informações, consulte [Políticas de atualização](#refresh-policies).

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

Pode alterar o idioma e o formato de país/região no separador **Geral**.

O Customer Insights [suporta vários idiomas](/dynamics365/get-started/availability). A aplicação usa a sua preferência de idioma para apresentar elementos como o menu, o texto da etiqueta e as mensagens do sistema no seu idioma preferencial.

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

   As operações que utilizam [a ingestão de dados em tempo real](real-time-data-ingestion.md) contêm um botão com um símbolo binocular para visualizar a utilização da API em tempo real. Selecione o botão para abrir um painel lateral contendo detalhes de utilização para a utilização da API em tempo real no ambiente atual.   
   Utilize a caixa **Agrupar por** no painel **Utilização da API em tempo real** para escolher como melhor apresentar as suas interações em tempo real. Pode agrupar os dados pelo método de API, nome qualificado de entidade (entidade ingerida), criado por (origem do evento), resultado (sucesso ou falha) ou códigos de erro. Os dados estão disponíveis como gráfico histórico e como tabela.

## <a name="security-tab"></a>Separador de segurança

O separador **Segurança** permite-lhe ligar e gerir o seu próprio [Azure Key Vault](/azure/key-vault/general/basic-concepts) ao ambiente.
O cofre de chaves dedicado pode ser utilizado para preparar e utilizar segredos no limiar de conformidade de uma organização. As informações de audiência podem utilizar os segredos no Azure Key Vault para [configurar as ligações](connections.md) aos sistemas de terceiros.

Para mais informações, consulte [Trazer o seu próprio Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Ver relatórios de dados
description: Utilize os relatórios disponíveis para ver a atividade em tempo real no seu site.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036662"
---
# <a name="view-reports"></a>Ver relatórios

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um relatório é uma coleção de visualizações de dados utilizando os dados recolhidos através da SDK, que o ajudam a medir e a compreender o comportamento do utilizador. As informações de cativação do Dynamics 365 Customer Insights incluem relatórios de origem (OOB) para projetos Web e móveis.  

## <a name="web-reports"></a>Relatórios Web

Pode aceder a relatórios Web sob **Detetar** no painel de navegação esquerdo.

:::image type="content" source="media/report-menu.png" alt-text="Navegação a mostrar a lista de relatórios disponíveis.":::

### <a name="real-time-usage-report"></a>Relatório de utilização em tempo real

O relatório de **Utilização em tempo real** fornece uma visão geral da atividade atual no seu site que atualiza automaticamente cada minuto. Use a utilização em tempo real para monitorizar o impacto de campanhas de marketing, eventos de imprensa e outros cenários no tráfego do seu site.

### <a name="key-metrics-reports"></a>Relatórios de métricas principais

- **Visualizações de página** lista as visualizações de página para páginas individuais, juntamente com o número total de visualizações de página sobre o período de tempo selecionado.

- **Visitas** mostra informações sobre o número de visitas e a duração da visita.

- **Visitantes** informa sobre visitantes exclusivos novos e de regresso ao seu site.

### <a name="content-reports"></a>Relatórios de conteúdo

- **Ligações** mostra informações sobre o número e o tipo de cliques.

- **Saída das páginas** lista as ligações em que os visitantes clicaram para sair do seu site.

### <a name="traffic-sources-reports"></a>Relatórios de origens de tráfego

- **Referências** lista os domínios e URLs que referiram os visitantes para o seu site.

- **Códigos de monitorização** fornece detalhes sobre os códigos de monitorização nas ligações que levaram os visitantes ao seu site.

### <a name="visitor-profiles-reports"></a>Relatórios de perfis de visitantes

- **Dispositivos** lista os dispositivos físicos que foram usados para aceder ao seu site.

- **SO e browsers** fornece informações sobre os sistemas operativos e navegadores que estavam em execução ao aceder ao seu site.

- **Localizações** mostra informações sobre visitantes por país, região e cidade.

- **Idiomas** lista as visualizações de página pelos idiomas preferenciais do visitante.

## <a name="mobile-reports"></a>Relatórios móveis

Os relatórios móveis são agrupados nas categorias de utilização em tempo real, aplicação e utilizador. Pode aceder a relatórios móveis sob **Detetar** no painel de navegação esquerdo.   

:::image type="content" source="media/mobile-reports.png" alt-text="Interface de utilizador de informações de cativação a mostrar o relatório de utilização em tempo real que compõe dados em gráficos e listas.":::   

### <a name="real-time-usage"></a>Utilização em tempo real

**Utilização em tempo real** fornece uma descrição geral da atividade atual na sua aplicação móvel que atualiza automaticamente a cada minuto. Utilize a utilização em tempo real para monitorizar o número de utilizadores e sessões atualmente ativas na sua aplicação e as principais visualizações de ecrã.

### <a name="app-reports"></a>Relatórios de aplicações

- **Visualizações de ecrã** listas as visualizações de ecrã para ecrãs individuais numa aplicação e o número total de visualizações de ecrã sobre um período de tempo selecionado. Pode ver as visualizações dE ecrã por nome do ecrã ou por título do ecrã.

- **Sessões** mostra informações sobre o número de sessões e a duração da sessão.

- **Frequência de regresso** agrupa contagens de sessões pelo número de dias desde a última sessão.

- **Utilizadores** mostra utilizadores novos e a regressar na sua aplicação móvel.

- **Eventos** lista todos os eventos recolhidos na sua aplicação, além da contagem total para cada evento.

### <a name="user-reports"></a>Relatórios de utilizadores

- **Versões de aplicações** lista as versões da sua aplicação móvel em utilização pela sua base de utilizadores.

- **Dispositivos e versões de SO** fornece informações sobre que dispositivos e sistemas operativos estão a executar a sua aplicação móvel.

- **Localizações** mostra informações sobre utilizadores de aplicação por país, região e cidade.

## <a name="filter-by-time-or-value"></a>Filtrar por tempo ou valor

Pode selecionar o período de tempo ou valor num relatório Web ou móvel para se concentrar num valor ou período de tempo. 

- Para selecionar um período de tempo, selecione **Mais [...]** da lista pendente do relatório. A seleção do intervalo de tempo é desativada para um relatório de utilização em tempo real; o intervalo de tempo para um relatório de utilização em tempo real é "agora."

- Na maioria dos relatórios, selecione um valor num gráfico ou lista para filtrar o relatório pelo valor selecionado.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
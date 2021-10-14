---
title: Tarefas partilhadas para cenários de predição
description: Aprenda a gerir, resolver problemas e refinar predições.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: eaccf23a81ca4de19763b761cc5a27c14515fe522ee36dc78f294208b681966e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036479"
---
# <a name="manage-predictions"></a>Gerir predições

Este artigo apresenta algumas tarefas que a maioria dos cenários de predição partilham.

## <a name="troubleshoot-a-failed-prediction"></a>Resolução de problemas de uma predição falhada

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione as reticências verticais ao lado da predição para a qual deseja ver os registos de erros.

1. Selecionar **Registos**.

1. Rever todos os erros. Existem vários tipos de erros que podem ocorrer, e estes descrevem que condição causou o erro. Por exemplo, um erro que não há dados suficientes para prever com precisão é, normalmente, resolvido carregando dados adicionais no Customer Insights.

## <a name="input-data-usability-report"></a>Relatório de capacidade de utilização de dados de entrada

O relatório de capacidade de utilização de dados de entrada fornece uma vista consolidada dos erros e avisos que as suas predições fornecidas com o programa podem estar a gerar. Também apresenta recomendações sobre como melhorar o desempenho do modelo.

O relatório está disponível depois de um modelo ter concluído o seu processo de preparação. É criado para cada modelo separadamente, independentemente de ter sido concluído com sucesso ou não.

### <a name="view-the-input-data-usability-report"></a>Ver o relatório de capacidade de utilização de dados de entrada

Depois de um modelo fornecido com o programa ter concluído o seu passo de preparação, veja o relatório:
- Selecione as reticências junto do nome do modelo e escolha **Relatório de capacidade de utilização de dados de entrada**.
- Para selecione o estado de um modelo, selecione **Ver o Relatório de capacidade de utilização de dados de entrada** no painel lateral.
- Selecionando um dos modelos na lista e selecione o **Relatório de capacidade de utilização de dados de entrada** na barra de comandos.
- Abra a página de resultados do modelo e selecione o **Relatório de capacidade de utilização de dados de entrada** na barra de comandos.

### <a name="information-in-the-input-data-usability-report"></a>Informações no relatório de capacidade de utilização de dados de entrada

As seguintes colunas no relatório contêm informações úteis para melhorar os dados do modelo.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo de um relatório de capacidade de utilização de dados de entrada a mostrar uma tabela com erros, avisos e recomendações.":::

- Nome: nome descritivo do erro, aviso ou recomendação.
- Passo: fase do modelo, preparação ou classificação, a que as informações se referem.
- Estado: gravidade das informações (erro, aviso, recomendação).
- Nome da coluna: coluna numa entidade que precisa de ser modificada para melhorar o desempenho do modelo.
- Nome da entidade: nome da entidade que precisa de ser modificada para melhorar o desempenho do modelo.
- Detalhes: detalhes sobre o erro, aviso ou recomendação.

## <a name="refresh-a-prediction"></a>Atualizar uma previsão

As previsões serão automaticamente atualizadas no mesmo [horário que as suas atualizações de dados](system.md#schedule-tab) como configurados nas definições. Também é possível atualizá-las manualmente.

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione as reticências verticais ao lado da previsão que pretende atualizar.

1. Selecione **Atualizar**.

## <a name="delete-a-prediction"></a>Eliminar uma previsão

A eliminação de uma predição também elimina a sua entidade de saída.

1. Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.

1. Selecione as reticências verticais ao lado da previsão que pretende eliminar.

1. Selecione **Eliminar**.
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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095740"
---
# <a name="manage-predictions"></a><span data-ttu-id="11424-103">Gerir predições</span><span class="sxs-lookup"><span data-stu-id="11424-103">Manage predictions</span></span>

<span data-ttu-id="11424-104">Este artigo apresenta algumas tarefas que a maioria dos cenários de predição partilham.</span><span class="sxs-lookup"><span data-stu-id="11424-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="11424-105">Resolução de problemas de uma predição falhada</span><span class="sxs-lookup"><span data-stu-id="11424-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="11424-106">Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.</span><span class="sxs-lookup"><span data-stu-id="11424-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="11424-107">Selecione as reticências verticais ao lado da predição para a qual deseja ver os registos de erros.</span><span class="sxs-lookup"><span data-stu-id="11424-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="11424-108">Selecionar **Registos**.</span><span class="sxs-lookup"><span data-stu-id="11424-108">Select **Logs**.</span></span>

1. <span data-ttu-id="11424-109">Rever todos os erros.</span><span class="sxs-lookup"><span data-stu-id="11424-109">Review all the errors.</span></span> <span data-ttu-id="11424-110">Existem vários tipos de erros que podem ocorrer, e estes descrevem que condição causou o erro.</span><span class="sxs-lookup"><span data-stu-id="11424-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="11424-111">Por exemplo, um erro que não há dados suficientes para prever com precisão é, normalmente, resolvido carregando dados adicionais no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11424-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="11424-112">Relatório de capacidade de utilização de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="11424-112">Input data usability report</span></span>

<span data-ttu-id="11424-113">O relatório de capacidade de utilização de dados de entrada fornece uma vista consolidada dos erros e avisos que as suas predições fornecidas com o programa podem estar a gerar.</span><span class="sxs-lookup"><span data-stu-id="11424-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="11424-114">Também apresenta recomendações sobre como melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="11424-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="11424-115">O relatório está disponível depois de um modelo ter concluído o seu processo de preparação.</span><span class="sxs-lookup"><span data-stu-id="11424-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="11424-116">É criado para cada modelo separadamente, independentemente de ter sido concluído com sucesso ou não.</span><span class="sxs-lookup"><span data-stu-id="11424-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="11424-117">Atualmente, esta funcionalidade só funciona para o modelo Abandono de Transações.</span><span class="sxs-lookup"><span data-stu-id="11424-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="11424-118">Ver o relatório de capacidade de utilização de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="11424-118">View the input data usability report</span></span>

<span data-ttu-id="11424-119">Depois de um modelo fornecido com o programa ter concluído o seu passo de preparação, veja o relatório:</span><span class="sxs-lookup"><span data-stu-id="11424-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="11424-120">Selecione as reticências junto do nome do modelo e escolha **Relatório de capacidade de utilização de dados de entrada**.</span><span class="sxs-lookup"><span data-stu-id="11424-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="11424-121">Para selecione o estado de um modelo, selecione **Ver o Relatório de capacidade de utilização de dados de entrada** no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="11424-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="11424-122">Selecionando um dos modelos na lista e selecione o **Relatório de capacidade de utilização de dados de entrada** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="11424-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="11424-123">Abra a página de resultados do modelo e selecione o **Relatório de capacidade de utilização de dados de entrada** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="11424-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="11424-124">Informações no relatório de capacidade de utilização de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="11424-124">Information in the input data usability report</span></span>

<span data-ttu-id="11424-125">As seguintes colunas no relatório contêm informações úteis para melhorar os dados do modelo.</span><span class="sxs-lookup"><span data-stu-id="11424-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo de um relatório de capacidade de utilização de dados de entrada a mostrar uma tabela com erros, avisos e recomendações.":::

- <span data-ttu-id="11424-127">Nome: nome descritivo do erro, aviso ou recomendação.</span><span class="sxs-lookup"><span data-stu-id="11424-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="11424-128">Passo: fase do modelo, preparação ou classificação, a que as informações se referem.</span><span class="sxs-lookup"><span data-stu-id="11424-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="11424-129">Estado: gravidade das informações (erro, aviso, recomendação).</span><span class="sxs-lookup"><span data-stu-id="11424-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="11424-130">Nome da coluna: coluna numa entidade que precisa de ser modificada para melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="11424-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="11424-131">Nome da entidade: nome da entidade que precisa de ser modificada para melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="11424-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="11424-132">Detalhes: detalhes sobre o erro, aviso ou recomendação.</span><span class="sxs-lookup"><span data-stu-id="11424-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="11424-133">Atualizar uma previsão</span><span class="sxs-lookup"><span data-stu-id="11424-133">Refresh a prediction</span></span>

<span data-ttu-id="11424-134">As previsões serão automaticamente atualizadas no mesmo [horário que as suas atualizações de dados](system.md#schedule-tab) como configurados nas definições.</span><span class="sxs-lookup"><span data-stu-id="11424-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="11424-135">Também é possível atualizá-las manualmente.</span><span class="sxs-lookup"><span data-stu-id="11424-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="11424-136">Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.</span><span class="sxs-lookup"><span data-stu-id="11424-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="11424-137">Selecione as reticências verticais ao lado da previsão que pretende atualizar.</span><span class="sxs-lookup"><span data-stu-id="11424-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="11424-138">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="11424-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="11424-139">Eliminar uma previsão</span><span class="sxs-lookup"><span data-stu-id="11424-139">Delete a prediction</span></span>

<span data-ttu-id="11424-140">A eliminação de uma predição também elimina a sua entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="11424-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="11424-141">Aceda a **Inteligência** > **Predições** e selecione o separador **As minhas predições**.</span><span class="sxs-lookup"><span data-stu-id="11424-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="11424-142">Selecione as reticências verticais ao lado da previsão que pretende eliminar.</span><span class="sxs-lookup"><span data-stu-id="11424-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="11424-143">Selecione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="11424-143">Select **Delete**.</span></span>
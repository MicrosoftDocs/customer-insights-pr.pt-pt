---
title: Página inicial em insights da audiência
description: Comece a explorar a aplicação na página inicial.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406635"
---
# <a name="create-a-new-environment"></a>Criar um novo ambiente

## <a name="create-a-trial-environment"></a>Criar um ambiente de avaliação

Pode inscrever-se para uma avaliação na [página de inscrição da avaliação](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> As versões expiram após 30 dias.

1. Escolha a opção **Inscrever para uma avaliação gratuita** e **Inscrever agora**.

1. Forneça o seu endereço de e-mail escolar ou profissional, conte-nos um pouco mais sobre si mesmo e selecione **Seguinte**.

1. Forneça um **Nome** para o seu novo ambiente. 

1. Selecione o tipo de avaliação.

1. Escolha a **Região** para o seu ambiente.

1. Opcionalmente, para administradores de uma organização do Dynamics 365: Selecione **Definições avançadas** e forneça o URL da sua organização para usar funcionalidades de predição como o abandono de clientes.

1. Selecione **Criar**. 

Depois do ambiente ter sido criado, verá o ambiente de **Demonstração** que lhe permite explorar a aplicações com dados fictícios. Pode alterar os dados de exemplo para corresponderem ao seu setor. Selecione o ícone **Definições** no cabeçalho e selecione **Definições de Demonstração**. Além disso, pode alterar o tema visual. 

[Muda para o ambiente](#change-between-environments) que criou durante o processo de inscrição para trabalhar com os seus próprios dados.

## <a name="create-a-new-production-or-sandbox-environment"></a>Criar um novo ambiente de produção ou de sandbox

No seu ambiente, selecione o ícone **Definições** no cabeçalho e selecione **Novo ambiente**.

Siga os passos como se [criasse um ambiente de avaliação](#create-a-trial-environment). Obtém uma opção adicional ao selecionar **Definições avançadas** para armazenar os seus dados no seu próprio Azure Data Lake. Forneça o nome da sua conta e a chave da sua conta para estabelecer uma ligação ao seu Azure Data Lake. Por predefinição, os dados são armazenados no data lake gerido pelo Customer Insights.

> [!IMPORTANT]
> Ao guardar dados no seu Azure Data Lake Storage, aceita que os dados serão transferidos e armazenados na localização geográfica adequada para essa apropriada para essa conta de armazenamento do Azure, que pode ser diferente daquela na qual os dados estão armazenados no Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorar a home page

Pode [aceder ao seu ambiente Customer Insights](https://home.ci.ai.dynamics.com/) no seguinte URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
A página **Home Page** mostra uma descrição geral da sua base de clientes e métricas-chave para acompanhar a saúde do seu negócio.

> [!div class="mx-imgBorder"] 
> ![Informações na Home page](media/home-page-insights.png "Informações na Home page")

Em **Segmentos recentes** vê grupos de clientes baseados em atributos demográficos, comportamentais ou transacionais que definiu. [Criar segmentos](segments.md) ajuda-o a direcionar melhor as suas atividades empresariais.

**Medidas recentes** mostra mosaicos com [medidas](measures.md). As medidas são indicadores chave de desempenho (KPIs) que definiu. Por exemplo, a probabilidade média de clientes ou gastos online médios por cliente.

A secção **Enriquecimentos recentes** lista os resultados das execuções de enriquecimento que foram concluídas recentemente. Os enriquecimentos adicionam informações sobre a sua base de clientes. Por exemplo, compreendendo os interesses e marcas para os quais têm afinidade. Esta informação pode ser desbloqueada utilizando as capacidades de [enriquecimento](enrichment-microsoft-graph.md) depois de completar as fases [mapear](map-entities.md), [corresponder](match-entities.md) e [unir](merge-entities.md).

## <a name="change-between-environments"></a>Alternar entre ambientes

Uma vez definidas e configuradas as [origens de dados](data-sources.md), vai querer mudar de um ambiente de demonstração para um ambiente ao vivo. A utilização do ambiente de produção permite-lhe trabalhar com os seus próprios dados de clientes. Selecione o controlo **Ambiente** no canto superior direito da página para mudar de ambiente.

> [!div class="mx-imgBorder"] 
> ![Mudar de ambiente](media/home-page-environment-switcher.png "Mudar de ambiente")

Os administradores podem criar e gerir [vários ambientes](manage-environments.md). Manter mais do que um ambiente pode ser útil se, por exemplo, a sua organização operar internacionalmente e precisar de segregar dados e informações de diferentes maneiras.

## <a name="next-step"></a>Passo seguinte

Para ver as suas próprias informações na home page, primeiro terá de [adicionar origens de dados](data-sources.md) e [unificar](data-unification.md) os seus dados para compilar perfis de clientes.

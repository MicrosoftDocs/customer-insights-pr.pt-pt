---
title: Página inicial em insights da audiência
description: Comece a explorar a aplicação na página inicial.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597249"
---
# <a name="create-a-new-environment"></a>Criar um novo ambiente

## <a name="create-a-trial-environment"></a>Criar um ambiente de avaliação

Pode inscrever-se para uma avaliação na [página de inscrição da avaliação](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> As versões expiram após 30 dias.

1. Escolha a opção **Inscrever para uma avaliação gratuita** e **Inscrever agora**.

1. Forneça o seu endereço de e-mail escolar ou profissional, conte-nos um pouco mais sobre si mesmo e selecione **Seguinte**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Caixa de diálogo para se inscrever numa instância de avaliação":::

1. Forneça um **Nome** para o seu novo ambiente. 

1. Selecione o tipo de avaliação.

1. Escolha a **Região** para o seu ambiente.

1. Opcionalmente, para administradores de uma organização do Dynamics 365: Selecione **Definições avançadas** e forneça o URL da sua organização para usar funcionalidades de predição como o abandono de clientes.

1. Selecione **Criar**. 

Depois do ambiente ter sido criado, verá o ambiente de **Demonstração** que lhe permite explorar a aplicações com dados fictícios. Pode alterar os dados de exemplo para corresponderem ao seu setor. Selecione o ícone **Definições** no cabeçalho e selecione **Definições de Demonstração**. Além disso, pode alterar o tema visual. 

[Muda para o ambiente](#switch-environments) que criou durante o processo de inscrição para trabalhar com os seus próprios dados.

## <a name="create-a-new-production-or-sandbox-environment"></a>Criar um novo ambiente de produção ou de sandbox

No seu ambiente, selecione o seletor **Ambientes** no cabeçalho da aplicação e selecione **Novo**.

Siga os passos como se [criasse um ambiente de avaliação](#create-a-trial-environment). Por predefinição, os dados são armazenados no data lake gerido pelo Customer Insights. Obtém uma opção adicional ao selecionar **Definições avançadas** para armazenar os seus dados no seu próprio Azure Data Lake. Forneça o nome da sua conta e a chave da sua conta para estabelecer uma ligação ao seu Azure Data Lake. 

> [!IMPORTANT]
> Ao guardar dados no seu Azure Data Lake Storage, aceita que os dados serão transferidos e armazenados na localização geográfica adequada para essa apropriada para essa conta de armazenamento do Azure, que pode ser diferente daquela na qual os dados estão armazenados no Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorar a home page

Pode [aceder a informações da audiência a partir do Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) no URL seguinte: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
A página **Home Page** mostra uma descrição geral de segmentos, medidas e dados de melhoramento (se configurados) depois de completar as fases [mapear](map-entities.md), [corresponder](match-entities.md) e [unir](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Informações na Home page](media/home-page-insights.png "Informações na Home page")

Em **Segmentos recentes** vê grupos de clientes baseados em atributos demográficos, comportamentais ou transacionais que definiu. [Criar segmentos](segments.md) ajuda-o a agrupar a sua base de clientes e a direcionar melhor as suas atividades empresariais.

As **medidas recentes** mostram mosaicos com [indicadores chave de desempenho (KPIs)](measures.md) que definiu. Por exemplo, a probabilidade média de um cliente de abandonar ou a média de gastos online por cliente.

A secção **Enriquecimentos recentes** lista os resultados das execuções de enriquecimento que foram concluídas recentemente. Os [melhoramentos](enrichment-hub.md) adicionam informações sobre a sua base de clientes. Por exemplo, compreendendo os interesses e marcas para os quais têm afinidade.

## <a name="switch-environments"></a>Mudar de ambientes

Selecione o controlo **Ambiente** no canto superior direito da página para mudar de ambiente.

> [!div class="mx-imgBorder"] 
> ![Mudar de ambiente](media/home-page-environment-switcher.png "Mudar de ambiente")

Os administradores podem criar e gerir [vários ambientes](manage-environments.md). Manter mais do que um ambiente pode ser útil se, por exemplo, a sua organização operar internacionalmente e precisar de segregar dados e informações de diferentes maneiras.

## <a name="next-step"></a>Passo seguinte

Para ver as suas próprias informações na home page, primeiro terá de [adicionar origens de dados](data-sources.md) e [unificar](data-unification.md) os seus dados para compilar perfis de clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
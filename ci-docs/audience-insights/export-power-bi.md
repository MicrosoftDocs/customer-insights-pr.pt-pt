---
title: Conector do Power BI
description: Saiba como utilizar o conector do Dynamics 365 Customer Insights no Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406610"
---
# <a name="connector-for-power-bi-preview"></a>Conector para Power BI (pré-visualização)

Crie visualizações para os seus dados com o Power BI Desktop. Gere informações adicionais e crie relatórios com os seus dados de cliente unificados.

## <a name="prerequisites"></a>Pré-requisitos

- Tem perfis unificados de clientes.
- A versão mais recente do [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalada no seu computador. [Mais informações sobre o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar o conector para Power BI

1. No Power BI Desktop, selecione **Ficheiro** > **Obter Dados**.

1. Selecione **Ver mais** e procure **Dynamics 365 Customer Insights**

1. Selecione o resultado e selecione **Ligar**.

1. **Inicie sessão** com a mesma conta organizacional utilizada para o Customer Insights e selecione **Ligar**.
   > [!NOTE]
   > A conta que indica neste passo é usada para recolher dados do Customer Insights e não precisa de ser a mesma em que está a iniciar sessão no Power BI. Para reiniciar a conta que é utilizada para a recolha de dados, abra o Power BI e vá a **Ficheiro** > **Opções** > **Definições** > **Definições de origem de dados**. Na lista de origens de dados, selecione **Iniciar sessão no Dynamics 365 Customer Insights** e selecione **Limpar permissões**.  

1. Na caixa de diálogo **Navegador**. vê a lista de todos os ambientes a que tem acesso. Expandir um ambiente e abrir qualquer uma das pastas (entidades, medidas, segmentos, melhoramentos). Por exemplo, abra a pasta **Entidades**, para ver todas as entidades que pode importar.

   ![Navegador do Conetor do Power BI](media/power-bi-navigator.png "Navegador do Conetor do Power BI")

1. Selecione as caixas de verificação junto às entidades que pretende incluir e **Carregar**. Pode selecionar várias entidades de vários ambientes.

1. Verá uma caixa de diálogo de carregamento enquanto as suas entidades estão a ser carregadas. Depois de todas as suas entidades selecionadas terem carregado, pode utilizar as capacidades do Power BI para visualizar os dados.

## <a name="large-data-sets"></a>Conjuntos de dados de grandes dimensões

O conector Customer Insights para o Power BI foi concebido para trabalhar com conjuntos de dados que contenham até 1 milhão de perfis de clientes. Importar conjuntos de dados maiores pode funcionar, mas leva muito tempo. Além disso, o processo pode exceder o tempo limite devido a limitações do Power BI. Para obter mais informações, consulte [Power BI : Recomendações para conjuntos de dados de grandes dimensões](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Trabalhar como um subconjunto de dados

Considere trabalhar com um subconjunto dos seus dados. Por exemplo, pode criar [segmentos](segments.md) em vez de exportar todos os registos de clientes para o Power BI.

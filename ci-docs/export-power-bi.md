---
title: Conector do Power BI (pré-visualização)
description: Saiba como utilizar o conector do Dynamics 365 Customer Insights no Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 72daf6d4ef3b6afb8049c622b57e7ec44762fb21
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051283"
---
# <a name="power-bi-connector-preview"></a>Conector do Power BI (pré-visualização)

Crie visualizações para os dados com o Microsoft Power BI Desktop. Gere informações adicionais e crie relatórios com os seus dados de cliente unificados.

## <a name="prerequisites"></a>Pré-requisitos

- Tem perfis unificados de clientes.
- A versão mais recente do [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalada no seu computador. [Mais informações sobre o Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar o conector para Power BI

1. No Power BI Desktop, selecione **Ficheiro** > **Obter Dados**.

1. Selecione **Ver mais** e procure **Dynamics 365 Customer Insights**

1. Selecione **Ligar**.

1. **Inicie sessão** com a mesma conta organizacional utilizada para o Customer Insights e selecione **Ligar**.
   > [!NOTE]
   > A conta que indica neste passo é usada para recolher dados do Customer Insights e não precisa de ser a mesma em que está a iniciar sessão no Power BI. Para reiniciar a conta que é utilizada para a recolha de dados, abra o Power BI e vá a **Ficheiro** > **Opções** > **Definições** > **Definições de origem de dados**. Na lista de origens de dados, selecione **Iniciar sessão no Dynamics 365 Customer Insights** e selecione **Limpar permissões**.  

1. Na caixa de diálogo **Navegador**. vê a lista de todos os ambientes a que tem acesso. Expandir um ambiente e abrir qualquer uma das pastas (entidades, medidas, segmentos, melhoramentos). Por exemplo, abra a pasta **Entidades**, para ver todas as entidades que pode importar.

   ![Navegador do Conetor do Power BI.](media/power-bi-navigator.png "Navegador do Conetor do Power BI")

1. Selecione as caixas de verificação junto às entidades que pretende incluir e **Carregar**. Pode selecionar várias entidades de vários ambientes.

1. Verá uma caixa de diálogo de carregamento enquanto as suas entidades estão a ser carregadas. Depois de todas as suas entidades selecionadas terem carregado, pode utilizar as capacidades do Power BI para visualizar os dados.

## <a name="large-data-sets"></a>Conjuntos de dados de grandes dimensões

O conector Customer Insights para o Power BI foi concebido para trabalhar com conjuntos de dados que contenham até 1 milhão de perfis de clientes. Importar conjuntos de dados maiores pode funcionar, mas leva muito tempo. Além disso, o processo pode exceder o tempo limite devido a limitações do Power BI. Para obter mais informações, consulte [Power BI : Recomendações para conjuntos de dados de grandes dimensões](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Trabalhar como um subconjunto de dados

Considere trabalhar com um subconjunto dos seus dados. Por exemplo, pode criar [segmentos](segments.md) em vez de exportar todos os registos de clientes para o Power BI.

## <a name="troubleshooting"></a>Resolução de Problemas

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>O ambiente do Customer Insights não aparece no Power BI

Os ambientes que tenham mais do que uma [relação](relationships.md) definida entre duas entidades idênticas no Customer Insights não estarão disponíveis no conector do Power BI.

Pode identificar e remover as relações duplicadas.

1. Aceda a **Dados** > **Relações** no ambiente que lhe falta no Power BI.
2. Identificar relações duplicadas:
   - Verifique se há mais de uma relação definida entre as mesmas duas entidades.
   - Verifique se existe uma relação criada entre duas entidades que estão ambas incluídas no processo de unificação. Existe uma relação implícita definida entre todas as entidades incluídas no processo de unificação.
3. Remova quaisquer relações duplicadas identificadas.

Após a remoção das relações duplicadas, tente configurar novamente o conector do Power BI. O ambiente deve estar agora disponível.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Erros em campos de data ao carregar entidades no Power BI Desktop

Ao carregar entidades que contenham campos com um formato de data como MM/DD/AAAA, pode encontrar erros devido a formatos locais sem correspondência. Este erro de correspondência ocorre quando o ficheiro do Power BI Desktop está definido para outra região que não o inglês (Estados Unidos), porque os campos de data no Customer Insights são guardados no formato dos EUA.

O ficheiro do Power BI Desktop tem uma única definição de região, que é aplicada ao obter dados. Para fazer com que estes campos de data sejam interpretados corretamente, defina a região do ficheiro .BPI para Inglês (Estados Unidos). [Aprenda a alterar a região de um ficheiro de ambiente de trabalho do Power BI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]

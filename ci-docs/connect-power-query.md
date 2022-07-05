---
title: Ligar a uma origem de dados do Power Query (contém vídeo)
description: Ingerir dados através de um conector do Power Query (contém vídeo).
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081269"
---
# <a name="connect-to-a-power-query-data-source"></a>Ligar a uma origem de dados do Power Query

O Power Query oferece um vasto conjunto de conectores para ingerir dados. A maioria destes conectores são suportados pelo Dynamics 365 Customer Insights.

Normalmente, a adição de origens de dados baseada em conectores do Power Query segue os passos descritos nesta secção. No entanto, dependendo do conector que utiliza, são necessárias informações diferentes. Para saber mais, consulte a documentação sobre os conectores individuais na [Referência do conector do Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Criar uma nova origem de dados

1. Aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Selecione **Microsoft Power Query**.

1. Forneça um **Nome** e uma **Descrição** opcional para a origem de dados e selecione **Seguinte**.

1. Escolha um dos [conectores disponíveis](#available-power-query-data-sources). Neste exemplo, selecionamos o conector **Text/CSV**.

1. Introduza os detalhes requeridos nas **Definições de ligação** para o conector selecionado e selecione **Seguinte** para ver uma pré-visualização dos dados.

1. Selecione **Transformar dados**. Neste passo, vai adicionar entidades à sua origem de dados. As entidades são conjuntos de dados. Se tiver uma base de dados que inclua vários conjuntos de dados, cada conjunto é a sua própria entidade.

1. O diálogo **Power Query – Editar consultas** permite-lhe rever e refinar os dados. As entidades que os sistemas identificaram na sua origem de dados ligada aparecem no painel esquerdo.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Diálogo Editar consultas":::

1. Também pode transformar os seus dados. Selecione uma entidade para edição ou transformação. Utilize as opções na janela do Power Query para aplicar transformações. Cada transformação é listada sob **Passos aplicados**. O Power Query fornece inúmeras opções de transformação pré-criadas. Para mais informações, consulte [Transformações do Power Query](/power-query/power-query-what-is-power-query#transformations).

   Recomendamos que utilize as seguintes transformações:

   - Se estiver a ingerir dados a partir de um ficheiro CSV, a primeira linha contém frequentemente cabeçalhos. Vá a **Transformar** e selecione **Utilizar a primeira linha como cabeçalhos**.
   - Certifique-se de que o tipo de dados está definido de forma adequada. Por exemplo, para campos de data, selecione um tipo de data.

1. Para adicionar entidades adicionais à sua origem de dados no diálogo **Editar consultas**, vá a **Base** e selecione **Obter dados**. Repita os passos 6 a 10 até ter adicionado todas as entidades para esta origem de dados.

1. Selecione **Guardar**. A página **Origens de dados** é aberta a mostrar a origem de dados novas no estado **A atualizar**.

### <a name="available-power-query-data-sources"></a>Origens de dados do Power Query disponíveis

Consulte a [Referência do conector do Power Query](/power-query/connectors/) para obter uma lista de conectores que poderá utilizar para importar dados para o Customer Insights.

Os conectores com uma marca de verificação na coluna **Customer Insights (Fluxos de dados)** estão disponíveis para criar novas origens de dados com base no Power Query. Consulte a documentação de um conector específico para obter mais informações sobre os pré-requisitos, [limitações de consulta](/power-query/power-query-online-limits) e outros detalhes.

## <a name="add-data-from-on-premises-data-sources"></a>Adicionar dados de origens de dados no local

A ingestão de dados de origens de dados no local é suportada com base em fluxos de dados do Microsoft Power Platform (PPDFs). Poderá ativar fluxos de dados no Customer Insights ao [fornecer o URL do ambiente do Microsoft Dataverse](create-environment.md) quando configurar o ambiente.

As origens de dados que são criadas após a associação de um ambiente do Dataverse ao Customer Insights utilizam [fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por predefinição. Os fluxos de dados suportam conectividade no local utilizando o gateway de dados. Poderá remover e recriar as origens de dados que existiam antes de um ambiente do Dataverse ser associado [através de gateways de dados no local](/data-integration/gateway/service-gateway-app).

Os gateways de dados de um ambiente Power BI ou Power Apps existente serão visíveis e poderá reutilizá-los no Customer Insights. A página de origens de dados mostra ligações para ir para o ambiente do Microsoft Power Platform onde pode ver e configurar gateways de dados no local.

> [!IMPORTANT]
> Certifique-se de que os seus gateways estão atualizados para a versão mais recente. Pode instalar uma atualização e reconfigurar um gateway a partir de um pedido mostrado diretamente no ecrã do gateway ou [transfira a versão mais recente](https://powerapps.microsoft.com/downloads/). Se não utilizar a versão mais recente do gateway, a atualização do fluxo de dados falha com mensagens de erro como **A palavra-chave não é suportada: propriedades de configuração. Nome do parâmetro: palavra-chave**.

## <a name="edit-power-query-data-sources"></a>Editar origens de dados do Power Query

> [!NOTE]
> Poderá não ser possível efetuar alterações às origens de dados que estão atualmente a ser utilizadas num dos processos da aplicação (*segmentação*, *corresponder* ou *intercalar*, por exemplo).
>
> Na página **Definições**, pode monitorizar o progresso de cada um dos processos ativos. Quando um processo é concluído, pode regressar à página **Origens de Dados** e efetuar as suas alterações.

1. Aceda a **Dados** > **Origens de dados**.

1. Junto da origem de dados que pretende atualizar, selecione **Editar**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Aplique as suas alterações e transformações no diálogo **Power Query – Editar consultas** como descrito na secção [Criar uma nova origem de dados](#create-a-new-data-source).

1. Selecione **Guardar** no Power Query depois de concluir as suas edições para guardar as suas alterações.

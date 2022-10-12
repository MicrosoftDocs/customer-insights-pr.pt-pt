---
title: Ligar a uma origem de dados do Power Query (contém vídeo)
description: Ingerir dados através de um conector do Power Query (contém vídeo).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609910"
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

1. Selecione **Transformar dados**.

1. Reveja e refine os seus dados na página **Power Query – Editar consultas**. As entidades que os sistemas identificaram na sua origem de dados ligada aparecem no painel esquerdo.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Diálogo Editar consultas":::

1. Transformar os seus dados. Selecione uma entidade para edição ou transformação. Utilize as opções na janela do Power Query para aplicar transformações. Cada transformação é listada sob **Passos aplicados**. O Power Query fornece inúmeras opções de [transformação pré-criadas](/power-query/power-query-what-is-power-query#transformations).

   > [!IMPORTANT]
   > Recomendamos que utilize as seguintes transformações:
   >
   > - Se estiver a ingerir dados a partir de um ficheiro CSV, a primeira linha contém frequentemente cabeçalhos. Vá a **Transformar** e selecione **Utilizar a primeira linha como cabeçalhos**.
   > - Certifique-se de que o tipo de dados está definido de forma adequada e que corresponde aos dados. Por exemplo, para campos de data, selecione um tipo de data.

1. Para adicionar entidades adicionais à sua origem de dados no diálogo **Editar consultas**, vá a **Base** e selecione **Obter dados**. Repita os passos 5 a 10 até ter adicionado todas as entidades para esta origem de dados. Se tiver uma base de dados que inclua vários conjuntos de dados, cada conjunto é a sua própria entidade.

1. Selecione **Guardar**. A página **Origens de dados** é aberta a mostrar a origem de dados novas no estado **A atualizar**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revistos na página [**Entidades**](entities.md).

> [!CAUTION]
>
> - Uma origem de dados baseada no Power Query cria um [fluxo de dados no Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Não altere o nome de um fluxo de dados no centro de administração do Power Platform que é utilizado no Customer Insights. Mudar o nome de um fluxo de dados causa problemas nas referências entre o a origem de dados do Customer Insights e o fluxo de dados do Dataverse.
> - As avaliações simultâneas para origens de dados do Power Query no Customer Insights têm os mesmos [limites de atualização como Fluxos de dados no PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Se uma atualização de dados falhar porque alcançou o limite de avaliação, recomendamos que ajuste a agenda de atualização para cada fluxo de dados, para garantir que as origens de dados não são processadas ao mesmo tempo.

### <a name="available-power-query-data-sources"></a>Origens de dados do Power Query disponíveis

Consulte a [Referência do conector do Power Query](/power-query/connectors/) para obter uma lista de conectores que poderá utilizar para importar dados para o Customer Insights.

Os conectores com uma marca de verificação na coluna **Customer Insights (Fluxos de dados)** estão disponíveis para criar novas origens de dados com base no Power Query. Consulte a documentação de um conector específico para obter mais informações sobre os pré-requisitos, [limitações de consulta](/power-query/power-query-online-limits) e outros detalhes.

## <a name="add-data-from-on-premises-data-sources"></a>Adicionar dados de origens de dados no local

A ingestão de dados de origens de dados no local é suportada com base em fluxos de dados do Microsoft Power Platform (PPDFs). Poderá ativar fluxos de dados no Customer Insights ao [fornecer o URL do ambiente do Microsoft Dataverse](create-environment.md) quando configurar o ambiente.

As origens de dados que são criadas após a associação de um ambiente do Dataverse ao Customer Insights utilizam [fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por predefinição. Os fluxos de dados suportam conectividade no local utilizando o gateway de dados. Poderá remover e recriar as origens de dados que existiam antes de um ambiente do Dataverse ser associado [através de gateways de dados no local](/data-integration/gateway/service-gateway-app).

Os gateways de dados de um ambiente Power BI ou Power Apps existente estarão visíveis e pode reutilizá-los no Customer Insights se o gateway de dados e o ambiente do Customer Insights estiverem na mesma região do Azure. A página de origens de dados mostra ligações para ir para o ambiente do Microsoft Power Platform onde pode ver e configurar gateways de dados no local.

> [!IMPORTANT]
> Certifique-se de que os seus gateways estão atualizados para a versão mais recente. Pode instalar uma atualização e reconfigurar um gateway a partir de um pedido mostrado diretamente no ecrã do gateway ou [transfira a versão mais recente](https://powerapps.microsoft.com/downloads/). Se não utilizar a versão mais recente do gateway, a atualização do fluxo de dados falha com mensagens de erro como **A palavra-chave não é suportada: propriedades de configuração. Nome do parâmetro: palavra-chave**.
>
> Os erros com os gateways de dados no local no Customer Insights são muitas vezes causados por problemas de configuração. Para mais informações sobre os gateways de dados de resolução de problemas, consulte [Resolver problemas com o gateway de dados no local](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Editar origens de dados do Power Query

> [!NOTE]
> Poderá não ser possível efetuar alterações às origens de dados que estão atualmente a ser utilizadas num dos processos da aplicação (segmentação ou unificação de dados, por exemplo).
>
> Na página **Definições**, pode monitorizar o progresso de cada um dos processos ativos. Quando um processo é concluído, pode regressar à página **Origens de Dados** e efetuar as suas alterações.

1. Aceda a **Dados** > **Origens de dados**.

1. Junto da origem de dados que pretende atualizar, selecione **Editar**.

1. Aplique as suas alterações e transformações no diálogo **Power Query – Editar consultas** como descrito na secção [Criar uma nova origem de dados](#create-a-new-data-source).

1. Selecione **Guardar** para aplicar as alterações e regressar à página **Origens de dados**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Razões comuns para erros de ingestão ou dados danificados

### <a name="data-type-does-not-match-data"></a>O tipo de dados não corresponde aos dados

A falta de correspondência do tipo de dados mais comum ocorre quando um campo de data não está definido com o formato de data correto.

Os dados podem ser corrigidos na origem e podem ser ingeridos novamente. Ou corrija a transformação no Customer Insights. Para corrigir a transformação:

1. Aceda a **Dados** > **Origens de dados**.

1. Junto à origem de dados com os dados corrompidos, selecione **Editar**.

1. Selecione **Seguinte**.

1. Selecione cada uma das consultas e procure pelas transformações aplicadas dentro de "Passos Aplicados" que estejam incorretos ou colunas de data que não tenham sido transformadas com um formato de data.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query – Edição a mostrar o formato de data incorreto":::

1. Altere o tipo de data para corresponder corretamente aos dados.

1. Selecione **Guardar**. A origem de dados é atualizada.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Resolução de problemas de atualização de origem de dados baseada no Power Query PPDF

Se os dados estiverem obsoletos ou se receber erros após uma atualização da origem de dados, efetue os seguintes passos:

1. Navegue para [Power Platform](https://make.powerapps.com).

1. Selecione o **Ambiente** para a sua instância do Customer Insights.

1. Navegue para o **Fluxos de dados**.

1. Para o fluxo de dados que corresponde à origem de dados no Customer Insights, selecione as reticências verticais (&vellip;) e, em seguida, selecione **Mostrar histórico de atualizações**.

1. Se o **Estado** do fluxo de dados for **Êxito**, a propriedade da origem de dados baseada no Power Query poderá ter alterado:

   1. Reveja a agenda de atualização a partir do histórico de atualizações.
   1. Defina a agenda do novo proprietário e guarde as definições.

1. Se o **Estado** do fluxo de dados for **Falhado**:

   1. Transfira o ficheiro do histórico de atualizações.
   1. Reveja o ficheiro transferido pelo motivo da falha.
   1. Se não for possível resolver o erro, selecione **?** para abrir um pedido de suporte. Inclua o ficheiro do histórico de atualizações transferido.


[!INCLUDE [footer-include](includes/footer-banner.md)]

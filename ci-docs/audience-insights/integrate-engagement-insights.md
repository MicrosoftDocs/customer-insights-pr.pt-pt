---
title: Integrar dados Web a partir de informações de cativação com informações da audiência
description: Traga informações Web sobre os clientes, desde informações de cativação até informações da audiência.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033783"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrar dados Web a partir de informações de cativação com informações da audiência

Frequentemente, os clientes fazem as suas transações diárias online usando sites. A capacidade de informações de cativação (pré-visualização) no Dynamics 365 Customer Insights é uma solução útil para integrar dados Web como uma origem. Além de dados transacionais, demográficos ou comportamentais, podemos ver atividades na Web em perfis de clientes unificados. Podemos utilizar estes perfis para obter informações adicionais como segmentos, medidas ou predições para a ativação da audiência.

Este artigo descreve os passos para trazer os dados de atividade Web dos seus clientes a partir de informações de cativação para o seu ambiente existente de informações da audiência.

Neste exemplo, assumimos um ambiente que contém perfis de cliente unificados. Os perfis foram unificados com origens de inquéritos, vendas a retalho e um sistema de emissão de permissões. Mostra também as atividades relacionadas dos clientes. 

Queremos agora saber se um cliente visita as nossas propriedades Web e compreender as suas atividades. As atividades incluem, por exemplo, sites visitados ou páginas de produtos visualizadas a partir de uma ligação recebida num e-mail.

## <a name="prerequisites"></a>Pré-requisitos

Para integrar dados de informações de cativação, é necessário cumprir alguns pré-requisitos: 

- Integre o SDK de informações de cativação com o seu site. Para mais informações, consulte [Descrição geral para programadores](../engagement-insights/developer-resources.md).
- Exportar eventos Web a partir de informações de cativação requer acesso a uma conta Azure Data Lake Storage que será usada para ingerir os dados de eventos Web para informações de audiência. Para obter mais informações, consulte [Exportar eventos](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configure eventos refinados em informações de cativação

Após um administrador instrumentar um site com a SDK de informações de cativação, os *eventos base* são recolhidos quando um utilizador visualiza uma página Web ou clica em algum lugar. Os eventos base tendem a conter inúmeros detalhes. Dependendo do seu caso de utilização, só precisa de um subconjunto dos dados num evento base. As informações de cativação permitem criar *eventos refinados* que contenham apenas as propriedades de um evento base que seleciona.     

Para obter mais informações, consulte [Criar e modificar eventos refinados](../engagement-insights/refined-events.md).

Considerações ao criar eventos refinados: 

- Forneça um nome significativo para o evento refinado. Será utilizado como um nome de atividade em informações de audiência.
- Selecione, pelo menos, as seguintes propriedades para criar uma atividade nas informações da audiência: 
    - Signal.Action.Name – indica os detalhes da atividade.
    - Signal.User.Id – utilizado para mapear com o ID do cliente.
    - Signal.View.Uri – utilizado como endereço Web como base para segmentos ou medidas.
    - Signal.Export.Id – utilizado como chave primária para eventos.
    - Signal.Timestamp – determina a data e hora para a atividade.

Selecione os filtros para se focar nos eventos e páginas que importam para o seu caso de utilização. Neste exemplo, utilizaremos o nome de ação "Promoção por e-mail".

## <a name="export-the-refined-web-events"></a>Exportar os eventos Web refinados 

Depois de definir o evento refinado, tem de configurar a exportação dos dados do evento para o Azure Data Lake Storage, o qual pode ser definido como uma origem de dados para ingestão em informações de audiência. As exportações acontecem constantemente à medida que os eventos fluem da propriedade Web.

Para obter mais informações, consulte [Exportar eventos](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Ingerir dados de eventos para informações da audiência

Agora que definiu o evento refinado e configurou a sua exportação, passamos a ingerir os dados para as informações da audiência. É necessário criar uma nova origem de dados baseada numa pasta Common Data Model. Insira os detalhes da conta de armazenamento para onde exporta os eventos. No ficheiro *default.cdm.json*, selecione o evento refinado a ingerir e crie a entidade nas informações da audiência.

Para obter mais informações, consulte [Ligar a uma pasta Common Data Model utilizando uma conta Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relacionar dados de eventos refinados como uma atividade de um perfil do cliente

Após completar a ingestão de entidades, pode configurar a atividade para o perfil do cliente.

Para mais informações, veja [Atividades de cliente](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Página de atividades com o painel Editar atividade expandido e com os campos preenchidos.":::

Configure a nova atividade com o seguinte mapeamento: 

- **Chave Primária**: Signal.Export.Id, um ID exclusivo que está disponível para cada registo de evento nas informações de cativação. Esta propriedade é gerada automaticamente.

- **Carimbo de data/hora**: Signal.Timestamp na propriedade do evento.

- **Evento**: Signal.Name, o nome do evento que pretende monitorizar.

- **Endereço Web**: Signal.View.Uri referindo-se ao URI da página que criou o evento.

- **Detalhes**: Signal.Action.Name para representar as informações a associar ao evento. A propriedade selecionada neste caso indica que o evento é para promoção por e-mail.

- **Tipo de atividade**: neste exemplo, escolhemos o WebLog do tipo de atividade existente. Esta seleção é uma opção de filtro útil para executar modelos de predição ou criar segmentos com base neste tipo de atividade.

- **Configurar relação**: esta definição importante liga a atividade aos perfis de clientes existentes. **Signal.User.Id** é o identificador configurado no SDK a ser recolhido e que se relaciona com o ID do utilizador noutras origens de dados que estão configuradas nas informações da audiência. Neste exemplo, configuramos a relação entre Signal.User.Id e RetailCustomers:CustomerRetailId, que é a chave primária que foi identificada no passo do mapa do processo de unificação de dados.

Após o processamento das atividades, pode rever os registos do cliente e abrir um cartão de cliente para ver as atividades das informações de cativação na linha cronológica. 

> [!TIP]
> Para encontrar um ID de cliente que tenha uma atividade de informações de cativação, vá a **Entidades** e pré-visualize os dados para a entidade UnifiedActivity. ActivityTypeDisplay = WebLog contém a atividade de informações de cativação configurada no exemplo acima. Copie o ID de cliente para um desses registos e para esse ID na página **Clientes**.

## <a name="next-steps"></a>Passos seguintes

Pode agora criar [segmentos](segments.md), [medidas](measures.md) e [predições](predictions.md) para fazer uma ligação significativa com os seus clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
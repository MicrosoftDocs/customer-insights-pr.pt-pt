---
title: Atividades do cliente
description: Defina as atividades dos clientes e veja-as numa linha cronológica nos perfis dos clientes.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188153"
---
# <a name="customer-activities"></a>Atividades do cliente

As atividades do cliente são ações ou eventos executados pelos clientes. Por exemplo, transações, duração da chamada de suporte, avaliações do Web site, compras ou devoluções. Estas atividades são contidas numa ou mais origens de dados. Com o Customers Insights, consolide as atividades dos seus clientes a partir destas [origens de dados](data-sources.md) e associe-as a perfis de cliente. Estas atividades aparecem cronologicamente numa linha cronológica no perfil de cliente. Inclua a linha cronológica em aplicações Dynamics 365 com a solução de [suplemento do Cartão de Cliente](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definir uma atividade

Uma entidade tem de ter, pelo menos, um atributo do tipo **Data** a ser incluído na linha cronológica. O controlo **Adicionar atividade** está desativado se não for encontrada nenhuma entidade.

1. Aceda a **Dados** > **Atividades**.

1. Selecione **Adicionar atividade** para iniciar a experiência guiada.

1. No passo **Dados de atividade**, introduza as seguintes informações:

   - **Nome da atividade**: o nome da sua atividade.
   - **Entidade de atividade**: a entidade que inclui os dados transacionais ou de atividade.
   - **Chave primária**: campo que identifica exclusivamente um registo. Não deve conter valores duplicados, valores vazios ou valores em falta.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configurar os dados de atividade com nome, entidade e chave primária.":::

1. Selecione **Seguinte**.

1. No passo **Relação**, selecione **Adicionar relação** para ligar os seus dados de atividade ao registo de cliente correspondente. Este passo visualiza a ligação entre entidades.  

   - **Chave externa de entidade**: campo estrangeiro na sua entidade de atividade que será utilizado para estabelecer uma relação com outra entidade.
   - **Nome da entidade de destino**: entidade de cliente de origem correspondente com a qual a sua entidade de atividade estará relacionada. Só pode relacionar-se com entidades de clientes de origem que são utilizadas no processo de unificação de dados.
   - **Nome de relação**: nome que identifica a relação entre as entidades. Se já existir uma relação entre esta entidade de atividade e a entidade de cliente de origem selecionada, o nome da relação é só de leitura.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definir a relação entre entidades.":::

   > [!TIP]
   > Em ambientes B2B, pode selecionar entre entidades de conta e outras entidades. Se selecionar uma entidade de conta, o caminho da relação é automaticamente definido. Para outras entidades, tem de definir o caminho de relação sobre uma ou mais entidades intermediárias até chegar a uma entidade de conta.

1. Selecione **Aplicar** para criar a relação.

1. Selecione **Seguinte**.

1. No passo **Unificação de atividades**, escolha o evento de atividade e a hora de início da sua atividade.
   - **Campos necessários**
      - **Atividade do evento**: campo que é o evento para esta atividade.
      - **Carimbo de data/hora**: campo que representa a hora de início da sua atividade.

   - **Campos opcionais**
      - **Detalhe adicional**: campo com informações relevantes para esta atividade.
      - **Ícone**: ícone que melhor representa este tipo de atividade.
      - **Endereço Web**: campo que contém um URL com informações sobre esta atividade. Por exemplo, o sistema transacional que fornece esta atividade. Este URL pode ser qualquer campo a partir da origem de dados ou pode ser construído como um novo campo usando uma transformação do Power Query. Os dados de URL serão armazenados na entidade de *Atividade Unificada*, que pode ser consumida a jusante utilizando [APIs](apis.md).

   - **Mostrar na linha cronológica**
      - Escolha se pretende mostrar esta atividade na vista de linha cronológica dos perfis dos clientes. Selecione **Sim** para mostrar a atividade na linha cronológica ou **Não** para ocultá-la.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especificar os dados de atividade do cliente numa entidade de Atividade Unificada.":::

1. Selecione **Seguinte** para escolher o tipo de atividade ou selecione **Terminar e rever** para guardar a atividade agora com o tipo de atividade definido como **Outro**.

1. No passo **Tipo de Atividade**, escolha o tipo de atividade e selecione opcionalmente se pretende mapear semântica alguns dos tipos de atividade para utilização noutras áreas do Customer Insights. Atualmente, os tipos de atividade *Comentários*, *Lealdade*, *SalesOrder*, *SalesOrderLine* e *Subscrição* suportam a semântica depois de concordar mapear os campos. Se um tipo de atividade não for relevante para a nova atividade, pode escolher *Outro* ou *Criar novo* para um tipo de atividade personalizada.

1. Selecione **Seguinte**.

1. No passo **Revisão**, verifique as suas seleções. Regresse a qualquer um dos passos anteriores e atualize as informações, se necessário.

1. Selecione **Guardar atividade** para aplicar as suas alterações e selecione **Concluído** para regressar a **Dados** > **Atividades**. A atividade criada é apresentada.

1. Depois de criar todas as suas atividades, selecione **Executar** para processá-las.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Gerir atividades existentes

Vá para **Dados** > **Atividades** para ver as suas atividades guardadas, a entidade de origem, o tipo de atividade e se foram incluídas na linha cronológica do cliente. Pode ordenar a lista de atividades por qualquer coluna ou utilizar a caixa de pesquisa para localizar a atividade que pretende gerir.

Selecione uma atividade para ver as ações disponíveis.

- **Editar** a atividade para alterar a sua configuração. A configuração é aberta no passo de revisão. Depois de alterar a configuração, selecione **Guardar atividade** e, em seguida, selecione **Executar** para processar as alterações.
- **Mudar o nome** da atividade. Selecione **Guardar** para aplicar as alterações.
- **Eliminar** a atividade. Para eliminar mais de uma atividade ao mesmo tempo, selecione as atividades e, em seguida, **Eliminar**. Confirme a eliminação.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ver linhas cronológicas de atividades nos perfis de clientes

1. Se selecionou **Mostrar na linha cronológica da atividade** na configuração da atividade, vá para **Clientes** e selecione o perfil de cliente para ver as atividades do cliente na secção **Linha cronológica da atividade**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Veja as atividades configuradas nos Perfis de Clientes.":::

1. Para filtrar as atividades na linha cronológica de atividade:

   - Selecione um ou mais ícones de atividade para refinar os seus resultados para incluir apenas os tipos selecionados.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtre as atividades por tipo utilizando os ícones.":::

   - Selecione **Filtro** para abrir um painel de filtros para configurar os filtros da linha cronológica. Filtre por *ActivityType* e/ou *Date*. Selecione **Aplicar**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilize o painel de filtros para configurar as condições do filtro.":::

1. Para remover os filtros, selecione **Limpar filtros** ou selecione **Filtrar** e desmarque a caixa de verificação do filtro.

> [!NOTE]
> Os filtros de atividades são removidos quando deixa o perfil do cliente. Tem de aplicá-los sempre que abrir um perfil de cliente.

[!INCLUDE [footer-include](includes/footer-banner.md)]

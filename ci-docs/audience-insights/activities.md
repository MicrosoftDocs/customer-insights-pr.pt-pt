---
title: Atividades do cliente
description: Defina as atividades dos clientes e veja-as numa linha cronológica nos perfis dos clientes.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c250efcd54ec126c0726b22a971cdedd89760d6b
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617983"
---
# <a name="customer-activities"></a>Atividades do cliente

Combine as atividades de clientes de [várias origens de dados](data-sources.md) no Dynamics 365 Customer Insights para criar uma linha cronológica que lista as atividades cronologicamente. Inclua a linha cronológica em aplicações Dynamics 365 com a solução de [suplemento do Cartão de Cliente](customer-card-add-in.md) ou num dashboard do Power BI.

## <a name="define-an-activity"></a>Definir uma atividade

As suas origens de dados podem incluir entidades com dados transacionais e de atividade a partir de várias origens de dados. Identifique estas entidades e selecione as atividades que pretende ver na linha cronológica do cliente. Escolha a entidade que inclui as atividades ou atividades de destino.

Uma entidade tem de ter, pelo menos, um atributo do tipo **Data** a ser incluído na linha cronológica do cliente e não é possível adicionar entidades sem campos de **Data**. O controlo **Adicionar atividade** está desativado se não for encontrada nenhuma entidade.

1. Em informações de audiência, aceda a **Dados** > **Atividades**.

1. Selecione **Adicionar atividade** para iniciar a experiência guiada para o processo de configuração da atividade.

1. No passo de **Dados de atividade**, defina os valores para os seguintes campos:

   - **Nome da atividade**: selecione um nome para a sua atividade.
   - **Entidade**: Selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Selecione o campo que identifica exclusivamente um registo. Não deve conter valores duplicados, valores vazios ou valores em falta.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configurar os dados de atividade com nome, entidade e chave primária.":::

1. Selecione **Seguinte** para avançar para o passo seguinte.

1. No passo **Relação**, configure os detalhes para ligar os dados da sua atividade ao respetivo registo de clientes. Este passo visualiza a ligação entre entidades.  

   - **Primeiro**: campo estrangeiro na sua entidade de atividade que será utilizado para estabelecer uma relação com outra entidade.
   - **Segundo**: entidade de cliente de origem correspondente com a qual a sua entidade de atividade estará em relacionamento. Só pode relacionar-se com entidades de clientes de origem que são utilizadas no processo de unificação de dados.
   - **Terceiro**: se já existir uma relação entre esta entidade de atividade e a entidade de cliente de origem selecionada, o nome da relação estará apenas em modo de leitura. Se não existir essa relação, uma nova relação será criada com o nome que fornecer nesta caixa.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definir a relação entre entidades.":::

   > [!TIP]
   > Em ambientes B2B, pode selecionar entre entidades de conta e outras entidades. Se selecionar uma entidade de conta, o caminho da relação é automaticamente definido. Para outras entidades, tem de definir o caminho de relação sobre uma ou mais entidades intermediárias até chegar a uma entidade de conta.

1. Selecione **Seguinte** para avançar para o passo seguinte. 

1. No passo **Unificação de atividades**, escolha o evento de atividade e a hora de início da sua atividade. 
   - **Campos necessários**
      - **Atividade do evento**: campo que é o evento para esta atividade.
      - **Carimbo de data/hora**: campo que representa a hora de início da sua atividade.

   - **Campos opcionais**
      - **Detalhe adicional**: campo com informações relevantes para esta atividade.
      - **Ícone**: ícone que melhor representa este tipo de atividade.
      - **Endereço Web**: campo que contém um URL com informações sobre esta atividade. Por exemplo, o sistema transacional que fornece esta atividade. Este URL pode ser qualquer campo da origem de dados, ou pode ser construído como um novo campo usando uma transformação Power Query. Os dados de URL serão armazenados na entidade de *Atividade Unificada*, que pode ser consumida a jusante utilizando [APIs](apis.md).

   - **Mostrar na linha cronológica**
      - Escolha se pretende mostrar esta atividade na vista de linha cronológica dos perfis dos clientes. Selecione **Sim** para mostrar a atividade na linha cronológica ou **Não** para ocultá-la.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especificar os dados de atividade do cliente numa entidade de Atividade Unificada.":::

1. Selecione **Seguinte** para avançar para o passo seguinte. Pode selecionar **Terminar e rever** para guardar a atividade agora com o tipo de atividade definido como **Outro**. 

1. No passo **Tipo de Atividade**, escolha o tipo de atividade e selecione opcionalmente se pretende mapear semântica alguns dos tipos de atividade para utilização noutras áreas do Customer Insights. Atualmente, os tipos de atividade *Comentários*, *Lealdade*, *SalesOrder*, *SalesOrderLine* e *Subscrição* podem ser semanticamente mapeados depois de concordar em mapear os campos. Se um tipo de atividade não for relevante para a nova atividade, pode escolher *Outro* ou *Criar novo* para um tipo de atividade personalizada.

1. Selecione **Seguinte** para avançar para o passo seguinte. 

1. No passo **Revisão**, verifique as suas seleções. Regresse a qualquer um dos passos anteriores e atualize as informações, se necessário.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Rever os campos especificados para uma atividade.":::
   
1. Selecione **Guardar atividade** para aplicar as suas alterações e selecione **Concluído** para regressar a **Dados** > **Atividades**. Aqui vê que atividades estão definidas para mostrar na linha cronológica. 

1. Na página **Atividades**, selecione **Executar** para processar a atividade. 

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.


## <a name="manage-existing-activities"></a>Gerir atividades existentes

Em **Dados** > **Atividades**, pode ver todas as suas atividades guardadas e geri-las. Cada atividade é representada por uma linha que também inclui detalhes sobre a origem, a entidade e o tipo de atividade.

As seguintes ações estão disponíveis quando seleciona uma atividade. 

- **Editar**: abre a configuração da atividade no passo de revisão. Pode alterar parte ou toda a configuração atual a partir deste passo. Depois de alterar a configuração, selecione **Guardar atividade** e, em seguida, selecione **Executar** para processar as alterações.

- **Mudar o nome**: abre um diálogo onde pode introduzir um nome diferente para a atividade selecionada. Selecione **Guardar** para aplicar as alterações.

- **Eliminar**: abre um diálogo para confirmar a eliminação da atividade selecionada. Também pode eliminar mais do que uma atividade ao mesmo tempo selecionando as atividades e, em seguida, selecionando o ícone de eliminação. Selecione **Eliminar** para confirmar a eliminação.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ver linhas cronológicas de atividades nos perfis de clientes

Depois de configurar as atividades do cliente, selecione **Mostrar na linha cronológica da atividade** na configuração da atividade para encontrar todas as atividades do seu cliente no perfil do cliente.

Para abrir a linha cronológica para um cliente, aceda a **Clientes** e escolha o perfil do cliente que pretende visualizar.

Se um cliente tiver participado numa atividade que tenha configurado, irá encontrá-la na secção **Linha cronológica da atividade**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Veja as atividades configuradas nos Perfis de Clientes.":::

Existem várias formas de filtrar as atividades na linha cronológica da atividade:

- Pode selecionar um ou muitos dos ícones de atividade para refinar os seus resultados apenas para incluir os tipos selecionados.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtre as atividades por tipo utilizando os ícones.":::

- Pode selecionar **Filtro** para abrir um painel de filtros para configurar os filtros da linha cronológica.

   1. Pode filtrar por *ActivityType* e *Date*
   1. Selecione **Aplicar** para utilizar os filtros na linha cronológica da atividade.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilize o painel de filtros para configurar as condições do filtro.":::

Para remover os filtros, selecione o **x** ao lado de cada filtro aplicado na linha cronológica ou selecione **Limpar filtros**.


> [!NOTE]
> Os filtros de atividades são removidos quando deixa o perfil do cliente. Tem de aplicá-los sempre que abrir um perfil do cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Atividades do cliente
description: Defina as atividades do cliente e veja-as na linha cronológica do cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667243"
---
# <a name="customer-activities"></a>Atividades do cliente

Combine as atividades do cliente de [várias origens de dados](data-sources.md) no Dynamics 365 Customer Insights para criar uma linha cronológica do cliente que lista as atividades por ordem cronológica. Pode incluir a linha cronológica nas aplicações do Customer Engagement no Dynamics 365 através do [suplemente do Cartão de Cliente](customer-card-add-in.md) ou num dashboard do Power BI.

## <a name="define-an-activity"></a>Definir uma atividade

As suas origens de dados incluem entidades com dados transacionais e de atividade a partir de várias origens de dados. Identifique estas entidades e selecione as atividades que pretende ver na linha cronológica do cliente. Escolha a entidade que inclui as atividades ou atividades de destino.

1. Em informações de audiência, aceda a **Dados** > **Atividades**.

1. Selecione **Adicionar atividade**.

   > [!NOTE]
   > Uma entidade tem de ter, pelo menos, um atributo do tipo **Data** a ser incluído na linha cronológica do cliente e não é possível adicionar entidades sem campos de **Data**. O controlo **Adicionar atividade** está desativado se não for encontrada nenhuma entidade.

1. No painel **Adicionar atividade**, defina os valores para os seguintes campos:

   - **Entidade**: Selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Selecione o campo que identifica exclusivamente um registo. Não deve conter valores duplicados, valores vazios ou valores em falta.
   - **Carimbo de data/hora**: Selecione o campo que representa a hora de início da atividade.
   - **Evento**: Selecione o campo que é o evento para a atividade.
   - **Endereço web**: Selecione o campo que representa um URL fornecendo informações adicionais sobre esta atividade. Por exemplo, o sistema transacional que fornece esta atividade. Este URL pode ser qualquer campo da origem de dados, ou pode ser construído como um novo campo usando uma transformação Power Query. Estes dados de URL serão armazenados na entidade de Atividade Unificada, que pode ser consumida a jusante usando APIs.
   - **Detalhes**: Opcionalmente, selecione o campo que é adicionado para obter mais detalhes.
   - **Ícone**: Opcionalmente, selecione o ícone que representa esta atividade.
   - **Tipo de Atividade**: Defina a referência do tipo de atividade ao Common Data Model que melhor descreve a definição semântica da atividade.

1. Na secção **Configurar relação**, configure os detalhes para ligar os seus dados de atividade ao seu cliente correspondente.

   > [!div class="mx-imgBorder"]
   > ![Definir A relação entre entidades](media/activities-entities-define.png "Definir a relação entre entidades")

    - **Campo de entidade de atividade**: selecione o campo na sua entidade de atividade que será utilizado para estabelecer uma relação com outra entidade.
    - **Entidade Cliente** : selecione a entidade Cliente de origem correspondente com a qual a sua entidade Atividade terá uma relação. Só poderá ter relação com as entidades Cliente de origem utilizadas no processo de unificação de dados.
    - **Campo Entidade cliente**: este campo mostra a chave primária da entidade Cliente de origem, conforme selecionada no processo de correspondência. Este campo de chave primária na entidade Cliente de origem é utilizado para estabelecer uma relação com a entidade Atividade.
    - **Nome** : se já existir uma relação entre esta entidade Atividade e a entidade Cliente de origem selecionada, o nome da relação estará em modo só de leitura. Se esta relação não existir, será criada uma nova relação com o nome aqui fornecido.

1. Selecione **Guardar** para aplicar as alterações.

1. Na página **Atividades**, selecione **Executar**.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="edit-an-activity"></a>Editar uma atividade

1. Em informações de audiência, aceda a **Dados** > **Atividades**.

2. Selecione a entidade Atividade que pretende editar e selecione **Editar**. Em alternativa, poderá passar com o cursor do rato sobre a linha e selecionar o ícone **Editar**.

3. Clique no ícone **Editar**.

4. No painel **Editar atividade**, atualize os valores e selecione **Guardar**.

5. Na página **Atividades**, selecione **Executar**.

## <a name="delete-an-activity"></a>Eliminar uma atividade

1. Em informações de audiência, aceda a **Dados** > **Atividades**.

2. Selecione a entidade Atividade que pretende remover e selecione **Eliminar**. Em alternativa, poderá passar com o cursor do rato sobre a linha e selecionar o ícone **Eliminar**. Além disso, poderá selecionar várias entidades Atividade a eliminar em simultâneo.
   > [!div class="mx-imgBorder"]
   > ![Editar ou eliminar a relação entre entidades](media/activities-entities-edit-delete.png "Editar ou eliminar a relação entre entidades")

3. Selecione o ícone **Eliminar**.

4. Confirme a eliminação.

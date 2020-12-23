---
title: Fundir entidades na unificação de dados
description: Fundir entidades para criar perfis unificados de clientes.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406645"
---
# <a name="merge-entities"></a>Unir entidades

A fase de intercalação é a última fase no processo de unificação de dados. Tem como objetivo reconciliar os dados em conflito. Os exemplos de dados em conflito poderão incluir um nome de cliente que se encontra em dois dos seus conjuntos de dados, mas que apresenta pequenas diferenças ("Grant Marshall" versus "Grant Marshal"), ou um número de telefone com que difere no formato (617-803-091X versus 617803091X). A intercalação destes pontos de dados em conflito é feita numa base atributo a atributo.

Depois de concluir a [fase de intercalação](match-entities.md), pode iniciar a fase de intercalação ao selecione o título **Intercalar** na página **Unificar**.

## <a name="review-system-recommendations"></a>Rever recomendações de sistema

Na página **Intercalar**, poderá optar escolher e excluir os atributos a unir na sua entidade de perfil de cliente unificada (o resultado do processo de configuração). Alguns atributos são intercalados automaticamente pelo sistema.

### <a name="view-merged-attributes"></a>Ver atributos intercalados

Para ver os atributos que estão incluídos num dos seus atributos intercalados automaticamente, selecione o atributo intercalado. Os dois atributos que compõem o atributo unido serão apresentados em duas novas linhas abaixo do atributo intercalado.

> [!div class="mx-imgBorder"]
> ![Selecionar o atributo intercalado](media/configure-data-merge-profile-attributes.png "Selecionar o atributo intercalado")

### <a name="separate-merged-attributes"></a>Atributos intercalados separados

Para separar ou intercalar qualquer um dos atributos intercalados automaticamente, localize o atributo na tabela **Atributos de perfil**.

1. Selecione o botão de elipse (...).
  
2. Na lista pendente, selecione **Separar campos**.

### <a name="remove-merged-attributes"></a>Remover atributos intercalados

Para excluir um atributo da entidade de perfil de cliente final, localize-o na tabela **Atributos de perfil**.

1. Selecione o botão de elipse (...).
  
2. Na lista pendente, selecione **Não unir**.

   O atributo é movido para a secção **Removido do registo de cliente**.

## <a name="manually-add-a-merged-attribute"></a>Adicionar manualmente um atributo intercalado

Para adicionar um atributo intercalado, vá para a página **Intercalar**.

1. Selecione **Adicionar atributo intercalado**.

2. Forneça um **Nome** para o identificar mais tarde na página **Intercalar**.

3. Opcionalmente, forneça um **Nome a apresentar** para aparecer na entidade Perfil de Cliente Unificado.

4. Configure **Selecionar atributos duplicados** para selecionar os atributos que pretende intercalar das entidades correspondidas. Também pode procurar atributos.

5. Defina **Classificar por importância** para dar prioridade a um atributo acima de outros. Por exemplo, se a entidade *WebAccountCSV* incluir os dados com maior precisão sobre o atributo *Nome Completos*, poderá dar prioridade a esta entidade em detrimento de *ContactCSV* ao selecionar *WebAccountCSV*. Como resultado, *WebAccountCSV* é movido para a primeira prioridade, enquanto *ContactCSV* é movido para a segunda prioridade ao solicitar valores para o atributo *Nome Completo*.

## <a name="run-your-merge"></a>Executar a intercalação

Quer intercale manualmente os atributos ou deixe que o sistema o faça, poderá sempre executar a intercalação. Selecione **Executar** na página **Intercalar** para iniciar o processo.

> [!div class="mx-imgBorder"]
> ![Guardar e Executar a intercalação de dados](media/configure-data-merge-save-run.png "Guardar e Executar a intercalação de dados")

Para efetuar alterações adicionais e executar novamente o passo, poderá cancelar uma união em curso. Selecione **A atualizar...** e selecione **Cancelar tarefa** no painel lateral apresentado.

Depois de o texto **A atualizar...** mudar para **Com êxito**, a união foi concluída e as contradições foram resolvidas nos seus dados, em conformidade com as políticas que definiu. Os atributos intercalados e não intercalados são incluídos na entidade de perfil unificada. Os atributos excluídos não são incluídos na entidade de perfil unificada.

Se não foi a primeira vez que executou uma intercalação com êxito, todos os processos de a jusante, incluindo o melhoramento, a segmentação e as medidas, serão novamente executados automaticamente. Depois de todos os processos a jusante serem novamente executados, os perfis de cliente refletem quaisquer alterações que tenha efetuado.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="next-step"></a>Passo Seguinte

Configure [atividades](activities.md), [melhoramento](enrichment-microsoft-graph.md) ou [relações](relationships.md) para obter mais informações sobre os seus clientes.

Se já tiver configurado atividades, enriquecimento ou relações, ou se tiver definido segmentos, estes serão processados automaticamente para utilizar os dados mais recentes do cliente.



---
title: Fundir entidades na unificação de dados
description: Fundir entidades para criar perfis unificados de clientes.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085590"
---
# <a name="merge-entities"></a>Unir entidades

A fase de intercalação é a última fase no processo de unificação de dados. Tem como objetivo reconciliar os dados em conflito. Os exemplos de dados em conflito poderão incluir um nome de cliente que se encontra em dois dos seus conjuntos de dados, mas que apresenta pequenas diferenças ("Grant Marshall" versus "Grant Marshal"), ou um número de telefone com que difere no formato (617-803-091X versus 617803091X). A intercalação destes pontos de dados em conflito é feita numa base atributo a atributo.

:::image type="content" source="media/merge-fields-page.png" alt-text="Unir página no processo de unificação de dados a mostrar tabela com campos unidos que definem o perfil do cliente unificado.":::

Depois de concluir a [fase de intercalação](match-entities.md), pode iniciar a fase de intercalação ao selecione o título **Intercalar** na página **Unificar**.

## <a name="review-system-recommendations"></a>Rever recomendações de sistema

Em **Dados** > **Unificar** > **Unir**, escolhe e exclui atributos para unir dentro da sua entidade de perfil de cliente unificado. O perfil de cliente unificado é o resultado do processo de unificação de dados. Alguns atributos são intercalados automaticamente pelo sistema.

Para ver os atributos incluídos num dos seus atributos automaticamente unidos, selecione o atributo unido no separador **Campos de cliente** da tabela. Os atributos que compõem o atributo unido apresentam duas novas linhas abaixo do atributo unido.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separar, mudar o nome, excluir e editar campos unidos

Pode alterar a forma como o sistema processa atributos unidos para gerar o perfil de cliente unificado. Selecione **Mostrar mais** e escolha o que pretende alterar.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opções no menu pendente Mostrar mais para gerir atributos unidos.":::

Para mais informações, consulte as secções seguintes.

## <a name="separate-merged-fields"></a>Separar campos unidos

Para separar campos unidos, encontre o atributo na tabela. Os campos separados mostram como pontos de dados individuais no perfil de cliente unificado. 

1. Selecione o campo unido.
  
1. Selecione **Mostrar mais** e escolha **Separar campos**.
 
1. Confirme a separação.

1. Selecione **Guardar** e **Executar** para processar as alterações.

## <a name="rename-merged-fields"></a>Renomear campos unidos

Altere o nome a apresentar dos atributos unidos. Não é possível alterar o nome da entidade de saída.

1. Selecione o campo unido.
  
1. Selecione **Mostrar mais** e escolha **Mudar o nome**.

1. Confirme o nome a apresentar alterado. 

1. Selecione **Guardar** e **Executar** para processar as alterações.

## <a name="exclude-merged-fields"></a>Excluir campos unidos

Excluir um atributo do perfil de cliente unificado. Se o campo for utilizado noutros processos, por exemplo num segmento, remova-o destes processos antes de o excluir do perfil do cliente. 

1. Selecione o campo unido.
  
1. Selecione **Mostrar mais** e escolha **Excluir**.

1. Confirme a exclusão.

1. Selecione **Guardar** e **Executar** para processar as alterações. 

Na página **Unir**, selecione **Campos excluídos** para ver a lista de todos os campos excluídos. Este painel permite-lhe adicionar novamente campos excluídos.

## <a name="manually-combine-fields"></a>Combinar campos manualmente

Especifique manualmente um atributo unido. 

1. Na página **Unir**, selecione **Combinar campos**.

1. Forneça um **Nome** e um **Nome de campo de saída**.

1. Escolha um campo a adicionar. Selecione **Adicionar campos** para combinar mais campos.

1. Confirme a exclusão.

1. Selecione **Guardar** e **Executar** para processar as alterações. 

## <a name="change-the-order-of-fields"></a>Alterar a ordem dos campos

Algumas entidades contêm mais detalhes do que outras. Se uma entidade incluir os dados mais recentes sobre um campo, pode priorizá-lo sobre outras entidades quando unir valores.

1. Selecione o campo unido.
  
1. Selecione **Mostrar mais** e escolha **Editar**.

1. No painel **Combinar campos**, selecione **Mover para cima/baixo** para definir a ordem ou arraste e largue-os na posição desejada.

1. Confirme a alteração.

1. Selecione **Guardar** e **Executar** para processar as alterações.

## <a name="run-your-merge"></a>Executar a intercalação

Quer intercale manualmente os atributos ou deixe que o sistema o faça, poderá sempre executar a intercalação. Selecione **Executar** na página **Intercalar** para iniciar o processo.

> [!div class="mx-imgBorder"]
> ![Guardar e Executar a intercalação de dados](media/configure-data-merge-save-run.png "Guardar e Executar a intercalação de dados")

Escolha **Executar apenas União** se pretender apenas ver a saída refletida na entidade de cliente unificado. Os processos a jusante serão atualizados conforme [definido na agenda de atualização](system.md#schedule-tab).

Escolha **Executar processos de União e a jusante** para atualizar o sistema com as suas alterações. Todos os processos, incluindo enriquecimento, segmentos e medidas serão executados novamente automaticamente. Depois de todos os processos a jusante estarem concluídos, os perfis de cliente refletem quaisquer alterações que tenha feito.

Para fazer mais alterações e voltar a executar o passo, pode cancelar uma união em curso. Selecione **A atualizar...** e selecione **Cancelar tarefa** no painel lateral apresentado.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="next-step"></a>Passo Seguinte

Configure [atividades](activities.md), [melhoramento](enrichment-hub.md) ou [relações](relationships.md) para obter mais informações sobre os seus clientes.

Se já configurou atividades, enriquecimento ou segmentos, estes serão processados automaticamente para utilizarem os dados mais recentes do cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

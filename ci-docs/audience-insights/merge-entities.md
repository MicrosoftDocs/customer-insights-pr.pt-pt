---
title: Fundir entidades na unificação de dados
description: Fundir entidades para criar perfis unificados de clientes.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: c218f9c1a1b7711ee48419470bf6c352450ffc0c
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732786"
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

1. Selecione um campo unido.
  
1. Selecione **Mostrar mais** e escolha **Excluir**.

1. Confirme a exclusão.

1. Selecione **Guardar** e **Executar** para processar as alterações. 

Na página **Unir**, selecione **Campos excluídos** para ver a lista de todos os campos excluídos. Este painel permite-lhe adicionar novamente campos excluídos.

## <a name="edit-a-merged-field"></a>Editar um campo unido

1.  Selecione um campo unido.

1.  Selecione **Mostrar mais** e escolha **Editar**.

1.  Especifique como combinar ou unir os campos a partir de uma de três opções:
    - **Importância**: identifica o valor vencedor com base na classificação de importância especificado para os campos participantes. É a opção de intercalação predefinida. Selecione **Mover para cima/para baixo** para definir a classificação de importância.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Opção de importância no diálogo de campos de união."::: 
    - **Mais recente**: identifica o valor vencedor com base na recência. Requer um campo de data ou numérico para cada entidade participante no âmbito dos campos de união para definir a recência.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Opção de recência no diálogo de campos de união.":::
    - **Menos recente**: identifica o valor vencedor com base na recência menor. Requer um campo de data ou numérico para cada entidade participante no âmbito dos campos de união para definir a recência.

1.  Pode adicionar mais campos para participar no processo de intercalação.

1.  Pode mudar o nome do campo unido.

1. Selecione **Concluído** para aplicar as alterações.

1. Selecione **Guardar** e **Executar** para processar as alterações. 

## <a name="manually-combine-fields"></a>Combinar campos manualmente

Especifique manualmente um atributo unido. 

1. Na página **Unir**, selecione **Combinar campos**.

1. Especifique a política vencedora de união no menu pendente **Combinar campos por**.

1. Escolha um campo a adicionar. Selecione **Adicionar campos** para combinar mais campos.

1. Forneça um **Nome** e um **Nome de campo de saída**.

1. Selecione **Concluído** para aplicar as alterações.

1. Selecione **Guardar** e **Executar** para processar as alterações. 

## <a name="change-the-order-of-fields"></a>Alterar a ordem dos campos

Algumas entidades contêm mais detalhes do que outras. Se uma entidade incluir os dados mais recentes sobre um campo, pode priorizá-lo sobre outras entidades quando unir valores.

1. Selecione o campo unido.
  
1. Selecione **Mostrar mais** e escolha **Editar**.

1. No painel **Combinar campos**, selecione **Mover para cima/baixo** para definir a ordem ou arraste e largue-os na posição desejada.

1. Confirme a alteração.

1. Selecione **Guardar** e **Executar** para processar as alterações.

## <a name="configure-customer-id-generation"></a>Configurar a geração de ID de Cliente 

Depois de configurar campos de união, pode definir como gerar valores CustomerId, os identificadores de perfil de cliente exclusivos. O passo de união no processo de unificação de dados gera o identificador de perfil de cliente exclusivo. O identificador é o CustomerId na entidade *Cliente* que resulta do processo de unificação de dados. 

O CustomerId na entidade Cliente baseia-se num hash do primeiro valor das chaves primárias vencedoras não nulas. Estas chaves provêm das entidades utilizadas na fase de correspondência e união e são influenciadas pela ordem da correspondência. Assim, o CustomerID gerado pode mudar quando um valor de chave primária muda na entidade primária da ordem de correspondência. Assim, o valor da chave primária pode nem sempre representar o mesmo cliente.

Configurar um ID de cliente estável permite-lhe evitar esse comportamento.

**Configurar um ID de cliente exclusivo**

1. Aceda a **Unificar** > **Unir**.

1. Selecione o separador **Chaves**. 

1. Passe o cursor sobre a linha **CustomerId** e selecione a opção **Configurar**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controlo para personalizar a geração de ID.":::

1. Selecione até cinco campos que incluirão um ID exclusivo do cliente e são mais estáveis. Os registos que não correspondem à sua configuração utilizam um ID configurado pelo sistema.  

1. Selecione **Concluído** e execute o processo de união para aplicar as suas alterações.

## <a name="group-profiles-into-households-or-clusters"></a>Agrupar perfis em agregados familiares ou clusters

Como parte do processo de configuração da geração de perfis de clientes, pode definir regras para agrupar perfis relacionados num cluster. Existem atualmente dois tipos de clusters disponíveis – agregado familiar e clusters personalizados. O sistema escolhe automaticamente um agregado familiar com regras predefinidas se a entidade *Cliente* contiver os campos semânticos *Person.LastName* e *Location.Address*. Também pode criar um cluster com as suas próprias regras e condições, semelhantes às [regras de correspondência](match-entities.md#define-rules-for-match-pairs).

**Definir um agregado familiar ou um cluster**

1. Aceda a **Unificar** > **Unir**.

1. No separador **Intercalar**, selecione **Avançado** > **Criar cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Controle para criar um novo cluster.":::

1. Escolha entre um **Agregado familiar** ou um cluster **Personalizado**. Se os campos semânticos *Person.LastName* e *Location.Address* existirem na entidade *Cliente*, o agregado familiar é automaticamente selecionado.

1. Forneça um nome ao cluster e selecione **Concluído**.

1. Selecione o separador **Clusters** para encontrar o cluster que criou.

1. Especifique as regras e as condições para definir o seu cluster.

1. Selecione **Executar** para executar o processo de intercalação e criar o cluster.

Após a execução do processo de intercalação, os identificadores do cluster são adicionados como novos campos à entidade *Cliente*.

## <a name="run-your-merge"></a>Executar a intercalação

Quer intercale manualmente os atributos ou deixe que o sistema o faça, poderá sempre executar a intercalação. Selecione **Executar** na página **Intercalar** para iniciar o processo.

> [!div class="mx-imgBorder"]
> ![Guardar e Executar a união de dados.](media/configure-data-merge-save-run.png "Guardar e Executar a intercalação de dados")

Escolha **Executar apenas União** se pretender apenas ver a saída refletida na entidade de cliente unificado. Os processos a jusante serão atualizados conforme [definido na agenda de atualização](system.md#schedule-tab).

Escolha **Executar processos de União e a jusante** para atualizar o sistema com as suas alterações. Todos os processos, incluindo enriquecimento, segmentos e medidas serão executados novamente automaticamente. Depois de todos os processos a jusante estarem concluídos, os perfis de cliente refletem quaisquer alterações que tenha feito.

Para fazer mais alterações e voltar a executar o passo, pode cancelar uma união em curso. Selecione **A atualizar...** e selecione **Cancelar tarefa** no painel lateral apresentado.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Caminho de desagregação para chegar aos detalhes do processo a partir da ligação do estado da tarefa.":::

## <a name="next-step"></a>Passo Seguinte

Configure [atividades](activities.md), [melhoramento](enrichment-hub.md) ou [relações](relationships.md) para obter mais informações sobre os seus clientes.

Se já configurou atividades, enriquecimento ou segmentos, estes serão processados automaticamente para utilizarem os dados mais recentes do cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

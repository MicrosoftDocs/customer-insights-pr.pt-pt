---
title: Unificar campos de clientes para unificação de dados
description: Fundir entidades para criar perfis unificados de clientes.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081626"
---
# <a name="unify-customer-fields-for-data-unification"></a>Unificar campos de clientes para unificação de dados

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Neste passo do processo de unificação, escolha e exclua atributos para unir na entidade do seu perfil unificado. Por exemplo, se três entidades tinham dados de e-mail, poderá querer manter os três campos de e-mail separados ou uni-los num único campo de e-mail para o perfil unificado. Alguns atributos são combinados automaticamente pelo sistema. Pode criar IDs de cliente estáveis e exclusivos e agrupar perfis relacionados num cluster.

:::image type="content" source="media/m3_unify.png" alt-text="Unir página no processo de unificação de dados a mostrar tabela com campos unidos que definem o perfil do cliente unificado.":::

## <a name="review-and-update-the-customer-fields"></a>Rever e atualizar os campos de cliente

1. Reveja a lista de campos que serão unificados no separador **Campos de cliente** na tabela. Efetue alterações aqui, se aplicável.

   1. Para quaisquer campos combinados, pode:
      - [Editar](#edit-a-merged-field)
      - [Mudar o nome](#rename-fields)
      - [Separar](#separate-merged-fields)
      - [Excluir](#exclude-fields)
      - [Mover para cima ou para baixo](#change-the-order-of-fields)

   1. Para quaisquer campos exclusivos, pode:
      - [Combinar campos](#combine-fields-manually)
      - [Combinar um grupo de campos](#combine-a-group-of-fields)
      - [Mudar o nome](#rename-fields)
      - [Excluir](#exclude-fields)
      - [Mover para cima ou para baixo](#change-the-order-of-fields)

1. Opcionalmente, [gere a configuração de ID do cliente](#configure-customer-id-generation).

1. Opcionalmente, [agrupe perfis em agregados familiares ou clusters](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Passo seguinte: Rever a unificação](review-unification.md)

### <a name="edit-a-merged-field"></a>Editar um campo unido

1. Selecione um campo unido e escolha **Editar**. O painel Combinar campos é apresentado.

1. Especifique como combinar ou unir os campos a partir de uma de três opções:
    - **Importância**: identifica o valor vencedor com base na classificação de importância especificado para os campos participantes. É a opção de intercalação predefinida. Selecione **Mover para cima/para baixo** para definir a classificação de importância.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Opção de importância no diálogo de campos de união.":::

    - **Mais recente**: identifica o valor vencedor com base na recência. Requer um campo de data ou numérico para cada entidade participante no âmbito dos campos de união para definir a recência.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Opção de recência no diálogo de campos de união.":::

    - **Menos recente**: identifica o valor vencedor com base na recência menor. Requer um campo de data ou numérico para cada entidade participante no âmbito dos campos de união para definir a recência.

1. Pode adicionar mais campos para participar no processo de intercalação.

1. Pode mudar o nome do campo unido.

1. Selecione **Concluído** para aplicar as alterações.

### <a name="rename-fields"></a>Renomear campos

Altere o nome a apresentar de campos separados ou unidos. Não é possível alterar o nome da entidade de saída.

1. Selecione o campo e escolha **Mudar o no me**.

1. Introduza o novo nome a apresentar.

1. Selecionar **Concluído**.

### <a name="separate-merged-fields"></a>Separar campos unidos

Para separar campos unidos, encontre o atributo na tabela. Os campos separados mostram como pontos de dados individuais no perfil de cliente unificado.

1. Selecione o campo unido e escolha **Campos separados**.

1. Confirme a separação.

### <a name="exclude-fields"></a>Excluir campos

Exclua um campo unidos ou separado do unified customer profile. Se o campo for utilizado noutros processos, por exemplo num segmento, remova-o destes processos antes de o excluir do perfil do cliente.

1. Selecione um campo unido e escolha **Excluir**.

1. Confirme a exclusão.

Para ver a lista de todos os campos excluídos, selecione **Campos excluídos**. Se for necessário, pode voltar a adicionar o campo excluído.

### <a name="change-the-order-of-fields"></a>Alterar a ordem dos campos

Algumas entidades contêm mais detalhes do que outras. Se uma entidade incluir os dados mais recentes sobre um campo, pode priorizá-lo sobre outras entidades quando unir valores.

1. Selecione o campo.
  
1. Escolha **Mover para cima/para baixo** para definir a ordem ou arraste e largue-os na posição pretendida.

### <a name="combine-fields-manually"></a>Combinar campos manualmente

Combine campos separados para criar um atributo unido.

1. Selecione **Combinar** > **Campos**. O painel Combinar campos é apresentado.

1. Especifique a política vencedora de união no menu pendente **Combinar campos por**.

1. Selecione **Adicionar campo** para combinar mais campos.

1. Forneça um **Nome** e um **Nome de campo de saída**.

1. Selecione **Concluído** para aplicar as alterações.

### <a name="combine-a-group-of-fields"></a>Combinar um grupo de campos

Trate um grupo de campos como uma única unidade. Por exemplo, se os nossos registos contêm os campos Endereço1, Endereço2, Cidade, Estado e Código Postal, não queremos unir o Endereço2 de outro registo, pensando que isso tornaria os nossos dados mais completos.

1. Selecione **Combinar** > **Grupo de campos**.

1. Especifique a política de unir vencedor no menu pendente **Classificar grupos por**.

1. Selecione **Adicionar** e escolha se pretende adicionar mais campos ou grupos aos campos.

1. Forneça um **Nome** e um **Nome de saída** para cada campo combinado.

1. Indique um **Nome** para o grupo de campos.

1. Selecione **Concluído** para aplicar as alterações.

## <a name="configure-customer-id-generation"></a>Configurar a geração de ID de cliente

Defina como gerar valores de ID de cliente, os identificadores de perfil de cliente exclusivos. O passo de unificação de campos no processo de unificação de dados gera o identificador de perfil de cliente exclusivo. O identificador é o *CustomerId* na entidade *Cliente* que resulta do processo de unificação de dados.

O *CustomerId* baseia-se num hash do primeiro valor das chaves primárias vencedoras não nulas. Estas chaves são fornecidas pelas entidades utilizadas na unificação de dados e são influenciadas pela ordem de correspondência Assim, o ID de cliente gerado pode ser alterado quando um valor de chave primária é alterado na entidade principal da ordem de correspondência. O valor da chave primária pode nem sempre representar o mesmo cliente.

Configurar um ID de cliente estável permite-lhe evitar esse comportamento.

1. Selecione o separador **Chaves**.

1. Passe o rato sobre a linha na **CustomerId** e selecione **Configurar**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controlo para personalizar a geração de ID.":::

1. Selecione até cinco campos que incluirão um ID exclusivo do cliente e são mais estáveis. Os registos que não correspondem à sua configuração utilizam um ID configurado pelo sistema.  

1. Selecionar **Concluído**.

## <a name="group-profiles-into-households-or-clusters"></a>Agrupar perfis em agregados familiares ou clusters

É possível definir regras para agrupar perfis relacionados num cluster. Existem atualmente dois tipos de clusters disponíveis – agregado familiar e clusters personalizados. O sistema escolhe automaticamente um agregado familiar com regras predefinidas se a entidade *Cliente* contiver os campos semânticos *Person.LastName* e *Location.Address*. Também pode criar um cluster com as suas próprias regras e condições, semelhantes às [regras de correspondência](match-entities.md#define-rules-for-match-pairs).

1. Selecionar **Avançadas** > **Criar cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Controle para criar um novo cluster.":::

1. Escolha entre um **Agregado familiar** ou um cluster **Personalizado**. Se os campos semânticos *Person.LastName* e *Location.Address* existirem na entidade *Cliente*, o agregado familiar é automaticamente selecionado.

1. Forneça um nome ao cluster e selecione **Concluído**.

1. Selecione o separador **Clusters** para encontrar o cluster que criou.

1. Especifique as regras e as condições para definir o seu cluster.

1. Selecionar **Concluído**. O cluster é criado quando o processo de unificação é concluído. Os identificadores do cluster são adicionados como novos campos à entidade *Cliente*.

> [!div class="nextstepaction"]
> [Passo seguinte: Rever a unificação](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]

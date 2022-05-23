---
title: Selecione campos de origem para unificação de dados
description: O primeiro passo no processo de unificação é selecionar entidades, atributos, chaves primárias e tipos de semântica para mapear dados para o unified customer profile.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741009"
---
# <a name="select-source-fields-for-data-unification"></a>Selecione campos de origem para unificação de dados

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

O primeiro passo na unificação é selecionar as entidades e os campos nos seus conjuntos de dados que pretende unificar. Selecione entidades que contenham detalhes relacionados com os clientes, tais como nome, endereço, número de telefone e e-mail. Pode selecionar uma ou mais entidades.

## <a name="select-entities-and-fields"></a>Selecionar entidades e campos

1. Vá para **Dados** > **Unificar**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captura de ecrã da página de destino de unificação para a primeira experiência de execução com Começar realçado.":::

1. Selecione **Introdução**.

1. Na página **Campos de origem**, selecione **Selecionar entidades e campos**. O painel **Selecionar entidades e campos** é apresentado.

1. Selecione pelo menos uma entidade.

1. Para cada entidade selecionada, identifique os campos que pretende utilizar para corresponder aos registos de clientes e os campos a incluir no perfil unificado. Estes campos são denominados *Atributos*. Pode selecionar os atributos necessários individualmente a partir de uma entidade ou incluir todos os atributos de uma entidade, selecionando a caixa de verificação ao nível da entidade. Pode pesquisar palavras-chave em todos os atributos e entidades para selecionar os atributos necessários que pretende mapear.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captura de ecrã de entidades e atributos selecionados.":::

   Neste exemplo, estamos a adicionar as entidades **Contacts** e **CustomerLoyalty**. Ao escolher estas entidades, pode obter informações sobre quais dos clientes de negócios online são membros do programa de fidelização.

1. Selecione **Aplicar** para confirmar as suas seleções. As entidades e atributos selecionados são apresentados.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selecionar chave primária e tipo semântico para atributos

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captura de ecrã de entidades selecionadas com chave primária não selecionada." lightbox="media/m3_select_primary.png":::

Para cada entidade, execute os seguintes passos.

1. Escolha a **Chave primária**. A chave primária é um atributo exclusivo da entidade. Para que um atributo seja uma chave primária válida, não deve incluir valores duplicados, valores em falta ou valores nulos. Os atributos de cadeia, número inteiro e tipo de dados GUID são suportados como chaves primárias.

1. Para utilizar modelos de IA para soluções predição de semântica, poupe tempo e melhore a precisão, certifique-se de que o **mapeamento inteligente** está ativado. O mapeamento inteligente destaca a recomendação de semântica baseada em IA no campo **Tipo**. Pode substituir a seleção sugerida escolhendo qualquer tipo de semântica a partir da lista de opções disponível.

1. Para cada atributo, escolha o **Tipo** de semântica que melhor descreve esse atributo, como o nome, a cidade ou o endereço de e-mail.

   > [!NOTE]
   > Um campo deve mapear para o tipo de semântica *Person.FullName* para povoar o nome do cliente no cartão de cliente. Caso contrário, os cartões do cliente serão apresentados sem nome.

   1. Para alterar um tipo de atributo identificado pelo sistema, selecione outro tipo. Se o tipo não existir, crie um tipo de semântica personalizado ao selecionar o campo **Tipo** para o atributo e introduzindo o nome do tipo de semântica personalizada.

   1. Para adicionar um atributo que contém um URL a imagens ou logótipos de perfil disponíveis ao público, selecione a entidade e o campo que contém o URL. No campo **Tipo**, introduz o seguinte:
      - Para uma pessoa: Person.ProfileImage
      - Para uma organização: Organization.LogoImage

   1. Para um atributo de nome da conta, introduza "Organization.Name" no campo **Tipo**.

1. Reveja os atributos em que um tipo de semântica é identificado automaticamente. Estes atributos estão listados em **Rever campos mapeados**. Só é possível combinar atributos com o mesmo tipo no passo **Campos de cliente unificados**. Os tipos semântica são utilizados para sugerir informações automaticamente. Certifique-se de que os tipos escolhidos são consistentes em todas as entidades selecionadas.

1. Para atributos que não sejam mapeados automaticamente para um tipo de semântica, selecione um campo tipo de semântica, insira o seu nome personalizado do tipo de atributo ou deixe-o não mapeado. Estes atributos estão listados em **Definir os dados nos campos não mapeados**.

1. Depois de concluir os passos para cada entidade, selecione **Guardar campos de origem**.

1. Selecione **Seguinte**.

> [!div class="nextstepaction"]
> [Passo seguinte: Remover duplicados](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]

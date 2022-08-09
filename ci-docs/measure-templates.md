---
title: Criar medidas a partir de modelos
description: Defina medidas, utilizando modelos para casos de utilização habituais.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170787"
---
# <a name="create-measures-from-templates"></a>Criar medidas a partir de modelos

Utilizar modelos predefinidos de [medidas](measures.md) utilizadas frequentemente para criá-las. Os modelos são criados a partir de dados mapeados da entidade de *Atividade Unificada*. Por isso, certifique-se de que configurou [atividades de cliente](activities.md) antes de criar uma medida a partir de um modelo.

Os modelos de medidas só são suportados em ambientes para **clientes individuais**. Para criar medidas personalizadas ou criar medidas para B2B, consulte [Utilizar o construtor de medidas](measure-builder.md).

Modelos de medidas disponíveis:
- Valor médio da transação (ATV)
- Valor total das transações
- Receita média diária
- Receita média mensal
- Receita média anual
- Contagem de transações
- Pontos de fidelização ganhos
- Pontos de fidelização resgatados
- Saldo de pontos de fidelização
- Período de tempo ativo do cliente
- Duração da adesão à fidelidade
- Tempo desde a última compra

## <a name="build-a-new-measure-using-a-template"></a>Criar uma nova medida utilizando um modelo

1. Va a **Medidas**.

1. Selecione **Novo** e, em seguida, selecione **Escolher um modelo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de ecrã do menu pendente ao criar uma nova medida com destaque no modelo.":::

1. Encontre o modelo que se adequa à sua necessidade e selecione **Escolher modelo**.

1. Reveja os dados necessários e selecione **Começar** se tiver todos os dados preparados.

1. Selecione **Editar detalhes** junto de Nome da medida. Forneça um nome para a medida. Opcionalmente, adicione [etiquetas](work-with-tags-columns.md#manage-tags) à medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Caixa de diálogo Editar detalhes.":::

1. Selecionar **Concluído**.

1. Na secção **Definir período de tempo**, defina o período de tempo dos dados. Escolha se pretende que a nova medida cubra todo o conjunto de dados selecionando **Sempre** ou se pretende que a medida se concentre num **Período de tempo específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de ecrã a mostrar a secção do período de tempo ao configurar uma medida a partir de um modelo.":::

1. Na secção seguinte, selecione **Adicionar dados** para escolher as atividades e mapear os dados correspondentes da sua entidade *Atividade Unificada*.

    1. Passo 1 de 2: sob **Tipo de atividade**, escolha o tipo de entidade que pretende utilizar. Para **Atividades**, selecione as entidades que pretende mapear e, em seguida, selecione **Seguinte**.
    1. Passo 2 de 2: escolha o atributo da entidade *Atividade Unificada* para o componente exigido pela fórmula. Por exemplo, para o valor de transação Médio, é o atributo que representa o valor da Transação. Para **Carimbo data/hora da atividade**, escolha o atributo da entidade *Atividade Unificada* que representa a data e a hora da atividade.
    1. Selecione **Guardar**.

    Quando o mapeamento de dados for bem-sucedido, o estado mostra **Concluído** e o nome das atividades e atributos mapeados é apresentado.

1. Selecione **Executar** para calcular os resultados da medida. Selecione **Guardar rascunho** se pretende manter a configuração atual e executar a medida mais tarde. É apresentada a página **Medidas**.

## <a name="next-step"></a>Próximo passo

Utilize as medidas existentes para criar [um segmento de cliente](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

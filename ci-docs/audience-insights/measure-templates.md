---
title: Criar medidas a partir de modelos
description: Defina medidas, utilizando modelos para casos de utilização habituais.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359933"
---
# <a name="use-a-template-to-build-a-measure"></a>Utilize um modelo para criar uma medida

Pode utilizar modelos predefinidos de [medidas](measures.md) utilizadas frequentemente para criá-las. Descrições detalhadas dos modelos e uma experiência guiada ajudam-no com a criação de medidas eficientes. Os modelos são criados a partir de dados mapeados da entidade de *Atividade Unificada*. Por isso, certifique-se de que configurou [atividades de cliente](activities.md) antes de criar uma medida a partir de um modelo.

Para criar medidas personalizadas, consulte [Utilizar o construtor de medidas para criar medidas de raiz](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Modelos de medidas disponíveis: 
- Valor médio da transação (ATV)
- Valor total das transações
- Receita média diária
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

1. No painel **Editar nome**, defina o nome da sua medida e a entidade de saída. 

1. Selecione **Concluído**.

1. Na secção **Definir período de tempo**, defina o período de tempo dos dados a utilizar. Escolha se pretende que a nova medida cubra todo o conjunto de dados selecionando **Sempre** ou se pretende que a medida se concentre num **Período de tempo específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de ecrã a mostrar a secção do período de tempo ao configurar uma medida a partir de um modelo.":::

1. Na secção seguinte, selecione **Adicionar dados** para escolher as atividades e mapear os dados correspondentes da sua entidade *Atividade Unificada*.

    1. Passo 1 de 2: sob **Tipo de atividade**, escolha o tipo de entidade que pretende utilizar. Para **Atividades**, selecione as entidades que pretende mapear.
    1. Passo 2 de 2: escolha o atributo da entidade *Atividade Unificada* para o componente exigido pela fórmula. Por exemplo, para o valor de transação Médio, é o atributo que representa o valor da Transação. Para **Carimbo data/hora da atividade**, escolha o atributo da entidade Atividade Unificada que representa a data e a hora da atividade.
   
1. Quando o mapeamento de dados for bem sucedido, pode ver o estado como **Concluído** e o nome das atividades e atributos mapeados.

1. Agora pode selecionar **Executar** para calcular os resultados da medida. Para refiná-la mais tarde, selecione **Guardar rascunho**.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Esta funcionalidade apenas está disponível para medidas criadas em ambientes com clientes individuais como a audiência alvo principal.

---
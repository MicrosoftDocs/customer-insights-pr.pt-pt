---
title: Ver e criar métricas
description: Como criar, editar e eliminar métricas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034283"
---
# <a name="view-and-create-metrics"></a>Ver e criar métricas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

As métricas ajudam a entender o comportamento dos seus visitantes. Agregam propriedades de eventos e medem estatísticas e o desempenho das suas propriedades Web.  

Suponha que está a decorrer uma promoção de marketing no seu site. Pode usar métricas para monitorizar o número de visitantes ou utilizadores exclusivos que vieram ao seu site durante a promoção. Analisar métricas ajuda-o a entender melhor a audiência do seu site. Combinar métricas com [dimensões](dimensions.md) num [relatório personalizado](custom-reports.md) permite medir o comportamento para entender os seus utilizadores. Por exemplo, pode separar os visitantes em categorias novas e de regresso para identificar as diferenças de interesse e intenção entre os grupos.

## <a name="view-metrics"></a>Ver métricas

As informações de cativação incluem agregações utilizadas com frequência de propriedades de eventos como métricas do sistema: 

- Visitantes
- Visitas
- Visualizações da página
- Cliques

Estas métricas do sistema baseiam-se nas propriedades de eventos existentes em eventos base.

1. Aceda a **Dados** no painel de navegação esquerdo. 
1. Selecione o separador **Métricas** para ver uma lista de todas as métricas na área de trabalho. 
   > [!NOTE]
   > As métricas geradas pelo sistema são apenas de leitura. Não pode alterá-las ou eliminá-las. Só é possível criar e editar métricas personalizadas.

## <a name="create-a-metric"></a>Criar uma métrica

Os admins de ambiente e da área de trabalho podem criar métricas. As propriedades de eventos têm de ser enviadas para a área de trabalho antes de criar uma métrica. Pode criar métricas com base em propriedades de eventos que são enviadas por eventos base ou usar o SDK Web para [enviar propriedades de eventos personalizadas](advanced-SDK-implementation.md).

1. Aceda a **Dados** > **Métricas**.
1. Selecione **Nova métrica**.

   :::image type="content" source="media/new-metric.png" alt-text="Adicionar uma métrica a um evento.":::

1. Para o formato, selecione o tipo de dados **Número Inteiro** ou **Duplo**. Número inteiro é um número completo. Para Duplo, pode escolher entre uma e três casas decimais.
1. No painel **Biblioteca de recursos**, encontre a propriedade do evento para basear a métrica.
1. Selecione o **sinal de adição (+)** junto da propriedade para usá-lo na fórmula. Só pode criar uma fórmula baseada em uma propriedade. 
1. Escolha uma das seguintes funções de agregação. 

   - Soma: o total aritmético de todos os valores 
   - Média: a média de todos os valores
   - Contagem: o número total de valores
   - Contagem de valores exclusivos: o número total de valores exclusivos

   Depois de definir a métrica, vê uma pré-visualização de atividade da métrica durante a última hora.

1. Selecione **Guardar**. 
1. Introduza um nome para a métrica e selecione **Guardar**.

Pode levar até um minuto para a métrica antes de a poder usar para [criar relatórios personalizados](custom-reports.md).

## <a name="edit-a-metric"></a>Editar uma métrica

1. Aceda a **Dados** > **Métricas**.
1. Selecione a métrica na lista.
1. Alterar a definição da métrica
1. Selecione **Guardar**.

## <a name="change-the-name-of-a-metric"></a>Alterar o nome de uma métrica

1. Aceda a **Dados** > **Métricas**.
1. Selecione **Mais [...]** para uma métrica e escolha o **Editar nome**.
1. Altere o nome. 
1. Selecione **Mudar nome**.

## <a name="delete-a-metric"></a>Eliminar uma métrica

1. Aceda a **Dados** > **Métricas**.
1. Selecione **Mais [...]** para uma métrica e escolha **Eliminar**.

   :::image type="content" source="media/delete-metric.png" alt-text="Eliminar uma métrica de um evento.":::

1. Selecione **Eliminar** para confirmar a eliminação.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Criar segmentos simples com segmentos rápidos
description: Crie segmentos de clientes simples para agrupá-los com base em vários atributos.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171141"
---
# <a name="create-simple-segments-with-quick-segments"></a>Criar segmentos simples com segmentos rápidos

Segmentos rápidos permitem criar segmentos simples com um único operador rapidamente para informações mais rápidas. Os segmentos rápidos só são suportados em ambientes para **clientes individuais**.

## <a name="create-a-new-segment-with-quick-segments"></a>Criar um novo segmento com segmentos rápidos

1. Aceda a **Segmentos**.

1. Selecione **Novo** > **Criar a partir de**.
   - Selecione a opção **Perfis** para criar um segmento baseado na entidade de *cliente unificado*.
   - Selecione a opção **Medidas** para criar um segmento em torno das medidas que criou anteriormente.
   - Selecione a opção **Inteligência** para criar um segmento à volta de uma das entidades de saída geradas com as capacidades **Predições** ou **Modelos Personalizados**.

1. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo na lista pendente **Campo**. Com base na sua seleção, o sistema fornece valores diferentes.
   - Para os campos categóricos, são apresentadas as 10 principais contagens de cliente. Escolha um **Valor** e selecione **Rever**.
   - Para um atributo numérico, o sistema mostra o valor do atributo que se situa no percentil de cada cliente. Escolha um **Operador** e um **Valor** e, em seguida, selecione **Rever**.

1. O sistema fornece um **Tamanho de segmento estimado**. Escolha se pretende gerar o segmento que definiu ou regresse para escolher um campo diferente.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nome e estimativa para um segmento rápido.":::

1. Forneça um **Nome** e **Nome de entidade de saída** para o seu segmento. Opcionalmente, adicione [etiquetas](work-with-tags-columns.md#manage-tags).

1. Selecione **Guardar** para criar o segmento. A página **Segmentos** é apresentada.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Próximos passos

[Exporte um segmento](export-destinations.md) e explore a [integração do Cartão de Cliente](customer-card-add-in.md) para utilizar segmentos noutras aplicações.

[!INCLUDE [footer-include](includes/footer-banner.md)]

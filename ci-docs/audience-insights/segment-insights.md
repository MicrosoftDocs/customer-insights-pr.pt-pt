---
title: Informações de segmentos para segmentos existentes
description: Obter informações sobre segmentos existentes para ver diferenças e pontos em comum.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306088"
---
# <a name="segment-insights-preview"></a>Informações de segmentos (pré-visualização)

Descubra informações adicionais e informações sobre os segmentos existentes. Descubra o que diferencia dois segmentos ou o que têm em comum.

## <a name="segment-overlap"></a>Sobreposição de segmentos

A análise da sobreposição de segmentos mostra quantos e quais os clientes comuns a dois ou mais segmentos. Por exemplo, como um segmento de clientes frequentes se sobrepõe a um segmento que contém clientes que estão satisfeitos com o seu serviço ou produto.
Também pode analisar como a sobreposição muda para atributos específicos.

### <a name="run-an-overlap-analysis"></a>Executar uma análise de sobreposição

1. Vá a **Segmentos** e selecione o separador **Informações (pré-visualização)**.

1. Selecione **Novo** e escolha a opção **Sobreposição** no painel **Escolher Tipo de Informações**.

1. Escolha os segmentos de interesse e selecione **Seguinte**.

1. Opcionalmente, escolha um ou mais campos de interesse para analisar sobreposições para cada valor de campo possível e selecione **Seguinte**.

1. Forneça um nome para a sua análise de sobreposição, um nome a apresentar opcional e uma descrição.

1. Selecione **Guardar** para iniciar a análise. A análise de sobreposição está pronta quando o estado muda de Em Atualização para Bem Sucedida.

### <a name="view-and-optimize-an-overlap-analysis"></a>Ver e otimizar uma análise de sobreposição

Após completar a análise, encontre detalhes sobre esta informação em **Segmentos** > **Informações (pré-visualização)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalhes de informações de sobreposição de segmentos":::

Selecione uma informação para ver os resultados da análise:

- O número de membros que se sobrepõem aos segmentos selecionados para análise.
- O número de membros incluídos num dos segmentos, mas não nos restantes segmentos.
- Se selecionar campos enquanto configura a análise de sobreposição, irá encontrá-los nos separadores correspondentes. Pode utilizar a lista pendente de filtros para selecionar qualquer nível de atributo de interesse e a tabela na parte inferior mostrará os dados correspondentes.

## <a name="segment-differentiators"></a>Diferenciadores de segmentos

Os diferenciadores de segmento ajudam-no a descobrir o que diferencia um segmento do resto dos seus clientes ou de outro segmento. Basta selecionar um segmento e o sistema identificará atributos de perfil e medidas que distinguem o segmento selecionado.

### <a name="run-a-differentiator-analysis"></a>Executar uma análise diferenciadora

1. Vá a **Segmentos** e selecione o separador **Informações (pré-visualização)**.

1. Selecione **Novo** e escolha a opção **Sobreposição** no painel **Escolher Tipo de Informações**.

1. Escolha o segmento que pretende analisar como **Segmento primário** e selecione **Seguinte**.

1. Escolha **Todos os clientes** ou um **Segmento secundário** para comparar o seu segmento primário com e selecione **Seguinte**.

1. Opcionalmente, escolha um ou mais campos de interesse para focar a análise em atributos específicos e selecione **Seguinte**.

1. Forneça um nome para a sua análise de sobreposição, um nome a apresentar opcional e uma descrição.

1. Selecione **Guardar** para iniciar a análise. A análise de sobreposição está pronta quando o estado muda de Em Atualização para Bem Sucedida.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Ver e otimizar uma análise de diferenciadores

Após completar a análise, encontre detalhes sobre esta informação em **Segmentos** > **Informações (pré-visualização)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalhes de informações de diferenciador de segmentos":::

Selecione uma informação para ver os resultados da análise. Uma análise diferenciadora inclui dois separadores. O separador **Atributos** lista atributos de perfil considerados diferenciadores. O separador **Medidas** lista diferenciadores. Cada separador inclui os seguintes detalhes:

- Lista classificada de diferenciadores, ordenada pela pontuação da diferença.
- A **Pontuação da diferença** para cada diferenciador. A pontuação da diferença representa o grau de diferença de um atributo entre dois segmentos. Quanto maior for a pontuação da diferença, mais os atributos diferem entre os dois segmentos. Selecione uma pontuação para abrir o painel de **Pontuação da diferença** com as distribuições de valores para esse atributo.

## <a name="manage-segment-insights"></a>Gerir informações de segmentos

Pode utilizar as seguintes opções nas suas informações a partir da barra de comando:

- **Anterior** para regressar à lista de informações
- **Atualizar** para executar a análise novamente
- **Eliminar** para remover esta informação


[!INCLUDE[footer-include](../includes/footer-banner.md)]
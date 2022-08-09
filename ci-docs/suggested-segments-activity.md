---
title: Segmentos sugeridos com base na atividade (pré-visualização)
description: Deixe que a aprendizagem automática o ajude a encontrar segmentos novos e interessantes baseados na atividade do cliente.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170603"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segmentos sugeridos com base na atividade (pré-visualização)

Descubra segmentos interessantes dos seus clientes com base em dados de atividade do cliente que são ingeridos para o Customer Insights. Exemplos de dados de atividade são transações, duração de chamadas de suporte, compras ou devoluções. Para sugerir segmentos, os dados da atividade são analisados por recência, frequência e valor monetário (ou duração). Em alternativa, pode gerar [segmentos sugeridos para melhorar uma medida ou entender melhor o que influencia um atributo](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Separador de segmentos sugeridos a mostrar sugestões de segmentos para segmentos baseados em atividades e em atributos.":::

## <a name="categorize-customers-by-activity"></a>Categorizar clientes por atividade

Com os [dados de atividade](activities.md) disponíveis no Customer Insights, podemos gerar sugestões que representem grupos de clientes:

- maioria dos clientes ativos 
- clientes que fizeram mais compras 
- clientes que geraram mais receitas 
- clientes que não têm estado ativos ultimamente 
- clientes que interagem frequentemente com o seu negócio  

Se tiver um negócio de retalho, poderá descobrir que clientes geram mais receitas e recompensá-los com um cupão. Ou pode identificar clientes ocasionais e oferecer-lhes para se juntarem a um programa de recompensas para que visitem o seu negócio com mais frequência.
Se prestar cuidados de saúde pública e o seu objetivo for minimizar as despesas dos pacientes individuais, poderá tentar reduzir as visitas recorrentes ao fornecer os melhores cuidados possíveis no menor número de visitas possível. Neste caso, o seu objetivo é manter a frequência de visitas baixa e minimizar os custos recorrentes para os pacientes. Ou pode identificar segmentos de pacientes que têm consultas frequentes e custos recorrentes elevados e analisar estes casos para melhorar o tratamento do indivíduo.

## <a name="required-data"></a>Dados necessários

As sugestões são geradas com base nos dados de entrada selecionados.

- Perfis do cliente: todos os clientes ou membros de um segmento específico.

- Período de tempo: Último mês, último ano ou em qualquer período de tempo personalizado.

- Tipo de atividade: compras, transações de retalho, transações online, casos de suporte ao cliente, subscrições, e assim por diante.  

- Entidade no Customer Insights que contém os dados da atividade: a entidade UnifiedActivity ou a entidade para uma atividade específica.

- Dimensões a incluir: recência, frequência ou dimensão monetária, dependendo dos requisitos do seu negócio.

## <a name="generate-suggested-segments"></a>Gerar segmentos sugeridos

1. Vá para **Segmentos** e selecione o separador **Sugestões (pré-visualização)**.

1. Selecione **Encontrar novas sugestões** e escolha **Ver ou antecipar o comportamento do cliente**. Selecione **Iniciar**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeiro passo do assistente de configuração para um segmento sugerido baseado em atividades.":::

1. Forneça os dados de entrada necessários e selecione **Seguinte**.

   - Escolher clientes: inclua todos os clientes ou um segmento específico.
   - Escolher atividade: selecione o tipo de atividade e as entidades que descrevem a atividade.
   - Preferências: defina o período de tempo a considerar, os fatores para sugestões e mapeie os atributos.

1. Reveja a sua entrada e selecione **Executar** para executar o modelo e gerar sugestões.

Dependendo do número de perfis de clientes e atividades selecionadas, pode levar alguns minutos para ser concluído.

Depois de gerar as sugestões, pode filtrá-las pela dimensão ou valor em que está mais interessado.

## <a name="manage-suggested-segments"></a>Gerir segmentos sugeridos

Vá para **Segmentos** e selecione o separador **Sugestões (pré-visualização)**. Na secção **Sugestões baseadas em atividades** , selecione um segmento sugerido para ver as ações disponíveis.

- **Ver sugestão** para ver os detalhes desse segmento, como a extensão de cada dimensão em comparação com o grupo de destino. Realça também o número de potenciais membros no segmento e a correspondente percentagem do total de clientes.
- **Criar segmento** para guardar a sugestão como um segmento. É apresentado no separador **Todos os segmentos** e pode ser [atualizado ou eliminado](segments.md). Não pode editar os detalhes do segmento. No entanto, pode alterar os critérios de entrada para as sugestões e gerar diferentes sugestões.
- **Editar sugestões** para modificar os atributos configurados que irão substituir as sugestões atuais.
- **Atualizar sugestões** para atualizar as sugestões mantendo os atributos configurados.

[!INCLUDE [footer-include](includes/footer-banner.md)]

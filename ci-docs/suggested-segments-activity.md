---
title: Segmentos sugeridos baseados em atividades.
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
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647039"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmentos sugeridos baseados em dados de atividades (pré-visualização)

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
Se está no ramo dos cuidados de saúde, fornece cuidados de saúde públicos e o seu objetivo é minimizar as despesas para cada paciente. Uma forma de o fazer poderia ser reduzir as visitas recorrentes, proporcionando o melhor cuidado possível no menor número possível de visitas. Neste caso, o seu objetivo é manter a frequência de visitas baixa e minimizar os custos recorrentes para os pacientes. Ou pode identificar segmentos de pacientes que têm consultas frequentes e custos recorrentes elevados e analisar estes casos para melhorar o tratamento do indivíduo. 

## <a name="required-data"></a>Dados necessários

As sugestões são geradas com base nos dados de entrada selecionados. 

- Perfis do cliente: todos os clientes ou membros de um segmento específico. 

- Período de tempo: Último mês, último ano ou em qualquer período de tempo personalizado.

- Tipo de atividade: compras, transações de retalho, transações online, casos de suporte ao cliente, subscrições, e assim por diante.  

- Entidade no Customer Insights que contém os dados da atividade: a entidade UnifiedActivity ou a entidade para uma atividade específica. 

- Dimensões a incluir: recência, frequência ou dimensão monetária, dependendo dos requisitos do seu negócio.

## <a name="generate-suggested-segments"></a>Gerar segmentos sugeridos

1. Aceda a **Segmentos**.

1. Selecione o separador **Sugestões (pré-visualização)**.

1. Selecione **Encontrar novas sugestões** e escolha **Ver ou antecipar o comportamento do cliente**. Selecione **Começar** para executar a experiência guiada.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeiro passo do assistente de configuração para um segmento sugerido baseado em atividades.":::

1. Forneça os dados de entrada necessários e selecione **Seguinte** para prosseguir.

   - Escolher clientes: inclua todos os clientes ou um segmento específico.
   - Escolher atividade: selecione o tipo de atividade e as entidades que descrevem a atividade.
   - Preferências: defina o período de tempo a considerar, os fatores para sugestões e mapeie os atributos.

1. Reveja a sua entrada e selecione **Executar** para executar o modelo e gerar sugestões.

1. Dependendo do número de perfis de clientes e atividades selecionadas, pode levar alguns minutos para ser concluído. 

Depois de gerar as sugestões, pode filtrá-las pela dimensão ou valor em que está mais interessado. 

## <a name="view-details-of-a-suggested-segment"></a>Ver detalhes de um segmento sugerido

Assim que as sugestões forem geradas, irá encontrá-las listadas em **Sugestões** > **Segmentos (pré-visualização)** na secção **Sugestões baseadas em atividades**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Painel lateral expandido a mostrar dados detalhados de um segmento sugerido.":::

Selecione **Ver sugestão** de um segmento sugerido para ver os detalhes desse segmento. O painel lateral fornece detalhes como a extensão de cada dimensão em comparação com o grupo de destino. Realça também o número de potenciais membros no segmento e a correspondente percentagem do total de clientes. Se quiser manter a sugestão como um segmento, selecione **Criar segmento**.    

## <a name="save-a-suggestion-as-a-segment"></a>Guardar uma sugestão como um segmento

1. Vá a **Segmentos** > **Sugestões (pré-visualização)**.

1. Selecione o segmento que pretende guardar. 

1. No painel lateral, selecione **Criar segmento**. 

1. Depois de guardar o segmento, aparecerá na lista de segmentos no separador **Todos os segmentos**. Pode agora ser [atualizado ou eliminado como qualquer outro segmento](segments.md). Não pode editar os detalhes do segmento. No entanto, pode alterar os critérios de entrada para as sugestões e gerar diferentes sugestões.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Atualizar ou editar um conjunto de sugestões

1. Vá a **Segmentos** > **Sugestões (pré-visualização)** e procure o segmento na secção de **Sugestões baseadas em atividades**.

1. Selecione **Atualizar sugestões** para atualizar as sugestões mantendo os atributos configurados. Ou selecione **Editar sugestões** para modificar os atributos configurados. O sistema irá voltar a executar o processo, gerar sugestões de segmentos com base nos dados mais recentes e substituir as sugestões atuais.

[!INCLUDE [footer-include](includes/footer-banner.md)]

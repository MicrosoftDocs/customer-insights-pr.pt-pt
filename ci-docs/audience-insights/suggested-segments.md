---
title: Segmentos sugeridos com tecnologia de aprendizagem automática
description: Deixe que a aprendizagem automática o ajude a encontrar segmentos novos e interessantes com base nos atributos do cliente.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: bbc22adcd7b6e756fa6128abd855795de7480f2d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597111"
---
# <a name="suggested-segments-preview"></a>Segmentos sugeridos (pré-visualização)

Descubra segmentos interessantes dos seus clientes com a ajuda de um modelo de IA. Esta funcionalidade com tecnologia de aprendizagem automática sugere segmentos baseados em medidas ou atributos do cliente. Pode ajudar a melhorar os seus KPIs ou a entender melhor a influência de atributos no contexto de outros atributos. 

> [!NOTE]
> Os segmentos sugeridos utilizam meios automatizados para avaliar dados e fazer predições com base nesses dados, pelo que têm a capacidade de ser utilizados como método de criar perfis, uma vez que esse termo é definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD"). A sua utilização desta funcionalidade para processar dados pode estar sujeita ao RGPD ou a outras leis ou regulamentos. É responsável por garantir que a sua utilização do Dynamics 365 Customer Insights, incluindo esta funcionalidade, está em conformidade com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas com privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Página de segmentos sugeridos no Customer Insights que mostra detalhes de uma sugestão num painel lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmentos sugeridos para melhorar os seus KPIs

Como utilizador das informações da audiência, é provável que tenha uma série de [medidas criadas](measures.md) que ajudam a monitorizar os seus Indicadores Chave de Desempenho (KPIs). É importante entender como certos atributos influenciam este KPI para criar segmentos e executar uma campanha altamente direcionada.   
Por exemplo, monitoriza uma medida chamada *TotalSpendPerCustomer*. Como um negócio, gostaria de ver este número crescer. Escolher uma medida como atributo principal, permite-lhe selecionar os atributos que pretende avaliar para influência. Digamos o *escalão de adesão*, o *período de adesão* e a *ocupação*. O Customer Insights pode então sugerir um segmento que lhe diga quem é a maior influência dessa medida. Por exemplo, os *Contabilistas* que são membros *Gold* e que estão no seu negócio há *pelo menos cinco anos*, são o maior influenciador da *TotalSpendPerCustomer*. Terá um tamanho de segmento estimado para cada sugestão. Pode utilizar estas informações para criar campanhas para o público de destino.

## <a name="understand-what-influences-a-customer-attribute"></a>Compreenda o que influencia um atributo do cliente

Pode escolher um atributo do cliente em vez de uma medida como atributo principal. Com base na sua escolha de influenciar atributos, o modelo de IA cria uma série de sugestões que mostram como os atributos selecionados influenciam o atributo principal.   
Por exemplo, escolhe o *Membro de Recompensas (Sim/Não)* como o atributo principal. *Antiguidade*, *Ocupação* e *Número de Pedidos de Suporte* são definidos como outros atributos de influência. O modelo de IA poderia sugerir segmentos que indicam que a maioria dos profissionais de TI com antiguidade ao longo de dois anos são membros de recompensas. Outra sugestão poderia destacar que os contabilistas com antiguidade superior a um ano e menos de três pedidos de suporte são membros de recompensas. 

## <a name="artificial-intelligence-usage"></a>Utilização de inteligência artificial

Ao utilizar o atributo principal e atributos influenciadores, um algoritmo de árvore de decisão sugere segmentos interessantes. As sugestões baseiam-se em regras ou padrões que foram captados pelo algoritmo de IA. Apenas segmentos que diferem significativamente da população média são apresentados como sugestões. A comparação com a população média baseia-se na medida selecionada ou no atributo principal.

### <a name="responsible-ai"></a>Responsável IA

Segmentos sugeridos permitem selecionar atributos para criar novos segmentos e processar os dados que seleciona. Ao escolher atributos, incluindo atributos sensíveis, como raça, orientação sexual ou sexo, deve garantir que pode e deve processar esses dados. É responsável por cumprir com quaisquer leis aplicáveis à sua organização e aderir aos princípios e políticas de privacidade da sua organização.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Resultados diferentes para atributos principais com valores categóricos e numéricos

As sugestões de segmento são diferentes se escolher um atributo numérico ou um atributo categórico como atributo principal. Os valores num atributo categórico contêm duas ou mais categorias ou tipos. Um atributo numérico contém dados quantitativos e tem uma sensação de medição associada a ele.

Com um atributo numérico, como *rendimento anual* ou *período de adesão* como atributo principal, o sistema sugere segmentos que têm um valor médio superior ou inferior ao atributo numérico quando comparado com todos os clientes.

Um atributo categórico, como *satisfação do cliente* como o atributo principal, resulta em segmentos sugeridos que têm uma percentagem maior ou menor de clientes pertencentes a uma determinada categoria quando comparados com a percentagem de todos os clientes pertencentes a essa mesma categoria. Por exemplo, *satisfação de cliente* é escolhida como o atributo principal e consiste em três categorias (*Baixa*, *Média* e *Alta*). Para cada categoria, serão sugeridos segmentos que tenham uma percentagem significativamente maior ou menor de clientes pertencentes a essa categoria em comparação com a proporção de todos os clientes na mesma categoria. Se 22% de todos os clientes tiverem uma satisfação *Alta*, apenas segmentos que tenham uma proporção significativamente maior ou menor de clientes com uma satisfação *Alta* em comparação com 22% serão sugeridos para esta categoria. Da mesma forma, serão sugeridos segmentos para cada uma das outras categorias (*Baixa* e *Média*) se forem estatisticamente significativos.

> [!NOTE]
> Atualmente, apenas suportamos atributos categóricos principais que têm até 10 categorias. Se quiser ver sugestões de segmentos com base num atributo principal com mais de 10 categorias, recomendamos que agrupe algumas das categorias para reduzir o número de categorias para 10 ou menos. Esta limitação aplica-se apenas aos atributos principais. Para influenciar atributos categóricos, atualmente, suportamos um máximo de 100 categorias.

## <a name="generate-suggested-segments"></a>Gerar segmentos sugeridos

1. Aceda a **Segmentos**.

1. Selecione o separador **Sugestões (pré-visualização)**.

1. Selecione **Obter novas sugestões** para iniciar a experiência guiada.

1. Escolha uma medida ou um atributo do cliente como atributo principal e selecione **Seguinte**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Escolher o atributo principal para sugestões nos segmentos sugeridos.":::

1. Selecione os atributos de influência e selecione **Guardar**.
   
   > [!TIP]
   > Selecionar múltiplos atributos influenciadores melhora as chances de avaliar como influenciam o atributo principal. Não inclua atributos que não influenciem o atributo principal. Por exemplo, se todos os seus clientes forem de um país específico, não inclua o atributo do *país* porque não terá qualquer impacto na produção.

1. Dependendo do número de perfis de clientes e atributos selecionados, pode levar alguns minutos para processar os atributos selecionados. 

## <a name="view-details-of-a-suggested-segment"></a>Ver detalhes de um segmento sugerido

Quando o modelo de IA gerar as sugestões, irá encontrá-las listadas em **Segmentos** > **Sugestões (pré-visualização)**.
 
Selecione um segmento sugerido para rever os detalhes dessa sugestão, incluindo uma comparação do valor médio e do número de membros do segmento. Também pode rever os valores ou regras de atributos que o modelo de IA aprendeu para sugerir o segmento selecionado.

## <a name="save-a-suggestion-as-a-segment"></a>Guardar uma sugestão como um segmento

1. Vá a **Segmentos** > **Sugestões (pré-visualização)**.

1. Selecione o segmento que pretende guardar. 

1. No painel lateral, selecione **Guardar como segmento**. 

1. Depois de guardar o segmento, aparecerá na lista de segmentos no separador **Todos os segmentos**. Pode agora ser [atualizado, editado ou eliminado como qualquer outro segmento](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Atualizar ou editar um conjunto de sugestões

1. Vá a **Segmentos** > **Sugestões (pré-visualização)**.

1. Selecione **Atualizar sugestões** para atualizar as sugestões mantendo os atributos configurados. Ou selecione **Editar atributos** para modificar os atributos configurados. O sistema irá voltar a executar o modelo de IA, gerar sugestões de segmentos com base nos dados mais recentes e substituir as sugestões atuais.

## <a name="limitations"></a>Limitações

1. Erro de correspondência de tamanho de segmento estimado: se escolher um atributo principal que contenha valores vazios, pode afetar o tamanho estimado do segmento nas sugestões do segmento. Ao poupar tal segmento, o tamanho real do segmento pode ser diferente da estimativa original.
 
2. Os atributos principais do tipo booleano não funcionam: atualmente, apenas suportamos tipos de dados de cadeia e numéricos como o atributo principal.

3. Os segmentos sugeridos não são suficientemente distintos: tenha em conta que os atributos selecionados e a distribuição de valores desses atributos influenciam os resultados. Pode alterar os seus atributos influenciadores ou até mesmo o seu atributo principal para obter resultados diferentes.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
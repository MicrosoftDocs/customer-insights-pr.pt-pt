---
title: Fazer corresponder entidades para unificação de dados
description: Corresponda entidades para combinar conjuntos de dados e criar perfis de clientes unificados.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: 67e17495fa6da1cfac7ee4ee165e798364f6cb27
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648222"
---
# <a name="match-entities"></a>Fazer corresponder entidades

A fase de correspondência especifica como combinar os seus conjuntos de dados num conjunto de dados de perfil do cliente unificado. Depois de concluir o [passo de mapeamento](map-entities.md) no processo de unificação de dados, está pronto para corresponder as suas entidades. A fase de correspondência exige pelo menos duas entidades correspondidas.

A página de correspondência é composta por três secções: 
- Métricas-chave que resumem o número de registos correspondidos
- Ordem de correspondência e regras para correspondência entre entidades
- Regras para a eliminação de duplicados de entidades correspondidas

## <a name="specify-the-match-order"></a>Especificar a ordem de correspondência

Vá a **Dados** > **Unificar** > **Corresponder** e selecione **Definir ordem** para iniciar a fase de correspondência.

Cada correspondência unifica duas ou mais entidades numa única entidade consolidada. Ao mesmo tempo, mantém os registos exclusivos dos clientes. Por exemplo, selecionámos duas entidades: **eCommerce:eCommerceContacts** como entidade principal e **LoyaltyScheme:loyCustomers** como segunda entidade. A ordem das entidades especifica em que ordem o sistema tentará corresponder os registos.

:::image type="content" source="media/match-page.png" alt-text="Captura de ecrã da página Correspondência na área Unificar do processo de unificação de dados.":::
  
A entidade principal *eCommerce:eCommerceContacts* é correpondida com a entidade seguinte *LoyaltyScheme:loyCustomers*. O conjunto de dados que resulta do primeiro passo de correspondência é combinado com a seguinte entidade se tiver mais de duas entidades.

> [!IMPORTANT]
> A entidade que escolher como entidade principal servirá como base para o seu conjunto de dados de perfis unificados. As entidades adicionais selecionadas durante a fase de correspondência serão adicionadas a esta entidade. Isto não significa que a entidade unificada incluirá *todos* os dados incluídos nesta entidade.
>
> Existem duas considerações que podem ajudá-lo a escolher a hierarquia das entidades:
>
> - Escolha a entidade com os dados de perfil mais completos e fiáveis sobre os seus clientes como entidade principal.
> - Escolha a entidade que tem vários atributos em comum com outras entidades (por exemplo, nome, número de telefone ou endereço de e-mail) como entidade principal.

Depois de especificar a ordem de correspondência, irá ver os pares de correspondência definidos na secção **Detalhes dos registos correspondidos** em **Dados** > **Unificar** > **Corresponder**. As métricas-chave ficarão vazias até que o processo de correspondência esteja concluído.

## <a name="define-rules-for-match-pairs"></a>Definir regras para pares de correspondência

As regras de correspondência especificam a lógica pela qual será feita a correspondência de um par de entidades específico.

O aviso **Necessita de regras** junto a um nome de entidade sugere que não existe nenhuma regra de correspondência definida para um par de correspondência. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de ecrã da secção de detalhes de registos de correspondência com controlo para adicionar regras realçadas.":::

1. Selecione **Adicionar regras** numa entidade na secção **Detalhes dos registos correspondidos** para definir as regras de correspondência.

1. No painel **Criar regra**, configure as condições para a regra.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de ecrã de uma regra de correspondência aberta com condições adicionadas.":::

   - **Entidade/Campo (primeira linha)**: escolha uma entidade relacionada e um atributo para especificar uma propriedade de registo que seja provavelmente única para um cliente. Por exemplo, um número de telefone ou endereço de e-mail. Evite corresponder por atributos do tipo de atividade. Por exemplo, um ID de compra provavelmente não encontrará correspondência noutros tipos de registo.

   - **Entidade/Campo (segunda linha)**: escolha um atributo que se relacione com o atributo da entidade especificada na primeira linha.

   - **Normalizar**: selecione a partir das seguintes opções de normalização para os atributos selecionados. 
     - Espaço em branco: remove todos os espaços. *Olá   Mundo* torna-se *OláMundo*.
     - Símbolos: remove todos os símbolos e caracteres especiais. *Head&Shoulder* torna-se *HeadShoulder*.
     - Texto para minúscula: converte todos os caracteres em minúsculas. *TODAS MAIÚSCULAS e Título* torna-se *todas maiúsculas e título*.
     - Unicode para ASCII: converte a notação unicode para caracteres ASCII. */u00B2* torna-se *2*.
     - Números: converte outros sistemas numéricos, como a numeração romana em algarismos árabes. *VIII* torna-se *8*.
     - Tipos de semântica: normaliza nomes, títulos, números de telefone, endereços, etc. 

   - **Precisão**: defina o nível de precisão para aplicar esta condição. 
     - **Básico**: escolha entre *Baixo*, *Médio*, *Alto* e *Exato*. Selecione **Exato** para fazer a correspondências apenas dos registos com uma correspondência de 100%. Selecione um dos outros níveis para fazer a correspondência dos registos que não são 100% idênticos.
     - **Personalizar**: defina uma percentagem que os registos têm de corresponder. O sistema só vai corresponder os registos que ultrapassam este limiar.

1. Forneça um **Nome** para a regra.

1. [Adicione mais condições](#add-conditions-to-a-rule) ou selecione **Concluído** para finalizar a regra.

1. Opcionalmente, [adicione mais regras](#add-rules-to-a-match-pair).

1. Selecione **Guardar** para aplicar as alterações.

### <a name="add-conditions-to-a-rule"></a>Adicionar condições a uma regra

Para corresponder entidades apenas se os atributos satisfaçam várias condições, adicione mais condições a uma regra de correspondência. As condições estão ligadas a um operador E lógico e, portanto, só são executadas se todas as condições forem satisfeitas.

1. Aceda a **Dados** > **Unificar** > **Corresponder** e selecione **Editar** na regra a que pretende adicionar condições.

1. No painel **Editar regra**, selecione **Adicionar condição**.

1. Selecione **Concluído** para guardar a regra.

### <a name="add-rules-to-a-match-pair"></a>Adicionar regras a um par de correspondências

As regras de correspondência representam conjuntos de condições. Para corresponder entidades por condições com base em vários atributos, adicione mais regras

1.  Aceda a **Dados** > **Unificar** > **Corresponder** e selecione **Adicionar regra** na entidade a que pretende adicionar regras.

2. Siga os passos em [Definir regras para pares de correspondência](#define-rules-for-match-pairs).

> [!NOTE]
> A ordem das regras é importante. O algoritmo de correspondência tenta corresponder com base na sua primeira regra e continua para a segunda regra apenas se não forem identificadas correspondências com a primeira regra.

### <a name="change-the-entity-order-in-match-rules"></a>Alterar a ordem da entidade nas regras de correspondência

Pode reordenar entidades para que as regras de correspondência alterem a ordem em que são processadas. As regras que estão em conflito por causa de uma ordem alterada serão removidas. Tem de recriar regras removidas com uma configuração atualizada.

1. Vá a **Dados** > **Unificar** > **Corresponder** e selecione **Editar**.

1. No painel **Editar regra**, selecione o controlo **Mover para cima/baixo** ou arraste e largue entidades para alterar a ordem.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opções para alterar em que ordem as entidades são processadas na fase de correspondência.":::

1. Selecione **Concluído** para guardar a regra.

## <a name="define-deduplication-on-a-match-entity"></a>Definir a duplicação sobre uma entidade correspondente

Além das [regras de correspondência entre entidades](#define-rules-for-match-pairs), também pode especificar regras de eliminação de duplicados. A *eliminação de duplicados* é outro processo de correspondência de registos. Identifica registos duplicados e intercala-os num único registo. Os registos de origem ligam-se ao registo intercalado com ID alternativos.

Os registos não duplicados serão utilizados no processo de correspondência entre entidades. A eliminação de duplicados ocorre em entidades individuais e pode ser configurada em todas as entidades utilizadas em pares de correspondência.

A especificação das regras de duplicação não é obrigatória. Se tais regras não forem configuradas, são aplicadas as regras definidas pelo sistema. Combinam todos os registos num único registo antes de transmitir os dados da entidade para a correspondência entre entidades para um maior desempenho.

### <a name="add-deduplication-rules"></a>Adicionar regras de duplicação

1. Aceda a **Dados** > **Unificar** > **Corresponder**.

1. Na secção **Duplicados fundidos**, selecione **Definir entidades**. Caso já estejam criadas regras de eliminação de duplicados, selecione **Editar**.

1. No painel **Preferências de intercalação**, escolha as entidades em que pretende realizar a eliminação de duplicados.

1. Especifique como combinar os registos duplicados e escolha uma das três opções:
   - **Mais preenchido**: identifica o registo com os campos de atributos mais povoados como registo vencedor. É a opção de intercalação predefinida.
   - **Mais recentes**: Identifica o registo vencedor com base no mais recente. Requer uma data ou um campo numérico para definir a atualidade.
   - **Menos recente**: Identifica o registo vencedor com base no menos recente. Requer uma data ou um campo numérico para definir a atualidade.
 
   > [!div class="mx-imgBorder"]
   > ![Regras de duplicação – passo 1.](media/match-selfconflation.png "Regras de duplicação etapa 1")
 
1. Assim que as entidades forem selecionadas e a sua preferência de intercalação for definida, selecione **Adicionar regra** para definir as regras de eliminação de duplicados a nível da entidade.
   - **Selecionar campo** apresenta todos os campos disponíveis dessa entidade. Escolha o campo que pretende verificar se existem duplicados. Escolha os campos que sejam provavelmente únicos para cada cliente. Por exemplo, um endereço de e-mail ou a combinação de nome, cidade e número de telefone.
   - Especifique as definições de normalização e precisão.
   - Defina mais condições selecionando **Adicionar condição**.
 
   > [!div class="mx-imgBorder"]
   > ![Regras de duplicação – passo 2.](media/match-selfconflation-rules.png "Regras de duplicação etapa 2")

  Pode criar múltiplas regras de duplicação para uma entidade. 

1. A execução do processo de correspondência agrupa agora os registos com base nas condições definidas nas regras de duplicação. Após agrupar os registos, a política de fusão é aplicada para identificar o registo vencedor.

1. Este registo de vencedores é então passado para a correspondência de entidade cruzada, juntamente com os registos de não vencedor (por exemplo, IDs alternativos) para melhorar a qualidade de correspondência.

1. As regras de correspondência personalizadas definidas substituem as regras de eliminação de duplicados. Se uma regra de duplicação identificar registos correspondentes, e uma regra de correspondência personalizada for definida para nunca corresponder a esses registos, então estes dois registos não terão correspondência.

1. Após [a execução do processo de correspondência](#run-the-match-process), irá ver as estatísticas de eliminação de duplicados nos mosaicos das principais métricas.

### <a name="deduplication-output-as-an-entity"></a>Saída de eliminação de duplicados como uma entidade

O processo de eliminação de duplicados cria uma nova entidade para cada entidade a partir dos pares de correspondência para identificar os registos não duplicados. Estas entidades podem ser encontradas juntamente com **ConflationMatchPairs:CustomerInsights** na secção **Sistema** na página **Entidades**, com o nome **Deduplication_DataSource_Entity**.

Uma entidade de saída de eliminação de duplicados contém as seguintes informações:
- IDs / Chaves
  - Campo de chave primária e o respetivo campo de IDs alternativos. O campo de IDs alternativos consiste em todos os IDs alternativos identificados para um registo.
  - O campo Deduplication_GroupId mostra o grupo ou o cluster identificado dentro de uma entidade que agrupa todos os registos semelhantes com base nos campos de eliminação de duplicados especificados. É utilizado para fins de processamento do sistema. Se não existirem regras de eliminação de duplicados manuais especificadas e se aplicarem regras de eliminação de duplicados definidas pelo sistema, poderá não encontrar este campo na entidade de saída de eliminação de duplicados.
  - Deduplication_WinnerId: este campo contém o ID de vencedor dos grupos ou clusters identificados. Se Deduplication_WinnerId é o mesmo que o valor da Chave primária para um registo, significa que o registo é o registo vencedor.
- Campos usados para definir as regras de eliminação de duplicados.
- Campos Regra e Pontuação para denotar quais as regras de eliminação de duplicados foram aplicadas e a pontuação devolvida pelo algoritmo correspondente.
   
## <a name="run-the-match-process"></a>Executar o processo de correspondência

Com as regras de correspondência configuradas, incluindo regras de correspondência e eliminação de duplicados entre entidades, pode executar o processo de correspondência. 

Aceda a **Dados** > **Unificar** > **Corresponder** e selecione **Executar** para iniciar o processo. O algoritmo de correspondência demora algum tempo a ser concluído e não é possível alterar a configuração até que esteja concluído. Para efetuar alterações, pode cancelar a execução. Selecione o estado da tarefa e selecione **Cancelar tarefa** no painel **Detalhes do progresso**.

Encontrará o resultado de uma execução bem-sucedida, a entidade unificada de perfil do cliente, na página **Entidades**. A sua entidade de cliente unificada chama-se **Clientes** na secção **Perfis**. A primeira execução de correspondência bem-sucedida cria a entidade unificada de *Cliente*. Todas as execuções de correspondência subsequentes expandem essa entidade.

> [!TIP]
> Depois de executar o processo de correspondência, selecione o estado do processo para abrir o painel de **Detalhes da tarefa**. Fornece uma descrição geral sobre o tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa. Selecione **Ver detalhes** para ver quais as entidades que participaram no processo de correspondência, quais as regras que lhes foram aplicadas e se as atualizações foram publicadas com sucesso.  
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Caminho de desagregação para chegar aos detalhes do processo a partir da ligação do estado da tarefa.":::

## <a name="review-and-validate-your-matches"></a>Rever e validar as suas correspondências

Aceda a **Dados** > **Unificar** > **Corresponder** para avaliar a qualidade dos seus pares de correspondência e refiná-los se necessário.

Os mosaicos na parte superior da página mostram as métricas-chave, resumindo o número de registos e duplicados correspondidos.

:::image type="content" source="media/match-KPIs.png" alt-text="Captura de ecrã recortada das métricas-chave na página Corresponder com números e detalhes.":::

- **Registos de origem exclusivos** mostra o número de registos de origem individuais que foram processados na última execução de correspondência.
- **Registos correspondidos e não correspondidos** destaca quantos registos únicos permanecem após o processamento das regras de correspondência.
- **Apenas registos correspondidos** mostra o número de correspondências em todos os seus pares de correspondências.

Pode avaliar os resultados de cada par de correspondência e as suas regras na tabela **Detalhes dos registos correspondidos**. Compare o número de registos que vieram de um par de correspondência com a percentagem de registos correspondidos com sucesso.

Reveja as regras de um par de correspondência para ver a percentagem de registos correspondidos com sucesso ao nível das regras. Selecione as reticências (...) e, em seguida, selecione **Pré-visualizar correspondência** para ver todos estes registos ao nível da regra. Recomendamos que veja alguns registos para validar se foram corretamente correspondidos.

Experimente limiares de precisão diferentes em condições para encontrar o valor ideal.

  1. Selecione as reticências (...) para a regra que pretende experimentar e selecione **Editar**.

  2. Altere os valores de precisão nas condições que pretende rever.

  3. Selecione **Pré-visualizar** para ver o número de registos correspondidos e não correspondidos para a condição selecionada.

## <a name="manage-match-rules"></a>Gerir regras de correspondência

Pode reconfigurar e aperfeiçoar a maioria dos parâmetros de correspondência.

:::image type="content" source="media/match-rules-management.png" alt-text="Captura de ecrã do menu pendente com opções de regras de correspondência.":::

- **Alterar a ordem das suas regras** se definiu várias regras. Pode reordenar as regras de correspondência selecionando as opções **Mover para cima** e **Mover para baixo** arrastando e largando.

- **Altere as condições da regra** selecionando **Editar** e escolha campos diferentes.

- **Desativar uma regra** para manter uma regra de correspondência, excluindo-a do processo de correspondência.

- **Duplique as suas regras** se tiver definido uma regra de correspondência e quiser criar uma regra semelhante com modificações, selecione **Duplicar**.

- **Elimine uma regra** selecionando o símbolo **Eliminar**.

## <a name="specify-custom-match-conditions"></a>Especificar condições de correspondência personalizadas

Pode especificar as condições que determinados registos devem corresponder sempre ou nunca. Estas regras podem ser carregadas para substituir o processo padrão de correspondência. Por exemplo, se houver John Doe I e John Doe II nos nossos registos, o sistema pode correspondê-los como uma pessoa. As regras de correspondência personalizadas permitem-lhe especificar que os seus perfis se referem a pessoas diferentes. 

1. Aceda a **Dados** > **Unificar** > **Corresponder** e selecione **Correspondência personalizada** na secção **Detalhes dos registos correspondidos**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Captura de ecrã da secção de regras de correspondência com o controlo de Correspondência personalizada realçado.":::

1. Se não tiver regras de correspondência personalizadas definidas, irá ver um novo painel **Correspondência personalizada** com mais detalhes.

1. Selecione **Preencher o modelo** para obter um ficheiro de modelo que especifique os registos a partir dos quais as entidades devem corresponder sempre ou nunca corresponder. Terá de preencher separadamente os registos "corresponder sempre" e "nunca corresponder" em dois ficheiros diferentes.

1. O modelo contém campos para especificar a entidade e os valores de chave primária da entidade que serão utilizados na correspondência personalizada. Por exemplo, se pretender que a chave primária *12345* da entidade *Vendas* corresponda sempre à chave primária *34567* da entidade *Contacto*, preencha o modelo:
    - Entidade1: Vendas
    - Entity1Key: 12345
    - Entidade2: Contacto
    - Entity2Key: 34567

   O mesmo ficheiro de modelo pode especificar registos de correspondência personalizados de várias entidades.
   
   Se pretender especificar a correspondência personalizada para a eliminação de duplicados numa entidade, forneça a mesma entidade que a Entidade1 e a Entidade2 e defina os diferentes valores chave primários.

1. Depois de adicionar todas as substituições que pretende aplicar, guarde o ficheiro de modelo.

1. Aceda a **Dados** > **Origens de dados** e ingere os ficheiros do modelo como novas entidades. Depois de ingeridos, pode utilizá-los para especificar a configuração Corresponder.

1. Após o carregamento dos ficheiros e de as entidades estarem disponíveis, selecione novamente a opção **Correspondência personalizada**. Verá opções para especificar as entidades que pretende incluir. Selecione as entidades necessárias no menu pendente.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de ecrã da caixa de diálogo para escolher substituições para um cenário de correspondência personalizada.":::

1. Selecione as entidades que pretende utilizar para **Corresponder sempre** e **Nunca corresponder**, e selecione **Concluído**.

1. Selecione **Guardar** na página **Corresponder** para aplicar a configuração de correspondência personalizada.

1. Selecione **Executar** na página **Corresponder** para iniciar o processo de correspondência. As outras regras de correspondência especificadas são substituídas pela configuração de correspondência personalizada.

> [!TIP]
> Aceda a **Dados** > **Entidades** e reveja a entidade **ConflationMatchPair** para confirmar que as substituições são aplicadas.

## <a name="next-step"></a>Passo seguinte

Depois de concluir o processo de correspondência para, pelo menos, um par de correspondência, poderá resolver as possíveis contradições nos seus dados através do tópico [**Intercalar**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

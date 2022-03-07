---
title: Fazer corresponder entidades para unificação de dados
description: Fazer corresponder entidades para criar perfis unificados de clientes.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 49729a13d26885c30039f9fa426eaee92c172424
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355167"
---
# <a name="match-entities"></a>Fazer corresponder entidades

A fase de correspondência especifica como combinar os seus conjuntos de dados num conjunto de dados de perfil do cliente unificado. Depois de concluir o [passo de mapeamento](map-entities.md) no processo de unificação de dados, está pronto para corresponder as suas entidades. A fase de correspondência exige pelo menos duas entidades correspondidas.

A página de correspondência é composta por três secções: 
- Métricas-chave que resumem o número de registos correspondidos
- Ordem de correspondência e regras para correspondência entre entidades
- Regras para a eliminação de duplicados de entidades correspondidas

## <a name="specify-the-match-order"></a>Especificar a ordem de correspondência

Cada correspondência unifica duas ou mais entidades numa única entidade consolidada. Ao mesmo tempo, mantém os registos exclusivos dos clientes. A ordem de correspondência indica a ordem em que o sistema tenta corresponder os registos.

> [!IMPORTANT]
> A entidade que escolher como entidade principal servirá como base para o seu conjunto de dados de perfis unificados. As entidades adicionais selecionadas durante a fase de correspondência serão adicionadas a esta entidade. Isto não significa que a entidade unificada incluirá *todos* os dados incluídos nesta entidade.
>
> Existem duas considerações que podem ajudá-lo a escolher a hierarquia das entidades:
>
> - Escolha a entidade com os dados de perfil mais completos e fiáveis sobre os seus clientes como entidade principal.
> - Escolha como entidade principal a entidade que tenha vários atributos em comum com outras entidades (por exemplo, nome, número de telefone ou endereço de e-mail).

1. Vá a **Dados** > **Unificar** > **Corresponder** e selecione **Definir ordem** para iniciar a fase de correspondência.
1. Selecione **Ordem das entidades**. Por exemplo, selecione **eCommerce:eCommerceContacts** como a entidade principal e **LoyaltyScheme:loyCustomers** como entidade secundária. 
1. Para fazer com que cada registo na entidade tenha um cliente exclusivo e correspondido a cada uma das entidades seguintes, selecione **Incluir todos**.
1. Selecionar **Concluído**. 

Depois de especificar a ordem de correspondência, os pares de correspondência definidos são apresentados na secção **Detalhes dos registos correspondidos** em **Dados** > **Unificar** > **Corresponder**. As métricas-chave estão vazias até que o processo de correspondência esteja concluído.

:::image type="content" source="media/match-page.png" alt-text="Captura de ecrã da página Correspondência na área Unificar do processo de unificação de dados.":::
  
A entidade principal *eCommerce:eCommerceContacts* é correpondida com a entidade seguinte *LoyaltyScheme:loyCustomers*. O conjunto de dados que resulta do primeiro passo de correspondência é correspondido com a seguinte entidade se tiver mais do que duas entidades.

## <a name="define-rules-for-match-pairs"></a>Definir regras para pares de correspondência

As regras de correspondência especificam a lógica pela qual será feita a correspondência de um par de entidades específico.

O aviso **Necessita de regras** junto a um nome de entidade sugere que não existe nenhuma regra de correspondência definida para um par de correspondência. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de ecrã da secção de detalhes de registos de correspondência com controlo para adicionar regras realçadas.":::

1. Selecione **Adicionar regra** sob uma entidade na secção **Detalhes dos registos correspondidos** para definir as regras de correspondência.

1. No painel **Criar regra**, configure as condições para a regra.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de ecrã de uma regra de correspondência aberta com condições adicionadas.":::

   - **Entidade/Campo (primeira linha)**: escolha uma entidade relacionada e um atributo para especificar uma propriedade de registo que seja provavelmente única para um cliente. Por exemplo, um número de telefone ou endereço de e-mail. Evite corresponder por atributos do tipo de atividade. Por exemplo, um ID de compra provavelmente não encontrará correspondência noutros tipos de registo.

   - **Entidade/Campo (segunda linha)**: escolha um atributo que se relacione com o atributo da entidade especificada na primeira linha.

   - **Normalizar**: selecione a partir das seguintes opções de normalização para os atributos selecionados. 
     - Números: converte outros sistemas numéricos, como a numeração romana em algarismos árabes. *VIII* torna-se *8*.
     - Símbolos: remove todos os símbolos e caracteres especiais. *Head&Shoulder* torna-se *HeadShoulder*.
     - Texto para minúscula: converte todos os caracteres em minúsculas. *TODAS MAIÚSCULAS e Título* torna-se *todas maiúsculas e título*.
     - Tipo (Telefone, Nome, Endereço, Organização): padroniza nomes, títulos, números de telefone, endereços, etc. 
     - Unicode para ASCII: converte a notação unicode para caracteres ASCII. */u00B2* torna-se *2*.
     - Espaço em branco: remove todos os espaços. *Olá   Mundo* torna-se *OláMundo*.

   - **Precisão**: defina o nível de precisão para aplicar esta condição. 
     - **Básico**: escolha entre *Baixo*, *Médio*, *Alto* e *Exato*. Selecione **Exato** para corresponder apenas registos que correspondam a 100 por cento. Selecione um dos outros níveis para fazer a correspondência dos registos que não são 100% idênticos.
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

As regras de correspondência representam conjuntos de condições. Para corresponder entidades por condições com base em vários atributos, adicione mais regras.

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

Os registos com eliminação de duplicados são utilizados no processo de correspondência entre entidades. A eliminação de duplicados ocorre em entidades individuais e pode ser configurada para cada entidade utilizada em pares de correspondência.

A especificação das regras de duplicação não é obrigatória. Se tais regras não forem configuradas, são aplicadas as regras definidas pelo sistema. Combinam todos os registos num único registo antes de transmitir os dados da entidade para a correspondência entre entidades para um maior desempenho.

### <a name="add-deduplication-rules"></a>Adicionar regras de duplicação

1. Aceda a **Dados** > **Unificar** > **Corresponder**.

1. Na secção **Detalhes de registos com eliminação de duplicados**, selecione **Definir entidades**. Caso já estejam criadas regras de eliminação de duplicados, selecione **Editar**.

1. No painel **Preferências de intercalação**, escolha as entidades em que pretende realizar a eliminação de duplicados.

   1. Especifique como combinar os registos duplicados e escolha uma das três opções:
      - **Mais preenchido**: identifica o registo com os campos de atributos mais povoados como registo vencedor. É a opção de intercalação predefinida.
      - **Mais recentes**: Identifica o registo vencedor com base no mais recente. Requer uma data ou um campo numérico para definir a atualidade.
      - **Menos recente**: Identifica o registo vencedor com base no menos recente. Requer uma data ou um campo numérico para definir a atualidade.

   1. Opcionalmente, para definir regras de eliminação de duplicados em atributos individuais de uma entidade, selecione **Avançadas**. Por exemplo, pode optar por manter o e-mail mais recente e o endereço mais completo de diferentes registos. Expanda a entidade para ver todos os seus atributos e definir que opção utilizar para atributos individuais. Se escolher uma opção baseada em recência, também precisa de especificar um campo de data/hora que defina a recência. 
 
      > [!div class="mx-imgBorder"]
      > ![Regras de duplicação – passo 1.](media/match-selfconflation.png "Regras de duplicação etapa 1")

   1. Selecione **Concluído** para aplicar as suas preferências de união para a eliminação de duplicados.
 
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

1. Depois de [executar o processo de correspondência](#run-the-match-process), verá as estatísticas de eliminação de duplicados nos mosaicos de métricas principais.

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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

## <a name="advanced-options"></a>Opções avançadas

### <a name="add-exceptions-to-a-rule"></a>Adicionar exceções a uma regra

Na maioria dos casos, a correspondência de entidades leva a perfis de utilizador exclusivos com dados consolidados. Para abordar dinamicamente casos raros de falsos positivos e falsos negativos, pode definir exceções para uma regra de correspondência. As exceções são aplicadas após o processamento das regras de correspondência e evitam a correspondência de todos os registos, as quais preenchem os critérios de exceção.

Por exemplo, se a sua regra de correspondência combinar apelido, cidade e data de nascimento, o sistema identificaria gémeos com o mesmo apelido que vivem na mesma cidade que o mesmo perfil. Pode especificar uma exceção que não corresponda aos perfis se os nomes próprios nas entidades que combinar não forem os mesmos.

1. Aceda a **Dados** > **Unificar** > **Corresponder** e selecione **Editar** na regra a que pretende adicionar condições.

1. No painel **Editar regra**, selecione **Adicionar exceção**.

1. Especifique os critérios de exceção. 

1. Selecione **Concluído** para guardar a regra.

### <a name="specify-custom-match-conditions"></a>Especificar condições de correspondência personalizadas

Poderá especificar as condições que substituem a lógica de correspondência predefinida. Estão disponíveis quatro opções: 

|Opção  |Description |Exemplo  |
|---------|---------|---------|
|Corresponder sempre     | Define valores sempre correspondentes.         |  Corresponde sempre a *Mike* e *MikeR*.       |
|Nunca corresponder     | Define valores que nunca correspondem.        | Nunca corresponde com *John* e *Jonathan*.        |
|Ignorar personalizado     | Define valores que o sistema deve sempre ignorar na fase de correspondência. |  Ignora os valores *11111* e *Unknown* durante a correspondência.        |
|Mapeamento de aliases    | Define valores que o sistema deve considerar como um mesmo valor.         | Considera *Joe* igual a *Joseph*.        |

1. Aceda a **Dados** > **Unificar** > **Corresponder** e selecione **Correspondência personalizada** na secção **Detalhes dos registos correspondidos**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Captura de ecrã da secção de regras de correspondência com o controlo de Correspondência personalizada realçado.":::

1. No painel **Personalizado**, vá para o separador **Registos**.

1. Escolha a opção de correspondência personalizada a partir da lista pendente **Tipo personalizado** e selecione **Transferir modelo**. É necessário um modelo separado para cada opção de correspondência.

1. Abra o ficheiro de modelo transferido e preencha os detalhes. O modelo contém campos para especificar a entidade e os valores de chave primária da entidade que serão utilizados na correspondência personalizada. Por exemplo, se pretender que a chave primária *12345* da entidade *Vendas* corresponda sempre à chave primária *34567* da entidade *Contacto*, preencha o modelo:
    - Entidade1: Vendas
    - Entity1Key: 12345
    - Entidade2: Contacto
    - Entity2Key: 34567

   O mesmo ficheiro de modelo pode especificar registos de correspondência personalizados de várias entidades.
   
   Se pretender especificar a correspondência personalizada para a eliminação de duplicados numa entidade, forneça a mesma entidade que a Entidade1 e a Entidade2 e defina os diferentes valores chave primários.

1. Depois de adicionar todas as substituições, guarde o ficheiro de modelo.

1. Aceda a **Dados** > **Origens de dados** e ingere os ficheiros do modelo como novas entidades.

1. Após o carregamento dos ficheiros e de as entidades estarem disponíveis, selecione novamente a opção **Correspondência personalizada**. Verá opções para especificar as entidades que pretende incluir. Selecione as entidades obrigatória no menu pendente e selecione **Concluído**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de ecrã da caixa de diálogo para escolher substituições para um cenário de correspondência personalizada.":::

1. A aplicação da correspondência personalizada depende da opção de correspondência que pretende utilizar. 

   - Para **Corresponder sempre** ou **Nunca corresponder**, avance para o passo seguinte.
   - Para **Ignorar personalizado** ou **Mapeamento de aliases**, selecione **Editar** numa regra de correspondência existente ou crie uma nova regra. No menu pendente Normalizações, escolha a opção **Ignorar personalizado** ou **Mapeamento de aliases** e selecione **Concluído**.

1. Selecione **Guardar** na página **Corresponder** para aplicar a configuração de correspondência personalizada.

1. Selecione **Executar** na página **Corresponder** para iniciar o processo de correspondência. As outras regras de correspondência especificadas são substituídas pela configuração de correspondência personalizada.

#### <a name="known-issues"></a>Problemas conhecidos

- A autoconjugação não mostra os dados normalizados nas entidades de eliminação de duplicados. No entanto, aplica a normalização internamente durante a eliminação de duplicados. Isto acontece por predefinição para todas as normalizações. 
- Se a definição de tipo semântico for removida na fase **Mapear** quando uma regra de correspondência utiliza o Mapeamento de aliases ou Ignorar personalizado, a normalização não será aplicada. Só acontece se limpar o tipo semântico depois de configurar a normalização na regra de correspondência porque o tipo semântico será desconhecido.


## <a name="next-step"></a>Próximo passo

Depois de concluir o processo de correspondência para, pelo menos, um par de correspondência, continue para o passo [**Unir**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

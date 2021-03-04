---
title: Fazer corresponder entidades para unificação de dados
description: Fazer corresponder entidades para criar perfis unificados de clientes.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267492"
---
# <a name="match-entities"></a>Fazer corresponder entidades

Depois de concluir a fase de correspondência, está pronto para fazer a correspondência das suas entidades. A fase de correspondência especifica como combinar os seus conjuntos de dados num conjunto de dados de perfil do cliente unificado. A fase de correspondência exige pelo menos [duas entidades correspondidas](map-entities.md).

## <a name="specify-the-match-order"></a>Especificar a ordem de correspondência

Vá a **Dados** > **Unificar** > **Corresponder** e selecione **Definir ordem** para iniciar a fase de correspondência.

Cada correspondência unifica duas ou mais entidades numa única entidade, mantendo cada registo de cliente exclusivo. No exemplo seguinte, selecionámos três entidades: **ContactCSV: TestData** como entidade **Primária**, **WebAccountCSV: TestData** como **Entidade 2** e **CallRecordSmall: TestData** como **Entidade 3**. O diagrama acima das seleções ilustra a forma como a ordem de correspondência será executada.

> [!div class="mx-imgBorder"]
> ![Editar a ordem de correspondência dos dados](media/configure-data-match-order-edit-page.png "Editar a ordem de correspondência dos dados")
  
É feita a correspondência da entidade **Primária** com a **Entidade 2**. O conjunto de dados resultante da primeira correspondência é correspondido com a **Entidade 3**.
Neste exemplo, selecionámos apenas duas correspondências, mas o sistema suporta mais.

> [!IMPORTANT]
> A entidade que escolher como entidade **Primária** servirá como base para o seu conjunto de dados principal unificado. As entidades adicionais selecionadas durante a fase de correspondência serão adicionadas a esta entidade. Ao mesmo tempo, isto não significa que a entidade unificada irá incluir *todos* os dados incluídos nesta entidade.
>
> Existem duas considerações que podem ajudá-lo a escolher a hierarquia das entidades:
>
> - Qual a entidade que considera ter os dados mais completos e fiáveis sobre os seus clientes?
> - A entidade que acabou de identificar tem atributos que também são partilhados por outras entidades (por exemplo, nome, número de telefone ou endereço de e-mail)? Caso contrário, escolha a segunda entidade mais fiável.

Selecione **Concluído** para guardar a ordem de correspondência.

## <a name="define-rules-for-your-first-match-pair"></a>Definir regras para o primeiro par de correspondência

Depois de especificar a ordem de correspondência, verá as correspondências definidas na página **Corresponder**. Os mosaicos na parte superior do ecrã ficarão vazios até executar a ordem de correspondência.

> [!div class="mx-imgBorder"]
> ![Definir regras](media/configure-data-match-need-rules.png "Definir regras")

O aviso **Necessita de Regras** sugere que não está definida nenhuma regra de correspondência para um par de correspondência. As regras de correspondência especificam a lógica pela qual será feita a correspondência de um par de entidades específico.

1. Para definir a sua primeira regra, abra o painel **Definição de Regra** ao selecionar a linha de correspondência correspondente na tabela de correspondências (1) e, depois, selecionar **Criar nova regra** (2).

   > [!div class="mx-imgBorder"]
   > ![Criar nova regra](media/configure-data-match-new-rule2.png "Criar nova regra")

2. No painel **Editar Regra**, configure as condições para essa regra. Cada condição é representada por duas linhas que incluem as seleções obrigatórias.

   > [!div class="mx-imgBorder"]
   > ![Painel Nova regra](media/configure-data-match-new-rule-condition.png "Painel Nova regra")

   Entidade/Campo (primeiro) - um atributo que será utilizado para a correspondência da primeira entidade de par de correspondência. Os exemplos podem incluir um número de telefone ou um endereço de e-mail. Escolha um atributo que provavelmente seja exclusivo do cliente.

   > [!TIP]
   > Evite fazer a correspondência com base nos atributos do tipo atividade. Por outras palavras, se um atributo parecer ser uma atividade, poderá ser um critério fraco para fazer a correspondência.  

   Entidade/Campo (Segundo) - um atributo que será utilizado para a correspondência da segunda entidade de par de correspondência.

   Normalizar - **Método de normalização**: estão disponíveis várias opções de normalização para os atributos selecionados. Por exemplo, remover a pontuação ou os espaços

   Para a normalização do Nome da Organização (Pré-visualização), poderá selecionar **Tipo (Telemóvel, Nome, Organização)**

   > [!div class="mx-imgBorder"]
   > ![Normalização-B2B](media/match-normalization-b2b.png "Normalização-B2B")

   Nível de precisão - o nível de precisão que será utilizado para esta condição. A definição de um nível de precisão para uma condição de correspondência pode ter dois tipos: **Básico** e **Personalizado**.  
   - Básico: fornece quatro opções para selecionar: Baixo, Médio, Alto e Exato. Selecione **Exato** para fazer a correspondências apenas dos registos com uma correspondência de 100%. Selecione um dos outros níveis para fazer a correspondência dos registos que não são 100% idênticos.
   - Personalizado: utilize o controlo de deslize para definir a percentagem personalizada com que os registos têm de corresponder ou introduza um valor no campo **Personalizado**. O sistema só irá fazer a correspondência com os registos que ultrapassam este limiar como pares de correspondência uniformes. Os valores no controlo de deslize variam entre 0 e 1. Assim, 0,64 representa 64%.

3. Selecione **Concluído** para guardar a regra.

### <a name="add-multiple-conditions"></a>Adicionar múltiplas condições

Para fazer a correspondência apenas se forem satisfeitas várias condições, adicione mais condições que estejam ligadas através de um operador AND.

1. No painel **Editar regra**, selecione **Adicionar condição**. Também pode eliminar condições ao selecionar o botão para remover junto a uma condição existente.

2. Selecione **Concluído** para guardar a regra.

## <a name="add-multiple-rules"></a>Adicionar múltiplas regras

Cada condição aplica-se a um único par de atributos, enquanto as regras representam conjuntos de condições. Para fazer a correspondência das suas entidades por diferentes conjuntos de atributos, poderá adicionar mais regras.

1. Nas informações de audiência, vá a **Dados** > **Unificar** > **Fazer corresponder**.

2. Selecione a entidade que pretende atualizar e selecione **Adicionar regras**.

3. Siga o procedimento conforme descrito em [Definir regras para o primeiro par de correspondência](#define-rules-for-your-first-match-pair).

> [!NOTE]
> A ordem das regras é importante. O algoritmo de correspondência tenta fazer a correspondência com base na primeira regra e avança para a segunda regra apenas se não forem identificadas correspondências na primeira regra.

## <a name="define-deduplication-on-a-match-entity"></a>Definir a duplicação sobre uma entidade correspondente

Juntamente com a especificação de regras de correspondência entre entidades, conforme descrito nas secções acima, também se podem especificar regras de duplicação. A *duplicação* é um processo. Identifica registos duplicados, funde-os num único registo, e liga todos os registos de origem a este registo fundido com identificações alternativas ao registo fundido.

Após identificação de um registo duplicado, esse registo será utilizado no processo de correspondência entre entidades. A duplicação é implementada ao nível da entidade e pode ser aplicada a todas as entidades utilizadas no processo de Correspondência.

### <a name="add-deduplication-rules"></a>Adicionar regras de duplicação

1. Nas informações de audiência, vá a **Dados** > **Unificar** > **Fazer corresponder**.

1. Na secção **Duplicados fundidos**, selecione **Definir entidades**.

1. Na secção **Preferências de fusão**, selecione as entidades a que pretende aplicar a duplicação.

1. Especificar como fundir os registos duplicados e escolher uma das três opções de fusão:
   - *Mais preenchidos*: Identifica o registo com os atributos mais preenchidos como o registo vencedor. Esta é a opção de fusão predefinida.
   - *Mais recentes*: Identifica o registo vencedor com base no mais recente. Requer uma data ou um campo numérico para definir a atualidade.
   - *Menos recente*: Identifica o registo vencedor com base no menos recente. Requer uma data ou um campo numérico para definir a atualidade.
 
   > [!div class="mx-imgBorder"]
   > ![Regras de duplicação etapa 1](media/match-selfconflation.png "Regras de duplicação etapa 1")
 
1. Uma vez selecionadas as entidades e estabelecida a sua preferência de fusão, selecionar **Criar nova regra** para definir as regras de duplicação a nível de entidade.
   - **Campo selecionado** lista todos os campos disponíveis dessa entidade em que pretende deduplicar os dados de origem.
   - Especificar as definições de normalização e precisão de forma semelhante à especificada na correspondência entre entidades cruzadas.
   - Pode definir condições adicionais, selecionando **Adicionar condição**.
 
   > [!div class="mx-imgBorder"]
   > ![Regras de duplicação etapa 2](media/match-selfconflation-rules.png "Regras de duplicação etapa 2")

  Pode criar múltiplas regras de duplicação para uma entidade. 

1. A execução do processo de correspondência agrupa agora os registos com base nas condições definidas nas regras de duplicação. Após agrupar os registos, a política de fusão é aplicada para identificar o registo vencedor.

1. Este registo de vencedores é então passado para a correspondência de entidade cruzada, juntamente com os registos de não vencedor (por exemplo, IDs alternativos) para melhorar a qualidade de correspondência.

1. Quaisquer regras de correspondência personalizadas definidas para coincidir sempre e nunca se sobrepor às regras de duplicação. Se uma regra de duplicação identificar registos correspondentes, e uma regra de correspondência personalizada for definida para nunca corresponder a esses registos, então estes dois registos não terão correspondência.

1. Depois de executar o processo de correspondência, verá as estatísticas de duplicação.
   
> [!NOTE]
> A especificação das regras de duplicação não é obrigatória. Se tais regras não forem configuradas, são aplicadas as regras definidas pelo sistema. Colapsam todos os registos que partilham a mesma combinação de valores (correspondência exata) da chave primária e os campos das regras de correspondência num único registo antes de passar os dados da entidade à correspondência entre entidades para um melhor desempenho e sanidade do sistema.

## <a name="run-your-match-order"></a>Executar a ordem de correspondência

Após definir as regras de correspondência, incluindo as regras de correspondência entre entidades e de duplicação, pode executar a ordem de correspondência. Na página **Corresponder**, selecione **Executar** para iniciar o processo. A execução do algoritmo de correspondência poderá demorar algum tempo. Não poderá alterar as propriedades na página **Corresponder** até o processo de correspondência ser concluído. Encontrará a entidade de perfil do cliente unificado que foi criada na página **Entidades**. A sua entidade de cliente unificada é denominada **ConflationMatchPairs : CustomerInsights**.

Para efetuar alterações adicionais e executar novamente o passo, poderá cancelar uma correspondência em curso. Selecione o texto **A atualizar...** e selecione **Cancelar tarefa** na parte inferior do painel lateral apresentado.

Quando o processo de correspondência estiver concluído, o texto **A atualizar...** mudará para **Com êxito** e poderá voltar a utilizar toda a funcionalidade da página.

O primeiro processo de correspondência resulta na criação de uma entidade principal unificada. Todas as execuções de correspondência subsequentes resultam na expansão dessa entidade.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="deduplication-output-as-an-entity"></a>Saída de eliminação de duplicados como uma entidade
Além da entidade mestre unificada criada como parte da correspondência entre entidades, o processo de eliminação de duplicados gera também uma nova entidade para cada entidade a partir da ordem de correspondência para identificar os registos de eliminação de duplicados. Estas entidades podem ser encontradas juntamente com **ConflationMatchPairs:CustomerInsights** na secção **Sistema** na página **Entidades**, com o nome **Deduplication_Datasource_Entity**.

Uma entidade de saída de eliminação de duplicados contém as seguintes informações:
- IDs / Chaves
  - Campo de chave primária e o respetivo campo de IDs alternativos. O campo de IDs alternativos consiste em todos os IDs alternativos identificados para um registo.
  - O campo Deduplication_GroupId mostra o grupo ou o cluster identificado dentro de uma entidade que agrupa todos os registos semelhantes com base nos campos de eliminação de duplicados especificados. Isto é utilizado para fins de processamento do sistema. Se não existirem regras de eliminação de duplicados manuais especificadas e se aplicarem regras de eliminação de duplicados definidas pelo sistema, poderá não encontrar este campo na entidade de saída de eliminação de duplicados.
  - Deduplication_WinnerId: este campo contém o ID de vencedor dos grupos ou clusters identificados. Se Deduplication_WinnerId é o mesmo que o valor da Chave primária para um registo, significa que o registo é o registo vencedor.
- Campos usados para definir as regras de eliminação de duplicados.
- Campos Regra e Pontuação para denotar quais as regras de eliminação de duplicados foram aplicadas e a pontuação devolvida pelo algoritmo correspondente.

## <a name="review-and-validate-your-matches"></a>Rever e validar as suas correspondências

Avalie a qualidade dos seus pares de correspondência e refine-os:

- Na página **Corresponder**, encontrará dois mosaicos a mostrar as informações iniciais sobre os seus dados.

  - **Clientes exclusivos**: mostra o número de perfis exclusivos que o sistema identificou.
  - **Registos correspondidos**: mostra o número de correspondências em todos os seus pares de correspondência.

- Na tabela **Ordem de correspondência**, poderá avaliar os resultados de cada par de correspondência ao comparar o número de registos com origem nesta entidade de pares de correspondência com a percentagem de registos correspondidos com êxito.

- Na secção **Regras** de uma entidade na tabela **Ordem de correspondência**, encontrará a percentagem de registos correspondidos com êxito a nível da regra. Ao selecionar o símbolo de tabela junto a uma regra, poderá ver todos estes registos a nível da regra. Recomendamos que reveja um subconjunto dos registos para validar que foram correspondidos corretamente.

- Experimente com diferentes limiares de precisão à volta das suas condições para identificar o valor ideal.

  1. Selecione as reticências (...) da regra do par de correspondência que pretende experimentar e selecione **Editar**.

  2. Selecione a condição com a qual pretende experimentar. Cada critério é representado por uma linha no painel **Regra de correspondência**.

  3. O que verá na página **Pré-visualização de critérios** depende do nível de precisão selecionado para uma condição. Localize o número de registos correspondidos e não correspondidos para a condição selecionada.

     Compreenda os efeitos de diferentes níveis de limiar. Pode comparar o número de registos que serão correspondidos em cada um dos níveis de limiar e ver os registos em cada opção. Selecione cada um dos mosaicos e reveja os dados na secção de tabela.

## <a name="optimize-your-matches"></a>Otimizar as suas correspondências

Aumente a qualidade ao reconfigurar alguns dos parâmetros de correspondência:

- **Alterar a ordem de correspondência** ao selecionar **Editar** e alterar os campos de ordem de correspondência.

  > [!div class="mx-imgBorder"]
  > ![Editar a ordem de correspondência dos dados](media/configure-data-match-order-edit.png "Editar a ordem de correspondência dos dados")

- **Alterar a ordem das suas regras** se definiu várias regras. Pode reordenar as regras de correspondência ao selecionar as opções **Mover Para Cima** e **Mover Para Baixo** na grelha de regras de correspondência.

  > [!div class="mx-imgBorder"]
  > ![Alterar ordem das regras](media/configure-data-change-rule-order.png "Alterar ordem das regras")

- **Duplicar as regras** se definiu uma regra de correspondência e pretende criar uma regra semelhante com modificações. Poderá fazê-lo ao selecionar **Duplicar**.

  > [!div class="mx-imgBorder"]
  > ![Duplicar uma regra](media/configure-data-duplicate-rule.png "Duplicar uma regra")

- **Desativar uma regra** para manter uma regra de correspondência, excluindo-a do processo de correspondência.

  > [!div class="mx-imgBorder"]
  > ![Desativar uma regra](media/configure-data-deactivate-rule.png "Desativar uma regra")

- **Editar as suas regras** ao selecionar o símbolo **Editar**. Pode aplicar as seguintes alterações:

  - Alterar os atributos para uma condição: selecione novos atributos na linha de condição específica.
  - Alterar o limiar para uma condição: ajuste o controlo de deslize de precisão.
  - Alterar o método de normalização de uma condição: atualize o método de normalização.

## <a name="specify-your-custom-match-records"></a>Especificar os seus registos de correspondência personalizados

Pode especificar as condições que determinados registos devem corresponder sempre ou nunca. Estas regras podem ser carregadas em massa para o processo de correspondência.

1. Selecione a opção **Correspondência personalizada** no ecrã **Ordem de correspondência**.

   > [!div class="mx-imgBorder"]
   > ![Criar uma correspondência personalizada](media/custom-match-create.png "Criar uma correspondência personalizada")

2. Se não tiver entidades carregadas, verá uma nova caixa de diálogo **Correspondência personalizada** que exige o preenchimento de alguns detalhes. Se forneceu estes detalhes anteriormente, avance para o passo 8.

   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo Nova correspondência personalizada](media/custom-match-new-dialog-box.png "Caixa de diálogo Nova correspondência personalizada")

3. Selecione **Preencher o modelo** para obter um ficheiro de modelo que especifique os registos a partir dos quais as entidades devem corresponder sempre ou nunca corresponder. Terá de preencher separadamente os registos "corresponder sempre" e "nunca corresponder" em dois ficheiros diferentes.

4. O modelo contém campos para especificar a entidade e os valores de chave primária da entidade que serão utilizados na correspondência personalizada. Por exemplo, se pretende que a chave primária 12345 da entidade Vendas faça sempre a correspondência com a chave primária 34567 da entidade Contacto, terá de especificar o seguinte:
    - Entidade1: Vendas
    - Entity1Key: 12345
    - Entidade2: Contacto
    - Entity2Key: 34567

   O mesmo ficheiro de modelo pode especificar registos de correspondência personalizados de várias entidades.
   
   Se pretender especificar a correspondência personalizada para a eliminação de duplicados numa entidade, forneça a mesma entidade que a Entidade1 e a Entidade2 e defina os diferentes valores chave primários.

5. Depois de adicionar todas as substituições que pretende aplicar, guarde o ficheiro de modelo.

6. Aceda a **Dados** > **Origens de dados** e ingere os ficheiros do modelo como novas entidades. Depois de ingeridos, pode utilizá-los para especificar a configuração Corresponder.

7. Após o carregamento dos ficheiros e de as entidades estarem disponíveis, selecione novamente a opção **Correspondência personalizada**. Verá opções para especificar as entidades que pretende incluir. Selecione as entidades obrigatórias a partir do menu pendente.

   > [!div class="mx-imgBorder"]
   > ![Substituições de correspondências personalizadas](media/custom-match-overrides.png "Substituições de correspondências personalizadas")

8. Selecione as entidades que pretende utilizar para **Corresponder sempre** e **Nunca corresponder**, e selecione **Concluído**.

9. Selecione **Guardar** na página **Corresponder** para a configuração da correspondência personalizada que acabou de configurar.

10. Selecione **Executar** na página **Corresponder** para iniciar o processo de correspondência e para a configuração da correspondência personalizada entrar em vigor. Quaisquer regras correspondentes do sistema são substituídas pelo conjunto de configurações.

11. Depois de concluída a correspondência, pode verificar a entidade **ConflationMatchPair** para confirmar se as substituições são aplicadas nas correspondências de combinação.

## <a name="next-step"></a>Passo seguinte

Depois de concluir o processo de correspondência para, pelo menos, um par de correspondência, poderá resolver as possíveis contradições nos seus dados através do tópico [**Intercalar**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
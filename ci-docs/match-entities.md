---
title: Condições de correspondência para a unificação de dados
description: Fazer corresponder entidades para criar perfis unificados de clientes.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: e3e4e37d5b4c9caf2520a789d5f78ef33b491793
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139717"
---
# <a name="match-conditions-for-data-unification"></a>Condições de correspondência para a unificação de dados

Este passo na unificação define a ordem de correspondência e as regras para correspondência entre entidades. Este passo necessita de pelo menos duas entidades.

> [!NOTE]
> Depois de criar as condições de combinação e selecionar **Seguinte**, não pode remover uma entidade ou atributo selecionado. Se necessário, selecione **Voltar** para rever as entidades e atributos selecionados antes de continuar.

## <a name="include-enriched-entities-preview"></a>Incluir entidades melhoradas (pré-visualização)

Se tiver melhorado entidades ao nível origem de dados para ajudar a melhorar os resultados de unificação, selecione-as. Para obter mais informações, consulte [Melhoramento para origens de dados](data-sources-enrichment.md). Se tiver selecionado entidades melhoradas na página **Registos duplicados**, não necessita de as selecionar novamente.

1. Na página **Condições correspondentes**, selecione **Utilizar entidades melhoradas** na parte superior da página.

1. A partir do painel **Utilizar entidades melhoradas**, escolha uma ou mais entidades melhoradas.

1. Selecionar **Concluído**.

## <a name="specify-the-match-order"></a>Especificar a ordem de correspondência

Cada correspondência unifica duas ou mais entidades numa única entidade consolidada. Ao mesmo tempo, mantém os registos exclusivos dos clientes. A ordem de correspondência indica a ordem em que o sistema tenta corresponder os registos.

> [!IMPORTANT]
> A primeira entidade na lista é chamada entidade primária. A entidade primária serve como base para os perfis unificados conjunto de dados. Serão adicionadas a esta entidade, entidades adicionais que estão selecionadas.
>
> Considerações importantes:
>
> - Escolha a entidade com os dados de perfil mais completos e fiáveis acerca dos clientes como a entidade primária.
> - Escolha como entidade principal a entidade que tenha vários atributos em comum com outras entidades (por exemplo, nome, número de telefone ou endereço de e-mail).

1. Na página **Condições correspondentes**, utilize as setas para cima e para baixo para mover as entidades pela ordem que pretende ou arraste-as e largue-as. Por exemplo, selecione **Contacts:eCommerce** como a entidade principal e **CustomerLoyalty:Loyalty** como entidade secundária.

1. Para fazer com que cada registo na entidade tenha um cliente exclusivo, independentemente de ser encontrada uma correspondência, selecione **Incluir todos os registos**. Quaisquer dados nesta entidade que não corresponderem aos registos de quaisquer outras entidades serão incluídos no perfil unificado. Os dados que não têm uma correspondência são denominados singletons.
  
A entidade primária *Contacts:eCommerce* é correspondida com a entidade seguinte *CustomerLoyalty:Loyalty*. O conjunto de dados que resulta do primeiro passo de correspondência é correspondido com a seguinte entidade se tiver mais do que duas entidades.

:::image type="content" source="media/m3_match.png" alt-text="Captura de ecrã da ordem de correspondência selecionada para as entidades." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definir regras para pares de correspondência

As regras de correspondência especificam a lógica pela qual será feita a correspondência de um par de entidades específico. Uma regra consiste numa ou mais condições.

O aviso junto de um nome de entidade significa que não está definida nenhuma regra de correspondência para um par de correspondências.

1. Selecione **Adicionar regra** para um par de entidades definir regras de correspondência.

1. No painel **Adicionar regra**, configure as condições para a regra.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Captura de ecrã do painel Adicionar nota":::

   - **Selecionar Entidade/Campo (primeira linha)**: escolha uma entidade relacionada e um atributo para especificar uma propriedade de registo que seja provavelmente única para um cliente. Por exemplo, um número de telefone ou endereço de e-mail. Evite corresponder por atributos do tipo de atividade. Por exemplo, um ID de compra provavelmente não encontrará correspondência noutros tipos de registo.

   - **Selecionar Entidade/Campo (segunda linha)**: escolha um atributo relacionado com o atributo da entidade especificada na primeira linha.

   - **Normalizar**: selecione a partir das seguintes opções de normalização para os atributos selecionados.
     - **Números**: converte outros sistemas numéricos, como a numeração romana em algarismos árabes. *VIII* torna-se *8*.
     - **Símbolos**: remove todos os símbolos e caracteres especiais. *Head&Shoulder* torna-se *HeadShoulder*.
     - **Texto para minúscula**: converte todos os caracteres em minúsculas. *TODAS MAIÚSCULAS e Título* torna-se *todas maiúsculas e título*.
     - **Tipo (Telefone, Nome, Endereço, Organização)**: padroniza nomes, títulos, números de telefone, endereços e organizações.
     - **Unicode para ASCII**: converte a notação unicode para caracteres ASCII. */u00B2* torna-se *2*.
     - **Espaço em branco**: remove todos os espaços. *Olá   Mundo* torna-se *OláMundo*.

   - **Precisão**: defina o nível de precisão para aplicar esta condição.
     - **Básico**: escolha entre *Baixo (30%)*, *Médio (60%)*, *Alto (80%)* e *Exato (100%)*. Selecione **Exato** para corresponder apenas registos que correspondam a 100 por cento.
     - **Personalizar**: defina uma percentagem que os registos têm de corresponder. O sistema só vai corresponder os registos que ultrapassam este limiar.

   - **Nome**: nome da regra.

1. Para corresponder às entidades apenas se os atributos cumprirem a várias condições, selecione condição **Adicionar** > **Adicionar condição** para adicionar mais condições a uma regra de correspondência. As condições estão ligadas a um operador E lógico e, portanto, só são executadas se todas as condições forem satisfeitas.

1. Opcionalmente, considere opções avançadas, tais como [exceções](#add-exceptions-to-a-rule) ou [condições de correspondência personalizadas](#specify-custom-match-conditions).

1. Selecione **Concluído** para finalizar a regra.

1. Opcionalmente, [adicione mais regras](#add-rules-to-a-match-pair).

1. Clique em **Seguinte**.

> [!div class="nextstepaction"]
> [Passo seguinte: Unificar campos](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Adicionar regras a um par de correspondências

As regras de correspondência representam conjuntos de condições. Para corresponder entidades por condições com base em vários atributos, adicione mais regras.

1. Selecione **Adicionar regra** na entidade à que pretende adicionar regras.

1. Siga os passos em [Definir regras para pares de correspondência](#define-rules-for-match-pairs).

> [!NOTE]
> A ordem das regras é importante. O algoritmo correspondente tenta corresponder a um determinado registo de cliente com base na sua primeira regra e continua para a segunda regra se não tiverem sido identificadas correspondências com a primeira regra.

## <a name="advanced-options"></a>Opções avançadas

### <a name="add-exceptions-to-a-rule"></a>Adicionar exceções a uma regra

Na maioria dos casos, a correspondência de entidades leva a perfis de utilizador exclusivos com dados consolidados. Para abordar dinamicamente casos raros de falsos positivos e falsos negativos, pode definir exceções para uma regra de correspondência. As exceções são aplicadas após o processamento das regras de correspondência e evitam a correspondência de todos os registos, as quais preenchem os critérios de exceção.

Por exemplo, se a sua regra de correspondência combinar apelido, cidade e data de nascimento, o sistema identificaria gémeos com o mesmo apelido que vivem na mesma cidade que o mesmo perfil. Pode especificar uma exceção que não corresponda aos perfis se os nomes próprios nas entidades que combinar não forem os mesmos.

1. No painel **Editar regra**, selecione **Adicionar** > **Adicionar exceção**.

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

1. Selecione **Personalizado**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Botão personalizado":::

1. Escolha o **Tipo de personalização** e selecione **Transferir modelo**. É necessário um modelo separado para cada opção de correspondência.

1. Abra o ficheiro de modelo transferido e preencha os detalhes. O modelo contém campos para especificar a entidade e os valores de chave primária da entidade que serão utilizados na correspondência personalizada. Por exemplo, se pretender que a chave primária *12345* da entidade *Vendas* corresponda sempre à chave primária *34567* da entidade *Contacto*, preencha o modelo:
    - Entidade1: Vendas
    - Entity1Key: 12345
    - Entidade2: Contacto
    - Entity2Key: 34567

   O mesmo ficheiro de modelo pode especificar registos de correspondência personalizados de várias entidades.

   Se pretender especificar a correspondência personalizada para a eliminação de duplicados numa entidade, forneça a mesma entidade que a Entidade1 e a Entidade2 e defina os diferentes valores chave primários.

1. Depois de adicionar todas as substituições, guarde o ficheiro de modelo.

1. Aceda a **Dados** > **Origens de dados** e ingere os ficheiros do modelo como novas entidades.

1. Depois de carregar os ficheiros, selecione novamente a opção **Personalizar**. Selecione as entidades obrigatória no menu pendente e selecione **Concluído**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de ecrã da caixa de diálogo para escolher substituições para um cenário de correspondência personalizada.":::

1. A aplicação da correspondência personalizada depende da opção de correspondência que pretende utilizar.

   - Para **Corresponder sempre** ou **Nunca corresponder**, avance para o passo seguinte.
   - Para **Ignorar** ou **Mapeamento de aliases**, selecione **Editar** numa regra de correspondência existente ou crie uma nova regra. No menu pendente Normalizações, escolha a opção **Ignorar personalizado** ou **Mapeamento de aliases** e selecione **Concluído**.

1. Selecione **Concluído** no painel **Personalizado** para aplicar a configuração de correspondência personalizada.

> [!div class="nextstepaction"]
> [Passo seguinte: Unificar campos](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Atividades de clientes ou contactos empresariais
description: Defina as atividades de clientes ou contactos empresariais e veja-as numa linha cronológica nos perfis dos clientes.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723795"
---
# <a name="customer-or-business-contact-activities"></a>Atividades de clientes ou contactos empresariais

As atividades de cliente são ações ou eventos executados por clientes ou contactos empresariais. Por exemplo, transações, duração da chamada de suporte, avaliações do Web site, compras ou devoluções. Estas atividades são contidas numa ou mais origens de dados. Com o Customers Insights, consolide as atividades dos seus clientes a partir destas [origens de dados](data-sources.md) e associe-as a perfis de cliente. Estas atividades aparecem cronologicamente numa linha cronológica no perfil de cliente. Inclua a linha cronológica em aplicações Dynamics 365 com a solução de [suplemento do Cartão de Cliente](customer-card-add-in.md).

## <a name="define-a-customer-activity"></a>Definir atividade do cliente

Uma entidade tem de ter, pelo menos, um atributo do tipo **Data** a ser incluído na linha cronológica. O controlo **Adicionar atividade** está desativado se não for encontrada nenhuma entidade.

1. Aceda a **Dados** > **Atividades**.

1. Selecione **Adicionar atividade** para iniciar a experiência guiada.

1. No passo **Dados de atividade**, introduza as seguintes informações:

   - **Nome da atividade**: selecione um nome para a sua atividade.
   - **Entidade de atividade**: selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Selecione o campo que identifica exclusivamente um registo. Não deve conter valores duplicados, valores vazios ou valores em falta.

     > [!NOTE]
     > A Chave primária de cada linha tem de permanecer consistente em todos as atualizações de origem de dados. Se a Chave primária de uma linha for atualizada numa atualização de origem de dados, cria duplicados na entidade Atividade de saída. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configurar os dados de atividade com nome, entidade e chave primária.":::

1. Selecione **Seguinte**.

1. No passo **Relação**, selecione **Adicionar relação** para ligar os seus dados de atividade ao registo de cliente correspondente. Este passo visualiza a ligação entre entidades.  

   - **Chave externa**: campo externo na sua entidade de atividade que será utilizado para estabelecer uma relação com outra entidade.
   - **Nome da entidade de destino**: entidade de cliente de origem correspondente com a qual a sua entidade de atividade estará relacionada. Só pode relacionar-se com entidades de clientes de origem que são utilizadas no processo de unificação de dados.
   - **Nome da relação**: se já existir uma relação entre esta entidade de atividade e a entidade cliente de origem selecionada, o nome da relação estará em modo só de leitura. Se não existir essa relação, uma nova relação será criada com o nome que fornecer nesta caixa.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definir a relação entre entidades.":::

   > [!TIP]
   > Em ambientes B2B, pode selecionar entre entidades de conta e outras entidades. Se selecionar uma entidade de conta, o caminho da relação é automaticamente definido. Para outras entidades, tem de definir o caminho de relação sobre uma ou mais entidades intermediárias até chegar a uma entidade de conta.

1. Selecione **Aplicar** para criar a relação.

1. Selecione **Seguinte**.

1. No passo **Unificação de atividades**, escolha o evento de atividade e a hora de início da sua atividade.
   - **Campos necessários**
      - **Atividade do evento**: campo que é o evento para esta atividade.
      - **Carimbo de data/hora**: campo que representa a hora de início da sua atividade.

   - **Campos opcionais**
      - **Detalhe adicional**: campo com informações relevantes para esta atividade.
      - **Ícone**: ícone que melhor representa este tipo de atividade.
      - **Endereço Web**: campo que contém um URL com informações sobre esta atividade. Por exemplo, o sistema transacional que fornece esta atividade. Este URL pode ser qualquer campo a partir da origem de dados ou pode ser construído como um novo campo usando uma transformação do Power Query. Os dados de URL serão armazenados na entidade de *Atividade Unificada*, que pode ser consumida a jusante utilizando [APIs](apis.md).

   - **Mostrar na linha cronológica**
      - Escolha se pretende mostrar esta atividade na vista de linha cronológica dos perfis dos clientes. Selecione **Sim** para mostrar a atividade na linha cronológica ou **Não** para ocultá-la.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especificar os dados de atividade do cliente numa entidade de Atividade Unificada.":::

1. Selecione **Seguinte** para escolher o tipo de atividade ou selecione **Terminar e rever** para guardar a atividade agora com o tipo de atividade definido como **Outro**.

1. No passo **Tipo de Atividade**, escolha o tipo de atividade e selecione opcionalmente se pretende mapear semântica alguns dos tipos de atividade para utilização noutras áreas do Customer Insights. Atualmente, os tipos de atividade *Comentários*, *Lealdade*, *SalesOrder*, *SalesOrderLine* e *Subscrição* suportam a semântica depois de concordar mapear os campos. Se um tipo de atividade não for relevante para a nova atividade, pode escolher *Outro* ou *Criar novo* para um tipo de atividade personalizada.

1. Selecione **Seguinte**.

1. No passo **Revisão**, verifique as suas seleções. Regresse a qualquer um dos passos anteriores e atualize as informações, se necessário.

1. Selecione **Guardar atividade** para aplicar as suas alterações e selecione **Concluído** para regressar a **Dados** > **Atividades**. A atividade criada é apresentada.

1. Depois de criar todas as suas atividades, selecione **Executar** para processá-las.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Gerir atividades de cliente existentes

Vá para **Dados** > **Atividades** para ver as suas atividades guardadas, a entidade de origem, o tipo de atividade e se foram incluídas na linha cronológica do cliente. Pode ordenar a lista de atividades por qualquer coluna ou utilizar a caixa de pesquisa para localizar a atividade que pretende gerir.

Selecione uma atividade para ver as ações disponíveis.

- **Editar** a atividade para alterar a sua configuração. A configuração é aberta no passo de revisão. Depois de alterar a configuração, selecione **Guardar atividade** e, em seguida, selecione **Executar** para processar as alterações.
- **Mudar o nome** da atividade. Selecione **Guardar** para aplicar as alterações.
- **Eliminar** a atividade. Para eliminar mais de uma atividade ao mesmo tempo, selecione as atividades e, em seguida, **Eliminar**. Confirme a eliminação.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ver linhas cronológicas de atividades nos perfis de clientes

1. Se selecionou **Mostrar na linha cronológica da atividade** na configuração da atividade, vá para **Clientes** e selecione o perfil de cliente para ver as atividades do cliente na secção **Linha cronológica da atividade**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Veja as atividades configuradas nos Perfis de Clientes.":::

1. Para filtrar as atividades na linha cronológica de atividade:

   - Selecione um ou mais ícones de atividade para refinar os seus resultados para incluir apenas os tipos selecionados.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtre as atividades por tipo utilizando os ícones.":::

   - Selecione **Filtro** para abrir um painel de filtros para configurar os filtros da linha cronológica. Filtre por *ActivityType* e/ou *Date*. Selecione **Aplicar**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilize o painel de filtros para configurar as condições do filtro.":::

> [!NOTE]
> Os filtros de atividades são removidos quando deixa o perfil do cliente. Tem de aplicá-los sempre que abrir um perfil de cliente.

## <a name="define-a-contact-activity"></a>Definir atividade do contacto

Para contas empresariais (B2B), utilize uma entidade *ContactProfile* para capturar atividades de contactos. Pode ver cujo contacto foi responsável por cada atividade numa conta, na linha cronológica da atividade. A maioria dos passos segue a configuração do mapeamento de atividades do cliente.

   > [!NOTE]
   > Para definir uma atividade ao nível do contacto, deve ser criada uma entidade *ContactProfile* quer como [perfil de contacto unificado](data-unification-contacts.md) ou através de [mapeamento semântico](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Deve ter os atributos **AccountID** e **ContactID** para cada registo nos seus dados de atividade.
  
1. Aceda a **Dados** > **Atividades**.

1. Selecione **Adicionar atividade**.

1. No passo **Dados de atividade**, introduza as seguintes informações:

   - **Nome da atividade**: selecione um nome para a sua atividade.
   - **Entidade de atividade**: selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Selecione o campo que identifica exclusivamente um registo. Não deve conter valores duplicados, valores vazios ou valores em falta.

     > [!NOTE]
     > A Chave primária de cada linha tem de permanecer consistente em todos as atualizações de origem de dados. Se a Chave primária de uma linha for atualizada numa atualização de origem de dados, cria duplicados na entidade Atividade de saída. 


1. No passo **Relações**, crie uma relação indireta entre os dados de origem da sua atividade para as contas, utilizando os seus dados de contacto como uma entidade intermediária. Para mais informações, consulte os [caminhos de relação direta e indireta](relationships.md#relationship-paths).
   - Relação de exemplo para uma atividade denominada *Compras*:
      - **Dados de Atividade da Origem das Compras** > **Dados do Contacto** no atributo **ContactID**
      - **Dados do Contacto** > **Dados da Conta** no atributo **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Configuração de uma relação de exemplo.":::

1. Depois de configurar as relações, selecione **Seguinte** e conclua a configuração do mapeamento da sua atividade. Para obter os passos detalhados sobre a criação da atividade, consulte [definir uma atividade de cliente](#define-a-customer-activity).

1. Execute os seus mapeamentos de atividades.

1. As suas atividades de nível de contacto estarão agora visíveis na linha cronológica do seu cliente.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultado final depois de configurar as atividade do contacto":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtragem da linha cronológica das atividades a nível do contacto

Depois de configurar um mapeamento de atividade a nível do contacto e executá-lo, será atualizada a cronologia de atividades para os seus clientes. Inclui os respetivos IDs ou nomes, consoante a sua configuração *ContactProfile* para as atividades nas quais atuaram. Poderá filtrar as atividades por contactos na linha cronológica para ver contactos específicos em que está interessado. Além disso, pode ver todas as atividades que não estão atribuídas a um contacto específico ao selecionar **Atividades não mapeadas para um Contacto**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opções de filtragem disponíveis para as atividades a nível do contacto.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]

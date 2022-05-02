---
title: Relações entre entidades e caminhos de entidades
description: Criar e gerir relações entre entidades a partir de múltiplas origens de dados.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647324"
---
# <a name="relationships-between-entities"></a>Relação entre entidades

As relações ligam entidades e definem um gráfico dos seus dados quando as entidades partilham um identificador comum, uma chave externa. Esta chave externa pode ser referenciada de uma entidade para outra. As entidades ligadas permitem a definição de segmentos e medidas com base em várias origens de dados.

Existem três tipos de relações: 
- Relações de sistema não editáveis, criadas pelo sistema como parte do processo de unificação de dados
- Relações herdados não editáveis, que são criadas automaticamente a partir da ingestão de origens de dados 
- Relações personalizadas editáveis, criadas e configuradas pelos utilizadores

## <a name="non-editable-system-relationships"></a>Relações de sistema não editáveis

Durante a unificação de dados, as relações de sistema são criadas automaticamente com base em correspondência inteligente. Estas relações ajudam a relacionar os registos do perfil de cliente com outros registos correspondentes. O diagrama que se segue ilustra a criação de três relações baseados em sistema. A entidade de cliente é compatível com outras entidades para produzir a entidade unificada de *Cliente*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama com caminhos de relação para a entidade de cliente com três relações 1-n.":::

- A **relação *CustomerToContact*** foi criada entre a entidade *Cliente* e a entidade *Contacto*. A entidade *Cliente* obtém o campo de chave **Contact_contactID** para estabelecer relação com o campo de chave da entidade *Contacto* **contactID**.
- A **relação *CustomerToAccount*** foi criada entre a entidade *Cliente* e a entidade *Conta*. A entidade *Cliente* obtém o campo de chave **Account_accountID** para estabelecer relação com o campo de chave da entidade *Conta* **accountID**.
- A **relação *CustomerToWebAccount*** foi criada entre a entidade *Cliente* e a entidade *WebAccount*. A entidade *Cliente* obtém o campo de chave **WebAccount_webaccountID** para estabelecer relação com o campo de chave da entidade *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Relações herdadas não editáveis

Durante o processo de ingestão de dados, o sistema verifica as origens de dados para relações existentes. Se não existe qualquer relação, o sistema cria-as automaticamente. Estas relações também são utilizadas em processos a jusante.

## <a name="create-a-custom-relationship"></a>Criar uma relação personalizada

A relação consiste numa *entidade fornecida com o programa* que contém a chave externa e uma *entidade de destino* a que a entidade fornecida com o programa aponta. 

1. Aceda a **Dados** > **Relações**.

2. Entidade de destino **Nova relação**.

3. No painel **Nova relação**, forneça as seguintes informações:

   :::image type="content" source="media/relationship-add.png" alt-text="Painel lateral de nova relação com campos de entrada vazios.":::

   - **Nome da relação**: nome que reflete o propósito da relação. Exemplo: CustomerToSupportCase.
   - **Descrição**: descrição da relação.
   - **Entidade fornecida com o programa**: entidade que é utilizada como origem na relação. Exemplo: SupportCase.
   - **Entidade de destino**: entidade que é utilizada como destino na relação. Exemplo: Customer.
   - **Cardinalidade fornecida com o programa**: especifique a cardinalidade da entidade fornecida com o programa. Cardinalidade descreve o número de elementos possíveis num conjunto. Está sempre relacionado com a cardinalidade de destino. Pode escolher entre **Um** e **Muitos**. Só são suportadas relações muitos-para-um e um-para-um.  
     - Muitos-para-um: vários registos fornecidos com o programa podem relacionar-se com um registo de destino. Exemplo: vários casos de suporte de um único cliente.
     - Um-para-um: um único registo fornecido com o programa relaciona-se com um registo de destino. Exemplo: um ID de fidelização para um único cliente.

     > [!NOTE]
     > É possível criar relações muitos-para-muitos utilizando duas relações muitos-para-um e uma entidade de ligação, a qual liga a entidade fornecida com o programa e a entidade de destino.

   - **Cardinalidade de destino**: selecione a cardinalidade dos registos da entidade de destino. 
   - **Campo de chave fornecida com o programa**: o campo de chave externa na entidade fornecida com o programa. Exemplo: SupportCase poderia utilizar CaseID como um campo de chave externa.
   - **Campo de chave de destino**: o campo de chave da entidade de destino. Exemplo que o Cliente poderia utilizar o campo de chave **CustomerID**.

4. Selecione **Guardar** para criar a relação personalizada.

## <a name="set-up-account-hierarchies"></a>Configurar hierarquias de contas

Os ambientes configurados para utilizar contas empresariais como audiência alvo principal podem configurar hierarquias de contas para contas empresariais relacionadas. Por exemplo, uma empresa que tem unidades de negócio separadas. 

As organizações criam hierarquias de contas para gerir melhor as contas e as suas relações entre si. O Customer Insights suporta hierarquias de contas principais e subordinadas que já existem nos dados do cliente ingeridos. Por exemplo, contas do Dynamics 365 Sales. Estas hierarquias podem ser configuradas na página **Relações**.

1. Aceda a **Dados** > **Relações**.
1. Selecione o separador **Hierarquia de contas**.
1. Selecione **Nova hierarquia de contas**. 
1. No painel **Hierarquia de contas**, forneça um nome para a hierarquia. O sistema cria um nome para a entidade de saída. Pode alterar o nome da entidade do nome de saída.
1. Selecione a entidade que contém a sua hierarquia de contas. Encontra-se geralmente na mesma entidade que contém as contas.
1. Selecione o **ID da Conta** e o **ID Principal da Conta** da entidade selecionada 
1. Selecione **Guardar** para aplicar as definições e finalizar a hierarquia de contas.

## <a name="view-relationships"></a>Ver relações

A página Relações lista todas as relações que foram criadas. Cada linha representa uma relação, que inclui também detalhes sobre a entidade fornecida com o programa, a entidade de destino e a cardinalidade. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de relações e opções na barra de ação da página Relações.":::

Esta página oferece um conjunto de opções para relações existentes e novas: 
- **Nova Relação**: [Criar uma relação personalizada](#create-a-custom-relationship).
- **Visualizador**: [Explore o visualizador de relações](#explore-the-relationship-visualizer) para ver um diagrama de rede de relações existentes e respetiva cardinalidade.
- **Filtrar por**: escolha o tipo de relações a apresentar na lista.
- **Pesquisar relações**: utilize uma pesquisa baseada em texto sobre as propriedades das relações.

### <a name="explore-the-relationship-visualizer"></a>Explore o visualizador de relações

O visualizador de relações mostra um diagrama de rede de relações existentes entre as entidades ligadas e a respetiva cardinalidade. Também visualiza o caminho da relação.

Para personalizar a vista, pode alterar a posição das caixas arrastando-as na tela.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de ecrã do diagrama de rede do visualizador de relações com ligações entre entidades relacionadas.":::

Opções disponíveis: 
- **Exportar como imagem**: guarde a vista atual como um ficheiro de imagem.
- **Alterar para esquema horizontal/vertical**: altere o alinhamento das entidades e relações.
- **Editar**: atualize as propriedades de relações personalizadas no painel de edição e guarde as alterações.

## <a name="relationship-paths"></a>Caminhos da relação

Um caminho da relação descreve as entidades que estão ligadas a relações entre uma entidade de origem e uma entidade de destino. É usado na criação de um segmento ou uma medida que inclui outras entidades que não a entidade de perfil unificado e existem múltiplas opções para chegar à entidade de perfil unificado. 

Um caminho de relação informa o sistema sobre que relações aceder à entidade de perfil unificado. Diferentes caminhos de relações podem produzir resultados diferentes.

Por exemplo, a entidade *eCommerce_eCommercePurchases* tem a seguinte relação com a entidade de *Cliente* de perfil unificado:

- eCommerce_eCommercePurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente 

Um caminho de relação determina que entidades pode usar ao criar regras para medidas ou segmentos. Escolher a opção com o caminho de relação mais longo provavelmente produzirá menos resultados porque os registos correspondentes precisam de fazer parte de todas as entidades. Neste exemplo, um cliente tem de ter comprado bens através de comércio eletrónico (eCommerce_eCommercePurchases), num ponto de venda (POS_posPurchases) e participar no nosso programa de fidelização (loyaltyScheme_loyCustomers). Ao escolher a primeira opção, provavelmente obteria mais resultados porque os clientes só precisam de existir numa entidade adicional.

### <a name="direct-relationship"></a>Relação direta

Uma relação é classificada como uma **relação direta** quando uma entidade de origem se relaciona com uma entidade de destino com apenas uma relação.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchases* se ligar a uma entidade de destino *eCommerce_eCommerceContacts* apenas através de *ContactId*, é uma relação direta.

:::image type="content" source="media/direct_Relationship.png" alt-text="A entidade de origem liga-se diretamente à entidade de destino.":::

#### <a name="multi-path-relationship"></a>Relação de múltiplos caminhos

Uma **relação de múltiplos caminhos** é um tipo especial de relação direta que liga uma entidade de origem a mais do que uma entidade de destino.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchases* se relaciona com duas entidades de destino, tanto *eCommerce_eCommerceContacts* como *loyaltyScheme_loyCustomers*, é uma relação de múltiplos caminhos.

:::image type="content" source="media/multi-path_relationship.png" alt-text="A entidade de origem liga-se diretamente a mais de uma entidade de destino através de uma relação de múltiplos saltos.":::

### <a name="indirect-relationship"></a>Relação indireta

Uma relação é classificada como uma **relação indireta** quando uma entidade de origem se relaciona com uma ou mais entidades adicionais antes de se relacionar com a entidade de destino.

#### <a name="multi-hop-relationship"></a>Relação de múltiplos saltos

Uma *relação de múltiplos saltos* é uma *relação indireta* que lhe permite ligar uma entidade de origem a uma entidade de destino através de uma ou mais outras entidades intermediárias.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchasesWest* se ligar a uma entidade intermediária chamada *eCommerce_eCommercePurchasesEast* e, em seguida, se ligar a uma entidade de destino chamada *eCommerce_eCommerceContacts*, é uma relação de múltiplos saltos.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="A entidade de origem liga-se diretamente a uma entidade de destino com uma entidade intermédia.":::

### <a name="multi-hop-multi-path-relationship"></a>Relação de de múltiplos saltos, múltiplos caminhos

Relações de múltiplos saltos e de múltiplos caminhos podem ser usadas em conjunto para criar **relações de múltiplos saltos e de de múltiplos caminhos**. Este tipo especial combina as funções de **Relações de múltiplos saltos** e de **múltiplos caminhos**. Permite ligar a mais de uma entidade de destino enquanto utiliza entidades intermediárias.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchasesWest* se ligar a uma entidade intermediária chamada *eCommerce_eCommercePurchasesEast* e, em seguida, se ligar a duas entidades de destino, ao *eCommerce_eCommerceContacts* e ao *loyaltyScheme_loyCustomers*, é uma relação de múltiplos saltos, múltiplos caminhos.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="A entidade de origem liga-se diretamente a uma entidade de destino e liga-se a outra entidade de destino através de uma entidade intermédia.":::

## <a name="manage-existing-relationships"></a>Gerir relações existentes 

Na página Relações, cada relação é representada por uma linha. 

Selecione uma relação e escolha uma das seguintes opções: 
 
- **Editar**: atualize as propriedades de relações personalizadas no painel de edição e guarde as alterações.
- **Eliminar**: elimine relações personalizadas.
- **Ver**: veja relações criadas pelo sistema e herdadas. 

## <a name="next-step"></a>Passo seguinte

Relações de sistema e personalizados são usadas para [criar segmentos](segments.md) e [medidas](measures.md) com base em múltiplas origens de dados que já não são colocadas em silo.

[!INCLUDE [footer-include](includes/footer-banner.md)]

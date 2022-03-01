---
title: Relações entre entidades e caminhos de entidades
description: Criar e gerir relações entre entidades a partir de múltiplas origens de dados.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171178"
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

1. Nas informações de audiência, vá a **Dados** > **Relações**.

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

## <a name="view-relationships"></a>Ver relações

A página Relações lista todas as relações que foram criadas. Cada linha representa uma relação, que inclui também detalhes sobre a entidade fornecida com o programa, a entidade de destino e a cardinalidade. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de relações e opções na barra de ação da página Relações.":::

Esta página oferece um conjunto de opções para relações existentes e novas: 
- **Nova Relação**: [Criar uma relação personalizada](#create-a-custom-relationship).
- **Visualizador**: [Explore o visualizador de relações](#explore-the-relationship-visualizer) para ver um diagrama de rede de relações existentes e respetiva cardinalidade.
- **Filtrar por**: escolha o tipo de relações a apresentar na lista.
- **Pesquisar relações**: utilize uma pesquisa baseada em texto sobre as propriedades das relações.

### <a name="explore-the-relationship-visualizer"></a>Explore o visualizador de relações

O visualizador de relações mostra um diagrama de rede de relações existentes entre as entidades ligadas e a respetiva cardinalidade.

Para personalizar a vista, pode alterar a posição das caixas arrastando-as na tela.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de ecrã do diagrama de rede do visualizador de relações com ligações entre entidades relacionadas.":::

Opções disponíveis: 
- **Exportar como imagem**: guarde a vista atual como um ficheiro de imagem.
- **Alterar para esquema horizontal/vertical**: altere o alinhamento das entidades e relações.
- **Editar**: atualize as propriedades de relações personalizadas no painel de edição e guarde as alterações.

## <a name="manage-existing-relationships"></a>Gerir relações existentes 

Na página Relações, cada relação é representada por uma linha. 

Selecione uma relação e escolha uma das seguintes opções: 
 
- **Editar**: atualize as propriedades de relações personalizadas no painel de edição e guarde as alterações.
- **Eliminar**: elimine relações personalizadas.
- **Ver**: veja relações criadas pelo sistema e herdadas. 

## <a name="next-step"></a>Passo seguinte

As relações do sistema e personalizadas são utilizadas para [criar segmentos](segments.md) baseados em várias origens de dados que já não estão repartidas em silos.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

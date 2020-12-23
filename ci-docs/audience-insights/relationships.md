---
title: Relações entre entidades e caminhos de entidades
description: Criar e gerir relações entre entidades a partir de múltiplas origens de dados.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406651"
---
# <a name="relationships-between-entities"></a>Relação entre entidades

As relações ajudam a ligar entidades e a gerar um gráfico dos seus dados quando as entidades partilham um identificador comum (chave externa) que pode ser referenciado de uma entidade para outra. As entidades ligadas permitem definir segmentos e medidas com base em várias origens de dados.

Existem dois tipos de relações. As relações do sistema não editáveis, que são criadas automaticamente, e as relações personalizadas criadas e configuradas pelos utilizadores.

Durante os processos de correspondência e intercalação, as relações do sistema são criadas em segundo com base numa correspondência inteligente. Estes relações ajudam a relacionar os registos do perfil de Cliente com outros registos de entidades correspondentes. O diagrama seguinte ilustra a criação de três relações do sistema quando a entidade do cliente é correspondida com entidades adicionais para produzir a entidade de Perfil de Cliente final.

> [!div class="mx-imgBorder"]
> ![Criação da relação](media/relationships-entities-merge.png "Criação da relação")

- A **relação *CustomerToContact*** foi criada entre a entidade Cliente e a entidade Contacto. A entidade Cliente obtém o campo de chave **Contact_contactId** para estabelecer relação com o campo de chave da entidade Contacto **contactId**.
- A **relação _CustomerToAccount_** foi criada entre a entidade Cliente e a entidade Conta. A entidade Cliente obtém o campo de chave **Account_accountId** para estabelecer relação com o campo de chave da entidade Conta **accountId**.
- A **relação _CustomerToWebAccount_** foi criada entre a entidade Cliente e a entidade WebAccount. A entidade Cliente obtém o campo de chave **WebAccount_webaccountId** para estabelecer relação com o campo de chave da entidade WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Criar uma relação

Defina relações personalizadas na página **Relações**. Cada relação consiste numa entidade Origem (a entidade que tem a chave externa) e uma Entidade de destino (a entidade para a qual a chave externa da entidade de origem aponta).

1. Nas informações de audiência, vá a **Dados** > **Relações**.

2. Entidade de destino **Nova relação**.

3. No painel **Adicionar relação**, forneça as seguintes informações:

   > [!div class="mx-imgBorder"]
   > ![Introduzir detalhes da relação](media/relationships-add.png "Introduzir detalhes da relação")

   - **Nome da relação**: nome que reflete o objetivo da relação (por exemplo, **AccountWebLogs**).
   - **Descrição**: descrição da relação.
   - **Entidade de origem**: selecione a entidade que é utilizada como origem na relação (por exemplo, WebLog).
   - **Cardinalidade**: selecione a cardinalidade dos registos da entidade de origem. Por exemplo, "muitos" significa que vários registos do Weblog estão relacionados com uma WebAccount.
   - **Campo de chave de origem**: representa o campo de chave externa na entidade de origem. Por exemplo, o WebLog tem o campo de chave externa **accountId**.
   - **Entidade de destino**: selecione a entidade que é utilizada como destino na relação (por exemplo, WebAccount).
   - **Cardinalidade de destino**: selecione a cardinalidade dos registos da entidade de destino. Por exemplo, "um" significa que vários registos do Weblog estão relacionados com uma WebAccount.
   - **Campo de chave de destino**: este campo representa o campo de chave da entidade de destino. Por exemplo, WebAccount tem o campo de chave **accountId**.

> [!NOTE]
> Só são suportadas relações muitos-para-um e um-para-um. As relações muitos-para-muitos podem ser criadas através de duas relações muitos-para-um e uma entidade de ligação (uma entidade que é utilizada para ligar a entidade de origem e a entidade de destino).

## <a name="delete-a-relationship"></a>Eliminar uma relação

1. Nas informações de audiência, vá a **Dados** > **Relações**.

2. Selecione as caixas de verificação para as relações que pretende eliminar.

3. Selecione **Eliminar** na parte superior da tabela **Relações**.

4. Confirme a eliminação.

## <a name="next-step"></a>Passo seguinte

As relações do sistema e personalizadas são utilizadas para criar segmentos baseados em várias origens de dados que já não estão repartidas em silos. Para mais informações, consulte [Segmentos](segments.md).

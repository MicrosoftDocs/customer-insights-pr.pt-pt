---
title: Ligar a tabelas no Microsoft Dataverse
description: Importar dados de um data lake gerido do Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011717"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conecte-se aos dados num data lake gerido do Microsoft Dataverse

Os utilizadores do Microsoft Dataverse podem ligar rapidamente a entidades analíticas num lake gerido do Microsoft Dataverse.

> [!NOTE]
> Tem de ser um administrador da organização do Dataverse para prosseguir e ver a lista de entidades disponíveis no data lake gerido.

## <a name="important-considerations"></a>Considerações importantes

1. Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados numa localização diferente do local em que os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar, ou ligar a, os dados armazenados em serviços online, como o , concorda que os dados podem ser transferidos para, e armazenados com o Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft](https://www.microsoft.com/trust-center).
2. Apenas entidades do Dataverse com o [controlo de alterações](/power-platform/admin/enable-change-tracking-control-data-synchronization) ativado são visíveis. Estas entidades podem ser exportadas para o data lake gerido pelo Dataverse e utilizadas no Customer Insights. Por predefinição, as tabelas do Dataverse de origem têm o controlo de alterações ativado. Tem de ativar o controlo de alterações para tabelas personalizadas. Para verificar se uma tabela do Dataverse tem o controlo de alterações ativado, aceda a [Power Apps](https://make.powerapps.com) > **Dados** > **Tabelas**. Encontre a tabela que lhe interessa e selecione-a. Vá a **Definições** > **Opções avançadas** e reveja a definição **Monitorizar alterações**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Ligar a um lake gerido do Dataverse

1. Aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Selecione **Microsoft Dataverse**.

1. Introduza um **Nome** para a origem de dados e uma **Descrição** opcional.

1. Forneça o **Endereço do servidor** da organização Dataverse e selecione **Iniciar sessão**.

1. Selecione as tabelas que pretende ingerir como entidades para o Customer Insights a partir da lista disponível.

   > [!NOTE]
   > Se algumas tabelas já estiverem selecionadas, poderão ser utilizadas por outras aplicações Dynamics 365 (tais como o Dynamics 365 Sales Insights ou o Customer Service Insights). Não pode alterar a seleção. Estas tabelas estarão disponíveis como entidades assim que a origem de dados for criada.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo a mostrar uma lista de entidades no ambiente do Dataverse.":::

1. Guarde a sua seleção para começar a sincronizar as tabelas selecionadas do Dataverse. Encontrará a ligação recentemente adicionada na página **Origens de dados**. Será colocado em fila para atualização e mostrará a contagem de entidades como 0, até que todas as tabelas selecionadas estejam sincronizadas.

Apenas uma origem de dados de um ambiente pode simultaneamente usar o mesmo lake gerido Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar uma origem de dados de lake gerido do Dataverse

Só edita a seleção de entidade depois de criar a origem de dados. Por exemplo, se entidades adicionais forem adicionadas ao Dataverse e quiser importá-las também.
Para se ligar a um data lake do Dataverse diferente, [crie uma nova origem de dados](#connect-to-a-dataverse-managed-lake).

1. Aceda a **Dados** > **Origens de dados**.

1. Junto da origem de dados que pretende atualizar, selecione **Editar**.

1. Selecione entidades adicionais a partir da lista de entidades disponíveis e selecione **Guardar**.

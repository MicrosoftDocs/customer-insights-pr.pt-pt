---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755558"
---
Depois de ingerir os dados, inicie o processo de unificação de dados para criar um unified customer profile. Para mais informações, consulte [Unificação de dados](../data-unification.md).

### <a name="select-source-fields"></a>Selecionar campos de origem

1. Depois de ingerir os dados, mapear os contactos desde os dados de eCommerce e Fidelidade até aos tipos de dados comuns. Vá para **Dados** > **Unificar**.

1. Selecionar as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.

   ![unificar as origens de dados do comércio eletrónico e da fidelidade.](../media/unify-ecommerce-loyalty.png)

1. Selecionar **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.

1. Selecione **Seguinte**. Ignore os dados duplicados e selecione **Seguinte**.

### <a name="match-conditions"></a>Condições de correspondência

1. Escolha **eCommerceContacts : eCommerce** como entidade principal e inclua todos os registos.

1. Escolha **loyCustomers : LoyaltyScheme** e inclua todos os registos.

1. Adicionar uma regra:
   - Selecione **FullName** para eCommerceContacts e loyCustomers.
   - Selecione **Tipo (Telefone, Nome, Endereço, ...)** para **Normalizar**.
   - Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.
   - Introduza **FullName, E-mail** para o nome.

1. Adicione uma segunda condição para o endereço de e-mail:
   - Selecione **E-mail** para eCommerceContacts e loyCustomers.
   - Deixar em branco Normalizar.
   - Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.

   ![Unificar a regra de correspondência para nome e e-mail.](../media/unify-match-rule.png)

1. Selecionar **Concluído**.

1. Selecione **Seguinte**.

### <a name="unify-fields"></a>Unificar campos

1. Altere o nome a entidade **ContactId** e **loyCustomers** para **ContactIdLOYALTY** para a diferenciar das outras IDs ingeridas.

1. Selecione **Seguinte** para rever e, em seguida, selecione **Criar perfis de cliente**.

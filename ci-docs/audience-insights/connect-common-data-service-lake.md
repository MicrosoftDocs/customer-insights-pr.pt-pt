---
title: Conecte-se a entidades no lake gerido do Common Data Service
description: Importar dados de um data lake gerido do Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596973"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Conecte-se aos dados num data lake gerido do Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artigo fornece informações sobre como os clientes existentes do Dynamics 365 podem rapidamente ligar-se às suas entidades analíticas no lake gerido do Common Data Service. Deve ser um administrador na organização do Common Data Service para prosseguir e ver a lista de entidades disponíveis no lake gerido.

## <a name="important-considerations"></a>Considerações importantes

Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados numa localização diferente do local em que os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar, ou ligar a, os dados armazenados em serviços online, como o , concorda que os dados podem ser transferidos para, e armazenados com o Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Ligar a um lake gerido do Common Data Service

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

2. Selecione **Adicionar origem de dados**.

3. Selecione **Ligar ao Common Data Service** e selecione **Seguinte**.

4. Introduza um **Nome** para a oridem de dados e, em seguida, selecione **Seguinte**. Nomear diretrizes: 
   - Comece com uma letra.
   - Utilize apenas letras e números. Não são permitidos carateres especiais e espaços.
   - Utilize entre 3 e 64 carateres.

5. Forneça o **Endereço de servidor** para a sua organização do Common Data Service e selecione **Iniciar sessão**.

   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo para introduzir o endereço do servidor do Common Data Service](media/enter-CDS-org-details.png)

6. Selecione as entidades que pretende ingerir a partir da lista disponível.    

   > [!NOTE]
   > Se algumas entidades já estiverem selecionadas, poderão ser utilizadas por outras aplicações do Dynamics 365 (como o Dynamics 365 Sales Insights ou o Customer Service Insights). Não pode alterar a seleção. Estas entidades estarão disponíveis assim que a origem de dados for criada.

   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo que mostra uma lista de entidades na organização do Common Data Service](media/select-analytical-entities.png)

7. Guarde a seleção para iniciar a sincronização das entidades selecionadas para o lake gerido do Common Data Service. Encontrará a ligação recentemente adicionada na página **Origens de dados**. A mesma será colocada em fila para atualização e mostrará as entidades como 0 até que todas as entidades sejam sincronizadas.

Apenas uma origem de dados de um ambiente pode simultaneamente usar o mesmo lake gerido Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Editar uma origem de dados de lake gerido do Common Data Service

Só edita a seleção de entidade depois de criar a origem de dados. Por exemplo, se entidades adicionais forem adicionadas ao Common Data Service e quiser importá-las também.    
Para ligar a outro Common Data Service, [crie uma nova origem de dados](#connect-to-a-common-data-service-managed-lake).

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

2. Junto da origem de dados que pretende atualizar, selecione as reticências.

3. Selecione a opção **Editar** da lista.

4. Selecione entidades adicionais a partir da lista de entidades disponíveis e selecione **Guardar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
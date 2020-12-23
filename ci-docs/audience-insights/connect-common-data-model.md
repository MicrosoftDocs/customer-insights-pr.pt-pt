---
title: Ligue os dados Common Data Model a uma conta Azure Data Lake
description: Trabalhe com dados do Common Data Model utilizando Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643472"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Ligar a uma pasta do Common Data Model com uma conta Azure Data Lake

Este artigo fornece informações sobre como ingerir dados a partir de uma pasta Common Data Model utilizando a sua conta Gen2 Azure Data Lake Storage.

## <a name="important-considerations"></a>Considerações importantes

- Os dados existentes no seu Azure Data Lake têm de seguir o padrão do Common Data Model. De momento, não há suporte para outros formatos.

- A ingestão de dados suporta exclusivamente as contas de armazenamento do Azure Data Lake *Gen2*. Não pode usar as contas de armazenamento do Azure Data Lake Gen1 para ingerir dados.

- Para autenticar com um principal de serviço da Azure, certifique-se de que está configurado no seu inquilino. Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md).

- O Azure Data Lake a que se quer conectar e do qual pretende ingerir dados tem de ser na mesma região do Azure que o ambiente Dynamics 365 Customer Insights. As ligações a uma pasta Common Data Model a partir de um data lake numa região do Azure diferente não são suportadas. Para conhecer a região do Azure do ambiente, vá a **Admin** > **Sistema** > **Sobre** informações da audiência.

- Os dados armazenados em serviços online podem ser armazenados numa localização diferente do local onde os dados são tratados ou armazenados em Dynamics 365 Customer Insights. Ao importar, ou ligar a, os dados armazenados em serviços online, como o , concorda que os dados podem ser transferidos para, e armazenados com o Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Ligar a uma pasta do Common Data Model

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Selecione **Ligar a uma pasta Common Data Model**, introduza um **Nome** para a origem de dados e selecione **Seguinte**.

1. Pode escolher entre usar uma opção baseada em recursos e uma opção baseada em subscrição para autenticação. Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md). Introduza as informações do **Recipiente** e selecione **Seguinte**.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo para introduzir detalhes de ligação para o Azure Data Lake](media/enter-new-storage-details.png)

1. No diálogo **Selecionar uma pasta Common Data Model**, selecione o ficheiro model.json para importar dados e selecione **Seguinte**.
   > [!NOTE]
   > Qualquer ficheiro model.json associado a outra origem de dados no ambiente não aparecerá na lista.

1. Irá receber uma lista de entidades disponíveis no ficheiro model.json selecionado. Pode rever e selecionae da lista de entidades disponíveis e selecione **Guardar**. Todas as entidades selecionadas serão ingeridas a partir da nova origem de dados.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo que mostra uma lista de entidades a partir de um ficheiro model.json](media/review-entities.png)

8. Indique as entidades de dados para as quais pretende ativar a criação de perfis de dados e selecione **Guardar**. A criação de perfis de dados permite utilizar análise e outras capacidades. Pode selecionar toda a entidade, o que seleciona todos os atributos da entidade, ou selecionar certos atributos à sua escolha. Por defeito, nenhuma entidade está habilitada para a criação de perfis de dados.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo que mostra a criação de perfis de dados](media/dataprofiling-entities.png)

9. Depois de guardar as seleções, é aberta a página **Origens de dados**. Deverá ver agora a ligação de pasta do Common Data Model como uma origem de dados.

> [!NOTE]
> Um ficheiro model.json só pode associar-se a um origem de dados no mesmo ambiente. No entanto, o mesmo ficheiro model.json pode ser usado para origens de dados em vários ambientes.

## <a name="edit-a-common-data-model-folder-data-source"></a>Editar uma origem de dados do Common Data Model

Pode atualizar a chave de acesso para a conta de armazenamento que contém a pasta Common Data Model. Também poderá alterar o ficheiro model.json. Para ligar a um contentor diferente da conta de armazenamento ou alterar o nome da conta, tem de [criar uma nova ligação à origem de dados](#connect-to-a-common-data-model-folder).

1. Em informações de audiência, aceda a **Dados** > **Origens de dados**.

2. Junto da origem de dados que pretende atualizar, selecione as reticências.

3. Selecione a opção **Editar** da lista.

4. Opcionalmente, atualize a **Chave de acesso** e selecione **Seguinte**.

   ![Diálogo para editar e atualizar uma tecla de acesso para uma origem de dados existente](media/edit-access-key.png)

5. Opcionalmente, pode atualizar a partir de uma ligação chave de conta a uma ligação baseada em recursos ou baseada em subscrição. Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md). Não é possível alterar as informações do **Recipiente** ao atualizar a ligação.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo para introduzir detalhes de ligação para o Azure Data Lake](media/enter-existing-storage-details.png)

6. Opcionalmente, escolha um ficheiro model.json diferente com um conjunto de entidades diferente do contentor.

7. Opcionalmente, pode selecionar entidades adicionais para ingerir. Também pode remover quaisquer entidades já selecionadas se não houver dependências.

   > [!IMPORTANT]
   > Se existirem dependências no ficheiro model.json e no conjunto de entidades, verá uma mensagem de erro e não poderá selecionar um ficheiro model.json diferente. Remova estas dependências antes de alterar o ficheiro model.json ou criar uma nova origem de dados com o ficheiro model.json que pretende utilizar para evitar a remoção das dependências.

8. Opcionalmente, pode selecionar atributos ou entidades adicionais para possibilitar a criação de perfis de dados ou desativar os já selecionados.   

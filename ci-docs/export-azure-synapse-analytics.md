---
title: Exportar dados do Customer Insights para o Azure Synapse Analytics
description: Saiba como configurar a ligação ao Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 772fe0978362ccd829077a8133e2a3e74043f3f8
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741517"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar para o Azure Synapse Analytics (pré-visualização)

O Azure Synapse é um serviço de análise que acelera o tempo para as informações através de armazéns de dados e sistemas de macrodados. Pode ingerir e utilizar os seus dados do Customer Insights no [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

Os seguintes pré-requisitos têm de ser cumpridos para configurar a ligação do Customer Insights para o Azure Synapse.

> [!NOTE]
> Certifique-se de que define todas as **atribuições de funções**, conforme descrito.  

## <a name="prerequisites-in-customer-insights"></a>Pré-requisitos no Customer Insights

* A sua conta de utilizador do Azure Active Directory (AD) tem uma função de **Administrador** no Customer Insights. Saiba mais sobre como [definir permissões de utilizador](permissions.md#assign-roles-and-permissions).

No Azure: 

- Uma subscrição ativa do Azure.

- Se utilizar uma nova conta Azure Data Lake Storage Gen2, o *principal de serviço para o Customer Insights* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento**. Saiba mais sobre como [ligar a uma conta Azure Data Lake Storage Gen2 com um principal de serviço do Azure para o Customer Insights](connect-service-principal.md). O Data Lake Storage Gen2 **tem de ter** [espaço de nomes hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos onde o Azure Synapse workspace está localizado, o *principal do serviço* e o *utilizador do Azure AD com permissões de admin no Customer Insights* precisam de, pelo menos, permissões de **Leitor**. Para obter mais informações, consulte [Atribuir funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

- O *utilizador do Azure AD precisa de permissões de admin no Customer Insights* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados ao Azure Synapse workspace. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade gerida da área de trabalho do Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse workspace, o *principal do serviço para o Customer Insights* precisa da função de **Administrador do Synapse** atribuída. Para mais informações, consulte [Como configurar o controlo de acesso à sua área de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configure a ligação exporte para o Azure Synapse

### <a name="configure-a-connection"></a>Configurar uma ligação

Para criar uma ligação, o principal do serviço e a conta de utilizador no Customer Insights precisam de permissões de **Leitor** no *grupo de recursos* onde está localizada o área de trabalho do Synapse Analytics. Além disso, o principal de serviço e o utilizador na área de trabalho do Synapse Analytics precisam de permissões de **Administrador do Synapse**. 

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Azure Synapse Analytics** ou selecione a **Configuração** no mosaico **Azure Synapse Analytics** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo Nome a apresentar. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione ou procure a subscrição em que pretende utilizar os dados do Customer Insights. Assim que uma subscrição for selecionada, também pode selecionar **Área de Trabalho**, **Conta de armazenamento** e **Contentor**.

1. Selecione **Guardar** para guardar a ligação.

### <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para configurar a exportação com uma ligação partilhada, são necessário, pelo menos, permissões de **Contribuidor** no Customer Insights. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar um nova exportação, selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação na secção **Azure Synapse Analytics**. Se não vir este nome de secção, não existem [ligações](connections.md) deste tipo disponíveis para si.

1. Forneça um **Nome a apresentar** reconhecível para a sua exportação e um **Nome de base de dados**.

1. Selecione quais as entidades que pretende exportar para o Azure Synapse Analytics.
   > [!NOTE]
   > As origens de dados baseadas numa [pasta Common Data Model](connect-common-data-model.md) não são suportadas.

2. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).

Para consultar dados que foram exportados para o Synapse Analytics, precisa de acesso de **Leitor de Armazenamento de Dados de Blob** ao armazenamento de destino na área de trabalho das exportações. 

### <a name="update-an-export"></a>Atualizar uma exportação

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Editar** na exportação que quer atualizar.

   - **Adicione** ou **Remova** entidades da seleção. Se as entidades forem removidas da seleção, não são eliminadas da base de dados da Análise do Synapse. No entanto, futuras atualizações de dados não atualizarão as entidades removidas nessa base de dados.

   - **Alterar o Nome da Base de Dados** cria uma nova base de dados de Análise do Synapse. A base de dados com o nome que foi configurado anteriormente não receberá quaisquer atualizações em futuras atualizações.

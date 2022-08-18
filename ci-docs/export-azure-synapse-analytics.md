---
title: Exportar para o Azure Synapse Analytics (pré-visualização)
description: Saiba como configurar a ligação ao Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259858"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar para o Azure Synapse Analytics (pré-visualização)

O Azure Synapse é um serviço de análise que acelera o tempo para as informações através de armazéns de dados e sistemas de macrodados. Pode ingerir e utilizar os seus dados do Customer Insights no [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

> [!NOTE]
> Certifique-se de que define todas as **atribuições de funções**, conforme descrito.

- No Customer Insights, a sua conta de utilizador do Azure Active Directory (AD) tem de ter uma [função de Administrador](permissions.md#add-users).

No Azure:

- Uma subscrição ativa do Azure.

- Se utilizar uma nova conta Azure Data Lake Storage Gen2, o [principal de serviço para o Customer Insights](connect-service-principal.md) tem permissões de **Contribuidor de Dados de Blobs de Armazenamento**. O Data Lake Storage Gen2 **tem de ter** [espaço de nomes hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos onde o Azure Synapse Workspace está localizada, ao *principal do serviço* e ao utilizador do *Azure AD com permissões de administrador no Customer Insights* precisam têm de ser atribuídas pelo menos as [permissões](/azure/role-based-access-control/role-assignments-portal) **Leitor**.

- O *utilizador do Azure AD com permissões de administrador no Customer Insights* tem permissões **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados ao Azure Synapse workspace. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade gerida do Azure Synapse Workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* tem permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse Workspace, o *principal do serviço para o Customer Insights* tem a [função atribuída](/azure/synapse-analytics/security/how-to-set-up-access-control) **Administrador do Synapse**.

- Se o seu ambiente do Customer Insights armazenar dados no seu [próprio Azure Data Lake Storage](own-data-lake-storage.md), o utilizador que configura a ligação ao Azure Synapse Analytics precisa pelo menos da função **Leitor** integrada na conta Data Lake Storage. Para obter mais informações, consulte [Atribuir funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Configurar ligação ao Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Azure Synapse Analytics**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione ou procure a subscrição em que pretende utilizar os dados do Customer Insights. Assim que uma subscrição for selecionada, também pode selecionar **Área de Trabalho**, **Conta de armazenamento** e **Contentor**.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)] Para configurar a exportação com uma ligação partilhada, são necessário, pelo menos, permissões de **Contribuidor** no Customer Insights.

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção Azure Synapse Analytics. Contacte um administrador se não houver nenhuma ligação disponível.

1. Forneça um **Nome a apresentar** reconhecível para a sua exportação e um **Nome de base de dados**. A exportação irá criar uma nova base de dados [Azure Synapse lake](/azure/synapse-analytics/database-designer/concepts-lake-database) na área de trabalho definida na ligação.

1. Selecione quais as entidades que pretende exportar para o Azure Synapse Analytics.
   > [!NOTE]
   > As origens de dados baseadas numa [pasta Common Data Model](connect-common-data-model.md) não são suportadas.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Para consultar dados que foram exportados para o Synapse Analytics, precisa de acesso de **Leitor de Armazenamento de Dados de Blob** ao armazenamento de destino na área de trabalho das exportações.

## <a name="update-an-export"></a>Atualizar uma exportação

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Editar** na exportação que quer atualizar.

   - **Adicione** ou **Remova** entidades da seleção. Se as entidades forem removidas da seleção, não são eliminadas da base de dados da Análise do Synapse. No entanto, futuras atualizações de dados não atualizarão as entidades removidas nessa base de dados.

   - **Alterar o Nome da Base de Dados** cria uma nova base de dados de Análise do Synapse. A base de dados com o nome que foi configurado anteriormente não receberá quaisquer atualizações em futuras atualizações.

[!INCLUDE [footer-include](includes/footer-banner.md)]

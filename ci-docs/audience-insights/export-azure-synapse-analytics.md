---
title: Exportar dados do Customer Insights para a Análise do Azure Synapse
description: Aprenda a configurar a ligação e exportar para a Análise do Azure Synapse.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f206043298bdbf8a84b0ef37b47a43290653beba7d3d0e8b807ec74513614aa8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031947"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar dados para a Análise do Azure Synapse (Pré-visualização)

O Azure Synapse é um serviço de análise que acelera o tempo para as informações através de armazéns de dados e sistemas de macrodados. Pode ingerir e utilizar os seus dados do Customer Insights no [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

Os seguintes pré-requisitos têm de ser cumpridos para configurar a ligação do Customer Insights para o Azure Synapse.

> [!NOTE]
> Certifique-se de que define todas as **atribuições de funções**, conforme descrito.  

## <a name="prerequisites-in-customer-insights"></a>Pré-requisitos no Customer Insights

* Tem uma função de **Administrador** nas informações de audiência. Saiba mais sobre [definir permissões de utilizador em informações de audiência](permissions.md#assign-roles-and-permissions)

No Azure: 

- Uma subscrição ativa do Azure.

- Se utilizar uma nova conta Azure Data Lake Storage Gen2, o *principal de serviço para informações de audiência* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento**. Saiba mais sobre [ligar a uma conta Azure Data Lake Storage Gen2 com o principal do serviço do Azure para informações de audiência](connect-service-principal.md). O Data Lake Storage Gen2 **tem de ter** [espaço de nomes hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos onde está localizada a área de trabalho do Azure Synapse, o *principal do serviço* e o *utilizador para as informações de audiência* precisam de ser atribuídas, pelo menos, as permissões de **Leitor**. Para obter mais informações, consulte [Atribuir funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

- O *utilizador* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade gerida da área de trabalho do Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na área de trabalho do Azure Synapse, o *principal do serviço para informações de audiência* precisa da função de **Administrador do Synapse** atribuída. Para mais informações, consulte [Como configurar o controlo de acesso à sua área de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configure a ligação exporte para o Azure Synapse

### <a name="configure-a-connection"></a>Configurar uma ligação

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha a **Análise do Azure Synapse** para selecionar **Configurar** no mosaico **Análise do Azure Synapse** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo Nome a apresentar. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione ou procure a subscrição em que pretende utilizar os dados do Customer Insights. Assim que uma subscrição for selecionada, também pode selecionar **Área de Trabalho**, **Conta de armazenamento** e **Contentor**.

1. Selecione **Guardar** para guardar a ligação.

### <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar um nova exportação, selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção **Análise do Azure Synapse**. Se não vir este nome de secção, não existem [ligações](connections.md) deste tipo disponíveis para si.

1. Forneça um **Nome a apresentar** reconhecível para a sua exportação e um **Nome de base de dados**.

1. Selecione que entidades pretende exportar para a Análise do Azure Synapse.
   > [!NOTE]
   > As origens de dados baseadas numa [pasta Common Data Model](connect-common-data-model.md) não são suportadas.

2. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Atualizar uma exportação

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Editar** na exportação que quer atualizar.

   - **Adicione** ou **Remova** entidades da seleção. Se as entidades forem removidas da seleção, não são eliminadas da base de dados da Análise do Synapse. No entanto, futuras atualizações de dados não atualizarão as entidades removidas nessa base de dados.

   - **Alterar o Nome da Base de Dados** cria uma nova base de dados de Análise do Synapse. A base de dados com o nome que foi configurado anteriormente não receberá quaisquer atualizações em futuras atualizações.

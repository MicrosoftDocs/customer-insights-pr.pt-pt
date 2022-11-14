---
title: Ligar uma origem de dados Azure Synapse (pré-visualização)
description: Utilizar uma base de dados em Azure Synapse como origem de dados em Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738170"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Ligar uma origem de dados Azure Synapse Analytics (pré-visualização)

Azure Synapse Analytics é um serviço de análise empresarial que acelera o tempo para insights em armazéns de dados e sistemas de macrodados. Azure Synapse Analytics reúne as melhores tecnologias SQL utilizadas no armazém de dados empresariais, tecnologias Spark utilizadas para macrodados, Data Explorer para análise de registos e de séries temporais, Pipelines para integração de dados e ETL/ELT e integração profunda com outros serviços Azure como o Power BI, Cosmos DB e o AzureML.

Para mais informações, consulte a descrição geral do [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

> [!NOTE]
> As Áreas de Trabalho do Synapse com a [firewall ativada](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) atualmente não são suportadas.
> [!IMPORTANT]
> Certifique-se de que define todas as **atribuições de funções**, conforme descrito.  

**No Customer Insights**:

* Tem uma função de **Administrador** no Customer Insights. Saiba mais sobre [as permissões de utilizador no Customer Insights](permissions.md#add-users).

**No Azure**:

- Uma subscrição ativa do Azure.

- Se utilizar uma nova conta Azure Data Lake Storage Gen2, o *principal de serviço para o Customer Insights*, que é o "Dynamics 365 AI para Customer Insights", precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento**. Saiba mais sobre como [ligar a um Azure Data Lake Storage com um principal de serviço para o Customer Insights](connect-service-principal.md). O Data Lake Storage Gen2 **tem de ter** [espaço de nomes hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos onde o Azure Synapse workspace está localizado, o *principal do serviço*, que é o which is "Dynamics 365 AI for Customer Insights", e o *utilizador do Customer Insights* precisam de receber, pelo menos, as permissões de **Leitor**. Para obter mais informações, consulte [Atribuir funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

- O *utilizador* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade gerida da área de trabalho do Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse workspace, o *principal do serviço para o Customer Insights*, que é o "Dynamics 365 AI para Customer Insights", precisa da função de **Administrador do Synapse** atribuída. O **utilizador** necessita de, pelo menos, uma função de **Contribuidor de Synapse** atribuída para a área de trabalho. Para mais informações, consulte [Como configurar o controlo de acesso à sua área de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Se o seu ambiente do Customer Insights armazenar dados no seu [próprio Azure Data Lake Storage](own-data-lake-storage.md), o utilizador que configura a ligação ao Azure Synapse Analytics precisa pelo menos da função **Leitor** integrada na conta Data Lake Storage. Para obter mais informações, consulte [Atribuir funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Ligar à base de dados do data lake no Azure Synapse Analytics

1. Aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Escolha o método **(Pré-visualização) do Azure Synapse Analytics**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Caixa de diálogo para ligar a dados do Synapse Analytics":::
  
1. Introduza um **Nome** para a origem de dados e uma **Descrição** opcional.

1. Escolha uma [ligação disponível](connections.md) para o Azure Synapse Analytics ou [crie uma nova](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Escolha uma **Base de Dados** a partir da área de trabalho ligada na ligação do Azure Synapse Analytics e selecione **Seguinte**. Atualmente, só fornecemos suporte à base de dados do tipo *Lake database.*

1. Selecione as entidades para ingerir a partir da base de dados ligadas e selecione **Seguinte**.

1. Em alternativa, escolha as entidades de dados para permitir a criação de perfis de dados.

1. Selecione **Guardar** para confirmar a sua seleção e iniciar a ingestão dos dados da sua origem de dados recém-criada, ligada às tabelas de base de dados de Data Lake no Azure Synapse Analytics. A página **Origens de dados** é aberta a mostrar a origem de dados novas no estado **A atualizar**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revistos na página [**Entidades**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

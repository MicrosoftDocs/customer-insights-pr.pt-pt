---
title: Ligar uma origem de dados Azure Synapse (pré-visualização)
description: Utilizar uma base de dados em Azure Synapse como origem de dados em Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052713"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Ligar uma origem de dados Azure Synapse Analytics (pré-visualização)

Azure Synapse Analytics é um serviço de análise empresarial que acelera o tempo para insights em armazéns de dados e sistemas de macrodados. Azure Synapse Analytics reúne as melhores tecnologias SQL utilizadas no armazém de dados empresariais, tecnologias Spark utilizadas para macrodados, Data Explorer para análise de registos e de séries temporais, Pipelines para integração de dados e ETL/ELT e integração profunda com outros serviços Azure como o Power BI, Cosmos DB e o AzureML.

Para mais informações, consulte a descrição geral do [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

> [!IMPORTANT]
> Certifique-se de que define todas as **atribuições de funções**, conforme descrito.  

**No Customer Insights**:

* Tem uma função de **Administrador** no Customer Insights. Saiba mais sobre [as permissões de utilizador no Customer Insights](permissions.md#assign-roles-and-permissions).

**No Azure**:

- Uma subscrição ativa do Azure.

- Se utilizar uma nova conta Azure Data Lake Storage Gen2, o *principal de serviço para o Customer Insights* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento**. Saiba mais sobre como [ligar a um Azure Data Lake Storage com um principal de serviço para o Customer Insights](connect-service-principal.md). O Data Lake Storage Gen2 **tem de ter** [espaço de nomes hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos onde o Azure Synapse workspace está localizado, o *principal do serviço* e o *utilizador do Customer Insights* precisa de receber, pelo menos, as permissões de **Leitor**. Para obter mais informações, consulte [Atribuir funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

- O *utilizador* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade gerida da área de trabalho do Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões de **Contribuidor de Dados de Blobs de Armazenamento** na conta Azure Data Lake Storage Gen2 onde os dados estão localizados e ligados à área de trabalho do Azure Synapse. Saiba mais sobre [utilizar o portal do Azure para atribuir uma função do Azure para acesso a dados de blob e de fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões de Contribuidor de Dados de Blobs de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse workspace, o *principal do serviço para o Customer Insights* precisa da função de **Administrador do Synapse** atribuída. Para mais informações, consulte [Como configurar o controlo de acesso à sua área de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Ligar à base de dados do data lake no Azure Synapse Analytics

1. Aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Escolha o método **(Pré-visualização) do Azure Synapse Analytics**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Caixa de diálogo para ligar a dados do Synapse Analytics":::
  
1. Introduza um **Nome** para a origem de dados e uma **Descrição** opcional.

1. Escolha uma [ligação disponível](connections.md) para Azure Synapse Analytics ou crie uma nova.

1. Escolha uma **Base de Dados** a partir da área de trabalho ligada na ligação do Azure Synapse Analytics e selecione **Seguinte**. Atualmente, só fornecemos suporte à base de dados do tipo *Lake database.*

1. Selecione as entidades para ingerir a partir da base de dados ligadas e selecione **Seguinte**.

1. Em alternativa, escolha as entidades de dados para permitir a criação de perfis de dados.

1. Selecione **Guardar** para confirmar a sua seleção e iniciar a ingestão dos dados da sua origem de dados recém-criada, ligada às tabelas de base de dados de Data Lake no Azure Synapse Analytics. A página **Origens de dados** é aberta a mostrar a origem de dados novas no estado **A atualizar**.

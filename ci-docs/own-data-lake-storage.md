---
title: Utilizar a sua própria conta do Azure Data Lake Storage Gen2
author: mukeshpo
description: Conheça os requisitos para utilizar a sua própria conta do Azure Data Lake Storage para armazenar dados do Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011947"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Utilizar a sua própria conta do Azure Data Lake Storage Gen2

O Dynamics 365 Customer Insights dá-lhe a opção de armazenar todos os seus dados no [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Ao guardar dados no Data Lake Storage, concorda que os dados serão transferidos para a localização geográfica apropriada e armazenados na mesma para essa conta de armazenamento do Azure. Para obter mais informações, consulte [Centro de Confiança da Microsoft](https://www.microsoft.com/trust-center).

Os administradores no Customer Insights podem [criar ambientes](create-environment.md) e [especificar a opção de armazenamento de dados](create-environment.md#step-2-configure-data-storage) no processo.

## <a name="prerequisites-to-use-your-storage-account"></a>Pré-requisitos para utilizar a sua conta de armazenamento

- As contas do Azure Data Lake Storage têm de estar na mesma região do Azure que selecionou ao criar o ambiente do Customer Insights. Pode verificar a região do ambiente do Customer Insights sob **Admin** > **Sistema** > **Acerca de**.
- O Data Lake Storage tem de ser Gen2 e de ter o [espaço de nomes hierárquico ativado](/azure/storage/blobs/create-data-lake-storage-account). As contas de armazenamento Gen1 não são suportadas.
- Um contentor chamado `customerinsights` tem de existir na conta de armazenamento. Tem de a criar antes de utilizar o seu próprio Data Lake Storage no Customer Insights. O administrador que configura o ambiente do Customer Insights necessita da função de Contribuidor de Dados de Blobs de Armazenamento ou Proprietário de Dados de Blobs de Armazenamento na conta de armazenamento ou no contentor `customerinsights`. Para obter mais informações sobre a atribuição da permissão numa conta de armazenamento, consulte [Criar uma conta de armazenamento](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Ligar o Customer Insights à sua conta de armazenamento

Quando criar um novo ambiente, certifique-se de que a conta do Data Lake Storage existe e que todos os pré-requisitos são cumpridos.

1. No passo **Armazenamento de dados**, durante a criação do ambiente, defina **Guardar dados de saída** como **Azure Data Lake Storage Gen2**.
1. Escolha como **Ligar o armazenamento**. Pode escolher entre uma opção baseada em recursos e uma opção de autenticação baseada em subscrições. Para obter mais informações, consulte [Ligar a uma conta do Azure Data Lake Storage utilizando um Principal de Serviço do Azure](connect-service-principal.md).
   - Para a **Subscrição do Azure**, escolha a **Subscrição**, **Grupo de recursos** e **Conta de armazenamento** que contém o contentor `customerinsights`.
   - Para **Chave de conta**, forneça o **Nome da conta** e a **Chave da conta** para a conta do Data Lake Storage. A utilização deste método de autenticação implica que está informado se a sua organização rodar as chaves. Tem de [atualizar a configuração do ambiente](manage-environments.md#edit-an-existing-environment) com a nova chave quando esta for rodada.
1. Escolha se pretende utilizar o Azure Private Link para ligar a conta de armazenamento e [criar a ligação ao Private Link](security-overview.md#private-links-tab) com um processo de dois passos.

Quando os processos do sistema, como a ingestão de dados, estão concluídos, o sistema cria pastas correspondentes na conta de armazenamento. Os ficheiros de dados e os ficheiros *model.json* são criados e adicionados a pastas com base no nome do processo.

Se criar vários ambientes do Customer Insights e optar por guardar as entidades de saída desses ambientes na sua conta de armazenamento, o Customer Insights cria pastas separadas para cada ambiente com `ci_environmentID` no contentor.

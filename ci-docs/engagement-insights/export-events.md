---
title: Exportar eventos refinados
description: Como exportar eventos refinados e eventos base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032399"
---
# <a name="export-events"></a>Exportar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um evento representa o comportamento do utilizador. Regista quando um utilizador vê uma página (ver evento) ou interage com conteúdo (evento de ação). Quando pode decidir quais as propriedades dos dados que pretende apresentar num relatório, esta visão virtual dos dados é chamada de *evento refinado*. 

- Pode exportar eventos e eventos refinados para armazenamento externo. 
- As exportações são um fluxo de dados a prazo. Não pode encher o fluxo. 
- As exportações têm esquemas fixos. Se adicionar propriedades personalizadas a um evento, não serão incluídas. Vai precisar de criar uma nova exportação.

## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar uma exportação, precisa de ter acesso e uma subscrição ativa ao portal do Azure. Vai precisar da informação da conta de armazenamento durante o processo de exportação. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Criar contas Azure Data Lake Storage Gen 2

1. Inicie sessão no portal do Azure e [crie uma nova conta de armazenamento](/azure/storage/common/storage-account-create). 

1. Certifique-se de que ativa o **Espaço de nomes hierárquicos** no separador **Avançado**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Ativar o espaço de nomes hierárquicos no separador avançado.":::

1. Uma vez implementado, vá para a conta de armazenamento recém-criada. No painel de navegação, selecione **Definições** > **Chaves de acesso**. 

1. Copie o **Nome de conta** e **Chave** para as usar ao criar uma nova exportação.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Chaves de acesso numa conta de armazenamento.":::

## <a name="export-events"></a>Exportar eventos

Existem duas formas de exportar eventos: 
- Vá a **Dados** > **Exportações** e selecione **Nova exportação**.
- Aceda a **Dados** > **Eventos**, selecione **Mais [...]** junto do evento que pretende exportar e selecione **Exportar** no menu pendente. 

É guiado através dos passos para criar uma exportação:

1. Indique um **Nome de exportação**.

1. Na lista pendente **Seleção de eventos**, escolha os eventos base e eventos refinados a incluir na exportação. 

1. Na **Estrutura de ficheiros**, selecione a cadência para criar novos ficheiros no armazenamento do destino. Os eventos são exportados continuamente à medida que chegam.

1. Selecione o formato para a sua exportação. Pode escolher entre os formatos **Common Data Model**, **CSV** e **JSON**. Para utilizar a exportação com outras aplicações do Dynamics 365, recomendamos a utilização do formato Common Data Model.

1. No passo **Escolher destino** especifique a localização Azure Data Lake Storage Gen 2.
    1. **Nome da conta ADLS Gen 2** é o nome da conta de armazenamento para a qual pretende guardar a exportação. 
    1. **O caminho da pasta** define onde a exportação deve ser armazenada no sistema de ficheiros e na estrutura do diretório da conta de armazenamento.
    1. **Chave partilhada** está disponível no portal do Azure para a conta de armazenamento.

1. Rever e confirmar as suas seleções.

## <a name="view-and-manage-exports"></a>Ver e gerir páginas exportações

Depois de configurar uma exportação, vá à **Dados** > **Exportações** para ver. Selecione **Mais [...]** para qualquer exportação existente para a editar ou eliminar.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
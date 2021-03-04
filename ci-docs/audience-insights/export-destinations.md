---
title: Destinos de exportação
description: Exportar dados e gerir destinos de exportação.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477147"
---
# <a name="export-destinations-preview-overview"></a>Descrição geral de destinos de exportação (pré-visualização)

A página **Exportar destinos** mostra-lhe todos os locais que configurou para onde exportar dados. Também pode adicionar novos destinos para exportação. Além disso, mostra as opções de exportação atualmente disponíveis. Obtenha uma descrição geral rápida e saiba o que pode fazer com cada opção de extensibilidade. Exporte perfis, medidas e segmentos unificados para aplicações suportadas relevantes para o seu negócio.

Aceda a **Administração** > **Exportar destinos** para localizar as seguintes opções de extensibilidade:

- [Suplemento de Cartões de Clientes do Dynamics 365](customer-card-add-in.md)
- [Conector Gestor de Anúncios do Facebook](export-facebook.md)
- [Conector do Power Automate](export-power-automate.md)
- [Conector do Power Apps](export-power-apps.md)
- [Conector do Power BI](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Armazenamento de Blobs do Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [Conector do LiveRamp&reg;](export-liveramp.md)
- [Bot para o Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API do Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Adicionar um novo destino de exportação

Para adicionar destinos de exportação, tem [permissões de administrador](permissions.md). Se exportar para serviços da Microsoft, vamos supor que ambos os serviços estão na mesma organização.

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Alterne para o separador **Os meus destinos de exportação**.

1. Selecione **Adicionar destino** para criar um novo destino de exportação.

1. No painel **Adicionar destino**, selecione o **Tipo** de destino de exportação na lista pendente.

1. Forneça os detalhes necessários e selecione **Seguinte** para criar o destino de exportação.

Também pode selecionar **Configurar** num mosaico no separador **Descobrir**.

## <a name="view-export-destinations"></a>Ver Destinos de exportação

Depois de criar os destinos de exportação, irá encontrá-los numa tabela no separador **Os meus destinos de exportação**. Esta tabela tem três colunas:

- **Nome a apresentar**: o nome que introduziu ao criar o destino.
- **Tipo**: o tipo de destino de exportação que definiu ao criar o destino.
- **Criado em**: a data de criação do destino.

## <a name="edit-an-export-destination"></a>Editar um destino de exportação

1. Selecione as reticências verticais do destino de Exportação que pretende editar.

   > [!div class="mx-imgBorder"]
   > ![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")

1. Selecione **Editar** no menu pendente.

1. Altere os valores que necessitam de atualização e selecione **Guardar**.

## <a name="export-data-on-demand"></a>Exportar dados a pedido

Depois de configurar um conector para um destino de exportação, as exportações serão executadas com cada [atualização agendada](system.md#schedule-tab).

Para exportar dados sem aguardar uma atualização agendada, vá para o separador **Os meus destinos de exportação** em **Administrador** > **Destinos de exportação**.

> [!div class="mx-imgBorder"]
> ![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")

- Selecione **Exportar** acima da lista para executar a exportação para todos os destinos de exportação simultaneamente.
- Selecione as reticências (...) à frente de um item de lista e, em seguida, escolha a opção **Exportar** para executar a exportação para um único destino de exportação.

## <a name="remove-an-export-destination"></a>Remover um destino de Exportação

Para remover um destino de Exportação, inicie a partir da página principal **Exportar destinos**.

1. Selecione as reticências verticais do destino de Exportação que pretende remover.

   > [!div class="mx-imgBorder"]
   > ![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")

2. Selecione **Remover** no menu pendente.

3. Confirme a remoção selecionando **Remover** no ecrã de confirmação.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
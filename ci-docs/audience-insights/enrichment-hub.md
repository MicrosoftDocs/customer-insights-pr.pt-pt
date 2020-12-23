---
title: Melhorar perfis unificados de clientes
description: Utilize as capacidades para melhorar os dados dos seus clientes.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667108"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimento para perfis de clientes (pré-visualização)

Utilize dados de origens como a Microsoft e outros parceiros para enriquecer os dados dos seus clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do Hub de enriquecimento":::

Nos insights de audiência, vá a **Dados** > **Melhoramento** para trabalhar com opções de melhoramento.    
É preciso ter permissões de Contribuidor ou Administrador para criar ou editar enriquecimentos. Para mais informações, consulte [Permissões](permissions.md).

No separador **Descobrir**, encontrará os seguintes enriquecimentos:

- [Marcas](enrichment-microsoft-graph.md) fornecidas pelo Microsoft Graph
- [Interesses](enrichment-microsoft-graph.md) fornecidos pelo Microsoft Graph
- [Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace
- [Dados demográficos](enrichment-experian.md) fornecidos pela Experian
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados](enrichment-SFTP-custom-import.md) através de Secure File Transfer Protocol (SFTP)

No separador **Meus enriquecimentos**, pode ver os enriquecimentos que configurou e editar as suas propriedades.

## <a name="manage-existing-enrichments"></a>Gerir enriquecimentos existentes

Vá a **Meus enriquecimentos** para ver todos os enriquecimentos configurados. Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.

Selecione um enriquecimento para ver as opções disponíveis. Em alternativa, pode selecionar as reticências (...) num item de lista para ver as opções.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerir enriquecimentos na lista de enriquecimentos":::

- **Ver** os detalhes do enriquecimento com o número de perfis de cliente enriquecidos.
- **Editar** a configuração de enriquecimento.
- **Executar** o enriquecimento para atualizar perfis de clientes com os dados mais recentes.
- **Desativar** um enriquecimento existente para impedir que atualize automaticamente com cada atualização programada. Os dados da última atualização bem sucedida continuarão disponíveis. **Ativar** um enriquecimento inativo para reiniciar a atualização automática com cada atualização programada.
- **Eliminar** um melhoramento.

Pode executar ou desativar vários enriquecimentos de uma só vez selecionando-os na lista. As opções de ver e editar não estão disponíveis como ação em massa e só funcionam para um enriquecimento de cada vez.

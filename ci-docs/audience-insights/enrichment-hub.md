---
title: Melhorar perfis unificados de clientes
description: Utilize as capacidades para melhorar os dados dos seus clientes.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 992c45e30e2dff00f5207290940b56b2fe1c08ad
ms.sourcegitcommit: b9a81c2acd42d774669d2db3d0430c7d81de991c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/02/2021
ms.locfileid: "7470018"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimento para perfis de clientes (pré-visualização)

Utilize dados de origens como a Microsoft e outros parceiros para enriquecer os dados dos seus clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do Hub de enriquecimento.":::

Nos insights de audiência, vá a **Dados** > **Melhoramento** para trabalhar com opções de melhoramento.  

É preciso ter permissões de Contribuidor ou Administrador para criar ou editar enriquecimentos. Para mais informações, consulte [Permissões](permissions.md).

No separador **Descobrir**, encontrará os seguintes enriquecimentos:

- [Azure Maps](enrichment-azure-maps.md) fornecido pela Microsoft
- [Marcas](enrichment-microsoft.md) fornecidas pela Microsoft
- [Interesses](enrichment-microsoft.md) fornecidos pela Microsoft
- [Endereços melhorados](enrichment-enhanced-addresses.md) fornecidos pela Microsoft
- [Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace
- [Informações demográficas](enrichment-experian.md) fornecidas pela Experian
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados](enrichment-SFTP-custom-import.md) através de Secure File Transfer Protocol (SFTP)

No separador **Meus enriquecimentos**, pode ver os enriquecimentos que configurou e editar as suas propriedades.

## <a name="manage-existing-enrichments"></a>Gerir enriquecimentos existentes

Aceda ao separador **Os meus melhoramentos** para ver todos os melhoramentos configurados. Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.

Selecione o enriquecimento para ver as opções disponíveis. Também pode selecionar as reticências (...) num item de lista para ver as opções. Se configurou vários enriquecimentos, pode usar a caixa de pesquisa para encontrá-lo rapidamente.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerir enriquecimentos na lista de enriquecimentos.":::

- **Ver** os detalhes do enriquecimento com o número de perfis de cliente enriquecidos.
- **Editar** a configuração de enriquecimento.
- **Executar** o enriquecimento para atualizar perfis de clientes com os dados mais recentes.
- **Desativar** um enriquecimento existente para impedir que atualize automaticamente com cada atualização programada. Os dados da última atualização bem sucedida continuarão disponíveis. **Ativar** um enriquecimento inativo para reiniciar a atualização automática com cada atualização programada.
- **Eliminar** o enriquecimento.

Executar ou desativar vários enriquecimentos de uma só vez selecionando-os na lista. As opções de ver e editar não estão disponíveis como ação em massa. Só funcionam para um enriquecimento de cada vez.

## <a name="enrichments-and-connections"></a>Enriquecimentos e ligações

Os enriquecimentos de terceiros são configurados através de [ligações](connections.md), que um administrador configura com credenciais e fornece consentimento para transferências de dados. A ligação pode então ser utilizada por administradores e contribuidores para configurar enriquecimentos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiplos enriquecimentos do mesmo tipo

A entidade a enriquecer é especificada durante a configuração do enriquecimento, o que lhe permite enriquecer apenas um subconjunto dos seus perfis. Por exemplo, melhorar dados apenas para um segmento específico. Pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma ligação. Alguns enriquecimentos terão limites ao número de enriquecimentos do mesmo tipo que podem ser criados. Os limites e a utilização atual podem ser vistos na página de **Enriquecimento**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Veja o progresso do processo de melhoramento

Pode encontrar detalhes sobre o processamento de um melhoramento, incluindo o seu estado e potenciais problemas enquanto está a atualizar ou após uma atualização concluída. Entenda quais os processos envolvidos na atualização de um melhoramento e quanto tempo demorou a executar os processos. O estado do melhoramento é suportado para Experian, Leadspace, HERE Technologies, SFTP Import e Azure Maps.

Para ver o estado do melhoramento

1. Aceda a **Dados** > **Enriquecimento**. 
1. No separador **Os meus melhoramentos**, selecione o estado de um melhoramento para abrir um painel lateral. 
1. No painel **Detalhes do progresso**, expanda a secção **Melhoramentos**. 
1. Sob o melhoramento do qual pretende ver o progresso, selecione **Ver detalhes**. 
1. No painel **Detalhes da tarefa**, selecione **Mostrar detalhes** para ver os processos envolvidos na atualização do melhoramento e respetivo estado. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
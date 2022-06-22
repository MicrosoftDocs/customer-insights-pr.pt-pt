---
title: Melhorar perfis unificados de clientes
description: Utilize as capacidades para melhorar os dados dos seus clientes.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954055"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimento para perfis de clientes (pré-visualização)

Utilize dados de origens como a Microsoft e outros parceiros para enriquecer os dados dos seus clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do Hub de enriquecimento.":::

Aceda a **Dados** > **Melhorar** para trabalhar com opções de melhoramento.  

É preciso ter permissões de Contribuidor ou Administrador para criar ou editar enriquecimentos. Para mais informações, consulte [Permissões](permissions.md).

No separador **Descobrir**, encontrará todas as opções de melhoramento suportadas.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- [Identidade AbiliTec](enrichment-liveramp.md) fornecida por LiveRamp AbiliTec
- [Marcas](enrichment-microsoft.md) fornecidas pela Microsoft
- [Informações demográficas](enrichment-experian.md) fornecidas pela Experian
- [Endereços melhorados](enrichment-enhanced-addresses.md) fornecidos pela Microsoft
- [Interesses](enrichment-microsoft.md) fornecidos pela Microsoft
- [Dados de localização](enrichment-azure-maps.md) fornecidos por Microsoft Azure Maps
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados SFTP](enrichment-SFTP-custom-import.md) através de Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- [Dados de interação de contas](enrichment-office.md) fornecidos pela Microsoft
- [Dados da empresa](enrichment-dnb.md) fornecidos pela Dun & Bradstreet
- [Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace
- [Endereços melhorados](enrichment-enhanced-addresses.md) fornecidos pela Microsoft
- [Dados melhorados da empresa](enrichment-enhanced-company-data.md) fornecidos pela Microsoft
- [Dados de localização](enrichment-azure-maps.md) fornecidos por Microsoft Azure Maps
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados SFTP](enrichment-SFTP-custom-import.md) através de Secure File Transfer Protocol (SFTP)

---

No separador **Meus enriquecimentos**, pode ver os enriquecimentos que configurou e editar as suas propriedades. Também pode criar [segmentos](segments.md) ou [medidas](measures.md) a partir de melhoramentos.

## <a name="manage-existing-enrichments"></a>Gerir enriquecimentos existentes

Aceda ao separador **Os meus melhoramentos** para ver todos os melhoramentos configurados. Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.

Selecione o enriquecimento para ver as opções disponíveis. Também pode selecionar as reticências verticais (&vellip;) num item de lista para ver as opções. Se configurou vários enriquecimentos, pode usar a caixa de pesquisa para encontrá-lo rapidamente.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerir enriquecimentos na lista de enriquecimentos.":::

- **Ver** os detalhes do enriquecimento com o número de perfis de cliente enriquecidos.
- **Editar** a configuração de enriquecimento.
- **Executar** o enriquecimento para atualizar perfis de clientes com os dados mais recentes.
- **Desativar** um enriquecimento existente para impedir que atualize automaticamente com cada atualização programada. Os dados da última atualização bem sucedida continuarão disponíveis. **Ativar** um enriquecimento inativo para reiniciar a atualização automática com cada atualização programada.
- **Eliminar** o enriquecimento.

Executar ou desativar vários enriquecimentos de uma só vez selecionando-os na lista. As opções de ver e editar não estão disponíveis como ação em massa. Só funcionam para um enriquecimento de cada vez.

## <a name="enrichments-and-connections"></a>Enriquecimentos e ligações

Os enriquecimentos de terceiros são configurados através de [ligações](connections.md), que um administrador configura com credenciais e fornece consentimento para transferências de dados. As ligações podem ser utilizadas por administradores e contribuidores para configurar os melhoramentos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiplos enriquecimentos do mesmo tipo

A entidade a enriquecer é especificada durante a configuração do enriquecimento, o que lhe permite enriquecer apenas um subconjunto dos seus perfis. Por exemplo, melhorar dados apenas para um segmento específico. Pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma ligação. Alguns enriquecimentos terão limites ao número de enriquecimentos do mesmo tipo que podem ser criados. Os limites e a utilização atual podem ser vistos em cada mosaico no separador **Descobrir** da página **Melhorar**.

## <a name="enrich-data-sources-before-unification"></a>Melhorar origens de dados antes da unificação

Pode melhorar os dados de clientes antes da unificação de dados para ajudar a aumentar a qualidade de uma correspondência de dados. Para obter mais informações, consulte [melhoramento de origens de dados](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Executar ou atualizar melhoramentos

1. Para iniciar o processo de melhoramento, selecione **Executar**. Ou, deixe o sistema executar o melhoramento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento depende do tamanho dos dados do seu cliente.

1. Opcionalmente, [consulte o progresso do processo de melhoramento](#see-the-progress-of-the-enrichment-process).

1. Depois de concluído o processo de melhoramento, aceda a **Os meus melhoramentos** para rever os dados de perfis de cliente recentemente melhorados, a hora da última atualização e o número de perfis melhorados.

1. Selecione o melhoramento para ver [resultados de melhoramento](#enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Veja o progresso do processo de melhoramento

Pode encontrar detalhes sobre o processamento de um melhoramento, incluindo o seu estado e potenciais problemas enquanto está a atualizar ou após uma atualização concluída. Entenda quais os processos envolvidos na atualização de um melhoramento e quanto tempo demorou a executar os processos. O estado do melhoramento é suportado para Experian, Leadspace, HERE Technologies, SFTP Import e Azure Maps.

1. Aceda a **Dados** > **Enriquecimento**.
1. No separador **Os meus melhoramentos**, selecione o estado do melhoramento para abrir um painel lateral.
1. No painel **Detalhes do progresso**, expanda a secção **Melhoramentos**.
1. Sob o melhoramento do qual pretende ver o progresso, selecione **Ver detalhes**.
1. No painel **Detalhes da tarefa**, selecione **Mostrar detalhes** para ver os processos envolvidos na atualização do melhoramento e respetivo estado.

## <a name="enrichment-results"></a>Resultados do enriquecimento

Após uma execução de melhoramento concluída, reveja os resultados do melhoramento.

1. Aceda a **Dados** > **Enriquecimento**.
1. No separador **Os meus melhoramentos**, selecione o melhoramento sobre o qual pretende obter informações.

Todos os melhoramentos mostram informações básicas, como o número de perfis melhorados e o número de perfis melhorados ao longo do tempo. O mosaico **Pré-visualização de clientes melhorados** mostra uma amostra da entidade de melhoramento gerada. Para ver uma vista detalhada, selecione **Ver mais** e selecione o separador **Dados**.

:::image type="content" source="media/enrichments-results.png" alt-text="Página de resultados de melhoramentos.":::

Se disponível, o **Número de clientes melhorados por campo** proporciona uma desagregação da cobertura de cada campo melhorado.

Alguns melhoramentos também mostram informações específicas para o tipo de melhoramento. Para mais informações, consulte a documentação relacionada.

[!INCLUDE [footer-include](includes/footer-banner.md)]

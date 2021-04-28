---
title: Melhorar perfis unificados de clientes
description: Utilize as capacidades para melhorar os dados dos seus clientes.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896019"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimento para perfis de clientes (pré-visualização)

Utilize dados de origens como a Microsoft e outros parceiros para enriquecer os dados dos seus clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do Hub de enriquecimento":::

Nos insights de audiência, vá a **Dados** > **Melhoramento** para trabalhar com opções de melhoramento.    
É preciso ter permissões de Contribuidor ou Administrador para criar ou editar enriquecimentos. Para mais informações, consulte [Permissões](permissions.md).

No separador **Descobrir**, encontrará os seguintes enriquecimentos:

- [Marcas](enrichment-microsoft.md) fornecidas pela Microsoft
- [Interesses](enrichment-microsoft.md) fornecidos pela Microsoft
- [Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace
- [Dados demográficos](enrichment-experian.md) fornecidos pela Experian
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados](enrichment-SFTP-custom-import.md) através de Secure File Transfer Protocol (SFTP)

No separador **Meus enriquecimentos**, pode ver os enriquecimentos que configurou e editar as suas propriedades.

## <a name="manage-existing-enrichments"></a>Gerir enriquecimentos existentes

Vá a **Meus enriquecimentos** para ver todos os enriquecimentos configurados. Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.

Selecione um enriquecimento para ver as opções disponíveis. Também pode selecionar as reticências (...) num item de lista para ver as opções.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerir enriquecimentos na lista de enriquecimentos":::

- **Ver** os detalhes do enriquecimento com o número de perfis de cliente enriquecidos.
- **Editar** a configuração de enriquecimento.
- **Executar** o enriquecimento para atualizar perfis de clientes com os dados mais recentes.
- **Desativar** um enriquecimento existente para impedir que atualize automaticamente com cada atualização programada. Os dados da última atualização bem sucedida continuarão disponíveis. **Ativar** um enriquecimento inativo para reiniciar a atualização automática com cada atualização programada.
- **Eliminar** um melhoramento.

Pode executar ou desativar vários enriquecimentos de uma só vez selecionando-os na lista. As opções de ver e editar não estão disponíveis como ação em massa e só funcionam para um enriquecimento de cada vez.

## <a name="enrichments-and-connections"></a>Enriquecimentos e ligações

Os enriquecimentos de terceiros são configurados através de [ligações](connections.md), que um administrador configura com credenciais e fornece consentimento para transferências de dados. A ligação pode então ser utilizada por administradores e contribuidores para configurar enriquecimentos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiplos enriquecimentos do mesmo tipo

A entidade a enriquecer é especificada durante a configuração do enriquecimento, o que lhe permite enriquecer apenas um subconjunto dos seus perfis. Por exemplo, enriqueça dados apenas para um segmento específico. Pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma ligação. Alguns enriquecimentos terão limites ao número de enriquecimentos do mesmo tipo que podem ser criados. Os limites e a utilização atual podem ser vistos na página de **Enriquecimento**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

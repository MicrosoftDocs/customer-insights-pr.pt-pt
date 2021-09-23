---
title: Ativar relatórios de perfil fora da caixa
description: Como criar relatórios de perfil fora da caixa agrupados por sexo, idade e concelho ou região de origem.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486134"
---
# <a name="out-of-box-profile-reports"></a>Relatórios de perfil fora da caixa

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um relatório é uma recolha de visualização de dados para o ajudar a compreender o comportamento dos utilizadores. Ao ligar-se às informações de audiência do Customer Insights as informações de cativação podem mostrar um relatório com informações sobre perfis de clientes unificados. Este relatório inclui o número de perfis que tem, agrupados por sexo, idade e localização geográfica.

## <a name="prerequisites"></a>Pré-requisitos

O ambiente das informações de audiência deve armazenar dados numa conta Azure Data Lake Storage gerida pelo cliente.

Se estiver a utilizar uma versão experimental da capacidade de informações de audiência ou de um ambiente num data lake gerido pelo Customer Insights, [contacte-nos](https://go.microsoft.com/fwlink/?linkid=2145734) para obter assistência.  


## <a name="enable-the-customer-profile-report"></a>Ativar o relatório do perfil do cliente

Um admin de ambiente tem de [associar informações de cativação e informações de audiência](integrate-audience-insights-engagement-insights.md).

Depois de especificar os detalhes da ligação, o administrador pode conceder acesso a outras pessoas da organização para ver o relatório. O administrador de ambiente que configura a ligação tem acesso automaticamente ao relatório. 

Após completar a ligação, a função **Perfis** estará disponível no painel de navegação esquerdo. 

- Ir a **Descobrir** > **Perfis** para ver o relatório.

O relatório **Perfis** contém visualizações sobre o sexo, idade e localização geográfica dos perfis de clientes conectados.

:::image type="content" source="media/customer-profiles.png" alt-text="Relatório de perfis de cliente.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
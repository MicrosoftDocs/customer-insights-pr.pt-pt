---
title: Melhorar perfis de clientes com dados de identidade da LiveRamp (pré-visualização)
description: Melhore os perfis de clientes com dados do LiveRamp.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237827"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Melhorar perfis de clientes com dados de identidade da LiveRamp (pré-visualização)

A LiveRamp fornece uma resolução de identidade offline determinística e a consolidação dos dados de clientes. Pode mapear identificadores pessoais nos seus dados de clientes para o gráfico de identidade da AbiliTec e receber os IDs da AbiliTec. Em seguida, pode utilizar estes IDs para melhorar a unificação dos seus dados de clientes.

## <a name="supported-countriesregions"></a>Países/regiões suportados

Atualmente, suportamos o melhoramento de perfis de clientes com dados da LiveRamp apenas nos Estados Unidos.

## <a name="prerequisites"></a>Pré-requisitos

- Uma subscrição da LiveRamp ativa. Para obter uma subscrição, contacte a sua equipa da conta LiveRamp ou [dynamics@liveramp.com](mailto:dynamics@liveramp.com) para obter mais informações.

- Uma subscrição ativa da AbiliTec com um ID de cliente e segredo para aceder à API. Para mais informações, consulte [Hub de Programadores da API AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Uma [ligação](connections.md) LiveRamp é [configurada](#configure-the-connection-for-liveramp) por um administrador.

## <a name="configure-the-connection-for-liveramp"></a>Configurar a ligação para a LiveRamp

Tem de ser um [administrador](permissions.md#admin) no Customer Insights e ter um ID de cliente da LiveRamp e um segredo ativos.

1. Selecione **Adicionar ligação** ao configurar um melhoramento ou vá para **Admin** > **Ligações** e selecione **Configurar** no mosaico LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Painel de configuração para configurar a ligação ao serviço AbiliTec da LiveRamp. ":::

1. Introduza um nome para a ligação, um ID de cliente da LiveRamp válido e um segredo válidos.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Guardar**.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Melhorar os meus dados** no mosaico **Identidade** da LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Mosaico Identidade na página de descrição geral do melhoramento. ":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione a ligação. Contacte um administrador se não houver nenhuma ligação disponível.

1. Selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar com os dados de identidade da LiveRamp. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

1. Defina que tipos de campos dos seus perfis unificados utilizar para corresponder dados de identidade da LiveRamp. É necessário pelo menos um dos campos **Nome e endereço**, **E-mail** ou **Telefone**. Para maior precisão de correspondência, adicione outros campos. Selecione **Seguinte**.

1. Mapeie os campos para o dados de identificação a partir da LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opções de mapeamento de dados para o melhoramento da LiveRamp.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o melhoramento e o **Nome da entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

## <a name="view-enrichment-results"></a>Ver resultados de melhoramento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes melhorados por campo** proporciona uma desagregação da cobertura de cada campo melhorado.

## <a name="next-steps"></a>Próximos passos

Desenvolva a partir dos seus dados de clientes melhorados. Utilize os IDs da AbiliTec para consolidar os perfis de clientes numa vista baseada na pessoa.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

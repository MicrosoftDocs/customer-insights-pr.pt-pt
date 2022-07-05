---
title: Melhorar perfis da empresa com dados melhorados da empresa
description: Melhore e normalize os dados da empresa com os modelos da Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054262"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Melhorar perfis da empresa com dados melhorados da empresa

Utilize os modelos da Microsoft e compile os dados da empresa para corrigir, suplementar e normalizar os perfis da empresa. Utilizaremos o [formato do Common Data Model](/common-data-model/schema/core/applicationcommon/account) para uma melhor precisão e informações.

Também pode [melhorar os dados da empresa nas origens de dados](data-sources-enrichment.md) para melhorar a precisão de correspondência no processo de unificação de dados.

Para empresas públicas nos Estados Unidos, estão disponíveis informações como receitas, cotações da bolsa, setor e muito mais.  

## <a name="how-we-enhance-company-data"></a>Como melhoramos os dados da empresa

O nosso modelo passa por um processo de dois passos para melhorar o perfil da empresa. Primeiro, normaliza o nome da empresa. Por exemplo, *Microsoft Corp* será corrigido e normalizado para *Microsoft Corporation*. Tenta encontrar uma correspondência nos dados da empresa compilados da Microsoft. Se for encontrada uma correspondência, melhoramos o perfil da empresa com informações dos dados compilados da nossa empresa, incluindo o nome da empresa.

### <a name="example"></a>Exemplo

As informações da sua empresa podem não seguir um formato normalizado e conter erros ortográficos. O modelo tenta corrigir estes problemas e criar informações consistentes.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Limitações

O modelo não:

- Confirme a identidade da empresa. Não verificamos se a entrada é uma organização existente ou se uma empresa utiliza a saída como o respetivo nome padrão.
- Abrange empresas de forma abrangente em todo o mundo. Os dados da empresa compilados da Microsoft têm cobertura global, mas oferecem a maior parte da cobertura na Austrália, Canadá, Reino Unido e Estados Unidos.
- Uniformize os endereços da empresa globalmente. Atualmente, suportamos a uniformização dos endereços nestes países ou regiões: Austrália, Canadá, França, Alemanha, Itália, Japão, Reino Unido e Estados Unidos.
- Garanta a precisão ou atualização dos dados. Como as informações de negócio mudam com frequência, não podemos garantir que os dados melhorados da empresa fornecidos sejam sempre exatos ou atualizados.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Melhorar os meus dados** no mosaico **Dados de empresas melhorados**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Mosaico de melhoramento no centro de melhoramento para os dados da empresa.":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

1. Selecione os tipos de campos dos perfis da sua empresa a utilizar para fazer a correspondência com os dados da empresa compilados da Microsoft. Esta seleção irá afetar os campos de mapeamento a que tem acesso no próximo passo.

1. Selecione **Seguinte**.

1. Mapeie os campos da empresa para o dados da empresa a partir da Microsoft. Para maior precisão de correspondência, adicione mais campos.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Passo de mapeamento de dados ao configurar o melhoramento de uma empresa.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o melhoramento e a **Entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

## <a name="view-enrichment-results"></a>Ver resultados de melhoramento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Cartão de descrição geral

O mosaico **Descrição geral de alterações de clientes** mostra detalhes sobre a cobertura do melhoramento

- **Empresas processadas e alteradas**: o número de perfis de empresas de clientes que foram enriquecidos com sucesso.
- **Empresas processadas e não alteradas**: o número de perfis de empresas de clientes que foram reconhecidos, mas não alterados. Normalmente, isto acontece quando os dados de entrada são válidos e não podem ser melhorados pelo enriquecimento.
- **Empresas não processadas e não alteradas**: o número de perfis de empresas de clientes que foram não reconhecidos. Normalmente, isto acontece para dados de entrada que são inválidos ou não suportados pelo enriquecimento.

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

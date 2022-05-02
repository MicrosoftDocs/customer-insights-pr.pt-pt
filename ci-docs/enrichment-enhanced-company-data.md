---
title: Melhoramento de dados da empresa
description: Melhore e normalize os dados da empresa com os modelos da Microsoft.
ms.date: 04/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6aa38afa7f92b512d19b4967fc1652b5e43ad094
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646510"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Melhoramento de perfis da empresa com dados melhorados da empresa

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

Existem algumas limitações com os dados melhorados. Os itens da lista abaixo não são suportados pelo modelo.

1.  Confirme a identidade da empresa. Não verificamos se a entrada é uma organização existente ou se uma empresa utiliza a saída como o respetivo nome padrão.
2.  Abrange empresas de forma abrangente em todo o mundo. Os dados da empresa compilados da Microsoft têm cobertura global, mas oferecem a maior parte da cobertura na Austrália, Canadá, Reino Unido e Estados Unidos.
3.  Uniformize os endereços da empresa globalmente. Atualmente, suportamos a uniformização dos endereços nestes países ou regiões: Austrália, Canadá, França, Alemanha, Itália, Japão, Reino Unido e Estados Unidos.
4.  Garanta a precisão ou atualização dos dados. Como as informações de negócio mudam com frequência, não podemos garantir que os dados melhorados da empresa fornecidos sejam sempre exatos ou atualizados.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento**.

1. Selecione **Melhorar os meus dados** no mosaico **Dados de empresas melhorados**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Mosaico de melhoramento no centro de melhoramento para os dados da empresa.":::

1. Selecione o **Conjunto de dados do cliente** e escolha a entidade que contém os endereços que pretende enriquecer. Pode selecionar a entidade *Cliente* para enriquecer endereços em todos os seus perfis de clientes ou selecionar uma entidade de segmento para enriquecer endereços apenas nos perfis de clientes contidos nesse segmento.

1. Selecione os tipos de campos dos perfis da sua empresa que devem ser utilizados para fazer a correspondência com os dados da empresa compilados da Microsoft. Esta seleção irá afetar os campos de mapeamento a que tem acesso no próximo passo.

1.  Mapeie os campos da empresa a partir da sua entidade de cliente unificada. Quanto mais identificadores e campos de chave mapear, maior será a probabilidade de uma taxa de correspondência mais alta.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Passo de mapeamento de dados ao configurar o melhoramento de uma empresa.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento e para a entidade de saída.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="enrichment-results"></a>Resultados do enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando. Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento depende do tamanho dos dados do seu cliente.

Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.

Pode ver uma amostra dos dados enriquecidos no mosaico **Pré-visualização de clientes enriquecidos**. Selecione **Ver mais** e selecione o separador **Dados** para aceder a uma vista detalhada de cada perfil enriquecido.

### <a name="overview-card"></a>Cartão de descrição geral

O cartão de descrição geral mostra detalhes sobre a cobertura do enriquecimento. 

* **Empresas processadas e alteradas**: o número de perfis de empresas de clientes que foram enriquecidos com sucesso.

* **Empresas processadas e não alteradas**: o número de perfis de empresas de clientes que foram reconhecidos, mas não alterados. Normalmente, isto acontece quando os dados de entrada são válidos e não podem ser melhorados pelo enriquecimento.

* **Empresas não processadas e não alteradas**: o número de perfis de empresas de clientes que foram não reconhecidos. Normalmente, isto acontece para dados de entrada que são inválidos ou não suportados pelo enriquecimento.

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

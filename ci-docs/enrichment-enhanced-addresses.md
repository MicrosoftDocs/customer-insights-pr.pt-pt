---
title: Melhorar perfis de cliente com endereços melhorados (contém vídeo)
description: Enriqueça e normalize a informação de endereço dos perfis de cliente com os modelos da Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081230"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Melhorar perfis de cliente com endereços melhorados

Os endereços nos seus dados podem não estar estruturados, estar incompletos ou incorretos. Utilize os modelos da Microsoft para normalizar e enriquecer os seus endereços no [formato do Common Data Model](/common-data-model/schema/core/applicationcommon/address) para uma melhor precisão e informações.

Também pode [melhorar os endereços nas origens de dados](data-sources-enrichment.md) para melhorar a precisão de correspondência no processo de unificação de dados. 

## <a name="how-we-enhance-addresses"></a>Como melhoramos endereços

O nosso modelo passa por um processo em dois passos para melhorar um endereço. Em primeiro lugar, analisa o endereço para identificar os seus componentes e coloca-os num formato estruturado. Em seguida, utilizamos IA para corrigir, preencher e uniformizar os valores no endereço.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Exemplo

As informações de endereço podem estar num formato não padrão e conter erros ortográficos. O modelo pode corrigir estes problemas e criar endereços consistentes em perfis de clientes unificados.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Limitações

Os endereços melhorados só funcionam com os valores já existentes nos seus dados de endereços ingeridos. O modelo não:

1. Verifica se o endereço é um endereço válido.
2. Verifica se algum dos valores, tais como códigos postais ou nomes de rua, são válidos.
3. Muda valores que não reconhece.

O modelo utiliza técnicas baseadas em aprendizagem automática para melhorar endereços. Tal como com qualquer modelo baseado em aprendizagem automática, não é possível garantir 100 por cento de precisão.

## <a name="supported-countries-or-regions"></a>Países ou regiões suportados

Atualmente, suportamos endereços enriquecedores nestes países ou regiões:

- Austrália
- Canadá
- França
- Alemanha
- Itália
- Japão
- Reino Unido
- Estados Unidos da América

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Enriquecer os meus dados** no mosaico **Endereços melhorados**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de ecrã do mosaico de endereços melhorados.":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

1. Selecionar a forma como os endereços estão formatados no seu conjunto de dados. Escolha **Endereço de atributo único** se os endereços dos seus dados utilizarem um único campo. Escolha **Endereço de vários atributos** se os endereços dos seus dados utilizarem mais do que um campo de dados.

1. Selecione **Seguinte** e mapeie os campos de endereço a partir da entidade cliente unificada.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Página de mapeamento de campo de endereço melhorado.":::

   > [!NOTE]
   > País/Região é obrigatório em endereços de atributo único e de múltiplos atributos. Endereços que não contenham valores válidos ou valores de país/região suportados não serão melhorados.

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o melhoramento e a **Entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="view-enrichment-results"></a>Ver resultados de melhoramento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes melhorados por campo** proporciona uma desagregação da cobertura de cada campo melhorado.

### <a name="overview-card"></a>Cartão de descrição geral

O cartão **Descrição geral de alterações de clientes** mostra detalhes sobre a cobertura do melhoramento:

- **Endereços processados e alterados**: o número de perfis de clientes com endereços que foram enriquecidos com sucesso.
- **Endereços processados e não alterados**: o número de perfis de clientes com endereços que foram reconhecidos, mas não alterados. Normalmente, acontece quando os dados de entrada são válidos e não podem ser melhorados pelo enriquecimento.
- **Endereços não processados e não alterados**: o número de perfis com endereços que não foram reconhecidos. Normalmente, para dados de entrada que são inválidos ou não suportados pelo enriquecimento.

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

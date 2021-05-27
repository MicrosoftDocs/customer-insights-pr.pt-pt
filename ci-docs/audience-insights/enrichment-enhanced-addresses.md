---
title: Enriquecimento de melhorias de endereços
description: Enriqueça e normalize a informação de endereço dos perfis de cliente com os modelos da Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965592"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enriquecimento de perfis de clientes com endereços melhorados

Os endereços nos seus dados podem não estar estruturados, estar incompletos ou incorretos. Utilize os modelos da Microsoft para normalizar e enriquecer os seus endereços no [formato do Common Data Model](/common-data-model/schema/core/applicationcommon/address) para uma melhor precisão e informações.

## <a name="how-we-enhance-addresses"></a>Como melhoramos endereços

O nosso modelo passa por um processo em dois passos para melhorar um endereço. Em primeiro lugar, analisa o endereço para identificar os seus componentes e coloca-os num formato estruturado. Depois, utilizamos inteligência artificial para corrigir, completar e uniformizar os valores no endereço.

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

Os endereços melhorados apenas funcionam com os valores que já existem nos dados de endereços ingeridos. O modelo não: 

1. Verifica se o endereço é um endereço válido.
2. Verifica se algum dos valores, tais como códigos postais ou nomes de rua, são válidos.
3. Muda valores que não reconhece.

O modelo utiliza técnicas baseadas em aprendizagem automática para melhorar endereços. Embora apliquemos um limiar de confiança elevado para quando o modelo muda um valor de entrada, como em qualquer modelo baseado em ML, a precisão de 100% não é garantida.

## <a name="supported-countries-or-regions"></a>Países ou regiões suportados

Atualmente, suportamos endereços enriquecedores nestes países ou regiões: 

- Austrália
- Canadá
- Reino Unido
- Estados Unidos da América

Os endereços têm de conter um valor de país/região. Não processamos endereços para países ou regiões que não são suportados e endereços que não têm nenhum país ou região fornecido.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento**.

1. Selecione **Enriquecer os meus dados** no mosaico **Endereços melhorados**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de ecrã do mosaico de endereços melhorados.":::

1. Selecione o **Conjunto de dados do cliente** e escolha a entidade que contém os endereços que pretende enriquecer. Pode selecionar a entidade *Cliente* para enriquecer endereços em todos os seus perfis de clientes ou selecionar uma entidade de segmento para enriquecer endereços apenas nos perfis de clientes contidos nesse segmento.

1. Selecionar a forma como os endereços estão formatados no seu conjunto de dados. Escolha **Endereço de atributo único** se os endereços dos seus dados utilizarem um único campo. Escolha **Endereço de vários atributos** se os endereços dos seus dados utilizarem mais do que um campo de dados.

   > [!NOTE]
   > País/Região é obrigatório tanto no endereço de atributo único como no endereço de vários atributos. Endereços que não contenham valores válidos ou valores de país/região suportados não serão enriquecidos

1.  Mapeie os campos de endereço da sua entidade de cliente unificado.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Página de mapeamento de campo de endereço melhorado.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento e para a entidade de saída.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="enrichment-results"></a>Resultados do enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando. Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento depende do tamanho dos dados do seu cliente.

Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

## <a name="next-steps"></a>Passos seguintes

Desenvolva a partir dos seus dados de clientes melhorados. Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

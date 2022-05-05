---
title: Melhoramento de endereços (contém vídeo)
description: Enriqueça e normalize a informação de endereço dos perfis de cliente com os modelos da Microsoft.
ms.date: 01/19/2022
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
ms.openlocfilehash: b4fef3b5e30e1cac4e5cb4401498f2f0981a409e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646525"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enriquecimento de perfis de clientes com endereços melhorados

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

Os endereços melhorados apenas funcionam com os valores que já existem nos dados de endereços ingeridos. O modelo não: 

1. Verifica se o endereço é um endereço válido.
2. Verifica se algum dos valores, tais como códigos postais ou nomes de rua, são válidos.
3. Muda valores que não reconhece.

O modelo utiliza técnicas baseadas em aprendizagem automática para melhorar endereços. Embora apliquemos um limiar de confiança elevado para quando o modelo muda um valor de entrada, como em qualquer modelo baseado em aprendizagem automática, a precisão de 100 por cento não é garantida.

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

Os endereços têm de conter um valor de país/região. Não processamos endereços para países ou regiões que não são suportados e endereços que não têm nenhum país ou região fornecido.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento**.

1. Selecione **Enriquecer os meus dados** no mosaico **Endereços melhorados**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de ecrã do mosaico de endereços melhorados.":::

1. Selecione o **Conjunto de dados do cliente** e escolha a entidade que contém os endereços que pretende enriquecer. Pode selecionar a entidade *Cliente* para enriquecer endereços em todos os seus perfis de clientes ou selecionar uma entidade de segmento para enriquecer endereços apenas nos perfis de clientes contidos nesse segmento.

1. Selecionar a forma como os endereços estão formatados no seu conjunto de dados. Escolha **Endereço de atributo único** se os endereços dos seus dados utilizarem um único campo. Escolha **Endereço de vários atributos** se os endereços dos seus dados utilizarem mais do que um campo de dados.

   > [!NOTE]
   > País/Região é obrigatório em endereços de atributo único e de múltiplos atributos. Endereços que não contenham valores válidos ou valores de país/região suportados não serão melhorados.

1.  Mapeie os campos de endereço da sua entidade de cliente unificado.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Página de mapeamento de campo de endereço melhorado.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento e para a entidade de saída.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="enrichment-results"></a>Resultados do enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando. Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento depende do tamanho dos dados do seu cliente.

Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.

Pode ver uma amostra dos dados enriquecidos no mosaico **Pré-visualização de clientes enriquecidos**. Selecione **Ver mais** e selecione o separador **Dados** para aceder a uma vista detalhada de cada perfil enriquecido.

### <a name="overview-card"></a>Cartão de descrição geral

O cartão de descrição geral mostra detalhes sobre a cobertura do enriquecimento. 

* **Endereços processados e alterados**: o número de perfis de clientes com endereços que foram enriquecidos com sucesso.

* **Endereços processados e não alterados**: o número de perfis de clientes com endereços que foram reconhecidos, mas não alterados. Normalmente, acontece quando os dados de entrada são válidos e não podem ser melhorados pelo enriquecimento.

* **Endereços não processados e não alterados**: o número de perfis com endereços que não foram reconhecidos. Normalmente, para dados de entrada que são inválidos ou não suportados pelo enriquecimento.

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
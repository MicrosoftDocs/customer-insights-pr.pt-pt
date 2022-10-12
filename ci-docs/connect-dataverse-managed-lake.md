---
title: Conecte-se aos dados num data lake gerido do Microsoft Dataverse
description: Importar dados de um data lake gerido do Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609810"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conecte-se aos dados num data lake gerido do Microsoft Dataverse

Os utilizadores do Microsoft Dataverse podem ligar rapidamente a entidades analíticas num lake gerido do Microsoft Dataverse. Apenas uma origem de dados de um ambiente pode simultaneamente usar o mesmo lake gerido Dataverse.

> [!NOTE]
> Tem de ser um administrador da organização do Dataverse para prosseguir e ver a lista de entidades disponíveis no data lake gerido.

## <a name="prerequisites"></a>Pré-requisitos

- Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados numa localização diferente do local em que os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar, ou ligar a, os dados armazenados em serviços online, como o , concorda que os dados podem ser transferidos para, e armazenados com o Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft](https://www.microsoft.com/trust-center).

- Apenas entidades do Dataverse com o [controlo de alterações](/power-platform/admin/enable-change-tracking-control-data-synchronization) ativado são visíveis. Estas entidades podem ser exportadas para o data lake gerido pelo Dataverse e utilizadas no Customer Insights. Por predefinição, as tabelas do Dataverse de origem têm o controlo de alterações ativado. Tem de ativar o controlo de alterações para tabelas personalizadas. Para verificar se uma tabela do Dataverse tem o controlo de alterações ativado, aceda a [Power Apps](https://make.powerapps.com) > **Dados** > **Tabelas**. Encontre a tabela que lhe interessa e selecione-a. Vá a **Definições** > **Opções avançadas** e reveja a definição **Monitorizar alterações**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Ligar a um lake gerido do Dataverse

1. Aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Selecione **Microsoft Dataverse**.

1. Introduza um **Nome** para a origem de dados e uma **Descrição** opcional.

1. Forneça o **Endereço do servidor** da organização Dataverse e selecione **Iniciar sessão**.

1. Selecione as tabelas que pretende ingerir como entidades para o Customer Insights a partir da lista disponível.

   > [!NOTE]
   > Se algumas tabelas já estiverem selecionadas, poderão ser utilizadas por outras aplicações Dynamics 365 (tais como o Dynamics 365 Sales Insights ou o Customer Service Insights). Não pode alterar a seleção. Estas tabelas estarão disponíveis como entidades assim que a origem de dados for criada.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo a mostrar uma lista de entidades no ambiente do Dataverse.":::

1. Guarde a sua seleção para começar a sincronizar as tabelas selecionadas do Dataverse. Encontrará a ligação recentemente adicionada na página **Origens de dados**. Será colocado em fila para atualização e mostrará a contagem de entidades como 0, até que todas as tabelas selecionadas estejam sincronizadas.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revistos na página [**Entidades**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar uma origem de dados de lake gerido do Dataverse

Só edita a seleção de entidade depois de criar a origem de dados. Por exemplo, se entidades adicionais forem adicionadas ao Dataverse e quiser importá-las também.
Para se ligar a um data lake do Dataverse diferente, [crie uma nova origem de dados](#connect-to-a-dataverse-managed-lake).

1. Aceda a **Dados** > **Origens de dados**.

1. Junto da origem de dados que pretende atualizar, selecione **Editar**.

1. Selecione entidades adicionais a partir da lista de entidades disponíveis.

1. Clique em **Guardar** para aplicar as alterações e regressar à página **Origens de dados**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Razões comuns para erros de ingestão ou dados danificados

As verificações que se seguem são executadas nos dados ingeridos para expor registos danificados:

- O valor de um campo não corresponde ao tipo de dados da sua coluna.
- Os campos contêm carateres que fazem com que as colunas não correspondam ao esquema esperado. Por exemplo: aspas mal formatadas, aspas não fechadas ou carateres de nova linha.
- Se existirem as colunas datetime/date/datetimeoffset, o respetivo formato tem de ser especificado no modelo se não seguir o formato ISO padrão.

### <a name="schema-or-data-type-mismatch"></a>Erro de correspondência de esquema ou de tipo de dados

Se os dados não estão em conformidade com o esquema, os registos são classificados como danificados. Corrija os dados de origem ou o esquema e volte a ingerir os dados.

### <a name="datetime-fields-in-the-wrong-format"></a>Campos datetime no formato errado

Os campos datetime na entidade não estão em formato ISO ou en-US. O formato datetime predefinido no Customer Insights está no formato en-US. Todos os campos datetime numa entidade devem estar no mesmo formato. O Customer Insights suporta outros formatos, desde que as anotações ou caraterísticas sejam feitas ao nível da origem ou da entidade no model ou manifest.json. Por exemplo: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Num manifest.json, o formato datetime pode ser especificado ao nível da entidade ou ao nível do atributo. Ao nível da entidade, utilize "exhibitsTraits" na entidade no *.manifest.cdm.json para definir o formato datetime. Ao nível do atributo, utilize "appliedTraits" no atributo em the entityname.cdm.json.

**Manifest.json ao nível da entidade**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json ao nível do atributo**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]

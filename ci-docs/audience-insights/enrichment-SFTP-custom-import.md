---
title: Enriquecimento com importação personalizada SFTP
description: Informação geral sobre o melhoramento de importação personalizado SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: fa1d4ffd9f77e128b5d804e4562e964561f4684f
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618719"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer perfis de clientes com dados personalizados (pré-visualização)

A importação personalizada do Secure File Transfer Protocol (SFTP) permite importar dados que não têm de passar pelo processo de unificação de dados. É uma forma flexível, segura, e fácil de trazer os seus dados. A importação personalizada SFTP pode ser utilizada em combinação com a [exportação SFTP](export-sftp.md) que lhe permite exportar os dados do perfil do cliente que são necessários para o melhoramento. Os dados podem então ser processados e melhorados e a importação SFTP personalizada pode ser usada para trazer os dados melhorados de volta para a capacidade de informações de audiência do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a importação personalizada do SFTP, devem ser cumpridos os seguintes pré-requisitos:

- Tem o nome do ficheiro e a localização (caminho) do ficheiro a ser importado no anfitrião do SFTP.
- Existe um ficheiro *model.json* que especifica [o esquema do Common Data Model](/common-data-model/) para os dados a serem importados. Este ficheiro deve estar no mesmo diretório do ficheiro a importar.
- Uma ligação SFTP já foi configurada por um administrador *ou* tem permissões de [administrador](permissions.md#administrator). Precisará das credenciais, URL e número de porta do utilizador para a localização SFTP de onde pretende importar dados.


## <a name="configure-the-import"></a>Configurar a importação

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. No **mosaico de importação personalizada SFTP**, selecione **Enriquecer os meus dados** e, em seguida, selecione **Começar**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mosaico de importação personalizada SFTP.":::

1. Selecione uma [ligação](connections.md) na lista pendente. Contacte um administrador se não houver nenhuma ligação disponível. Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação** e escolhendo a **Importação Personalizada SFTP** na lista pendente.

1. Selecione **Ligar à Importação Personalizada** para confirmar a ligação selecionada.

1.  Selecione **Seguinte** e introduza o **Caminho** e o **Nome do ficheiro** do ficheiro de dados que pretende importar.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de ecrã ao introduzir a localização dos dados.":::

1. Selecione **Seguinte** e escolha o conjunto de dados do cliente. Isto pode ser todos os perfis de clientes ou um segmento.

1. Selecione **Seguinte** e forneça um nome para o enriquecimento e um nome para a entidade de saída. 

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configure a ligação para a Importação Personalizada SFTP 

Tens de ser um administrador para configurar ligações. Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico de Importação Personalizada.

1. Introduza um nome para a ligação na caixa **Nome a Apresentar**.

1. Introduza um nome de utilizador, palavra-passe e URL de anfitrião válidos para o servidor SFTP em que os dados a importar residem.

1. Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Uma vez concluída a verificação, a ligação pode ser guardada selecionando **Guardar**.

   > [!div class="mx-imgBorder"]
   > ![Página de configuração da ligação à Experian.](media/enrichment-SFTP-connection.png "Página de configuração da ligação à Experian")


## <a name="defining-field-mappings"></a>Definir mapeamentos de campo 

O diretório que contém o ficheiro a importar no servidor SFTP também deve conter um ficheiro *model.json*. Este ficheiro define o esquema a utilizar para a importação dos dados. O esquema tem de utilizar o [Common Data Model](/common-data-model/) para especificar o mapeamento de campos. Um exemplo simples de um ficheiro model.json parece-se com isto:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Resultados do enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando. Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados a importar e da ligação ao servidor SFTP.

Após a conclusão do processo de melhoramento, pode rever os seus dados de melhoramento personalizados recentemente importados em **Os meus melhoramentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Enriquecimento com importação personalizada SFTP
description: Informação geral sobre o melhoramento de importação personalizado SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595869"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer perfis de clientes com dados personalizados (pré-visualização)

A importação personalizada do Secure File Transfer Protocol (SFTP) permite importar dados que não têm de passar pelo processo de unificação de dados. É uma forma flexível, segura, e fácil de trazer os seus dados. A importação personalizada SFTP pode ser utilizada em combinação com a [exportação SFTP](export-sftp.md) que lhe permite exportar os dados do perfil do cliente que são necessários para o melhoramento. Os dados podem então ser processados, enriquecidos e a importação personalizada de SFTP pode ser utilizada para trazer os dados enriquecidos de volta à capacidade de insights da audiência do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a importação personalizada do SFTP, devem ser cumpridos os seguintes pré-requisitos:

- Tem credenciais de utilizador (nome de utilizador e palavra-chave) para o local SFTP de onde os dados que vão ser importados.
- Tem o URL e o número da porta (normalmente 22) para o anfitrião STFP.
- Tem o nome do ficheiro e a localização do ficheiro a ser importado no anfitrião SFTP.
- Há um ficheiro *model.json* que especifica o esquema para os dados a importar. Este ficheiro deve estar no mesmo diretório do ficheiro a importar.
- Tem permissão de [Administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuração

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. No **Mosaico de importação personalizada SFTP**, selecione **Melhorar os meus dados**.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de importação personalizada SFTP](media/SFTP_Custom_Import_tile.png "Mosaico de importação personalizada SFTP")

1. Selecione **Iniciar** e forneça as credenciais e o endereço para o servidor SFTP. Por exemplo, sftp://mysftpserver.com:22.

1. Introduza o nome do ficheiro que contém os dados e o caminho para o ficheiro no servidor SFTP se este não estiver na pasta raiz.

1. Confirmar todas as entradas, selecionando **Ligar à importação personalizada**.

   > [!div class="mx-imgBorder"]
   > ![Lista de opções de configuração de importação personalizada SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Lista de opções de configuração de importação personalizada SFTP")

## <a name="defining-field-mappings"></a>Definir mapeamentos de campo 

O diretório que contém o ficheiro a importar no servidor SFTP também deve conter um ficheiro *model.json*. Este ficheiro define o esquema a utilizar para a importação dos dados. O esquema tem de utilizar [o Common Data Model](/common-data-model/) para especificar o mapeamento de campo. Um exemplo simples de um ficheiro model.json parece-se com isto:

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

Desenvolva a partir dos seus dados de clientes melhorados. Criar [segmentos](segments.md), [medidas](measures.md), e [exportar os dados](export-destinations.md) para proporcionar experiências personalizadas aos seus clientes.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
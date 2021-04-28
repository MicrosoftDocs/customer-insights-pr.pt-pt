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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896295"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer perfis de clientes com dados personalizados (pré-visualização)

A importação personalizada do SFTP (Secure File Transfer Protocol) permite-lhe importar dados que não tenham de passar pelo processo de unificação de dados. É uma forma flexível, segura, e fácil de trazer os seus dados. A importação personalizada SFTP pode ser utilizada em combinação com a [exportação SFTP](export-sftp.md) que lhe permite exportar os dados do perfil do cliente que são necessários para o melhoramento. Os dados podem então ser processados, enriquecidos e a importação personalizada de SFTP pode ser utilizada para trazer os dados enriquecidos de volta à capacidade de insights da audiência do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a importação personalizada do SFTP, devem ser cumpridos os seguintes pré-requisitos:

- Tem o nome de ficheiro e a localização (caminho) do ficheiro a ser importado no anfitrião SFTP.
- Existe um ficheiro *model.json* que especifica [o esquema do Common Data Model](/common-data-model/) para os dados a serem importados. Este ficheiro deve estar no mesmo diretório do ficheiro a importar.
- Uma ligação SFTP já foi configurada por um administrador *ou* tem permissões de [administrador](permissions.md#administrator). Precisará das credenciais, URL e número de porta do utilizador para a localização SFTP de onde pretende importar dados.


## <a name="configure-the-import"></a>Configurar a importação

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. No **mosaico de importação personalizada SFTP**, selecione **Enriquecer os meus dados** e, em seguida, selecione **Começar**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mosaico de importação personalizada SFTP.":::

1. Selecione uma [ligação](connections.md) na lista pendente. Contacte um administrador se não houver nenhuma ligação disponível. Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação** e escolhendo a **Importação Personalizada SFTP** na lista pendente.

1. Selecione **Ligar à Importação Personalizada** para confirmar a ligação selecionada.

1.  Selecione **Seguinte** e insira o **Nome de ficheiro** e o **Caminho** do ficheiro de dados que pretende importar.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de ecrã ao introduzir a localização dos dados.":::

1. Selecione **Seguinte** e forneça um nome para o enriquecimento e um nome para a entidade de saída. 

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configure a ligação para a Importação Personalizada SFTP 

Tens de ser um administrador para configurar ligações. Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico de Importação Personalizada.

1. Introduza um nome para a ligação na caixa **Nome a Apresentar**.

1. Introduza o nome de utilizador, a palavra-passe e o URL válidos do anfitrião para o servidor STFP onde residem os dados a importar.

1. Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Uma vez concluída a verificação, a ligação pode ser guardada clicando em **Guardar**.

> [!div class="mx-imgBorder"]
   > ![Página de configuração de ligação à Experian](media/enrichment-SFTP-connection.png "Página de configuração de ligação à Experian")


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

---
title: Melhorar os perfis dos clientes com importação personalizada SFTP (pré-visualização)
description: Informação geral sobre o melhoramento de importação personalizado SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 88fc366ab9478c3b67034af794e237ff4573da7c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081338"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Melhorar os perfis dos clientes com importação personalizada SFTP (pré-visualização)

A importação personalizada do Secure File Transfer Protocol (SFTP) permite importar dados que não têm de passar pelo processo de unificação de dados. É uma forma flexível, segura, e fácil de trazer os seus dados. A importação personalizada SFTP pode ser utilizada em combinação com a [exportação SFTP](export-sftp.md) que lhe permite exportar os dados do perfil do cliente que são necessários para o melhoramento. Os dados podem então ser processados e melhorados, sendo possível utilizar a importação personalizada de SFTP para trazer os dados melhorados de volta para o Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

- O nome do ficheiro e a localização (caminho) do ficheiro a importar no anfitrião SFTP são conhecidos.

- Está disponível um ficheiro *model.json* que especifica o esquema do Common Data Model para os dados a importar. Este ficheiro deve estar no mesmo diretório do ficheiro a importar.

- Uma [ligação](connections.md) SFTP é [configurada](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Exemplo de esquema de ficheiro

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configure a ligação para a Importação Personalizada SFTP

Tem de ser um [administrador](permissions.md#admin) no Customer Insights e ter as credenciais de utilizador, URL e número da porta para a localização SFTP a partir da qual pretende importar dados.

1. Selecione **Adicionar ligação** ao configurar um enriquecimento ou vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico de Importação Personalizada.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Página de configuração de ligação de Importação Personalizada.":::

1. Introduzir um nome para a ligação.

1. Introduza um nome de utilizador, palavra-passe e URL de anfitrião válidos para o servidor SFTP em que os dados a importar residem.

1. Reveja e forneça o seu consentimento para a [Privacidade e conformidade dos dados](#data-privacy-and-compliance) selecionando **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Guardar**.

### <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados utilizando a Importação Personalizada, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá estes dados após a sua instrução, mas é responsável por assegurar que os Dados cumprem quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.

## <a name="configure-the-import"></a>Configurar a importação

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Melhorar os meus dados** no mosaico **Importação personalizada SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mosaico de importação personalizada SFTP.":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione a ligação. Contacte um administrador, caso não esteja nenhuma disponível.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

1. Selecione **Seguinte**.

1. Introduza o **Caminho** e o **Nome de ficheiro** do ficheiro de dados que pretende importar.

1. Selecione **Seguinte**.

1. Forneça um **Nome** para o melhoramento e o **Nome da entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

## <a name="view-enrichment-results"></a>Ver resultados de melhoramento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Próximos passos

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

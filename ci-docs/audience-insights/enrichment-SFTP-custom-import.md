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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="4709d-103">Enriquecer perfis de clientes com dados personalizados (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="4709d-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="4709d-104">A importação personalizada do Secure File Transfer Protocol (SFTP) permite importar dados que não têm de passar pelo processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="4709d-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="4709d-105">É uma forma flexível, segura, e fácil de trazer os seus dados.</span><span class="sxs-lookup"><span data-stu-id="4709d-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="4709d-106">A importação personalizada SFTP pode ser utilizada em combinação com a [exportação SFTP](export-sftp.md) que lhe permite exportar os dados do perfil do cliente que são necessários para o melhoramento.</span><span class="sxs-lookup"><span data-stu-id="4709d-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="4709d-107">Os dados podem então ser processados, enriquecidos e a importação personalizada de SFTP pode ser utilizada para trazer os dados enriquecidos de volta à capacidade de insights da audiência do Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4709d-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4709d-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4709d-108">Prerequisites</span></span>

<span data-ttu-id="4709d-109">Para configurar a importação personalizada do SFTP, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="4709d-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4709d-110">Tem credenciais de utilizador (nome de utilizador e palavra-chave) para o local SFTP de onde os dados que vão ser importados.</span><span class="sxs-lookup"><span data-stu-id="4709d-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="4709d-111">Tem o URL e o número da porta (normalmente 22) para o anfitrião STFP.</span><span class="sxs-lookup"><span data-stu-id="4709d-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="4709d-112">Tem o nome do ficheiro e a localização do ficheiro a ser importado no anfitrião SFTP.</span><span class="sxs-lookup"><span data-stu-id="4709d-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="4709d-113">Há um ficheiro *model.json* que especifica o esquema para os dados a importar.</span><span class="sxs-lookup"><span data-stu-id="4709d-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="4709d-114">Este ficheiro deve estar no mesmo diretório do ficheiro a importar.</span><span class="sxs-lookup"><span data-stu-id="4709d-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="4709d-115">Tem permissão de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="4709d-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="4709d-116">Configuração</span><span class="sxs-lookup"><span data-stu-id="4709d-116">Configuration</span></span>

1. <span data-ttu-id="4709d-117">Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="4709d-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4709d-118">No **Mosaico de importação personalizada SFTP**, selecione **Melhorar os meus dados**.</span><span class="sxs-lookup"><span data-stu-id="4709d-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4709d-119">![Mosaico de importação personalizada SFTP](media/SFTP_Custom_Import_tile.png "Mosaico de importação personalizada SFTP")</span><span class="sxs-lookup"><span data-stu-id="4709d-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="4709d-120">Selecione **Iniciar** e forneça as credenciais e o endereço para o servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="4709d-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="4709d-121">Por exemplo, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="4709d-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="4709d-122">Introduza o nome do ficheiro que contém os dados e o caminho para o ficheiro no servidor SFTP se este não estiver na pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="4709d-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="4709d-123">Confirmar todas as entradas, selecionando **Ligar à importação personalizada**.</span><span class="sxs-lookup"><span data-stu-id="4709d-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4709d-124">![Lista de opções de configuração de importação personalizada SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Lista de opções de configuração de importação personalizada SFTP")</span><span class="sxs-lookup"><span data-stu-id="4709d-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="4709d-125">Definir mapeamentos de campo</span><span class="sxs-lookup"><span data-stu-id="4709d-125">Defining field mappings</span></span> 

<span data-ttu-id="4709d-126">O diretório que contém o ficheiro a importar no servidor SFTP também deve conter um ficheiro *model.json*.</span><span class="sxs-lookup"><span data-stu-id="4709d-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="4709d-127">Este ficheiro define o esquema a utilizar para a importação dos dados.</span><span class="sxs-lookup"><span data-stu-id="4709d-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="4709d-128">O esquema tem de utilizar [o Common Data Model](/common-data-model/) para especificar o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="4709d-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="4709d-129">Um exemplo simples de um ficheiro model.json parece-se com isto:</span><span class="sxs-lookup"><span data-stu-id="4709d-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="4709d-130">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="4709d-130">Enrichment results</span></span>

<span data-ttu-id="4709d-131">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="4709d-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4709d-132">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4709d-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4709d-133">O tempo de processamento dependerá do tamanho dos dados a importar e da ligação ao servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="4709d-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="4709d-134">Após a conclusão do processo de melhoramento, pode rever os seus dados de melhoramento personalizados recentemente importados em **Os meus melhoramentos**.</span><span class="sxs-lookup"><span data-stu-id="4709d-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="4709d-135">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="4709d-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4709d-136">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="4709d-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4709d-137">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="4709d-137">Next steps</span></span>

<span data-ttu-id="4709d-138">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="4709d-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4709d-139">Criar [segmentos](segments.md), [medidas](measures.md), e [exportar os dados](export-destinations.md) para proporcionar experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="4709d-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]
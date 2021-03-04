---
title: Enriquecimento com importação personalizada SFTP
description: Informação geral sobre o melhoramento de importação personalizado SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269620"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="d3f42-103">Enriquecer perfis de clientes com dados personalizados (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="d3f42-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="d3f42-104">A importação personalizada do Secure File Transfer Protocol (SFTP) permite importar dados que não têm de passar pelo processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="d3f42-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="d3f42-105">É uma forma flexível, segura, e fácil de trazer os seus dados.</span><span class="sxs-lookup"><span data-stu-id="d3f42-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="d3f42-106">A importação personalizada SFTP pode ser utilizada em combinação com a [exportação SFTP](export-sftp.md) que lhe permite exportar os dados do perfil do cliente que são necessários para o melhoramento.</span><span class="sxs-lookup"><span data-stu-id="d3f42-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="d3f42-107">Os dados podem então ser processados, enriquecidos e a importação personalizada de SFTP pode ser utilizada para trazer os dados enriquecidos de volta à capacidade de insights da audiência do Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d3f42-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3f42-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d3f42-108">Prerequisites</span></span>

<span data-ttu-id="d3f42-109">Para configurar a importação personalizada do SFTP, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="d3f42-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d3f42-110">Tem credenciais de utilizador (nome de utilizador e palavra-chave) para o local SFTP de onde os dados que vão ser importados.</span><span class="sxs-lookup"><span data-stu-id="d3f42-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="d3f42-111">Tem o URL e o número da porta (normalmente 22) para o anfitrião STFP.</span><span class="sxs-lookup"><span data-stu-id="d3f42-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="d3f42-112">Tem o nome do ficheiro e a localização do ficheiro a ser importado no anfitrião SFTP.</span><span class="sxs-lookup"><span data-stu-id="d3f42-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="d3f42-113">Há um ficheiro *model.json* que especifica o esquema para os dados a importar.</span><span class="sxs-lookup"><span data-stu-id="d3f42-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="d3f42-114">Este ficheiro deve estar no mesmo diretório do ficheiro a importar.</span><span class="sxs-lookup"><span data-stu-id="d3f42-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="d3f42-115">Tem permissão de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="d3f42-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="d3f42-116">Configuração</span><span class="sxs-lookup"><span data-stu-id="d3f42-116">Configuration</span></span>

1. <span data-ttu-id="d3f42-117">Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="d3f42-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="d3f42-118">No **Mosaico de importação personalizada SFTP**, selecione **Melhorar os meus dados**.</span><span class="sxs-lookup"><span data-stu-id="d3f42-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3f42-119">![Mosaico de importação personalizada SFTP](media/SFTP_Custom_Import_tile.png "Mosaico de importação personalizada SFTP")</span><span class="sxs-lookup"><span data-stu-id="d3f42-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="d3f42-120">Selecione **Iniciar** e forneça as credenciais e o endereço para o servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="d3f42-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="d3f42-121">Por exemplo, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="d3f42-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="d3f42-122">Introduza o nome do ficheiro que contém os dados e o caminho para o ficheiro no servidor SFTP se este não estiver na pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="d3f42-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="d3f42-123">Confirmar todas as entradas, selecionando **Ligar à importação personalizada**.</span><span class="sxs-lookup"><span data-stu-id="d3f42-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3f42-124">![Lista de opções de configuração de importação personalizada SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Lista de opções de configuração de importação personalizada SFTP")</span><span class="sxs-lookup"><span data-stu-id="d3f42-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="d3f42-125">Definir mapeamentos de campo</span><span class="sxs-lookup"><span data-stu-id="d3f42-125">Defining field mappings</span></span> 

<span data-ttu-id="d3f42-126">O diretório que contém o ficheiro a importar no servidor SFTP também deve conter um ficheiro *model.json*.</span><span class="sxs-lookup"><span data-stu-id="d3f42-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="d3f42-127">Este ficheiro define o esquema a utilizar para a importação dos dados.</span><span class="sxs-lookup"><span data-stu-id="d3f42-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="d3f42-128">O esquema tem de utilizar [o Common Data Model](https://docs.microsoft.com/common-data-model/) para especificar o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="d3f42-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="d3f42-129">Um exemplo simples de um ficheiro model.json parece-se com isto:</span><span class="sxs-lookup"><span data-stu-id="d3f42-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="d3f42-130">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="d3f42-130">Enrichment results</span></span>

<span data-ttu-id="d3f42-131">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="d3f42-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d3f42-132">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d3f42-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d3f42-133">O tempo de processamento dependerá do tamanho dos dados a importar e da ligação ao servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="d3f42-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="d3f42-134">Após a conclusão do processo de melhoramento, pode rever os seus dados de melhoramento personalizados recentemente importados em **Os meus melhoramentos**.</span><span class="sxs-lookup"><span data-stu-id="d3f42-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="d3f42-135">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="d3f42-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d3f42-136">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="d3f42-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3f42-137">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="d3f42-137">Next steps</span></span>

<span data-ttu-id="d3f42-138">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="d3f42-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d3f42-139">Criar [segmentos](segments.md), [medidas](measures.md), e [exportar os dados](export-destinations.md) para proporcionar experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="d3f42-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]
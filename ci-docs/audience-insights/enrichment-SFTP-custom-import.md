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
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304664"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="b0d9c-103">Enriquecer perfis de clientes com dados personalizados (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="b0d9c-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="b0d9c-104">A importação personalizada do Secure File Transfer Protocol (SFTP) permite importar dados que não têm de passar pelo processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="b0d9c-105">É uma forma flexível, segura, e fácil de trazer os seus dados.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="b0d9c-106">A importação personalizada SFTP pode ser utilizada em combinação com a [exportação SFTP](export-sftp.md) que lhe permite exportar os dados do perfil do cliente que são necessários para o melhoramento.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="b0d9c-107">Os dados podem então ser processados e melhorados e a importação SFTP personalizada pode ser usada para trazer os dados melhorados de volta para a capacidade de informações de audiência do Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0d9c-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b0d9c-108">Prerequisites</span></span>

<span data-ttu-id="b0d9c-109">Para configurar a importação personalizada do SFTP, devem ser cumpridos os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="b0d9c-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b0d9c-110">Tem o nome do ficheiro e a localização (caminho) do ficheiro a ser importado no anfitrião do SFTP.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="b0d9c-111">Existe um ficheiro *model.json* que especifica [o esquema do Common Data Model](/common-data-model/) para os dados a serem importados.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="b0d9c-112">Este ficheiro deve estar no mesmo diretório do ficheiro a importar.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="b0d9c-113">Uma ligação SFTP já foi configurada por um administrador *ou* tem permissões de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="b0d9c-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="b0d9c-114">Precisará das credenciais, URL e número de porta do utilizador para a localização SFTP de onde pretende importar dados.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="b0d9c-115">Configurar a importação</span><span class="sxs-lookup"><span data-stu-id="b0d9c-115">Configure the import</span></span>

1. <span data-ttu-id="b0d9c-116">Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="b0d9c-117">No **mosaico de importação personalizada SFTP**, selecione **Enriquecer os meus dados** e, em seguida, selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mosaico de importação personalizada SFTP.":::

1. <span data-ttu-id="b0d9c-119">Selecione uma [ligação](connections.md) na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="b0d9c-120">Contacte um administrador se não houver nenhuma ligação disponível.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="b0d9c-121">Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação** e escolhendo a **Importação Personalizada SFTP** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="b0d9c-122">Selecione **Ligar à Importação Personalizada** para confirmar a ligação selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="b0d9c-123">Selecione **Seguinte** e introduza o **Caminho** e o **Nome do ficheiro** do ficheiro de dados que pretende importar.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de ecrã ao introduzir a localização dos dados.":::

1. <span data-ttu-id="b0d9c-125">Selecione **Seguinte** e forneça um nome para o enriquecimento e um nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="b0d9c-126">Selecione **Guardar enriquecimento** depois de rever as suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="b0d9c-127">Configure a ligação para a Importação Personalizada SFTP</span><span class="sxs-lookup"><span data-stu-id="b0d9c-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="b0d9c-128">Tens de ser um administrador para configurar ligações.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b0d9c-129">Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico de Importação Personalizada.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="b0d9c-130">Introduza um nome para a ligação na caixa **Nome a Apresentar**.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b0d9c-131">Introduza um nome de utilizador, palavra-passe e URL de anfitrião válidos para o servidor SFTP em que os dados a importar residem.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="b0d9c-132">Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b0d9c-133">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b0d9c-134">Uma vez concluída a verificação, a ligação pode ser guardada selecionando **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0d9c-135">![Página de configuração da ligação à Experian](media/enrichment-SFTP-connection.png "Página de configuração da ligação à Experian")</span><span class="sxs-lookup"><span data-stu-id="b0d9c-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="b0d9c-136">Definir mapeamentos de campo</span><span class="sxs-lookup"><span data-stu-id="b0d9c-136">Defining field mappings</span></span> 

<span data-ttu-id="b0d9c-137">O diretório que contém o ficheiro a importar no servidor SFTP também deve conter um ficheiro *model.json*.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="b0d9c-138">Este ficheiro define o esquema a utilizar para a importação dos dados.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="b0d9c-139">O esquema tem de utilizar o [Common Data Model](/common-data-model/) para especificar o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="b0d9c-140">Um exemplo simples de um ficheiro model.json parece-se com isto:</span><span class="sxs-lookup"><span data-stu-id="b0d9c-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="b0d9c-141">Resultados do enriquecimento</span><span class="sxs-lookup"><span data-stu-id="b0d9c-141">Enrichment results</span></span>

<span data-ttu-id="b0d9c-142">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b0d9c-143">Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b0d9c-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b0d9c-144">O tempo de processamento dependerá do tamanho dos dados a importar e da ligação ao servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="b0d9c-145">Após a conclusão do processo de melhoramento, pode rever os seus dados de melhoramento personalizados recentemente importados em **Os meus melhoramentos**.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="b0d9c-146">Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b0d9c-147">Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0d9c-148">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="b0d9c-148">Next steps</span></span>

<span data-ttu-id="b0d9c-149">Desenvolva a partir dos seus dados de clientes melhorados.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b0d9c-150">Crie [segmentos](segments.md), [medidas](measures.md) e [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="b0d9c-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

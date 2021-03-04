---
title: Exportar dados Customer Insights para anfitriões SFTP
description: Saiba como configurar a ligação a um anfitrião SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268012"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="66763-103">Conector para SFTP (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="66763-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="66763-104">Utilize os seus dados de clientes em aplicações de terceiros, exportando-os para um anfitrião SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="66763-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66763-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="66763-105">Prerequisites</span></span>

- <span data-ttu-id="66763-106">Disponibilidade de um anfitrião SFTP e credenciais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="66763-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="66763-107">Ligar à SFTP</span><span class="sxs-lookup"><span data-stu-id="66763-107">Connect to SFTP</span></span>

1. <span data-ttu-id="66763-108">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="66763-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="66763-109">Em **SFTP**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="66763-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="66763-110">Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="66763-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="66763-111">Forneça um **Nome de utilizador**, **Palavra-passe**, **Nome do anfitrião** e **Pasta de exportação** para a sua conta SFTP.</span><span class="sxs-lookup"><span data-stu-id="66763-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="66763-112">Selecione **Verificar** para testar a ligação.</span><span class="sxs-lookup"><span data-stu-id="66763-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="66763-113">Após uma verificação bem sucedida, escolha se pretende exportar os seus dados **Comprimidos por G** ou **Não comprimidos** e selecione o **delimitador de campo** para os ficheiros exportados.</span><span class="sxs-lookup"><span data-stu-id="66763-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="66763-114">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="66763-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="66763-115">Selecione **Seguinte** para começar aconfigurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="66763-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="66763-116">Configurar a exportação</span><span class="sxs-lookup"><span data-stu-id="66763-116">Configure the export</span></span>

1. <span data-ttu-id="66763-117">Selecione as entidades, para segmentos de exemplo, que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="66763-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="66763-118">Cada entidade selecionada terá até cinco ficheiros de saída quando exportado.</span><span class="sxs-lookup"><span data-stu-id="66763-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="66763-119">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="66763-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="66763-120">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="66763-120">Export the data</span></span>

<span data-ttu-id="66763-121">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="66763-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="66763-122">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="66763-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="66763-123">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="66763-123">Known limitations</span></span>

- <span data-ttu-id="66763-124">O runtime de uma exportação depende do desempenho do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="66763-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="66763-125">Recomendamos dois núcleos CPU e 1 Gb de memória como configuração mínima do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="66763-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="66763-126">As entidades exportadoras com até 100 milhões de perfis de clientes podem demorar 90 minutos quando utilizam a configuração mínima recomendada de dois núcleos CPU e 1 Gb de memória.</span><span class="sxs-lookup"><span data-stu-id="66763-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="66763-127">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="66763-127">Data privacy and compliance</span></span>

<span data-ttu-id="66763-128">Quando ativa Dynamics 365 Customer Insights para transmitir dados através de SFTP, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="66763-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="66763-129">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o destino de exportação cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="66763-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="66763-130">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="66763-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="66763-131">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="66763-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
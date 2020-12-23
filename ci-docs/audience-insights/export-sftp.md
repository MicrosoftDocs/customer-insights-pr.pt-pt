---
title: Exportar dados Customer Insights para anfitriões SFTP
description: Saiba como configurar a ligação a um anfitrião SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643517"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="deee4-103">Conector para SFTP (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="deee4-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="deee4-104">Utilize os seus dados de clientes em aplicações de terceiros, exportando-os para um anfitrião SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="deee4-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="deee4-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="deee4-105">Prerequisites</span></span>

- <span data-ttu-id="deee4-106">Disponibilidade de um anfitrião SFTP e credenciais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="deee4-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="deee4-107">Ligar ao SFTP</span><span class="sxs-lookup"><span data-stu-id="deee4-107">Connect to SFTP</span></span>

1. <span data-ttu-id="deee4-108">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="deee4-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="deee4-109">Em **SFTP**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="deee4-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="deee4-110">Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="deee4-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="deee4-111">Forneça um **nome de utilizador**, **palavra-passe** e **nome do anfitrião** para a sua conta SFTP.</span><span class="sxs-lookup"><span data-stu-id="deee4-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="deee4-112">Exemplo: Se a pasta raiz do seu servidor SFTP é /root/folder, e gostaria que os dados fossem exportados para /root/folder/ci_export_destination_folder, o anfitrião deve ser sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="deee4-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="deee4-113">Selecione **Verificar** para testar a ligação.</span><span class="sxs-lookup"><span data-stu-id="deee4-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="deee4-114">Após uma verificação bem sucedida, escolha se pretende exportar os seus dados **Em zip** ou **Sem zip** e selecione o **delimitador de campo** para os ficheiros exportados.</span><span class="sxs-lookup"><span data-stu-id="deee4-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="deee4-115">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="deee4-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="deee4-116">Selecione **Seguinte** para começar aconfigurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="deee4-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="deee4-117">Configurar a ligação</span><span class="sxs-lookup"><span data-stu-id="deee4-117">Configure the connection</span></span>

1. <span data-ttu-id="deee4-118">Selecione os **atributos do cliente** que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="deee4-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="deee4-119">Pode exportar um ou vários atributos.</span><span class="sxs-lookup"><span data-stu-id="deee4-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="deee4-120">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="deee4-120">Select **Next**.</span></span>

1. <span data-ttu-id="deee4-121">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="deee4-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="deee4-122">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="deee4-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="deee4-123">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="deee4-123">Export the data</span></span>

<span data-ttu-id="deee4-124">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="deee4-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="deee4-125">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="deee4-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="deee4-126">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="deee4-126">Data privacy and compliance</span></span>

<span data-ttu-id="deee4-127">Quando ativa Dynamics 365 Customer Insights para transmitir dados através de SFTP, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="deee4-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="deee4-128">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o destino de exportação cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="deee4-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="deee4-129">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="deee4-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="deee4-130">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="deee4-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

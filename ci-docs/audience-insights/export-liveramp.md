---
title: Conector do LiveRamp
description: Obter informações sobre como exportar dados para o LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270172"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="eb5b9-103">Conector do LiveRamp&reg; (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="eb5b9-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="eb5b9-104">Ativar os seus dados no LiveRamp para ligar a mais de 500 plataformas em ecossistemas digitais, de redes sociais e de TV.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="eb5b9-105">Trabalhar com os seus dados no LiveRamp para campanhas publicitárias com alvo, supressão e personalizar.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb5b9-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="eb5b9-106">Prerequisites</span></span>

- <span data-ttu-id="eb5b9-107">Necessita de uma subscrição do LiveRamp para utilizar este conector.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="eb5b9-108">Para obter uma subscrição, [contacte a LiveRamp](https://liveramp.com/contact/) diretamente.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="eb5b9-109">[Obtenha mais informações sobre a Inclusão do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="eb5b9-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="eb5b9-110">Ligar ao LiveRamp</span><span class="sxs-lookup"><span data-stu-id="eb5b9-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="eb5b9-111">Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="eb5b9-112">No mosaico **LiveRamp**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="eb5b9-113">Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="eb5b9-114">Forneça um **Nome de utilizador** e **Palavra-passe** para a sua conta LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="eb5b9-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="eb5b9-115">Estas credenciais podem ser diferentes das suas credenciais de Integração do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="eb5b9-116">Selecione **Verificar** para testar a ligação ao LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="eb5b9-117">Após uma verificação com êxito, forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="eb5b9-118">Selecione **Seguinte** para configurar o conector do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="eb5b9-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="eb5b9-119">Configure the connector</span></span>

1. <span data-ttu-id="eb5b9-120">No campo **Escolher o identificador-chave**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o LiveRamp para a resolução de identidades.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="eb5b9-121">Mapeie os atributos correspondentes da entidade de cliente unificada para o identificador-chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="eb5b9-122">Selecione **Adicionar atributo** para mapear atributos adicionais a enviar para o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="eb5b9-123">É provável que o envio de atributos de identificador-chave para o LiveRamp tenha uma taxa de correspondência superior.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="eb5b9-124">Selecione os segmentos que pretende exportar para o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="eb5b9-125">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eb5b9-126">![Conector do LiveRamp com mapeamento de atributos](media/export-liveramp-segments.png "Conector do LiveRamp com mapeamento de atributos")</span><span class="sxs-lookup"><span data-stu-id="eb5b9-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="eb5b9-127">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="eb5b9-127">Export the data</span></span>

<span data-ttu-id="eb5b9-128">A exportação será iniciada em breve se todos os pré-requisitos para exportação tiverem sido concluídos.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="eb5b9-129">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eb5b9-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="eb5b9-130">Quando a exportação tiver sido concluída com êxito, pode iniciar sessão na Inclusão do LiveRamp para ativar e distribuir os seus dados.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eb5b9-131">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="eb5b9-131">Data privacy and compliance</span></span>

<span data-ttu-id="eb5b9-132">Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Liveramp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eb5b9-133">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Liveramp cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="eb5b9-134">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="eb5b9-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="eb5b9-135">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="eb5b9-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
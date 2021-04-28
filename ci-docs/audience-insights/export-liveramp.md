---
title: Conector do LiveRamp
description: Aprenda a configurar a ligação e exportar para o LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760341"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="daf19-103">Exportar segmentos para o LiveRamp&reg; (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="daf19-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="daf19-104">Ative os seus dados no LiveRamp para se ligar a mais de 500 plataformas através de canais digitais, sociais e TVs.</span><span class="sxs-lookup"><span data-stu-id="daf19-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="daf19-105">Trabalhar com os seus dados no LiveRamp para campanhas publicitárias com alvo, supressão e personalizar.</span><span class="sxs-lookup"><span data-stu-id="daf19-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="daf19-106">Pré-requisitos para uma ligação</span><span class="sxs-lookup"><span data-stu-id="daf19-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="daf19-107">Necessita de uma subscrição do LiveRamp para utilizar este conector.</span><span class="sxs-lookup"><span data-stu-id="daf19-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="daf19-108">Para obter uma subscrição, [contacte a LiveRamp](https://liveramp.com/contact/) diretamente.</span><span class="sxs-lookup"><span data-stu-id="daf19-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="daf19-109">[Obtenha mais informações sobre a Inclusão do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="daf19-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="daf19-110">Configurar ligação ao LiveRamp</span><span class="sxs-lookup"><span data-stu-id="daf19-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="daf19-111">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="daf19-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="daf19-112">Selecione **Adicionar ligação** e escolha **LiveRamp** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="daf19-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="daf19-113">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="daf19-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="daf19-114">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="daf19-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="daf19-115">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="daf19-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="daf19-116">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="daf19-116">Choose who can use this connection.</span></span> <span data-ttu-id="daf19-117">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="daf19-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="daf19-118">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="daf19-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="daf19-119">Forneça um **Nome de utilizador** e **Palavra-passe** para a sua conta LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="daf19-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="daf19-120">Estas credenciais podem ser diferentes das suas credenciais de Integração do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="daf19-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="daf19-121">Selecione **Verificar** para testar a ligação ao LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="daf19-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="daf19-122">Após uma verificação com êxito, forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="daf19-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="daf19-123">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="daf19-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="daf19-124">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="daf19-124">Configure an export</span></span>

<span data-ttu-id="daf19-125">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="daf19-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="daf19-126">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="daf19-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="daf19-127">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="daf19-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="daf19-128">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="daf19-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="daf19-129">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="daf19-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="daf19-130">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="daf19-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="daf19-131">No campo **Escolher o identificador-chave**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o LiveRamp para a resolução de identidades.</span><span class="sxs-lookup"><span data-stu-id="daf19-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="daf19-132">![Conector do LiveRamp com mapeamento de atributos](media/export-liveramp-segments.png "Conector do LiveRamp com mapeamento de atributos")</span><span class="sxs-lookup"><span data-stu-id="daf19-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="daf19-133">Mapeie os atributos correspondentes da entidade de cliente unificada para o identificador-chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="daf19-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="daf19-134">Selecione **Adicionar atributo** para mapear mais atributos para enviar para o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="daf19-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="daf19-135">É provável que o envio de atributos de identificador-chave para o LiveRamp tenha uma taxa de correspondência superior.</span><span class="sxs-lookup"><span data-stu-id="daf19-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="daf19-136">Selecione os segmentos que pretende exportar para o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="daf19-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="daf19-137">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="daf19-137">Select **Save**.</span></span>

<span data-ttu-id="daf19-138">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="daf19-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="daf19-139">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="daf19-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="daf19-140">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="daf19-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="daf19-141">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="daf19-141">Data privacy and compliance</span></span>

<span data-ttu-id="daf19-142">Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Liveramp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="daf19-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="daf19-143">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Liveramp cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="daf19-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="daf19-144">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="daf19-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="daf19-145">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="daf19-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

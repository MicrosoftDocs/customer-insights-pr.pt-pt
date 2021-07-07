---
title: Exportar dados do Customer Insights para o Marketing Cloud da Salesforce
description: Aprenda a configurar a ligação e a exportar para o Marketing Cloud da Salesforce.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314657"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="49c05-103">Exporte segmentos e outros dados para o Marketing Cloud da Salesforce (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="49c05-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="49c05-104">Utilize os dados dos seus clientes no Marketing Cloud da Salesforce exportando-os através de uma localização do SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="49c05-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="49c05-105">Pré-requisitos para a ligação</span><span class="sxs-lookup"><span data-stu-id="49c05-105">Prerequisites for connection</span></span>

- <span data-ttu-id="49c05-106">Disponibilidade de um anfitrião SFTP e credenciais de admin correspondentes.</span><span class="sxs-lookup"><span data-stu-id="49c05-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="49c05-107">Como configurar localizações SFTP para o Marketing Cloud da Salesforce</span><span class="sxs-lookup"><span data-stu-id="49c05-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="49c05-108">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="49c05-108">Known limitations</span></span>

- <span data-ttu-id="49c05-109">O runtime de uma exportação depende do desempenho do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="49c05-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="49c05-110">Recomendamos dois núcleos CPU e 1 Gb de memória como configuração mínima do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="49c05-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="49c05-111">As entidades exportadoras com até 100 milhões de perfis de clientes podem demorar 90 minutos quando utilizam a configuração mínima recomendada.</span><span class="sxs-lookup"><span data-stu-id="49c05-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="49c05-112">Configurar a ligação ao Marketing Cloud da Salesforce</span><span class="sxs-lookup"><span data-stu-id="49c05-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="49c05-113">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="49c05-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="49c05-114">Selecione **Adicionar ligação** e escolha **Marketing Cloud da Salesforce** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="49c05-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="49c05-115">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="49c05-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="49c05-116">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="49c05-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="49c05-117">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="49c05-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="49c05-118">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="49c05-118">Choose who can use this connection.</span></span> <span data-ttu-id="49c05-119">Se não tomar nenhuma ação, a predefinição será Administradores.</span><span class="sxs-lookup"><span data-stu-id="49c05-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="49c05-120">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="49c05-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="49c05-121">Forneça um **Nome de utilizador**, **Palavra-passe**, **Nome do anfitrião** e **Pasta de exportação** para a sua conta SFTP.</span><span class="sxs-lookup"><span data-stu-id="49c05-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="49c05-122">Selecione **Verificar** para testar a ligação.</span><span class="sxs-lookup"><span data-stu-id="49c05-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="49c05-123">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="49c05-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="49c05-124">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="49c05-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="49c05-125">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="49c05-125">Configure an export</span></span>

<span data-ttu-id="49c05-126">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="49c05-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="49c05-127">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="49c05-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="49c05-128">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="49c05-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="49c05-129">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="49c05-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="49c05-130">No campo **Ligação para a exportação**, escolha uma ligação a partir da secção SFTP.</span><span class="sxs-lookup"><span data-stu-id="49c05-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="49c05-131">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="49c05-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="49c05-132">Escolha se pretende exportar os seus dados em **Gzip** ou **Deszipados** e o **delimitador de campo** para os ficheiros exportados.</span><span class="sxs-lookup"><span data-stu-id="49c05-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="49c05-133">Selecione as entidades, para segmentos de exemplo, que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="49c05-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49c05-134">Cada entidade selecionada será dividida em até cinco ficheiros de saída quando exportada.</span><span class="sxs-lookup"><span data-stu-id="49c05-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="49c05-135">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="49c05-135">Select **Save**.</span></span>

<span data-ttu-id="49c05-136">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="49c05-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="49c05-137">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="49c05-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="49c05-138">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="49c05-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="49c05-139">Importar dados do Customer Insights da localização SFTP para o Marketing Cloud da Salesforce</span><span class="sxs-lookup"><span data-stu-id="49c05-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="49c05-140">Crie [extensões de dados no Marketing Cloud da Salesforce](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o ficheiro de dados do Customer Insights a partir da localização SFTP.</span><span class="sxs-lookup"><span data-stu-id="49c05-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="49c05-141">[Importe os dados da localização SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) para a extensão de dados do Marketing Cloud da Salesforce.</span><span class="sxs-lookup"><span data-stu-id="49c05-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="49c05-142">Configure a automatização para importar os dados para as extensões de dados.</span><span class="sxs-lookup"><span data-stu-id="49c05-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="49c05-143">Saiba mais sobre [automatizações de largada de ficheiros e automatizações agendadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="49c05-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="49c05-144">Defina uma [automatização de largada de ficheiros](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou uma [automatização agendada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="49c05-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="49c05-145">Eis um exemplo de [uma automatização com SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="49c05-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="49c05-146">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="49c05-146">Data privacy and compliance</span></span>

<span data-ttu-id="49c05-147">Quando ativa Dynamics 365 Customer Insights para transmitir dados através de SFTP, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="49c05-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="49c05-148">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o destino de exportação cumpre quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="49c05-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="49c05-149">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="49c05-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="49c05-150">O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="49c05-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

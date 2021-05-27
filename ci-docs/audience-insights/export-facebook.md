---
title: Exportar dados Customer Insights para o Facebook Ads Manager
description: Aprenda a configurar a ligação e exportar para o Gestor de Anúncios do Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976056"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="e3d7c-103">Lista de segmentos de exportação para o Gestor de Anúncios do Facebook (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="e3d7c-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="e3d7c-104">Exportar segmentos de perfis de cliente unificados para o Gestor de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e3d7c-105">Pré-requisitos para a ligação</span><span class="sxs-lookup"><span data-stu-id="e3d7c-105">Prerequisites for connection</span></span>

- <span data-ttu-id="e3d7c-106">Necessita de ter uma [**Conta de Publicidade do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclua uma [**Conta Empresarial do Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="e3d7c-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="e3d7c-107">Tem de ser um administrador na [**Conta De Anúncio do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="e3d7c-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e3d7c-108">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="e3d7c-108">Known limitations</span></span>

- <span data-ttu-id="e3d7c-109">Até 10 milhões de perfis de clientes por exportação para o Gestor de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="e3d7c-110">A exportação para o Gestor de Anúncios do Facebook está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="e3d7c-111">Crie ou atualize audiências personalizadas apenas no Facebook do tipo *lista de clientes* apenas.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="e3d7c-112">Exportar segmentos com um total de 10 milhões de perfis podem levar até 90 minutos para completar.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="e3d7c-113">Configurar ligação ao Gestor de Anúncios do Facebook</span><span class="sxs-lookup"><span data-stu-id="e3d7c-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="e3d7c-114">Antes de os utilizadores poderem criar uma exportação, um administrador tem de configurar a ligação ao serviço e permitir que os contribuidores utilizem a ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="e3d7c-115">Aceda a **Admin** > **Ligações**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e3d7c-116">Selecione **Adicionar ligação** e escolha **Gestor de Anúncios do Facebook** para configurar a ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="e3d7c-117">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e3d7c-118">O nome e o tipo de ligação descrevem esta ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e3d7c-119">Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e3d7c-120">Escolher quem pode utilizar esta ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-120">Choose who can use this connection.</span></span> <span data-ttu-id="e3d7c-121">Se não tomar nenhuma ação, a predefinição será **Administradores**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="e3d7c-122">Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e3d7c-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e3d7c-123">Autenticar com os Anúncios do Facebook:</span><span class="sxs-lookup"><span data-stu-id="e3d7c-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="e3d7c-124">Selecione **Continuar com o Facebook** para iniciar sessão na sua Conta de Anúncio do Facebook.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="e3d7c-125">Permitir a permissão **ads_management** após autenticação com o Facebook.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="e3d7c-126">Selecione a **Conta de Anúncios do Facebook** com que pretende trabalhar.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="e3d7c-127">Selecione uma **Audiência personalizada existente** na lista pendente ou crie uma **Nova audiência personalizada**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="e3d7c-128">Para mais informações, consulte [**Audiências no Gestor de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="e3d7c-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="e3d7c-129">Com esta exportação, só é possível criar ou atualizar audiências personalizadas no Facebook do tipo *lista de clientes*.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="e3d7c-130">Em alguns casos, vê audiências personalizadas de diferentes tipos na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="e3d7c-131">A seleção de um tipo diferente de *lista de clientes* resultará numa exportação falhada.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="e3d7c-132">Reveja a **Privacidade e conformidade dos dados** e selecione **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="e3d7c-133">Selecione **Guardar** para concluir a ligação.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e3d7c-134">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="e3d7c-134">Configure an export</span></span>

<span data-ttu-id="e3d7c-135">Pode configurar esta exportação se tiver acesso a uma ligação deste tipo.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e3d7c-136">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e3d7c-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e3d7c-137">Aceda a **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e3d7c-138">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="e3d7c-139">Em **Ligação para a exportação**, escolha uma ligação a partir da secção **Gestor de Anúncios do Facebook**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="e3d7c-140">Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e3d7c-141">Em **Escolher o campo de identificador de chave**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o Gestor de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="e3d7c-142">Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e3d7c-143">Mapeie os atributos correspondentes da entidade de cliente unificada para o identificador-chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="e3d7c-144">[DICA] As melhores hipóteses para que uma correspondência ocorra é se selecionar **E-mail** como identificador de chave.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="e3d7c-145">A adição de identificadores adicionais pode melhorar a correspondência.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="e3d7c-146">Selecione **Adicionar atributo** para mapear mais atributos para enviar para o Gestor de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="e3d7c-147">Atributos do Gestor de Anúncios do Facebook estão a mapear para os seguintes nomes amigáveis de utilizador: **NP** = **Nome Próprio**, **AP** = **Apelido**, **PI** = **Primeira Inicial**, **TELEFONE** = **Telefone**, **SEX** = **Sexo**, **DN** = **Data de nascimento**, **EST** = **Estado**, **CD** = **Cidade**, **CP** = **Código postal**, **PAÍS** = **País / Região**</span><span class="sxs-lookup"><span data-stu-id="e3d7c-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="e3d7c-148">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e3d7c-149">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-149">Select **Save**.</span></span>

<span data-ttu-id="e3d7c-150">Guardar uma exportação não executa a exportação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e3d7c-151">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e3d7c-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3d7c-152">Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e3d7c-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e3d7c-153">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="e3d7c-153">Data privacy and compliance</span></span>

<span data-ttu-id="e3d7c-154">Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Gestor de Anúncios do Facebook, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e3d7c-155">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que os Anúncios do Facebook cumprem quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e3d7c-156">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e3d7c-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e3d7c-157">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="e3d7c-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

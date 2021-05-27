---
title: Suplemento de Cartões de Cliente para aplicações Dynamics 365
description: Mostrar dados de informações de audiência em aplicações Dynamics 365 com este suplemento.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059602"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="90bd9-103">Suplemento de Cartões de Cliente (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="90bd9-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="90bd9-104">Obtenha uma visão de 360 graus dos seus clientes diretamente nas aplicações Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="90bd9-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="90bd9-105">Com o Suplemento de Cartões de Cliente instalado numa aplicação suportada do Dynamics 365, pode optar por apresentar linhas cronológicas de dados demográficos, de informações e de atividades.</span><span class="sxs-lookup"><span data-stu-id="90bd9-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="90bd9-106">O suplemento irá obter dados do Customer Insights sem afetar os dados na aplicação ligada do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="90bd9-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="90bd9-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="90bd9-107">Prerequisites</span></span>

- <span data-ttu-id="90bd9-108">O suplemento funciona apenas com aplicações condicionadas por modelo do Dynamics 365, como o Sales ou o Customer Service, versão 9.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="90bd9-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="90bd9-109">Para que os seus dados do Dynamics 365 mapeiem para perfis de clientes de informações de audiência, precisam de ser [ingeridos a partir da aplicação Dynamics 365 usando o conector do Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="90bd9-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="90bd9-110">Todos os utilizadores do Dynamics 365 do Suplemento de Cartões de Cliente têm de ser [adicionados como utilizadores](permissions.md) nas informações de audiência para ver os dados.</span><span class="sxs-lookup"><span data-stu-id="90bd9-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="90bd9-111">As [capacidades de pesquisa e de filtragem configuradas](search-filter-index.md) nas informações de audiência são necessárias para que a pesquisa de dados funcione.</span><span class="sxs-lookup"><span data-stu-id="90bd9-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="90bd9-112">Cada controlo de suplemento baseia-se em dados específicos em informações de audiência:</span><span class="sxs-lookup"><span data-stu-id="90bd9-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="90bd9-113">Controlo das medidas: Requer [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="90bd9-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="90bd9-114">Controlo de inteligência: requer dados gerados utilizando [predições](predictions.md) ou [modelos personalizados](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="90bd9-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="90bd9-115">Controlo demográfico: Campos demográficos (tais como idade ou sexo) estão disponíveis no perfil unificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="90bd9-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="90bd9-116">Controlo do enriquecimento: Requer [enriquecimentos](enrichment-hub.md) ativos aplicados aos perfis do cliente.</span><span class="sxs-lookup"><span data-stu-id="90bd9-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="90bd9-117">Controlo da linha cronológica: Requer [atividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="90bd9-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="90bd9-118">Instalar o Suplemento Ficha de Cliente</span><span class="sxs-lookup"><span data-stu-id="90bd9-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="90bd9-119">O Suplemento do Cartão de Cliente é uma solução para aplicações Customer Engagement no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="90bd9-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="90bd9-120">Para instalar a solução, aceda a AppSource e procure **Ficha de Cliente do Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="90bd9-121">Selecione o [Suplemento de Cartões de Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="90bd9-122">Poderá ter de iniciar sessão com as suas credenciais de administrador para a aplicação Dynamics 365 para instalar a solução.</span><span class="sxs-lookup"><span data-stu-id="90bd9-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="90bd9-123">Poderá demorar algum tempo a instalar a solução no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="90bd9-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="90bd9-124">Configurar o Suplemento de Cartões de Cliente</span><span class="sxs-lookup"><span data-stu-id="90bd9-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="90bd9-125">Como administrador, vá para a secção **Definições** no Dynamics 365 e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="90bd9-126">Selecione a ligação **Nome a Apresentar** para a solução **Suplemento de Cartões de Cliente do Dynamics 365 Customer Insights (Pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90bd9-127">![Selecionar nome a apresentar](media/select-display-name.png "Selecionar nome a apresentar")</span><span class="sxs-lookup"><span data-stu-id="90bd9-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="90bd9-128">Selecione **Iniciar sessão** e introduza as credenciais da conta de administrador que utiliza para configurar o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="90bd9-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="90bd9-129">Verifique se o bloqueador de janelas de pop-up do browser não bloquear a janela de autenticação quando seleciona o botão **Iniciar sessão**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="90bd9-130">Selecione o ambiente do Customer Insights a partir do qual pretende obter dados.</span><span class="sxs-lookup"><span data-stu-id="90bd9-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="90bd9-131">Defina o mapeamento de campo para registos na aplicação Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="90bd9-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="90bd9-132">Dependendo dos seus dados no Customer Insights, pode optar por mapear as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="90bd9-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="90bd9-133">Para mapear com um contacto, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade de contacto.</span><span class="sxs-lookup"><span data-stu-id="90bd9-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="90bd9-134">Para mapear com uma conta, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade da conta.</span><span class="sxs-lookup"><span data-stu-id="90bd9-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90bd9-135">![Campo ID do Contacto](media/contact-id-field.png "Campo ID do Contacto")</span><span class="sxs-lookup"><span data-stu-id="90bd9-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="90bd9-136">Selecione **Guardar configuração** para guardar as definições.</span><span class="sxs-lookup"><span data-stu-id="90bd9-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="90bd9-137">Em seguida, tem de atribuir direitos de acesso no Dynamics 365 para os utilizadores poderem personalizar e ver o cartão de cliente.</span><span class="sxs-lookup"><span data-stu-id="90bd9-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="90bd9-138">No Dynamics 365, aceda a **Definições** > **Segurança** > **Utilizadores**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="90bd9-139">Selecione os utilizadores para os direitos de utilizador e selecione **Gerir funções**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="90bd9-140">Atribua a função **Personalizador do Cartão Customer Insights** aos utilizadores que personalizem o conteúdo apresentado no cartão para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="90bd9-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="90bd9-141">Adicionar cartão de cliente aos formulários</span><span class="sxs-lookup"><span data-stu-id="90bd9-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="90bd9-142">Para adicionar os controlos da Ficha de Cliente ao seu formulário Contacto, aceda a **Definições** > **Personalizações** no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="90bd9-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="90bd9-143">Selecione **Personalizar o Sistema**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="90bd9-144">Navegue para a entidade **Contacto**, expanda-a e selecione **Formulários**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="90bd9-145">Selecione o formulário de contacto ao qual pretende adicionar controlos da Ficha de Cliente.</span><span class="sxs-lookup"><span data-stu-id="90bd9-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="90bd9-146">![Selecionar formulário Contacto](media/contact-active-forms.png "Selecionar formulário Contacto")</span><span class="sxs-lookup"><span data-stu-id="90bd9-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="90bd9-147">Para adicionar um controlo, no editor de formulários, arraste qualquer campo do **Explorador de Campos** para onde pretende que o controlo seja apresentado.</span><span class="sxs-lookup"><span data-stu-id="90bd9-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="90bd9-148">Selecione o campo no formulário que acabou de adicionar e selecione **Alterar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="90bd9-149">Aceda ao separador **Controlos** e selecione **Adicionar Controlo**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="90bd9-150">Escolha um dos controlos personalizados disponíveis e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="90bd9-151">Na caixa de diálogo **Propriedades do Campo**, desmarque a caixa de verificação **Apresentar etiqueta no formulário**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="90bd9-152">Selecione a opção **Web** para o controlo.</span><span class="sxs-lookup"><span data-stu-id="90bd9-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="90bd9-153">Para o controlo de Enriquecimento, selecione o tipo de enriquecimento que pretende visualizar configurando o campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="90bd9-154">Adicione um controlo de melhoramento separado para cada tipo de melhoramento.</span><span class="sxs-lookup"><span data-stu-id="90bd9-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="90bd9-155">Selecione **Guardar** e **Publicar** para publicar o formulário de contacto atualizado.</span><span class="sxs-lookup"><span data-stu-id="90bd9-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="90bd9-156">Vá para o formulário de contacto publicado.</span><span class="sxs-lookup"><span data-stu-id="90bd9-156">Go to the published contact form.</span></span> <span data-ttu-id="90bd9-157">Verá o controlo adicionado recentemente.</span><span class="sxs-lookup"><span data-stu-id="90bd9-157">You'll see the newly added control.</span></span> <span data-ttu-id="90bd9-158">Poderá ter de iniciar sessão quando o utiliza pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="90bd9-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="90bd9-159">Para personalizar o que pretende mostrar no controlo personalizado, selecione o botão de editação no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="90bd9-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="90bd9-160">Atualizar Versão do Suplemento Ficha de Cliente</span><span class="sxs-lookup"><span data-stu-id="90bd9-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="90bd9-161">O Suplemento da Ficha de Cliente não atualiza a versão automaticamente.</span><span class="sxs-lookup"><span data-stu-id="90bd9-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="90bd9-162">Para atualizar para a versão mais recente, siga este procedimento na aplicação Dynamics 365 que tem o Suplemento instalado.</span><span class="sxs-lookup"><span data-stu-id="90bd9-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="90bd9-163">Na aplicação Dynamics 365, vá a **Definições** > **Personalização** e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="90bd9-164">Na tabela de suplementos, procure **CustomerInsightsCustomerCard** e selecione a linha.</span><span class="sxs-lookup"><span data-stu-id="90bd9-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="90bd9-165">Selecione a **Aplicar Atualização da Versão da Solução** na barra de ação.</span><span class="sxs-lookup"><span data-stu-id="90bd9-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atualize a versão da solução na área Personalização das aplicações Dynamics 365":::

1. <span data-ttu-id="90bd9-167">Depois de iniciar o processo de atualização de versão, verá um indicador de carregamento até que a atualização esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="90bd9-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="90bd9-168">Se não houver uma versão mais recente, a atualização mostrará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="90bd9-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

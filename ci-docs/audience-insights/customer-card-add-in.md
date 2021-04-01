---
title: Instale e configure o Suplemento Ficha de Cliente
description: Instalar e configurar o suplemento Ficha de Cliente para o Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597341"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="38128-103">Suplemento de Cartões de Cliente (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="38128-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="38128-104">Obtenha uma visão de 360 graus dos seus clientes diretamente nas aplicações Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38128-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="38128-105">Veja dados demográficos, informações e linhas cronológicas de atividades com o Suplemento de Cartões de Cliente.</span><span class="sxs-lookup"><span data-stu-id="38128-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38128-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="38128-106">Prerequisites</span></span>

- <span data-ttu-id="38128-107">Aplicação Dynamics 365 (como Hub de Vendas ou Hub do Customer Service), versão 9.0 e posterior com a Interface Unificada ativada.</span><span class="sxs-lookup"><span data-stu-id="38128-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="38128-108">Perfis de clientes [ingerido a partir da aplicação Dynamics 365 utilizando Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="38128-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="38128-109">Os utilizadores do Suplemento Cartão de Cliente têm de ser [adicionados como utilizadores](permissions.md) em insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="38128-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="38128-110">[Capacidades de pesquisa e filtragem configuradas](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="38128-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="38128-111">Controlo demográfico: Campos demográficos (tais como idade ou sexo) estão disponíveis no perfil unificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="38128-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="38128-112">Controlo do enriquecimento: Requer [enriquecimentos](enrichment-hub.md) ativos aplicados aos perfis do cliente.</span><span class="sxs-lookup"><span data-stu-id="38128-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="38128-113">Controlo da inteligência: Necessita de dados gerados através do Azure Machine Learning ([Predições](predictions.md) ou [Modelos Personalizados](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="38128-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="38128-114">Controlo das medidas: Requer [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="38128-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="38128-115">Controlo da linha cronológica: Requer [atividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="38128-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="38128-116">Instalar o Suplemento Ficha de Cliente</span><span class="sxs-lookup"><span data-stu-id="38128-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="38128-117">O Suplemento do Cartão de Cliente é uma solução para aplicações Customer Engagement no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38128-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="38128-118">Para instalar a solução, aceda a AppSource e procure **Ficha de Cliente do Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="38128-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="38128-119">Selecione o [Suplemento de Cartões de Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.</span><span class="sxs-lookup"><span data-stu-id="38128-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="38128-120">Poderá ter de iniciar sessão com as suas credenciais de administrador para a aplicação Dynamics 365 para instalar a solução.</span><span class="sxs-lookup"><span data-stu-id="38128-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="38128-121">Poderá demorar algum tempo a instalar a solução no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="38128-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="38128-122">Configurar o Suplemento de Cartões de Cliente</span><span class="sxs-lookup"><span data-stu-id="38128-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="38128-123">Como administrador, vá para a secção **Definições** no Dynamics 365 e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="38128-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="38128-124">Selecione a ligação **Nome a Apresentar** para a solução **Suplemento de Cartões de Cliente do Dynamics 365 Customer Insights (Pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="38128-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38128-125">![Selecionar nome a apresentar](media/select-display-name.png "Selecionar nome a apresentar")</span><span class="sxs-lookup"><span data-stu-id="38128-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="38128-126">Selecione **Iniciar sessão** e introduza as credenciais da conta de administrador que utiliza para configurar o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="38128-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="38128-127">Verifique se o bloqueador de janelas de pop-up do browser não bloquear a janela de autenticação quando seleciona o botão **Iniciar sessão**.</span><span class="sxs-lookup"><span data-stu-id="38128-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="38128-128">Selecione o ambiente a partir da qual pretende obter dados.</span><span class="sxs-lookup"><span data-stu-id="38128-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="38128-129">Definir qual o mapeamento de campo a registar na aplicação Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38128-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="38128-130">Para mapear com um contacto, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade de contacto.</span><span class="sxs-lookup"><span data-stu-id="38128-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="38128-131">Para mapear com uma conta, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade da conta.</span><span class="sxs-lookup"><span data-stu-id="38128-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38128-132">![Campo ID do Contacto](media/contact-id-field.png "Campo ID do Contacto")</span><span class="sxs-lookup"><span data-stu-id="38128-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="38128-133">Selecione **Guardar configuração** para guardar as definições.</span><span class="sxs-lookup"><span data-stu-id="38128-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="38128-134">Em seguida, tem de atribuir direitos de acesso no Dynamics 365 para os utilizadores poderem personalizar e ver o cartão de cliente.</span><span class="sxs-lookup"><span data-stu-id="38128-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="38128-135">No Dynamics 365, aceda a **Definições** > **Segurança** > **Utilizadores**.</span><span class="sxs-lookup"><span data-stu-id="38128-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="38128-136">Selecione os utilizadores para os direitos de utilizador e selecione **Gerir funções**.</span><span class="sxs-lookup"><span data-stu-id="38128-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="38128-137">Atribua a função **Personalizador do Cartão Customer Insights** aos utilizadores que personalizem o conteúdo apresentado no cartão para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="38128-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="38128-138">Adicionar cartão de cliente aos formulários</span><span class="sxs-lookup"><span data-stu-id="38128-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="38128-139">Para adicionar os controlos da Ficha de Cliente ao seu formulário Contacto, aceda a **Definições** > **Personalizações** no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38128-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="38128-140">Selecione **Personalizar o Sistema**.</span><span class="sxs-lookup"><span data-stu-id="38128-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="38128-141">Navegue para a entidade **Contacto**, expanda-a e selecione **Formulários**.</span><span class="sxs-lookup"><span data-stu-id="38128-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="38128-142">Selecione o formulário de contacto ao qual pretende adicionar controlos da Ficha de Cliente.</span><span class="sxs-lookup"><span data-stu-id="38128-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="38128-143">![Selecionar formulário Contacto](media/contact-active-forms.png "Selecionar formulário Contacto")</span><span class="sxs-lookup"><span data-stu-id="38128-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="38128-144">Para adicionar um controlo, no editor de formulários, arraste qualquer campo do **Explorador de Campos** para onde pretende que o controlo seja apresentado.</span><span class="sxs-lookup"><span data-stu-id="38128-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="38128-145">Selecione o campo no formulário que acabou de adicionar e selecione **Alterar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38128-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="38128-146">Aceda ao separador **Controlos** e selecione **Adicionar Controlo**.</span><span class="sxs-lookup"><span data-stu-id="38128-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="38128-147">Escolha um dos controlos personalizados disponíveis e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="38128-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="38128-148">Na caixa de diálogo **Propriedades do Campo**, desmarque a caixa de verificação **Apresentar etiqueta no formulário**.</span><span class="sxs-lookup"><span data-stu-id="38128-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="38128-149">Selecione a opção **Web** para o controlo.</span><span class="sxs-lookup"><span data-stu-id="38128-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="38128-150">Para o controlo de Enriquecimento, selecione o tipo de enriquecimento que pretende visualizar configurando o campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="38128-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="38128-151">Adicione um controlo de melhoramento separado para cada tipo de melhoramento.</span><span class="sxs-lookup"><span data-stu-id="38128-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="38128-152">Selecione **Guardar** e **Publicar** para publicar o formulário de contacto atualizado.</span><span class="sxs-lookup"><span data-stu-id="38128-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="38128-153">Vá para o formulário de contacto publicado.</span><span class="sxs-lookup"><span data-stu-id="38128-153">Go to the published contact form.</span></span> <span data-ttu-id="38128-154">Verá o controlo adicionado recentemente.</span><span class="sxs-lookup"><span data-stu-id="38128-154">You'll see the newly added control.</span></span> <span data-ttu-id="38128-155">Poderá ter de iniciar sessão quando o utiliza pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="38128-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="38128-156">Para personalizar o que pretende mostrar no controlo personalizado, selecione o botão de editação no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="38128-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="38128-157">Atualizar Versão do Suplemento Ficha de Cliente</span><span class="sxs-lookup"><span data-stu-id="38128-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="38128-158">O Suplemento da Ficha de Cliente não atualiza a versão automaticamente.</span><span class="sxs-lookup"><span data-stu-id="38128-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="38128-159">Para atualizar para a versão mais recente, siga este procedimento na aplicação Dynamics 365 que tem o Suplemento instalado.</span><span class="sxs-lookup"><span data-stu-id="38128-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="38128-160">Na aplicação Dynamics 365, vá a **Definições** > **Personalização** e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="38128-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="38128-161">Na tabela de suplementos, procure **CustomerInsightsCustomerCard** e selecione a linha.</span><span class="sxs-lookup"><span data-stu-id="38128-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="38128-162">Selecione a **Aplicar Atualização da Versão da Solução** na barra de ação.</span><span class="sxs-lookup"><span data-stu-id="38128-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atualize a versão da solução na área Personalização das aplicações Dynamics 365":::

1. <span data-ttu-id="38128-164">Depois de iniciar o processo de atualização de versão, verá um indicador de carregamento até que a atualização esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="38128-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="38128-165">Se não houver uma versão mais recente, a atualização mostrará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="38128-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
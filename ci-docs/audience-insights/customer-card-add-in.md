---
title: Instale e configure o Suplemento Ficha de Cliente
description: Instalar e configurar o suplemento Ficha de Cliente para o Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644057"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="edbb8-103">Suplemento de Cartões de Cliente (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="edbb8-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="edbb8-104">Obtenha uma visão de 360 graus dos seus clientes diretamente nas aplicações Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="edbb8-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="edbb8-105">Veja dados demográficos, informações e linhas cronológicas de atividades com o Suplemento de Cartões de Cliente.</span><span class="sxs-lookup"><span data-stu-id="edbb8-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="edbb8-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="edbb8-106">Prerequisites</span></span>

- <span data-ttu-id="edbb8-107">Aplicação Dynamics 365 (como Hub de Vendas ou Hub do Customer Service), versão 9.0 e posterior com a Interface Unificada ativada.</span><span class="sxs-lookup"><span data-stu-id="edbb8-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="edbb8-108">Perfis de clientes [ingerido a partir da aplicação Dynamics 365 utilizando Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="edbb8-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="edbb8-109">Os utilizadores do Suplemento Cartão de Cliente têm de ser [adicionados como utilizadores](permissions.md) em insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="edbb8-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="edbb8-110">[Capacidades de pesquisa e filtragem configuradas](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="edbb8-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="edbb8-111">Controlo demográfico: Campos demográficos, tais como idade ou sexo, estão disponíveis no perfil unificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="edbb8-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="edbb8-112">Controlo do enriquecimento: Requer [enriquecimentos](enrichment-hub.md) ativos aplicados aos perfis do cliente.</span><span class="sxs-lookup"><span data-stu-id="edbb8-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="edbb8-113">Controlo da inteligência: Necessita de dados gerados através do Azure Machine Learning ([Predições](predictions.md) ou [Modelos Personalizados](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="edbb8-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="edbb8-114">Controlo das medidas: Requer [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="edbb8-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="edbb8-115">Controlo da linha cronológica: Requer [atividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="edbb8-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="edbb8-116">Instalar o Suplemento Ficha de Cliente</span><span class="sxs-lookup"><span data-stu-id="edbb8-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="edbb8-117">O Suplemento do Cartão de Cliente é uma solução para aplicações Customer Engagement no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="edbb8-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="edbb8-118">Para instalar a solução, aceda a AppSource e procure **Ficha de Cliente do Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="edbb8-119">Selecione o [Suplemento de Cartões de Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="edbb8-120">Poderá ter de iniciar sessão com as suas credenciais de administrador para a aplicação Dynamics 365 para instalar a solução.</span><span class="sxs-lookup"><span data-stu-id="edbb8-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="edbb8-121">Poderá demorar algum tempo a instalar a solução no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="edbb8-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="edbb8-122">Configurar o Suplemento de Cartões de Cliente</span><span class="sxs-lookup"><span data-stu-id="edbb8-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="edbb8-123">Como administrador, vá para a secção **Definições** no Dynamics 365 e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="edbb8-124">Selecione a ligação **Nome a Apresentar** para a solução **Suplemento de Cartões de Cliente do Dynamics 365 Customer Insights (Pré-visualização)**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="edbb8-125">![Selecionar nome a apresentar](media/select-display-name.png "Selecionar nome a apresentar")</span><span class="sxs-lookup"><span data-stu-id="edbb8-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="edbb8-126">Selecione **Iniciar sessão** e introduza as credenciais da conta de administrador que utiliza para configurar o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="edbb8-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="edbb8-127">Verifique se o bloqueador de janelas de pop-up do browser não bloquear a janela de autenticação quando seleciona o botão **Iniciar sessão**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="edbb8-128">Selecione o ambiente a partir da qual pretende obter dados.</span><span class="sxs-lookup"><span data-stu-id="edbb8-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="edbb8-129">Definir qual o mapeamento de campo a registar na aplicação Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="edbb8-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="edbb8-130">Para mapear com um contacto, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade de contacto.</span><span class="sxs-lookup"><span data-stu-id="edbb8-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="edbb8-131">Para mapear com uma conta, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade da conta.</span><span class="sxs-lookup"><span data-stu-id="edbb8-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="edbb8-132">![Campo ID do Contacto](media/contact-id-field.png "Campo ID do Contacto")</span><span class="sxs-lookup"><span data-stu-id="edbb8-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="edbb8-133">Selecione **Guardar configuração** para guardar as definições.</span><span class="sxs-lookup"><span data-stu-id="edbb8-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="edbb8-134">Em seguida, tem de atribuir direitos de acesso no Dynamics 365 para os utilizadores poderem personalizar e ver o cartão de cliente.</span><span class="sxs-lookup"><span data-stu-id="edbb8-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="edbb8-135">No Dynamics 365, aceda a **Definições** > **Segurança** > **Utilizadores**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="edbb8-136">Selecione os utilizadores para os direitos de utilizador e selecione **Gerir funções**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="edbb8-137">Atribua a função **Personalizador do Cartão Customer Insights** aos utilizadores que personalizem o conteúdo apresentado no cartão para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="edbb8-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="edbb8-138">Adicionar cartão de cliente aos formulários</span><span class="sxs-lookup"><span data-stu-id="edbb8-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="edbb8-139">Para adicionar os controlos da Ficha de Cliente ao seu formulário Contacto, aceda a **Definições** > **Personalizações** no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="edbb8-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="edbb8-140">Selecione **Personalizar o Sistema**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="edbb8-141">Navegue para a entidade **Contacto**, expanda-a e selecione **Formulários**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="edbb8-142">Selecione o formulário de contacto ao qual pretende adicionar controlos da Ficha de Cliente.</span><span class="sxs-lookup"><span data-stu-id="edbb8-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="edbb8-143">![Selecionar formulário Contacto](media/contact-active-forms.png "Selecionar formulário Contacto")</span><span class="sxs-lookup"><span data-stu-id="edbb8-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="edbb8-144">Para adicionar um controlo, no editor de formulários, arraste qualquer campo do **Explorador de Campos** para onde pretende que o controlo seja apresentado.</span><span class="sxs-lookup"><span data-stu-id="edbb8-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="edbb8-145">Selecione o campo no formulário que acabou de adicionar e selecione **Alterar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="edbb8-146">Aceda ao separador **Controlos** e selecione **Adicionar Controlo**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="edbb8-147">Escolha um dos controlos personalizados disponíveis e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="edbb8-148">Na caixa de diálogo **Propriedades do Campo**, desmarque a caixa de verificação **Apresentar etiqueta no formulário**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="edbb8-149">Selecione a opção **Web** para o controlo.</span><span class="sxs-lookup"><span data-stu-id="edbb8-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="edbb8-150">Para o controlo de Enriquecimento, selecione o tipo de enriquecimento que pretende visualizar configurando o campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="edbb8-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="edbb8-151">É necessário adicionar um controlo de enriquecimento separado para cada tipo de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="edbb8-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="edbb8-152">Selecione **Guardar** e **Publicar** para publicar o formulário de contacto atualizado.</span><span class="sxs-lookup"><span data-stu-id="edbb8-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="edbb8-153">Vá para o formulário de contacto publicado.</span><span class="sxs-lookup"><span data-stu-id="edbb8-153">Go to the published contact form.</span></span> <span data-ttu-id="edbb8-154">Verá o controlo adicionado recentemente.</span><span class="sxs-lookup"><span data-stu-id="edbb8-154">You'll see the newly added control.</span></span> <span data-ttu-id="edbb8-155">Poderá ter de iniciar sessão quando o utiliza pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="edbb8-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="edbb8-156">Para personalizar o que pretende mostrar no controlo personalizado, selecione o botão de editação no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="edbb8-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

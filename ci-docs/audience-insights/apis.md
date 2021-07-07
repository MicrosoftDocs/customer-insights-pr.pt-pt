---
title: Trabalhar com APIs
description: Use APIs e compreenda as limitações.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304756"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="a92fe-103">Trabalhar com APIs no Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a92fe-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="a92fe-104">O Dynamics 365 Customer Insights fornece APIs para criar as suas próprias aplicações com base nos seus dados no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a92fe-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a92fe-105">Os detalhes destas APIs estão listados na [referência de APIs do Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="a92fe-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="a92fe-106">Incluem informações adicionais sobre operações, parâmetros e respostas.</span><span class="sxs-lookup"><span data-stu-id="a92fe-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="a92fe-107">Este artigo descreve como aceder às APIs do Customer Insights, criar um Registo de Aplicações Azure AD e começar a trabalhar com as bibliotecas de clientes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a92fe-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="a92fe-108">Começar a experimentar as APIs do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a92fe-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="a92fe-109">[Inicie sessão](https://home.ci.ai.dynamics.com) no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a92fe-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="a92fe-110">Se ainda não tiver uma subscrição, [inscreva-se para uma versão experimental do Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="a92fe-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="a92fe-111">Para ativar APIs no seu ambiente de Customer Insights, aceda a **Admin** > **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="a92fe-112">Vai precisar de permissões de administração para o fazer.</span><span class="sxs-lookup"><span data-stu-id="a92fe-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="a92fe-113">Vá ao separador **APIs** e selecione o botão **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="a92fe-114">Ativar as APIs cria uma chave de subscrição primária e secundária para a sua instância que é usada nos pedidos da API.</span><span class="sxs-lookup"><span data-stu-id="a92fe-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="a92fe-115">Pode regenerar as chaves selecionando **Regenerar primária** ou **Regenerar secundária** em **Admin** > **Permissões** > **APIs**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Ativar APIs do Customer Insights":::

1. <span data-ttu-id="a92fe-117">Selecione **Explore as nossas APIs** para [experimentar as APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="a92fe-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="a92fe-118">Escolha uma operação API e selecione **Experimentar**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="a92fe-119">No painel lateral, defina o valor no menu pendente **Autorização** para **implícita**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="a92fe-120">O cabeçalho `Authorization` é adicionado com um token de portador.</span><span class="sxs-lookup"><span data-stu-id="a92fe-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="a92fe-121">A sua chave de subscrição será automaticamente preenchida.</span><span class="sxs-lookup"><span data-stu-id="a92fe-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="a92fe-122">Opcionalmente, adicione todos os parâmetros de consulta necessários.</span><span class="sxs-lookup"><span data-stu-id="a92fe-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="a92fe-123">Percorra a parte inferior do painel lateral e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="a92fe-124">A resposta HTTP em breve aparecerá abaixo.</span><span class="sxs-lookup"><span data-stu-id="a92fe-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Como testar as APIs.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="a92fe-126">Crie o registo de uma nova aplicação no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="a92fe-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="a92fe-127">Estes passos ajudam-no a começar a trabalhar com APIs do Customer Insights numa aplicação Azure utilizando permissões delegadas.</span><span class="sxs-lookup"><span data-stu-id="a92fe-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="a92fe-128">Certifique-se de que conclui primeiro a [secção Começar](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="a92fe-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="a92fe-129">Inicie sessão no [portal Azure](https://portal.azure.com) com a conta que pode aceder aos dados do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a92fe-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="a92fe-130">À esquerda, selecione **registos de Aplicações**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="a92fe-131">Selecione **Novo registo**, forneça um nome de aplicação e escolha o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="a92fe-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="a92fe-132">Opcionalmente, adicione um URL de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="a92fe-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="a92fe-133">http://localhost é suficiente para desenvolver uma aplicação no seu computador local.</span><span class="sxs-lookup"><span data-stu-id="a92fe-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="a92fe-134">No seu novo registo de Aplicação, aceda às **permissões da API**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Como definir permissões de API no registo da Aplicação.":::

1. <span data-ttu-id="a92fe-136">Selecione **Adicione uma permissão** e selecione **Customer Insights** no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="a92fe-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="a92fe-137">Para **Tipo de permissão**, selecione **Permissões delegadas** e, em seguida, selecione a permissão **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="a92fe-138">Selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-138">Select **Add permissions**.</span></span> <span data-ttu-id="a92fe-139">Se precisar de aceder à API sem que um utilizador faça login, reveja a secção de [permissões de aplicação Server-to-Server](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="a92fe-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="a92fe-140">Selecione **Conceder o consentimento do administrador para...** completar o registo da aplicação.</span><span class="sxs-lookup"><span data-stu-id="a92fe-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="a92fe-141">Pode utilizar o ID de Aplicação/Cliente para este registo de aplicações com a Biblioteca de Autenticação da Microsoft (MSAL) para obter um token de portador para enviar com o seu pedido para a API.</span><span class="sxs-lookup"><span data-stu-id="a92fe-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Como conceder consentimento de administrador.":::

<span data-ttu-id="a92fe-143">Para obter mais informações sobre o MSAL, consulte a [visão geral da Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="a92fe-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="a92fe-144">Para obter mais informações sobre o registo de aplicações no Azure, consulte [Registar uma aplicação](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="a92fe-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="a92fe-145">Para obter informações sobre a utilização de APIs nas bibliotecas dos nossos clientes, consulte [Bibliotecas de clientes do Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="a92fe-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="a92fe-146">Permissões de aplicação server-to-server</span><span class="sxs-lookup"><span data-stu-id="a92fe-146">Server-to-server application permissions</span></span>

<span data-ttu-id="a92fe-147">A [secção de registo de aplicações](#create-a-new-app-registration-in-the-azure-portal) descreve como registar uma aplicação que requer que um utilizador faça login para autenticação.</span><span class="sxs-lookup"><span data-stu-id="a92fe-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="a92fe-148">Saiba como criar um registo de aplicações que não precisa de interação do utilizador e que pode ser executado num servidor.</span><span class="sxs-lookup"><span data-stu-id="a92fe-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="a92fe-149">No registo da sua aplicação no portal Azure, aceda às **permissões da API**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="a92fe-150">Selecione **Adicionar uma permissão**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="a92fe-151">Selecione o separador **APIs que a minha organização utiliza** e escolha **IA do Dynamics 365 para o Customer Insights** da lista.</span><span class="sxs-lookup"><span data-stu-id="a92fe-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="a92fe-152">Para **Tipo de permissão**, selecione **Permissões da aplicação** e, em seguida, selecione a permissão **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="a92fe-153">Selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="a92fe-154">Aceda novamente às **permissões da API** para registo da sua aplicação.</span><span class="sxs-lookup"><span data-stu-id="a92fe-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="a92fe-155">Selecione **Conceder o consentimento do administrador para...** completar o registo da aplicação.</span><span class="sxs-lookup"><span data-stu-id="a92fe-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Como conceder consentimento de administrador.":::

1. <span data-ttu-id="a92fe-157">Para concluir, temos de adicionar o nome do registo da aplicação como utilizador no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a92fe-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="a92fe-158">Abrir Customer Insights, ir a **Admin** > **Permissões** e selecionar **Adicionar utilizador**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="a92fe-159">Pesquisar o nome do registo da sua aplicação, selecione-o nos resultados da pesquisa e selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="a92fe-160">Bibliotecas de clientes Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a92fe-160">Customer Insights client libraries</span></span>

<span data-ttu-id="a92fe-161">Esta secção ajuda-o a começar a utilizar as bibliotecas de clientes disponíveis para as APIs de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a92fe-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="a92fe-162">Todos os códigos de origem da biblioteca e aplicações de exemplo podem ser encontrados na [página GitHub do Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="a92fe-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="a92fe-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="a92fe-163">C# NuGet</span></span>

<span data-ttu-id="a92fe-164">Saiba como começar a usar as bibliotecas de clientes C# a partir de NuGet.org. Para obter mais informações sobre o pacote NuGet, consulte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="a92fe-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="a92fe-165">Atualmente, este pacote destina-se aos quadros netstandard2.0 e netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="a92fe-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="a92fe-166">Adicione a biblioteca C# ao projeto C#</span><span class="sxs-lookup"><span data-stu-id="a92fe-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="a92fe-167">No Visual Studio, abra o **NuGet Gestor do pacote** para o seu projeto.</span><span class="sxs-lookup"><span data-stu-id="a92fe-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="a92fe-168">Pesquisar por **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="a92fe-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="a92fe-169">Selecione **Instalar** para adicionar o pacote ao projeto.</span><span class="sxs-lookup"><span data-stu-id="a92fe-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="a92fe-170">Em alternativa, executar este comando na **NuGet Consola do Gestor de Pacotes**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="a92fe-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Adicionar NuGet pacote ao projeto Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="a92fe-172">Use a biblioteca de cliente C#</span><span class="sxs-lookup"><span data-stu-id="a92fe-172">Use the C# client library</span></span>

1. <span data-ttu-id="a92fe-173">Utilize a [Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter um `AccessToken` utilizando o seu [registo de aplicações Azure](#create-a-new-app-registration-in-the-azure-portal) existente.</span><span class="sxs-lookup"><span data-stu-id="a92fe-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="a92fe-174">Depois de autenticar e adquirir com sucesso um token, construa um novo ou utilize um existente `HttpClient` com o adicional de **"Autorização" DefaultRequestHeaders** para **Portador <access token>** e **Ocp-Apim-Chave de Subscrição** para a [**chave de subscrição** a partir do ambiente de Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="a92fe-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="a92fe-175">Reinicie o cabeçalho de **Autorização** quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="a92fe-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="a92fe-176">Por exemplo, quando o token expirou.</span><span class="sxs-lookup"><span data-stu-id="a92fe-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="a92fe-177">Passe isto `HttpClient` para a construção do cliente do `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="a92fe-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Amostra de httpclient":::

1. <span data-ttu-id="a92fe-179">Faça chamadas com o cliente para os "métodos de extensão" – por exemplo, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="a92fe-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="a92fe-180">Se for preferido o acesso ao subjacente `Microsoft.Rest.HttpOperationResponse`, utilize os "métodos de mensagem http" – por exemplo, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="a92fe-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="a92fe-181">A resposta será provavelmente do tipo `object` porque o método pode devolver vários tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="a92fe-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="a92fe-182">Para verificar o tipo de devolução, pode converter os objetos com segurança nos tipos de resposta especificados na [página de detalhes da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para essa operação.</span><span class="sxs-lookup"><span data-stu-id="a92fe-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="a92fe-183">Se forem necessárias mais informações sobre o pedido, utilize os **métodos de mensagem http** para aceder ao objeto de resposta bruta.</span><span class="sxs-lookup"><span data-stu-id="a92fe-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="a92fe-184">Pacote NodeJS</span><span class="sxs-lookup"><span data-stu-id="a92fe-184">NodeJS package</span></span>

<span data-ttu-id="a92fe-185">Utilize as bibliotecas de cliente NodeJS disponíveis através do NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="a92fe-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="a92fe-186">Pacote Python</span><span class="sxs-lookup"><span data-stu-id="a92fe-186">Python package</span></span>

<span data-ttu-id="a92fe-187">Utilize as bibliotecas de cliente Python disponíveis através do PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="a92fe-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

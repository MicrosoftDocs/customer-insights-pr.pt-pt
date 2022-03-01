---
title: Trabalhar com APIs
description: Use APIs e compreenda as limitações.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689144"
---
# <a name="work-with-customer-insights-apis"></a>Trabalhar com APIs no Customer Insights

O Dynamics 365 Customer Insights fornece APIs para construir as suas próprias aplicações baseadas nos seus dados no Customer Insights.

> [!IMPORTANT]
> Os detalhes destas APIs estão listados na [referência APIs do Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Incluem informações adicionais sobre operações, parâmetros e respostas.

Este artigo guia-o para aceder às APIs do Customer Insights, criar um Registo na Aplicação Azure AD e ajudá-lo a começar com as bibliotecas de clientes disponíveis.

## <a name="get-started-trying-the-customer-insights-apis"></a>Começar a experimentar as APIs do Customer Insights

1. [Inicie sessão](https://home.ci.ai.dynamics.com) no Customer Insights. Se ainda não tiver uma subscrição, [inscreva-se para uma versão experimental do Customer Insights](https://aka.ms/tryci).

1. Para ativar APIs no seu ambiente de Customer Insights, aceda a **Admin** > **Permissões**. Vai precisar de permissões de administração para o fazer.

1. Vá ao separador **APIs** e selecione o botão **Ativar**.    
   Ativar as APIs cria uma chave de subscrição primária e secundária para a sua instância que é usada nos pedidos da API. Pode regenerar as chaves selecionando **Regenerar primária** ou **Regenerar secundária** em **Admin** > **Permissões** > **APIs**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Ativar APIs do Customer Insights":::

1. Selecione **Explore as nossas APIs** para experimentar as APIs.

1. Escolha uma operação API e selecione **Experimentar**.

1. No painel lateral, definir o valor no menu pendente **Autorização** para **implícito**. O cabeçalho `Authorization` fica com um token de portador adicionado. A sua chave de subscrição será automaticamente preenchida.
  
1. Opcionalmente, adicione todos os parâmetros de consulta necessários.

1. Percorra a parte inferior do painel lateral e selecione **Enviar**.

A resposta HTTP em breve aparecerá abaixo.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Crie o registo de uma nova aplicação no portal do Azure

Estes passos ajudam-no a começar a utilizar as APIs do Customer Insights numa aplicação Azure utilizando permissões delegadas. Certifique-se de ter concluído primeiro a [secção Começar](#get-started-trying-the-customer-insights-apis).

1. Inicie sessão no [portal Azure](https://portal.azure.com) com a conta que pode aceder aos dados do Customer Insights.

1. À esquerda, selecione **registos de Aplicações**.

1. Selecione **Novo registo**, forneça um nome de aplicação e escolha o tipo de conta.
   Opcionalmente, adicione um URL de redirecionamento. http://localhost é suficiente para desenvolver uma aplicação no seu computador local.

1. No seu novo registo de Aplicação, aceda às **permissões da API**.

1. Selecione **Adicione uma permissão** e selecione **Customer Insights** no painel lateral.

1. Para o **tipo de Permissão**, selecione **permissões delegadas** e selecione a permissão **user_impersonation**.

1. Selecione **Adicionar permissões**. Se precisar de aceder à API sem que um utilizador faça login, reveja a secção de [permissões de aplicação Server-to-Server](#server-to-server-application-permissions).

1. Selecione **Conceder o consentimento do administrador para...** completar o registo da aplicação.

Pode utilizar o ID de Aplicação/Cliente para este registo de aplicações com a Biblioteca de Autenticação da Microsoft (MSAL) para obter um token de portador para enviar com o seu pedido para a API.

Para obter mais informações sobre o MSAL, consulte a [visão geral da Biblioteca de Autenticação da Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Para mais informações sobre o registo de aplicações no Azure, consulte a [nova experiência de registo de aplicações do portal Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Para obter informações sobre a utilização das APIs das bibliotecas do nosso cliente, consulte as [bibliotecas de clientes do Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permissões de aplicação server-to-server

A [secção de registo de aplicações](#create-a-new-app-registration-in-the-azure-portal) descreve como registar uma aplicação que requer que um utilizador faça login para autenticação. Saiba como criar um registo de aplicações que não precisa de interação do utilizador e que pode ser executado num servidor.

1. No registo da sua aplicação no portal Azure, aceda às **permissões da API**.

1. Selecione **Adicione uma permissão** e selecione **Customer Insights** no painel lateral.

1. Para o **tipo de Permissão**, selecione **permissões da aplicação** e selecione a permissão **CustomerInsights.Api.All**.

1. Selecione **Adicionar permissões**.

1. Para dar o consentimento do administrador a esta permissão de Aplicação, tem de adicionar um Principal de Serviço.

   1. Instale o módulo PowerShell (AD) do Azure Active Directory: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Ligar à sua conta AD: `Connect-AzureAD -TenantId <your tenant id>`. Pode encontrar a sua identificação de inquilino na **visão geral** > **Azure Active Directory**.
   1. Executar o seguinte comando para adicionar um Principal de Serviço do Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` O parâmetro AppId diz respeito à aplicação API do Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Exemplo do Principal do Serviço":::

1. Aceda novamente às **permissões da API** para registo da sua aplicação.

1. Selecione **Conceder o consentimento do administrador para...** completar o registo da aplicação.

1. Para concluir, temos de adicionar o nome do registo da aplicação como utilizador no Customer Insights.    
   Abrir Customer Insights, ir a **Admin** > **Permissões** e selecionar **Adicionar utilizador**.

1. Pesquisar o nome do registo da sua aplicação, selecione-o nos resultados da pesquisa e selecione **Guardar**.

## <a name="customer-insights-client-libraries"></a>Bibliotecas de clientes Customer Insights

Esta secção ajuda-o a começar a utilizar as bibliotecas de clientes disponíveis para as APIs de Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Saiba como começar a usar as bibliotecas de clientes C# a partir de NuGet.org. Para obter mais informações sobre o pacote NuGet, consulte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Atualmente, este pacote destina-se aos quadros netstandard2.0 e netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Adicione a biblioteca C# ao projeto C#

1. No Visual Studio, abra o **NuGet Gestor do pacote** para o seu projeto.

1. Pesquisar por **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selecione **Instalar** para adicionar o pacote ao projeto.
   Em alternativa, executar este comando na **NuGet Consola do Gestor de Pacotes**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Adicionar NuGet pacote ao projeto Visual Studio":::

#### <a name="use-the-c-client-library"></a>Use a biblioteca de cliente C#

1. Utilize a [Biblioteca de Autenticação da Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) para obter um `AccessToken` utilizando o seu [registo de aplicações Azure](#create-a-new-app-registration-in-the-azure-portal) existente.

1. Depois de autenticar e adquirir com sucesso um token, construa um novo ou utilize um existente `HttpClient` com o adicional de **"Autorização" DefaultRequestHeaders** para **Portador <access token>** e **Ocp-Apim-Chave de Subscrição** para a [**chave de subscrição** a partir do ambiente de Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Reinicie o cabeçalho de **Autorização** quando apropriado. Por exemplo, quando o token expirou.

1. Passe isto `HttpClient` para a construção do cliente do `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Amostra de httpclient":::

1. Faça chamadas com o cliente para os "métodos de extensão", por exemplo, `GetAllInstancesAsync`. Se for preferido o acesso ao subjacente `Microsoft.Rest.HttpOperationResponse`, utilize os "métodos de mensagem http", por exemplo, `GetAllInstancesWithHttpMessagesAsync`.

1. A resposta será provavelmente do tipo `object` porque o método pode devolver vários tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`). Para verificar o tipo de devolução, pode converter os objetos com segurança nos tipos de resposta especificados na [página de detalhes da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para essa operação.    
   Se forem necessárias mais informações sobre o pedido, utilize os **métodos de mensagem http** para aceder ao objeto de resposta bruta.

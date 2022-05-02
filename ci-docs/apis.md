---
title: Trabalhar com APIs
description: Use APIs e compreenda as limitações.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: ecc8bb3dbec1d4583c4bf2a58058145343945299
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646789"
---
# <a name="work-with-customer-insights-apis"></a>Trabalhar com APIs no Customer Insights

O Dynamics 365 Customer Insights fornece APIs para criar as suas próprias aplicações com base nos seus dados no Customer Insights.

> [!IMPORTANT]
> Os detalhes destas APIs estão listados na [referência de APIs do Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Incluem informações adicionais sobre operações, parâmetros e respostas.

Este artigo descreve como aceder às APIs do Customer Insights, criar um Registo de Aplicações Azure AD e começar a trabalhar com as bibliotecas de clientes disponíveis.

## <a name="get-started-trying-the-customer-insights-apis"></a>Começar a experimentar as APIs do Customer Insights

1. [Inicie sessão](https://home.ci.ai.dynamics.com) no Customer Insights. Se ainda não tiver uma subscrição, [inscreva-se para uma versão experimental do Customer Insights](https://aka.ms/tryci).

1. Para ativar APIs no seu ambiente de Customer Insights, aceda a **Admin** > **Permissões**. Vai precisar de permissões de administração para o fazer.

1. Vá ao separador **APIs** e selecione o botão **Ativar**.    
 
   Ativar as APIs cria uma chave de subscrição primária e secundária para a sua instância que é usada nos pedidos da API. Pode regenerar as chaves selecionando **Regenerar primária** ou **Regenerar secundária** em **Admin** > **Permissões** > **APIs**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Selecione **Explore as nossas APIs** para [experimentar as APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Escolha uma operação API e selecione **Experimentar**.

1. No painel lateral, defina o valor no menu pendente **Autorização** para **implícita**. O cabeçalho `Authorization` é adicionado com um token de portador. A sua chave de subscrição será automaticamente preenchida.
  
1. Opcionalmente, adicione todos os parâmetros de consulta necessários.

1. Percorra a parte inferior do painel lateral e selecione **Enviar**.

A resposta HTTP em breve aparecerá abaixo.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Crie o registo de uma nova aplicação no portal do Azure

Estes passos ajudam-no a começar a trabalhar com APIs do Customer Insights numa aplicação Azure utilizando permissões delegadas. Certifique-se de que conclui primeiro a [secção Começar](#get-started-trying-the-customer-insights-apis).

1. Inicie sessão no [portal Azure](https://portal.azure.com) com a conta que pode aceder aos dados do Customer Insights.

1. À esquerda, selecione **registos de Aplicações**.

1. Selecione **Novo registo**, forneça um nome de aplicação e escolha o tipo de conta.
 
   Opcionalmente, adicione um URL de redirecionamento. http://localhost é suficiente para desenvolver uma aplicação no seu computador local.

1. No seu novo registo de Aplicação, aceda às **permissões da API**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Selecione **Adicione uma permissão** e selecione **Customer Insights** no painel lateral.

1. Para **Tipo de permissão**, selecione **Permissões delegadas** e, em seguida, selecione a permissão **user_impersonation**.

1. Selecione **Adicionar permissões**. Se precisar de aceder à API sem que um utilizador faça login, reveja a secção de [permissões de aplicação Server-to-Server](#server-to-server-application-permissions).

1. Selecione **Conceder o consentimento do administrador para...** completar o registo da aplicação.

Pode utilizar o ID de Aplicação/Cliente para este registo de aplicações com a Biblioteca de Autenticação da Microsoft (MSAL) para obter um token de portador para enviar com o seu pedido para a API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Para obter mais informações sobre o MSAL, consulte a [visão geral da Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Para obter mais informações sobre o registo de aplicações no Azure, consulte [Registar uma aplicação](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Para obter informações sobre a utilização de APIs nas bibliotecas dos nossos clientes, consulte [Bibliotecas de clientes do Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permissões de aplicação server-to-server

A [secção de registo de aplicações](#create-a-new-app-registration-in-the-azure-portal) descreve como registar uma aplicação que requer que um utilizador faça login para autenticação. Saiba como criar um registo de aplicações que não precisa de interação do utilizador e que pode ser executado num servidor.

1. No registo da sua aplicação no portal Azure, aceda às **permissões da API**.

1. Selecione **Adicionar uma permissão**. 

1. Selecione o separador **APIs que a minha organização utiliza** e escolha **IA do Dynamics 365 para o Customer Insights** da lista. 

1. Para **Tipo de permissão**, selecione **Permissões da aplicação** e, em seguida, selecione a permissão **CustomerInsights.Api.All**.

1. Selecione **Adicionar permissões**.

1. Aceda novamente às **permissões da API** para registo da sua aplicação.

1. Selecione **Conceder o consentimento do administrador para...** completar o registo da aplicação.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Para concluir, temos de adicionar o nome do registo da aplicação como utilizador no Customer Insights.  
   
   Abrir Customer Insights, ir a **Admin** > **Permissões** e selecionar **Adicionar utilizador**.

1. Pesquisar o nome do registo da sua aplicação, selecione-o nos resultados da pesquisa e selecione **Guardar**.

## <a name="customer-insights-client-libraries"></a>Bibliotecas de clientes Customer Insights

Esta secção ajuda-o a começar a utilizar as bibliotecas de clientes disponíveis para as APIs de Customer Insights. Todos os códigos de origem da biblioteca e aplicações de exemplo podem ser encontrados na [página GitHub do Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Saiba como começar a usar as bibliotecas de clientes C# a partir de NuGet.org. Para obter mais informações sobre o pacote NuGet, consulte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Atualmente, este pacote destina-se aos quadros netstandard2.0 e netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Adicione a biblioteca C# ao projeto C#

1. No Visual Studio, abra o **NuGet Gestor do pacote** para o seu projeto.

1. Pesquisar por **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selecione **Instalar** para adicionar o pacote ao projeto.
 
   Em alternativa, executar este comando na **NuGet Consola do Gestor de Pacotes**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Use a biblioteca de cliente C#

1. Utilize a [Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter um `AccessToken` utilizando o seu [registo de aplicações Azure](#create-a-new-app-registration-in-the-azure-portal) existente.

1. Depois de autenticar e adquirir um token com êxito, crie um ou utilize um `HttpClient` existente com a **"Autorização" DefaultRequestHeaders** adicional definida como **"Token de acesso" de Portador** e **Ocp-Apim-Subscription-Key** definida como a [**chave de subscrição** do seu ambiente do Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Reinicie o cabeçalho de **Autorização** quando apropriado. Por exemplo, quando o token expirou.

1. Passe isto `HttpClient` para a construção do cliente do `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Faça chamadas com o cliente para os "métodos de extensão" – por exemplo, `GetAllInstancesAsync`. Se for preferido o acesso ao subjacente `Microsoft.Rest.HttpOperationResponse`, utilize os "métodos de mensagem http" – por exemplo, `GetAllInstancesWithHttpMessagesAsync`.

1. A resposta será provavelmente do tipo `object` porque o método pode devolver vários tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`). Para verificar o tipo de devolução, pode converter os objetos com segurança nos tipos de resposta especificados na [página de detalhes da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para essa operação.    
   
   Se forem necessárias mais informações sobre o pedido, utilize os **métodos de mensagem http** para aceder ao objeto de resposta bruta.

### <a name="nodejs-package"></a>Pacote NodeJS

Utilize as bibliotecas de cliente NodeJS disponíveis através do NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pacote Python

Utilize as bibliotecas de cliente Python disponíveis através do PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]

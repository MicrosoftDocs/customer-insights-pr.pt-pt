---
title: Ingestão de dados em tempo real e limitações
description: Informações gerais sobre as capacidades em tempo real nas informações de audiência.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598583"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="32bf2-103">Ingestão de dados em tempo real (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="32bf2-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="32bf2-104">A funcionalidade em tempo quase real permite ver, em poucos segundos, as interações mais recentes dos seus clientes com os seus produtos ou serviços.</span><span class="sxs-lookup"><span data-stu-id="32bf2-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="32bf2-105">[Atualizações programadas](system.md#schedule-tab) incluem um grande número de registos e várias operações complexas.</span><span class="sxs-lookup"><span data-stu-id="32bf2-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="32bf2-106">Primeiro, os dados são extraídos da origem de dados.</span><span class="sxs-lookup"><span data-stu-id="32bf2-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="32bf2-107">Em seguida, os dados são unificados e, em seguida, melhorados com informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="32bf2-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="32bf2-108">Cada execução deste processo pode demorar desde minutos a horas.</span><span class="sxs-lookup"><span data-stu-id="32bf2-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="32bf2-109">A funcionalidade em tempo real fornece dados imediatamente para consumo, até a subsequente atualização programada extrair estes dados da origem de dados.</span><span class="sxs-lookup"><span data-stu-id="32bf2-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="32bf2-110">As atualizações em tempo real têm uma hora de expiração após a qual deixam de substituir o valor da origem de dados:</span><span class="sxs-lookup"><span data-stu-id="32bf2-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="32bf2-111">As atualizações do perfil serão mantidas durante 4 horas</span><span class="sxs-lookup"><span data-stu-id="32bf2-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="32bf2-112">As atividades serão mantidas durante 30 dias</span><span class="sxs-lookup"><span data-stu-id="32bf2-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="32bf2-113">Estes valores são os parâmetros de chamada à API que pode alterar.</span><span class="sxs-lookup"><span data-stu-id="32bf2-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="32bf2-114">Visam assegurar que os seus dados de origem permanecem a sua origem da verdade.</span><span class="sxs-lookup"><span data-stu-id="32bf2-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="32bf2-115">Se quiser que as atualizações em tempo real sejam incluídas por mais tempo, é necessário adicioná-las a uma origem de dados para que sejam extraídas durante a próxima atualização programada.</span><span class="sxs-lookup"><span data-stu-id="32bf2-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="32bf2-116">Atualização em tempo real dos campos do perfil de cliente unificado</span><span class="sxs-lookup"><span data-stu-id="32bf2-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="32bf2-117">Os perfis atualizados serão mostrados na visualização do cartão do cliente, ou qualquer outra visualização, dentro de alguns segundos.</span><span class="sxs-lookup"><span data-stu-id="32bf2-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="32bf2-118">Como as operações em tempo real ocorrem depois de a unificação de dados ter acontecido, só são aplicáveis aos perfis de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="32bf2-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="32bf2-119">Consequentemente, as alterações ao perfil em tempo real não irão atualizar as medidas, a associação a segmentos ou os melhoramentos.</span><span class="sxs-lookup"><span data-stu-id="32bf2-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="32bf2-120">Limitações</span><span class="sxs-lookup"><span data-stu-id="32bf2-120">Limitations</span></span>

- <span data-ttu-id="32bf2-121">Os perfis de cliente podem ser atualizados, mas não criados ou eliminados.</span><span class="sxs-lookup"><span data-stu-id="32bf2-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="32bf2-122">A exportação de atualizações em tempo real para sistemas externos, como o Power BI, não é possível de momento.</span><span class="sxs-lookup"><span data-stu-id="32bf2-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="32bf2-123">Criação de atividades em tempo real</span><span class="sxs-lookup"><span data-stu-id="32bf2-123">Real-time creation of activities</span></span>

<span data-ttu-id="32bf2-124">A API em tempo real permite-lhe publicar uma nova atividade a partir do seu sistema de origem (um registo de origem individual) para um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="32bf2-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="32bf2-125">A nova atividade estará disponível como uma atividade unificada na linha cronológica do perfil desse cliente unificado em poucos segundos.</span><span class="sxs-lookup"><span data-stu-id="32bf2-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="32bf2-126">Pode ver a cronologia na visualização do cartão de cliente ou qualquer outra integração da cronologia que tenha configurado.</span><span class="sxs-lookup"><span data-stu-id="32bf2-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="32bf2-127">As atividades são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="32bf2-127">Activities are immutable.</span></span> <span data-ttu-id="32bf2-128">Não são alteradas depois de serem criadas.</span><span class="sxs-lookup"><span data-stu-id="32bf2-128">They don't change once created.</span></span>
> - <span data-ttu-id="32bf2-129">Atualmente, os segmentos e as medidas não serão atualizados com base na nova atividade.</span><span class="sxs-lookup"><span data-stu-id="32bf2-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="32bf2-130">As atividades adicionadas apenas através da API em tempo real não fazem parte das exportações e não serão mostradas no PowerBI.</span><span class="sxs-lookup"><span data-stu-id="32bf2-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="32bf2-131">Há duas formas de ligação ao API em tempo real:</span><span class="sxs-lookup"><span data-stu-id="32bf2-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="32bf2-132">[indiretamente](#connect-via-the-dynamics-365-customer-insights-connector), através do conector do [Dynamics 365 Customer Insights](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="32bf2-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="32bf2-133">[diretamente](#connect-directly-to-the-real-time-api), com código</span><span class="sxs-lookup"><span data-stu-id="32bf2-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="32bf2-134">Ambas as formas partilham os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="32bf2-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="32bf2-135">Um ambiente de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="32bf2-135">A Customer Insights environment</span></span>
- <span data-ttu-id="32bf2-136">Perfis de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="32bf2-136">Unified customer profiles</span></span>
- <span data-ttu-id="32bf2-137">Atividades configuradas e executadas</span><span class="sxs-lookup"><span data-stu-id="32bf2-137">Activities configured and run</span></span>
- <span data-ttu-id="32bf2-138">Permissões de Contribuidor ou Administrador para autenticar a sua conta</span><span class="sxs-lookup"><span data-stu-id="32bf2-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="32bf2-139">Ligar através do conector do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="32bf2-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="32bf2-140">A API em tempo real pode ingerir os dados a partir de um conector do Power Platform dedicado, o conector do [Dynamics 365 Customer Insights](/connectors/customerinsights/), sem a necessidade de escrever e implementar qualquer código.</span><span class="sxs-lookup"><span data-stu-id="32bf2-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="32bf2-141">O conector pode executar as mesmas ações em tempo real que a API.</span><span class="sxs-lookup"><span data-stu-id="32bf2-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="32bf2-142">Necessita de uma licença válida para os conectores premium.</span><span class="sxs-lookup"><span data-stu-id="32bf2-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="32bf2-143">Para mais informações, consulte [FAQ sobre o licenciamento do Power Apps e do Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="32bf2-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="32bf2-144">Power Platform [Power Apps e/ou Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="32bf2-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="32bf2-145">Azure [Logic Apps](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="32bf2-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="32bf2-146">Para obter detalhes sobre como criar fluxos, consulte a [documentação do Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="32bf2-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="32bf2-147">Ligar directamente à API em tempo real</span><span class="sxs-lookup"><span data-stu-id="32bf2-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="32bf2-148">Pode utilizar as capacidades em tempo real construindo o seu próprio pipeline e ligando-se diretamente ao API em tempo real.</span><span class="sxs-lookup"><span data-stu-id="32bf2-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="32bf2-149">Poderá publicar uma atividade no formato do seu sistema de origem ou no formato UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="32bf2-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="32bf2-150">Obtenha o formato ao efetuar uma chamada à API para /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="32bf2-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="32bf2-151">Detalhes desta API, incluindo parâmetros e respostas, podem ser encontrados na secção **EntityData** na [Referência de APIs de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="32bf2-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="32bf2-152">Para mais informações, consulte [Trabalhar com APIs de Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="32bf2-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="32bf2-153">Compreenda a sua utilização em tempo real com telemetria</span><span class="sxs-lookup"><span data-stu-id="32bf2-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="32bf2-154">Obtenha uma visão geral do volume de pedidos para o API em tempo real e informações sobre questões que o sistema possa encontrar.</span><span class="sxs-lookup"><span data-stu-id="32bf2-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="32bf2-155">Pode [aceder à telemetria em tempo real](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="32bf2-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Guia de predição de abandono da subscrição
description: Utilize este guia de amostra para experimentar o modelo de predição de abandono de subscrição.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306317"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1a853-103">Guia de predição de abandono da subscrição (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="1a853-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1a853-104">Iremos acompanhá-lo através de um exemplo de predição de abandono de subscrição usando os dados de amostra fornecidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="1a853-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="1a853-105">Cenário</span><span class="sxs-lookup"><span data-stu-id="1a853-105">Scenario</span></span>

<span data-ttu-id="1a853-106">A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que vende através do seu site Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="1a853-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1a853-107">Iniciaram recentemente um negócio de subscrições para que os seus clientes pudessem tomar café com regularidade.</span><span class="sxs-lookup"><span data-stu-id="1a853-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="1a853-108">O seu objetivo é compreender, quais os clientes subscritores que poderão cancelar a sua subscrição nos próximos meses.</span><span class="sxs-lookup"><span data-stu-id="1a853-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="1a853-109">Saber qual dos seus clientes os pode **abandonar** pode ajudá-los a poupar esforços de marketing, concentrando-se em mantê-los.</span><span class="sxs-lookup"><span data-stu-id="1a853-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1a853-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1a853-110">Prerequisites</span></span>

- <span data-ttu-id="1a853-111">Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1a853-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1a853-112">Recomendamos-lhe que implemente as seguintes etapas [num ambiente novo](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="1a853-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1a853-113">Tarefa 1 - Ingerir dados</span><span class="sxs-lookup"><span data-stu-id="1a853-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="1a853-114">Rever os artigos [sobre ingestão de dados](data-sources.md) e [importar origens de dados utilizando conectores Power Query](connect-power-query.md) especificamente.</span><span class="sxs-lookup"><span data-stu-id="1a853-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1a853-115">A seguinte informação pressupõe que está familiarizado com a ingestão de dados em geral.</span><span class="sxs-lookup"><span data-stu-id="1a853-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1a853-116">Ingerir dados de clientes a partir da plataforma eCommerce</span><span class="sxs-lookup"><span data-stu-id="1a853-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1a853-117">Criar uma origem de dados com o nome **eCommerce**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1a853-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1a853-118">Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="1a853-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1a853-119">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="1a853-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1a853-120">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="1a853-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1a853-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="1a853-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1a853-122">**CreatedOn**: Data/Hora/Zona</span><span class="sxs-lookup"><span data-stu-id="1a853-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. <span data-ttu-id="1a853-124">No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="1a853-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1a853-125">Guardar a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="1a853-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1a853-126">Ingerir dados de clientes a partir do esquema de fidelidade</span><span class="sxs-lookup"><span data-stu-id="1a853-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1a853-127">Criar uma origem de dados com o nome **LoyaltyScheme**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1a853-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1a853-128">Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="1a853-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1a853-129">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="1a853-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1a853-130">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="1a853-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1a853-131">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="1a853-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1a853-132">**RewardsPoints**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="1a853-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1a853-133">**CreatedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="1a853-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1a853-134">No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1a853-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1a853-135">Guardar a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="1a853-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="1a853-136">Ingerir informações de subscrição</span><span class="sxs-lookup"><span data-stu-id="1a853-136">Ingest subscription information</span></span>

1. <span data-ttu-id="1a853-137">Criar uma origem de dados com o nome **SubscriptionHistory**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1a853-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1a853-138">Introduza o URL para contactos de eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="1a853-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="1a853-139">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="1a853-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1a853-140">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="1a853-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1a853-141">**SubscriptioID**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="1a853-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="1a853-142">**SubscriptionAmount**: Moeda</span><span class="sxs-lookup"><span data-stu-id="1a853-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="1a853-143">**SubscriptionEndDate**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="1a853-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="1a853-144">**SubscriptionStartDate**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="1a853-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="1a853-145">**TransactionDate**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="1a853-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="1a853-146">**IsRecurring**: Verdadeiro/Falso</span><span class="sxs-lookup"><span data-stu-id="1a853-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="1a853-147">**Is_auto_renew**: Verdadeiro/Falso</span><span class="sxs-lookup"><span data-stu-id="1a853-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="1a853-148">**RecurringFrequencyInMonths**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="1a853-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="1a853-149">No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="1a853-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="1a853-150">Guardar a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="1a853-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="1a853-151">Ingerir dados de clientes a partir de avaliações de websites</span><span class="sxs-lookup"><span data-stu-id="1a853-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="1a853-152">Criar uma origem de dados com o nome **Website**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1a853-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1a853-153">Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="1a853-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="1a853-154">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="1a853-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1a853-155">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="1a853-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1a853-156">**ReviewRating**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="1a853-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="1a853-157">**ReviewDate**: Data</span><span class="sxs-lookup"><span data-stu-id="1a853-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="1a853-158">No campo "Nome" no painel da direita, altere o nome da sua origem de dados de **Consulta** para **webReview**.</span><span class="sxs-lookup"><span data-stu-id="1a853-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="1a853-159">Tarefa 2 - Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="1a853-159">Task 2 - Data unification</span></span>

<span data-ttu-id="1a853-160">Depois de ingerirmos os dados, iniciamos agora o processo **Mapear, Corresponder, Intercalar** para criar um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="1a853-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1a853-161">Para mais informações, consulte [Unificação de dados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1a853-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1a853-162">Mapear</span><span class="sxs-lookup"><span data-stu-id="1a853-162">Map</span></span>

1. <span data-ttu-id="1a853-163">Depois de ingerir os dados, mapear os contactos desde os dados de eCommerce e Fidelidade até aos tipos de dados comuns.</span><span class="sxs-lookup"><span data-stu-id="1a853-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1a853-164">Aceder a **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="1a853-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1a853-165">Selecionar as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1a853-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar as origens de dados do comércio eletrónico e da fidelidade.":::

1. <span data-ttu-id="1a853-167">Selecionar **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1a853-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificar LoyaltyId como a chave primária.":::

### <a name="match"></a><span data-ttu-id="1a853-169">Corresponder</span><span class="sxs-lookup"><span data-stu-id="1a853-169">Match</span></span>

1. <span data-ttu-id="1a853-170">Aceda ao separador **Corresponder** e selecione **Definir encomenda**.</span><span class="sxs-lookup"><span data-stu-id="1a853-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1a853-171">Na lista pendente **Primário**, escolha **eCommerceContacts : eCommerce** como a origem primária e inclua todos os registos.</span><span class="sxs-lookup"><span data-stu-id="1a853-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1a853-172">Na lista pendente **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registos.</span><span class="sxs-lookup"><span data-stu-id="1a853-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificar corresponder comércio eletrónico e fidelidade.":::

1. <span data-ttu-id="1a853-174">Selecione **Criar uma nova regra**</span><span class="sxs-lookup"><span data-stu-id="1a853-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1a853-175">Adicione a sua primeira condição usando FullName.</span><span class="sxs-lookup"><span data-stu-id="1a853-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1a853-176">Para eCommerceContacts, selecione **FullName** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="1a853-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="1a853-177">Para loyCustomers, selecione **FullName** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="1a853-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="1a853-178">Selecione a lista pendente **Normalizar** e escolha **Tipo (Telefone, Nome, Morada, ...)**.</span><span class="sxs-lookup"><span data-stu-id="1a853-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1a853-179">Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.</span><span class="sxs-lookup"><span data-stu-id="1a853-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1a853-180">Introduzir o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="1a853-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1a853-181">Acrescentar uma segunda condição para o endereço de correio eletrónico, selecionando **Adicionar condição**</span><span class="sxs-lookup"><span data-stu-id="1a853-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1a853-182">Para a entidade eCommerceContacts, escolha **E-mail** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="1a853-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="1a853-183">Para a entidade loyCustomers, escolha **E-mail** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="1a853-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="1a853-184">Deixar em branco Normalizar.</span><span class="sxs-lookup"><span data-stu-id="1a853-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1a853-185">Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.</span><span class="sxs-lookup"><span data-stu-id="1a853-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificar a regra de correspondência para nome e e-mail.":::

7. <span data-ttu-id="1a853-187">Selecione **Guardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1a853-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1a853-188">Unir</span><span class="sxs-lookup"><span data-stu-id="1a853-188">Merge</span></span>

1. <span data-ttu-id="1a853-189">Aceda ao separador **Intercalar**.</span><span class="sxs-lookup"><span data-stu-id="1a853-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1a853-190">No **ContactId** para a entidade **loyCustomers**, alterar o nome a apresentar para **ContactIdLOYALTY** para o diferenciar das outras IDs ingeridas.</span><span class="sxs-lookup"><span data-stu-id="1a853-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid a partir de loyalty id.":::

1. <span data-ttu-id="1a853-192">Selecione **Guardar** e **Executar** para iniciar o processo de intercalar.</span><span class="sxs-lookup"><span data-stu-id="1a853-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="1a853-193">Tarefa 3 - Configurar a predição de abandono da subscrição</span><span class="sxs-lookup"><span data-stu-id="1a853-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="1a853-194">Com os perfis unificados de clientes em vigor, podemos agora executar a predição de abandono da subscrição.</span><span class="sxs-lookup"><span data-stu-id="1a853-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1a853-195">Para passos detalhados, ver o artigo [Predição de abandono da subscrição (pré-visualização)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="1a853-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1a853-196">Vá a **Inteligência** > **Descobrir** e selecione para utilizar o **Modelo de abandono do cliente**.</span><span class="sxs-lookup"><span data-stu-id="1a853-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1a853-197">Selecione a opção **Subscrição** e selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="1a853-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="1a853-198">Dê um nome ao modelo **Predição de abandono de subscrição OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1a853-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="1a853-199">Definir duas condições para o modelo de abandono:</span><span class="sxs-lookup"><span data-stu-id="1a853-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1a853-200">**Dias desde o fim da subscrição**: **pelo menos 60** dias.</span><span class="sxs-lookup"><span data-stu-id="1a853-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="1a853-201">Se um cliente não renovar a subscrição neste período após o fim da sua subscrição, considera-se um abandono.</span><span class="sxs-lookup"><span data-stu-id="1a853-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="1a853-202">**Definição de abandono**: **pelo menos 93** dias.</span><span class="sxs-lookup"><span data-stu-id="1a853-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="1a853-203">A duração que o modelo prevê quais os clientes que poderão abandonar.</span><span class="sxs-lookup"><span data-stu-id="1a853-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="1a853-204">Quanto mais longe olhar no futuro, menos precisos serão os resultados.</span><span class="sxs-lookup"><span data-stu-id="1a853-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecionar as alavancas do modelo Janela de Predição e Definição de Abandono.":::

1. <span data-ttu-id="1a853-206">Selecione **Adicionar dados necessários** e selecione **Adicionar dados** para o histórico de subscrições.</span><span class="sxs-lookup"><span data-stu-id="1a853-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="1a853-207">Adicionar a entidade **Subscrição : SubscriptionHistory** e mapear os campos desde o comércio eletrónico até aos campos correspondentes exigidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="1a853-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1a853-208">Junte-se à entidade **Subscrição: SubscriptionHistory** com **eCommerceContacts : eCommerce**, dê um nome à relação **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="1a853-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Junte-se às entidade de eCommerce.":::

1. <span data-ttu-id="1a853-210">Em Atividades de Cliente, adicionar a entidade **webReviews : Website** e mapear os campos desde webReviews até aos campos correspondentes exigidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="1a853-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="1a853-211">Chave primária: ReviewId</span><span class="sxs-lookup"><span data-stu-id="1a853-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="1a853-212">Carimbo de Data/Hora: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="1a853-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="1a853-213">Evento: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="1a853-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="1a853-214">Configurar uma atividade para avaliações de website.</span><span class="sxs-lookup"><span data-stu-id="1a853-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="1a853-215">Selecione a atividade **Avaliar** e junte a entidade **webReviews : Website** com **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1a853-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="1a853-216">Selecione **Seguinte** para definir o agendar do modelo.</span><span class="sxs-lookup"><span data-stu-id="1a853-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1a853-217">O modelo precisa de treinar regularmente para aprender novos padrões quando há novos dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="1a853-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1a853-218">Para este exemplo, selecione **Mensalmente**.</span><span class="sxs-lookup"><span data-stu-id="1a853-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1a853-219">Depois de rever todos os detalhes, selecione **Guardar e Executar**.</span><span class="sxs-lookup"><span data-stu-id="1a853-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1a853-220">Tarefa 4 - Rever resultados do modelo e explicações</span><span class="sxs-lookup"><span data-stu-id="1a853-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1a853-221">Deixe o modelo completar a formação e a pontuação dos dados.</span><span class="sxs-lookup"><span data-stu-id="1a853-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1a853-222">Pode agora rever as explicações do modelo de abandono da subscrição.</span><span class="sxs-lookup"><span data-stu-id="1a853-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1a853-223">Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1a853-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1a853-224">Tarefa 5 - Criar um segmento de clientes de alto risco de abandono</span><span class="sxs-lookup"><span data-stu-id="1a853-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1a853-225">A execução do modelo de produção cria uma nova entidade que se pode ver em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="1a853-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1a853-226">Pode criar um novo segmento com base na entidade criada pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="1a853-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1a853-227">Aceda a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="1a853-227">Go to **Segments**.</span></span> <span data-ttu-id="1a853-228">Selecione **Novo** e escolha **Criar a partir de** > **Inteligência**.</span><span class="sxs-lookup"><span data-stu-id="1a853-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Criar um segmento com a saída do modelo.":::

1. <span data-ttu-id="1a853-230">Selecione o ponto final **OOBSubscriptionChurnPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="1a853-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1a853-231">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1a853-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="1a853-232">Operador: maior do que</span><span class="sxs-lookup"><span data-stu-id="1a853-232">Operator: greater than</span></span>
   - <span data-ttu-id="1a853-233">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="1a853-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar um segmento de abandono de subscrição.":::

<span data-ttu-id="1a853-235">Tem agora um segmento dinamicamente atualizado que identifica clientes com alto risco de abandono para este negócio de subscrições.</span><span class="sxs-lookup"><span data-stu-id="1a853-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1a853-236">Para obter mais informações, veja [Criar e gerir segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1a853-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
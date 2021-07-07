---
title: Guia de exemplo de predição de valor vitalício do cliente
description: Utilize este guia de exemplo para experimentar o modelo de predição de valor vitalício do cliente.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306363"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="aa984-103">Guia de exemplo de predição de valor vitalício do cliente (CLV)</span><span class="sxs-lookup"><span data-stu-id="aa984-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="aa984-104">Este guia irá orientá-lo através de exemplo de ponta a ponta da Predição de valor vitalício do cliente (CLV) no Customer Insights utilizando dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="aa984-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="aa984-105">Cenário</span><span class="sxs-lookup"><span data-stu-id="aa984-105">Scenario</span></span>

<span data-ttu-id="aa984-106">A Contoso é uma empresa que produz café e máquinas de café de alta qualidade.</span><span class="sxs-lookup"><span data-stu-id="aa984-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="aa984-107">Vendem os produtos através do seu site Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="aa984-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="aa984-108">A empresa quer entender o valor (receita) que os seus clientes podem gerar nos próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="aa984-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="aa984-109">Conhecer o valor esperado dos seus clientes nos próximos 12 meses irá ajudá-los a orientar os seus esforços de marketing para clientes de valor elevado.</span><span class="sxs-lookup"><span data-stu-id="aa984-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa984-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="aa984-110">Prerequisites</span></span>

- <span data-ttu-id="aa984-111">Pelo menos, [Permissões de contribuidor](permissions.md) em informações de audiência.</span><span class="sxs-lookup"><span data-stu-id="aa984-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="aa984-112">Recomendamos-lhe que implemente as seguintes etapas [num ambiente novo](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="aa984-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="aa984-113">Tarefa 1 - Ingerir dados</span><span class="sxs-lookup"><span data-stu-id="aa984-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="aa984-114">Reveja os artigos [sobre a ingestão de dados](data-sources.md) e a [importar origens de dados utilizando conectores do Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="aa984-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="aa984-115">A seguinte informação pressupõe que está familiarizado com a ingestão de dados em geral.</span><span class="sxs-lookup"><span data-stu-id="aa984-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="aa984-116">Ingerir dados de clientes a partir da plataforma eCommerce</span><span class="sxs-lookup"><span data-stu-id="aa984-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="aa984-117">Criar uma origem de dados com o nome **eCommerce**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="aa984-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="aa984-118">Introduza o URL para contactos de eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="aa984-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="aa984-119">Ao editar os dados, selecione **Transformar** e, em seguida, **Utilizar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="aa984-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="aa984-120">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="aa984-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="aa984-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="aa984-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="aa984-122">**CreatedOn**: Data/Hora/Zona</span><span class="sxs-lookup"><span data-stu-id="aa984-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. <span data-ttu-id="aa984-124">No campo "Nome" no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="aa984-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="aa984-125">**Guardar** a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="aa984-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="aa984-126">Ingerir dados de compra online</span><span class="sxs-lookup"><span data-stu-id="aa984-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="aa984-127">Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="aa984-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="aa984-128">Escolha novamente o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="aa984-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="aa984-129">Introduza o URL para dados de **Compras online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="aa984-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="aa984-130">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="aa984-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="aa984-131">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="aa984-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="aa984-132">**PurchasedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="aa984-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="aa984-133">**TotalPrice**: Moeda</span><span class="sxs-lookup"><span data-stu-id="aa984-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="aa984-134">No campo **Nome** no painel lateral, mude o nome da sua origem de dados de **Consulta** para **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="aa984-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="aa984-135">**Guardar** a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="aa984-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="aa984-136">Ingerir dados de clientes a partir do esquema de fidelidade</span><span class="sxs-lookup"><span data-stu-id="aa984-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="aa984-137">Criar uma origem de dados com o nome **LoyaltyScheme**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="aa984-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="aa984-138">Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="aa984-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="aa984-139">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="aa984-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="aa984-140">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="aa984-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="aa984-141">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="aa984-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="aa984-142">**RewardsPoints**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="aa984-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="aa984-143">**CreatedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="aa984-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="aa984-144">No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="aa984-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="aa984-145">**Guardar** a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="aa984-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="aa984-146">Ingerir dados de clientes a partir de avaliações de websites</span><span class="sxs-lookup"><span data-stu-id="aa984-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="aa984-147">Criar uma origem de dados com o nome **Website**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="aa984-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="aa984-148">Introduza o URL para contactos de eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="aa984-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="aa984-149">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="aa984-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="aa984-150">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="aa984-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="aa984-151">**ReviewRating**: número Decimal</span><span class="sxs-lookup"><span data-stu-id="aa984-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="aa984-152">**ReviewDate**: Data</span><span class="sxs-lookup"><span data-stu-id="aa984-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="aa984-153">No campo "Nome" no painel direito, mude o nome da sua origem de dados de **Consulta** para **Revisão**.</span><span class="sxs-lookup"><span data-stu-id="aa984-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="aa984-154">**Guardar** a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="aa984-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="aa984-155">Tarefa 2 - Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="aa984-155">Task 2 - Data unification</span></span>

<span data-ttu-id="aa984-156">Depois de ingerir os dados, iniciamos agora o processo de unificação de dados para criar um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="aa984-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="aa984-157">Para mais informações, consulte [Unificação de dados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="aa984-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="aa984-158">Mapear</span><span class="sxs-lookup"><span data-stu-id="aa984-158">Map</span></span>

1. <span data-ttu-id="aa984-159">Depois de ingerir os dados, mapear os contactos desde os dados de eCommerce e Fidelidade até aos tipos de dados comuns.</span><span class="sxs-lookup"><span data-stu-id="aa984-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="aa984-160">Aceder a **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="aa984-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="aa984-161">Selecionar as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="aa984-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="aa984-162">Em seguida, selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="aa984-162">Then, select **Apply**.</span></span>

   ![unificar as origens de dados do comércio eletrónico e da fidelidade.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="aa984-164">Selecionar **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="aa984-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unificar LoyaltyId como a chave primária.](media/unify-loyaltyid.png)

1. <span data-ttu-id="aa984-166">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa984-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="aa984-167">Corresponder</span><span class="sxs-lookup"><span data-stu-id="aa984-167">Match</span></span>

1. <span data-ttu-id="aa984-168">Aceda ao separador **Corresponder** e selecione **Definir encomenda**.</span><span class="sxs-lookup"><span data-stu-id="aa984-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="aa984-169">Na lista pendente **Primário**, escolha **eCommerceContacts : eCommerce** como a origem primária e inclua todos os registos.</span><span class="sxs-lookup"><span data-stu-id="aa984-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="aa984-170">Na lista pendente **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registos.</span><span class="sxs-lookup"><span data-stu-id="aa984-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unificar corresponder comércio eletrónico e fidelidade.](media/unify-match-order.png)

1. <span data-ttu-id="aa984-172">Selecione **Adicionar regra**</span><span class="sxs-lookup"><span data-stu-id="aa984-172">Select **Add rule**</span></span>

1. <span data-ttu-id="aa984-173">Adicione a sua primeira condição usando FullName.</span><span class="sxs-lookup"><span data-stu-id="aa984-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="aa984-174">Para eCommerceContacts, selecione **FullName** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="aa984-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="aa984-175">Para loyCustomers, selecione **FullName** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="aa984-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="aa984-176">Selecione a lista pendente **Normalizar** e escolha **Tipo (Telefone, Nome, Endereço, ...)**.</span><span class="sxs-lookup"><span data-stu-id="aa984-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="aa984-177">Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.</span><span class="sxs-lookup"><span data-stu-id="aa984-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="aa984-178">Introduzir o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="aa984-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="aa984-179">Acrescentar uma segunda condição para o endereço de correio eletrónico, selecionando **Adicionar condição**</span><span class="sxs-lookup"><span data-stu-id="aa984-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="aa984-180">Para a entidade eCommerceContacts, escolha **E-mail** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="aa984-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="aa984-181">Para a entidade loyCustomers, escolha **E-mail** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="aa984-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="aa984-182">Deixar em branco Normalizar.</span><span class="sxs-lookup"><span data-stu-id="aa984-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="aa984-183">Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.</span><span class="sxs-lookup"><span data-stu-id="aa984-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificar a regra de correspondência para nome e e-mail.](media/unify-match-rule.png)

1. <span data-ttu-id="aa984-185">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="aa984-185">Select **Done**.</span></span>

1. <span data-ttu-id="aa984-186">Selecione **Guardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="aa984-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="aa984-187">Intercalar</span><span class="sxs-lookup"><span data-stu-id="aa984-187">Merge</span></span>

1. <span data-ttu-id="aa984-188">Aceda ao separador **Intercalar**.</span><span class="sxs-lookup"><span data-stu-id="aa984-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="aa984-189">No **ContactId** para a entidade **loyCustomers**, alterar o nome a apresentar para **ContactIdLOYALTY** para o diferenciar das outras IDs ingeridas.</span><span class="sxs-lookup"><span data-stu-id="aa984-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![renomear contactid a partir de loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="aa984-191">Selecione **Guardar** e **Executar processos de união e a jusante**.</span><span class="sxs-lookup"><span data-stu-id="aa984-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="aa984-192">Tarefa 3 – Configurar a predição de valor vitalício do cliente</span><span class="sxs-lookup"><span data-stu-id="aa984-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="aa984-193">Com os perfis de clientes unificados no lugar, podemos agora executar a predição de valor vitalício do cliente.</span><span class="sxs-lookup"><span data-stu-id="aa984-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="aa984-194">Para passos detalhados, consulte [Predição de Valor Vitalício do Cliente (pré-visualização)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="aa984-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="aa984-195">Aceda a **Inteligência**  > **Predições** e selecione o **Modelo de valor vitalício do cliente**.</span><span class="sxs-lookup"><span data-stu-id="aa984-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="aa984-196">Veja as informações no painel lateral e selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="aa984-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="aa984-197">Nomeie o modelo **Predição de CLV de eCommerce OOB** e a entidade de saída **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="aa984-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="aa984-198">Defina preferências de modelo para o modelo CLV:</span><span class="sxs-lookup"><span data-stu-id="aa984-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="aa984-199">**Período de tempo da predição**: **12 meses ou 1 ano**.</span><span class="sxs-lookup"><span data-stu-id="aa984-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="aa984-200">Esta definição define até onde no futuro pretende prever o valor vitalício do cliente.</span><span class="sxs-lookup"><span data-stu-id="aa984-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="aa984-201">**Clientes ativos**: especifique o que clientes ativos significam para o seu negócio.</span><span class="sxs-lookup"><span data-stu-id="aa984-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="aa984-202">Defina o intervalo de tempo histórico em que um cliente tem de ter tido, pelo menos, uma transação para ser considerado ativo.</span><span class="sxs-lookup"><span data-stu-id="aa984-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="aa984-203">O modelo apenas irá prever o CLV para clientes ativos.</span><span class="sxs-lookup"><span data-stu-id="aa984-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="aa984-204">Escolha entre deixar o modelo calcular o período de tempo com base em dados de transações históricos ou fornecer um intervalo de tempo específico.</span><span class="sxs-lookup"><span data-stu-id="aa984-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="aa984-205">Neste guia de exemplo, **deixámos o modelo calcular o intervalo de compra**, que é a opção predefinida.</span><span class="sxs-lookup"><span data-stu-id="aa984-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="aa984-206">**Clientes de valor elevado**: defina clientes de valor elevado como um percentil de clientes que mais pagam.</span><span class="sxs-lookup"><span data-stu-id="aa984-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="aa984-207">O modelo utiliza esta entrada para fornecer resultados que se adequam à sua definição de negócio de clientes de valor elevado.</span><span class="sxs-lookup"><span data-stu-id="aa984-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="aa984-208">Pode escolher deixar o modelo definir os clientes de valor elevado.</span><span class="sxs-lookup"><span data-stu-id="aa984-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="aa984-209">Utiliza uma regra heurística que deriva o percentil.</span><span class="sxs-lookup"><span data-stu-id="aa984-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="aa984-210">Também pode definir clientes de valor elevado como um percentil de clientes que mais pagam futuros.</span><span class="sxs-lookup"><span data-stu-id="aa984-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="aa984-211">Neste guia de exemplo, definimos manualmente clientes de valor elevado como **30%** dos clientes que pagam ativos e selecionamos **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="aa984-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Passo de preferências na experiência guiada para o modelo CLV.":::

1. <span data-ttu-id="aa984-213">No passo **Dados Exigidos**, selecione **Adicionar dados** para fornecer os dados do histórico de transações.</span><span class="sxs-lookup"><span data-stu-id="aa984-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="aa984-214">Adicione e entidade **eCommercePurchases : eCommerce** e mapeie os atributos que são exigidos pelo modelo:</span><span class="sxs-lookup"><span data-stu-id="aa984-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="aa984-215">ID da Transação: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="aa984-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="aa984-216">Data da transação: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="aa984-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="aa984-217">Montante da transação: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="aa984-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="aa984-218">ID do Produto: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="aa984-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="aa984-219">Selecione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="aa984-219">Select **Next**.</span></span>

1. <span data-ttu-id="aa984-220">Configure a relação entre a entidade **eCommercePurchases : eCommerce** e **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="aa984-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="aa984-221">O passo **Dados adicionais (opcional)** permite-lhe adicionar mais dados de atividade do cliente.</span><span class="sxs-lookup"><span data-stu-id="aa984-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="aa984-222">Estes dados podem ajudar a obter mais informações sobre as interações do cliente com o seu negócio, o que pode contribuir para o CLV.</span><span class="sxs-lookup"><span data-stu-id="aa984-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="aa984-223">Adicionar interações chave do cliente, como o histórico de registos Web, registos de suporte ao cliente ou recompensas do programa pode melhorar a precisão das predições.</span><span class="sxs-lookup"><span data-stu-id="aa984-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="aa984-224">Selecione **Adicionar dados** para incluir mais dados de atividade do cliente.</span><span class="sxs-lookup"><span data-stu-id="aa984-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="aa984-225">Adicione a entidade de atividade do cliente e mapeie os respetivos nomes dos campos para os campos correspondentes exigidos pelo modelo:</span><span class="sxs-lookup"><span data-stu-id="aa984-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="aa984-226">Entidade de atividade do cliente: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="aa984-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="aa984-227">Chave primária: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="aa984-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="aa984-228">Carimbo de data/hora: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="aa984-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="aa984-229">Evento (nome da atividade): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="aa984-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="aa984-230">Detalhes (montante ou valor): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="aa984-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="aa984-231">Selecione **Seguinte** e configure a atividade e a relação entre os dados de transação e os dados do cliente:</span><span class="sxs-lookup"><span data-stu-id="aa984-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="aa984-232">Tipo de atividade: escolha um existente</span><span class="sxs-lookup"><span data-stu-id="aa984-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="aa984-233">Etiqueta de atividade: Review</span><span class="sxs-lookup"><span data-stu-id="aa984-233">Activity label: Review</span></span>
   - <span data-ttu-id="aa984-234">Etiqueta correspondente: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="aa984-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="aa984-235">Entidade de cliente: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="aa984-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="aa984-236">Relação: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="aa984-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="aa984-237">Selecione **Seguinte** para definir o agendar do modelo.</span><span class="sxs-lookup"><span data-stu-id="aa984-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="aa984-238">O modelo precisa de treinar regularmente para aprender novos padrões quando há novos dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="aa984-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="aa984-239">Para este exemplo, escolha **Mensalmente**.</span><span class="sxs-lookup"><span data-stu-id="aa984-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="aa984-240">Depois de rever todos os detalhes, selecione **Guardar e Executar**.</span><span class="sxs-lookup"><span data-stu-id="aa984-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="aa984-241">Tarefa 4 - Rever resultados do modelo e explicações</span><span class="sxs-lookup"><span data-stu-id="aa984-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="aa984-242">Deixe o modelo completar a formação e a pontuação dos dados.</span><span class="sxs-lookup"><span data-stu-id="aa984-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="aa984-243">Em seguida, pode rever os resultados e explicações do modelo CLV.</span><span class="sxs-lookup"><span data-stu-id="aa984-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="aa984-244">Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="aa984-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="aa984-245">Tarefa 5 – Criar um segmento de clientes de valor elevado</span><span class="sxs-lookup"><span data-stu-id="aa984-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="aa984-246">A execução do modelo cria uma nova entidade, que é listada em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="aa984-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="aa984-247">Pode criar um novo segmento de cliente baseado na entidade criada pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="aa984-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="aa984-248">Aceda a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="aa984-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="aa984-249">Selecione **Novo** e escolha **Criar a partir de** > **Inteligência**.</span><span class="sxs-lookup"><span data-stu-id="aa984-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Criar um segmento com a saída do modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="aa984-251">Selecione a entidade **OOBeCommerceCLVPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="aa984-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="aa984-252">Campo: CLVScore</span><span class="sxs-lookup"><span data-stu-id="aa984-252">Field: CLVScore</span></span>
  - <span data-ttu-id="aa984-253">Operador: maior do que</span><span class="sxs-lookup"><span data-stu-id="aa984-253">Operator: greater than</span></span>
  - <span data-ttu-id="aa984-254">Valor: 1500</span><span class="sxs-lookup"><span data-stu-id="aa984-254">Value: 1500</span></span>

1. <span data-ttu-id="aa984-255">Selecione **Rever** e **Guarde** o segmento.</span><span class="sxs-lookup"><span data-stu-id="aa984-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="aa984-256">Tem agora um segmento que identifica clientes que se prevê gerarem mais de 1500$ de receitas nos próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="aa984-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="aa984-257">Este segmento é atualizado dinamicamente se mais dados forem ingeridos.</span><span class="sxs-lookup"><span data-stu-id="aa984-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="aa984-258">Para obter mais informações, veja [Criar e gerir segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="aa984-258">For more information, see [Create and manage segments](segments.md).</span></span>

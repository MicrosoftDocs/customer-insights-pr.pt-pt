---
title: Guia de exemplos de predição de recomendações de produtos
description: Utilize este guia de exemplos para experimentar o modelo de predição de recomendações de produtos de origem.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595287"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="95e5d-103">Guia de exemplos de predição de recomendações de produtos (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="95e5d-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="95e5d-104">Iremos acompanhá-lo do princípio ao fim num exemplo de predição de recomendações de produtos usando os dados de exemplo fornecidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="95e5d-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="95e5d-105">Cenário</span><span class="sxs-lookup"><span data-stu-id="95e5d-105">Scenario</span></span>

<span data-ttu-id="95e5d-106">Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que vendem através do seu site Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="95e5d-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="95e5d-107">O objetivo é compreender quais os produtos que devem recomendar aos seus clientes recorrentes.</span><span class="sxs-lookup"><span data-stu-id="95e5d-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="95e5d-108">Saber quais os clientes mais **propensos a comprar**, pode ajudá-los a economizar esforços de marketing, focando-se em itens específicos.</span><span class="sxs-lookup"><span data-stu-id="95e5d-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95e5d-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="95e5d-109">Prerequisites</span></span>

- <span data-ttu-id="95e5d-110">Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="95e5d-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="95e5d-111">Recomendamos-lhe que implemente as seguintes etapas [num ambiente novo](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="95e5d-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="95e5d-112">Tarefa 1 - Ingerir dados</span><span class="sxs-lookup"><span data-stu-id="95e5d-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="95e5d-113">Rever os artigos [sobre ingestão de dados](data-sources.md) e [importar origens de dados utilizando conectores Power Query](connect-power-query.md) especificamente.</span><span class="sxs-lookup"><span data-stu-id="95e5d-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="95e5d-114">A seguinte informação pressupõe que está familiarizado com a ingestão de dados em geral.</span><span class="sxs-lookup"><span data-stu-id="95e5d-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="95e5d-115">Ingerir dados de clientes a partir da plataforma eCommerce</span><span class="sxs-lookup"><span data-stu-id="95e5d-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="95e5d-116">Criar uma origem de dados com o nome **eCommerce**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="95e5d-117">Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="95e5d-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="95e5d-118">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="95e5d-119">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="95e5d-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="95e5d-120">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="95e5d-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="95e5d-121">**CreatedOn**: Data/Hora/Zona</span><span class="sxs-lookup"><span data-stu-id="95e5d-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

5. <span data-ttu-id="95e5d-123">No campo "Nome" no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="95e5d-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="95e5d-124">**Guardar** a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="95e5d-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="95e5d-125">Ingerir dados de compra online</span><span class="sxs-lookup"><span data-stu-id="95e5d-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="95e5d-126">Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="95e5d-127">Escolha novamente o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="95e5d-128">Introduza o URL para dados de **Compras online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="95e5d-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="95e5d-129">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="95e5d-130">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="95e5d-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="95e5d-131">**PurchasedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="95e5d-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="95e5d-132">**TotalPrice**: Moeda</span><span class="sxs-lookup"><span data-stu-id="95e5d-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="95e5d-133">No campo **Nome** no painel lateral, mude o nome da sua origem de dados de **Consulta** para **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="95e5d-134">Guardar a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="95e5d-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="95e5d-135">Ingerir dados de clientes a partir do esquema de fidelidade</span><span class="sxs-lookup"><span data-stu-id="95e5d-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="95e5d-136">Criar uma origem de dados com o nome **LoyaltyScheme**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="95e5d-137">Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="95e5d-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="95e5d-138">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="95e5d-139">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="95e5d-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="95e5d-140">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="95e5d-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="95e5d-141">**RewardsPoints**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="95e5d-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="95e5d-142">**CreatedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="95e5d-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="95e5d-143">No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="95e5d-144">Guardar a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="95e5d-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="95e5d-145">Tarefa 2 - Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="95e5d-145">Task 2 - Data unification</span></span>

<span data-ttu-id="95e5d-146">Depois de ingerirmos os dados, iniciamos agora o processo **Mapear, Corresponder, Intercalar** para criar um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="95e5d-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="95e5d-147">Para mais informações, consulte [Unificação de dados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="95e5d-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="95e5d-148">Mapear</span><span class="sxs-lookup"><span data-stu-id="95e5d-148">Map</span></span>

1. <span data-ttu-id="95e5d-149">Depois de ingerir os dados, mapear os contactos desde os dados de eCommerce e Fidelidade até aos tipos de dados comuns.</span><span class="sxs-lookup"><span data-stu-id="95e5d-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="95e5d-150">Aceder a **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="95e5d-151">Selecionar as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![unificar as origens de dados do comércio eletrónico e da fidelidade.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="95e5d-153">Selecionar **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unificar LoyaltyId como a chave primária.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="95e5d-155">Corresponder</span><span class="sxs-lookup"><span data-stu-id="95e5d-155">Match</span></span>

1. <span data-ttu-id="95e5d-156">Aceda ao separador **Corresponder** e selecione **Definir encomenda**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="95e5d-157">Na lista pendente **Primária**, escolher **eCommerceContacts : eCommerce** como a origem primária e incluir todos os registos.</span><span class="sxs-lookup"><span data-stu-id="95e5d-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="95e5d-158">Na lista pendente **Entidade 2**, escolher **loyCustomers : LoyaltyScheme** e incluir todos os registos.</span><span class="sxs-lookup"><span data-stu-id="95e5d-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unificar corresponder comércio eletrónico e fidelidade.](media/unify-match-order.png)

4. <span data-ttu-id="95e5d-160">Selecione **Criar uma nova regra**</span><span class="sxs-lookup"><span data-stu-id="95e5d-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="95e5d-161">Adicione a sua primeira condição usando FullName.</span><span class="sxs-lookup"><span data-stu-id="95e5d-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="95e5d-162">Para eCommerceContacts selecione **FullName** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="95e5d-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="95e5d-163">Para loyCustomers selecione **FullName** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="95e5d-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="95e5d-164">Selecione a lista pendente **Normalizar** e escolha **Tipo (Telefone, Nome, Morada, ...)**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="95e5d-165">Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="95e5d-166">Introduzir o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="95e5d-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="95e5d-167">Acrescentar uma segunda condição para o endereço de correio eletrónico, selecionando **Adicionar condição**</span><span class="sxs-lookup"><span data-stu-id="95e5d-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="95e5d-168">Para a entidade eCommerceContacts, escolha **EMail** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="95e5d-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="95e5d-169">Para a entidade loyCustomers, escolha **EMail** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="95e5d-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="95e5d-170">Deixar em branco Normalizar.</span><span class="sxs-lookup"><span data-stu-id="95e5d-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="95e5d-171">Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificar a regra de correspondência para nome e e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="95e5d-173">Selecione **Guardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="95e5d-174">Unir</span><span class="sxs-lookup"><span data-stu-id="95e5d-174">Merge</span></span>

1. <span data-ttu-id="95e5d-175">Aceda ao separador **Intercalar**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="95e5d-176">No **ContactId** para a entidade **loyCustomers**, alterar o nome a apresentar para **ContactIdLOYALTY** para o diferenciar das outras IDs ingeridas.</span><span class="sxs-lookup"><span data-stu-id="95e5d-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![renomear contactid a partir de loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="95e5d-178">Selecione **Guardar** e **Executar** para iniciar o processo de intercalar.</span><span class="sxs-lookup"><span data-stu-id="95e5d-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="95e5d-179">Tarefa 3 – Configurar a predição de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="95e5d-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="95e5d-180">Com os perfis unificados de clientes em vigor, podemos agora executar a predição de abandono da subscrição.</span><span class="sxs-lookup"><span data-stu-id="95e5d-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="95e5d-181">Vá à **Inteligência** > **Predição**, escolha **Recomendação do produto**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="95e5d-182">Selecione **Introdução**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-182">Select **Get started**.</span></span>

1. <span data-ttu-id="95e5d-183">Nomeie o modelo **Predição do Modelo de Recomendações de Produtos OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="95e5d-184">Definir três condições para o modelo:</span><span class="sxs-lookup"><span data-stu-id="95e5d-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="95e5d-185">**Número de produtos**: defina este valor para **5**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="95e5d-186">Esta definição define quantos produtos pretende recomendar aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="95e5d-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="95e5d-187">**Sugerir produtos que os clientes compraram recentemente?**: selecione **Sim** para indicar que pretende incluir produtos na recomendação que os seus clientes já compraram anteriormente.</span><span class="sxs-lookup"><span data-stu-id="95e5d-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="95e5d-188">**Janela de recuo:** selecione, pelo menos, **365 dias**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="95e5d-189">Esta definição define o período passado que o modelo irá observar a atividade do cliente para a utilizar como entrada para as respetivas recomendações.</span><span class="sxs-lookup"><span data-stu-id="95e5d-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferências de modelo para o modelo de recomendação de produtos.":::

1. <span data-ttu-id="95e5d-191">Selecione **Dados obrigatórios** e selecione **Adicionar dados** para o histórico de compras.</span><span class="sxs-lookup"><span data-stu-id="95e5d-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="95e5d-192">Adicionar a entidade **eCommercePurchases : eCommerce** e mapear os campos desde o comércio eletrónico até aos campos correspondentes exigidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="95e5d-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="95e5d-193">Junte a entidade **eCommercePurchases : eCommerce** com **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Junte-se às entidade de eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="95e5d-195">Selecione **Seguinte** para definir o agendar do modelo.</span><span class="sxs-lookup"><span data-stu-id="95e5d-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="95e5d-196">O modelo precisa de treinar regularmente para aprender novos padrões quando há novos dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="95e5d-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="95e5d-197">Para este exemplo, selecione **Mensalmente**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="95e5d-198">Depois de rever todos os detalhes, selecione **Guardar e Executar**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="95e5d-199">Tarefa 4 - Rever resultados do modelo e explicações</span><span class="sxs-lookup"><span data-stu-id="95e5d-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="95e5d-200">Deixe o modelo completar a formação e a pontuação dos dados.</span><span class="sxs-lookup"><span data-stu-id="95e5d-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="95e5d-201">Pode agora rever as explicações do modelo de recomendação de produtos.</span><span class="sxs-lookup"><span data-stu-id="95e5d-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="95e5d-202">Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="95e5d-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="95e5d-203">Tarefa 5 – Criar um segmento de produtos muito comprados</span><span class="sxs-lookup"><span data-stu-id="95e5d-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="95e5d-204">A execução do modelo de produção cria uma nova entidade que se pode ver em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="95e5d-205">Pode criar um novo segmento com base na entidade criada pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="95e5d-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="95e5d-206">Aceda a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-206">Go to **Segments**.</span></span> <span data-ttu-id="95e5d-207">Selecione **Novo** e escolha **Criar a partir de** > **Inteligência**.</span><span class="sxs-lookup"><span data-stu-id="95e5d-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Criar um segmento com a saída do modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="95e5d-209">Selecione o ponto final **OOBProductProductRecommendationModelPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="95e5d-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="95e5d-210">Campo: ProductID</span><span class="sxs-lookup"><span data-stu-id="95e5d-210">Field: ProductID</span></span>
   - <span data-ttu-id="95e5d-211">Operador: Valor</span><span class="sxs-lookup"><span data-stu-id="95e5d-211">Operator: Value</span></span>
   - <span data-ttu-id="95e5d-212">Valor: selecione os três principais IDs do produto</span><span class="sxs-lookup"><span data-stu-id="95e5d-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Criar um segmento a partir dos resultados do modelo.":::

<span data-ttu-id="95e5d-214">Tem agora um segmento que é atualizado dinamicamente que identifica os clientes que estão mais dispostos a comprar os três produtos mais recomendados</span><span class="sxs-lookup"><span data-stu-id="95e5d-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="95e5d-215">Para obter mais informações, veja [Criar e gerir segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="95e5d-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
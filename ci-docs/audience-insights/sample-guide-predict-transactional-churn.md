---
title: Guia de predição de abandono transacional
description: Utilize este guia de amostra para experimentar o modelo de predição de abandono transacional.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306134"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="12877-103">Guia de amostra de predição de abandono transacional (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="12877-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="12877-104">Este guia irá guiá-lo através de um exemplo da predição de abandono transacional no Customer Insights, utilizando os dados fornecidos abaixo</span><span class="sxs-lookup"><span data-stu-id="12877-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="12877-105">Todos os dados utilizados neste guia não são dados reais de clientes e fazem parte do conjunto de dados da Contoso encontrados no ambiente de *Demonstração* da sua Subscrição do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="12877-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="12877-106">Cenário</span><span class="sxs-lookup"><span data-stu-id="12877-106">Scenario</span></span>

<span data-ttu-id="12877-107">A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que vende através do seu site Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="12877-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="12877-108">O seu objetivo é saber quais os clientes que normalmente adquirem os seus produtos regularmente deixarão de ser clientes ativos nos próximos 60 dias.</span><span class="sxs-lookup"><span data-stu-id="12877-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="12877-109">Saber qual dos seus clientes os pode **abandonar** pode ajudá-los a poupar esforços de marketing, concentrando-se em mantê-los.</span><span class="sxs-lookup"><span data-stu-id="12877-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12877-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="12877-110">Prerequisites</span></span>

- <span data-ttu-id="12877-111">Pelo menos, [Permissões de contribuinte](permissions.md) no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="12877-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="12877-112">Recomendamos-lhe que implemente as seguintes etapas [num ambiente novo](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="12877-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="12877-113">Tarefa 1 - Ingerir dados</span><span class="sxs-lookup"><span data-stu-id="12877-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="12877-114">Rever os artigos [sobre ingestão de dados](data-sources.md) e [importar origens de dados utilizando conectores Power Query](connect-power-query.md) especificamente.</span><span class="sxs-lookup"><span data-stu-id="12877-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="12877-115">A seguinte informação pressupõe que está familiarizado com a ingestão de dados em geral.</span><span class="sxs-lookup"><span data-stu-id="12877-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="12877-116">Ingerir dados de clientes a partir da plataforma eCommerce</span><span class="sxs-lookup"><span data-stu-id="12877-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="12877-117">Criar uma origem de dados com o nome **eCommerce**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="12877-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="12877-118">Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="12877-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="12877-119">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="12877-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="12877-120">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="12877-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="12877-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="12877-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="12877-122">**CreatedOn**: Data/Hora/Zona</span><span class="sxs-lookup"><span data-stu-id="12877-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="12877-123">![Transformar data de nascimento em data](media/ecommerce-dob-date.PNG "transformar data de nascimento em data")</span><span class="sxs-lookup"><span data-stu-id="12877-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="12877-124">No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="12877-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="12877-125">Guardar a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="12877-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="12877-126">Ingerir dados de compra online</span><span class="sxs-lookup"><span data-stu-id="12877-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="12877-127">Acrescentar outro conjunto de dados à mesma origem de dados **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="12877-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="12877-128">Escolha novamente o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="12877-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="12877-129">Introduza o URL para dados de **Compras online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="12877-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="12877-130">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="12877-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="12877-131">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="12877-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="12877-132">**PurchasedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="12877-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="12877-133">**TotalPrice**: Moeda</span><span class="sxs-lookup"><span data-stu-id="12877-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="12877-134">No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="12877-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="12877-135">Guardar a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="12877-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="12877-136">Ingerir dados de clientes a partir do esquema de fidelidade</span><span class="sxs-lookup"><span data-stu-id="12877-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="12877-137">Criar uma origem de dados com o nome **LoyaltyScheme**, escolha a opção de importação, e selecione o conetor **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="12877-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="12877-138">Introduza o URL para contactos de eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="12877-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="12877-139">Ao editar os dados, selecione **Transformar** e depois **Usar primeira fila como cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="12877-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="12877-140">Atualizar o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="12877-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="12877-141">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="12877-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="12877-142">**RewardsPoints**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="12877-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="12877-143">**CreatedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="12877-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="12877-144">No campo **Nome** no painel da direita, altere o nome da sua origem de dados de **Consulta** para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="12877-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="12877-145">Guardar a origem dos dados.</span><span class="sxs-lookup"><span data-stu-id="12877-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="12877-146">Tarefa 2 - Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="12877-146">Task 2 - Data unification</span></span>

<span data-ttu-id="12877-147">Depois de ingerirmos os dados, iniciamos agora o processo **Mapear, Corresponder, Intercalar** para criar um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="12877-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="12877-148">Para mais informações, consulte [Unificação de dados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="12877-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="12877-149">Mapear</span><span class="sxs-lookup"><span data-stu-id="12877-149">Map</span></span>

1. <span data-ttu-id="12877-150">Depois de ingerir os dados, mapear os contactos desde os dados de eCommerce e Fidelidade até aos tipos de dados comuns.</span><span class="sxs-lookup"><span data-stu-id="12877-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="12877-151">Aceder a **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="12877-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="12877-152">Selecionar as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="12877-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar as origens de dados do comércio eletrónico e da fidelidade.":::

1. <span data-ttu-id="12877-154">Selecionar **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="12877-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificar LoyaltyId como a chave primária.":::

### <a name="match"></a><span data-ttu-id="12877-156">Corresponder</span><span class="sxs-lookup"><span data-stu-id="12877-156">Match</span></span>

1. <span data-ttu-id="12877-157">Aceda ao separador **Corresponder** e selecione **Definir encomenda**.</span><span class="sxs-lookup"><span data-stu-id="12877-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="12877-158">Na lista pendente **Primário**, escolha **eCommerceContacts : eCommerce** como a origem primária e inclua todos os registos.</span><span class="sxs-lookup"><span data-stu-id="12877-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="12877-159">Na lista pendente **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registos.</span><span class="sxs-lookup"><span data-stu-id="12877-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificar corresponder comércio eletrónico e fidelidade.":::

1. <span data-ttu-id="12877-161">Selecione **Criar uma nova regra**</span><span class="sxs-lookup"><span data-stu-id="12877-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="12877-162">Adicione a sua primeira condição usando FullName.</span><span class="sxs-lookup"><span data-stu-id="12877-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="12877-163">Para eCommerceContacts, selecione **FullName** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="12877-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="12877-164">Para loyCustomers, selecione **FullName** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="12877-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="12877-165">Selecione a lista pendente **Normalizar** e escolha **Tipo (Telefone, Nome, Morada, ...)**.</span><span class="sxs-lookup"><span data-stu-id="12877-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="12877-166">Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.</span><span class="sxs-lookup"><span data-stu-id="12877-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="12877-167">Introduzir o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="12877-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="12877-168">Acrescentar uma segunda condição para o endereço de correio eletrónico, selecionando **Adicionar condição**</span><span class="sxs-lookup"><span data-stu-id="12877-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="12877-169">Para a entidade eCommerceContacts, escolha **E-mail** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="12877-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="12877-170">Para a entidade loyCustomers, escolha **E-mail** na lista pendente.</span><span class="sxs-lookup"><span data-stu-id="12877-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="12877-171">Deixar em branco Normalizar.</span><span class="sxs-lookup"><span data-stu-id="12877-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="12877-172">Definir **Nível de precisão**: **Básico** e **Valor**: **Elevado**.</span><span class="sxs-lookup"><span data-stu-id="12877-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificar a regra de correspondência para nome e e-mail.":::

7. <span data-ttu-id="12877-174">Selecione **Guardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="12877-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="12877-175">Unir</span><span class="sxs-lookup"><span data-stu-id="12877-175">Merge</span></span>

1. <span data-ttu-id="12877-176">Aceda ao separador **Intercalar**.</span><span class="sxs-lookup"><span data-stu-id="12877-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="12877-177">No **ContactId** para a entidade **loyCustomers**, alterar o nome a apresentar para **ContactIdLOYALTY** para o diferenciar das outras IDs ingeridas.</span><span class="sxs-lookup"><span data-stu-id="12877-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid a partir de loyalty id.":::

1. <span data-ttu-id="12877-179">Selecione **Guardar** e **Executar** para iniciar o processo de intercalar.</span><span class="sxs-lookup"><span data-stu-id="12877-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="12877-180">Tarefa 3 - Configurar a predição de abandono da transação</span><span class="sxs-lookup"><span data-stu-id="12877-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="12877-181">Com os perfis unificados de clientes em vigor, podemos agora executar a predição de abandono da subscrição.</span><span class="sxs-lookup"><span data-stu-id="12877-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="12877-182">Para passos detalhados, ver o artigo [Predição de abandono da subscrição (pré-visualização)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="12877-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="12877-183">Vá a **Inteligência** > **Descobrir** e selecione para utilizar o **Modelo de abandono do cliente**.</span><span class="sxs-lookup"><span data-stu-id="12877-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="12877-184">Selecione a opção **Transacional** e selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="12877-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="12877-185">Dê um nome ao modelo **Predição de abandono de transação por comércio eletrónico OOB** e a entidade de saída **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="12877-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="12877-186">Definir duas condições para o modelo de abandono:</span><span class="sxs-lookup"><span data-stu-id="12877-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="12877-187">**Janela de predição**: **pelo menos 60** dias.</span><span class="sxs-lookup"><span data-stu-id="12877-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="12877-188">Esta definição estabelece até que ponto queremos prever o abandono dos clientes no futuro.</span><span class="sxs-lookup"><span data-stu-id="12877-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="12877-189">**Definição de abandono**: **pelo menos 60** dias.</span><span class="sxs-lookup"><span data-stu-id="12877-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="12877-190">A duração sem compras após a qual um cliente é considerado em abandono.</span><span class="sxs-lookup"><span data-stu-id="12877-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecionar as alavancas do modelo Janela de Predição e Definição de Abandono.":::

1. <span data-ttu-id="12877-192">Selecione **Histórico de Compras (obrigatório)** e selecione **Adicionar dados** para o histórico de compras.</span><span class="sxs-lookup"><span data-stu-id="12877-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="12877-193">Adicionar a entidade **eCommercePurchases : eCommerce** e mapear os campos desde o comércio eletrónico até aos campos correspondentes exigidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="12877-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="12877-194">Junte a entidade **eCommercePurchases : eCommerce** com **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="12877-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Junte-se às entidade de eCommerce.":::

1. <span data-ttu-id="12877-196">Selecione **Seguinte** para definir o agendar do modelo.</span><span class="sxs-lookup"><span data-stu-id="12877-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="12877-197">O modelo precisa de treinar regularmente para aprender novos padrões quando há novos dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="12877-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="12877-198">Para este exemplo, selecione **Mensalmente**.</span><span class="sxs-lookup"><span data-stu-id="12877-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="12877-199">Depois de rever todos os detalhes, selecione **Guardar e Executar**.</span><span class="sxs-lookup"><span data-stu-id="12877-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="12877-200">Tarefa 4 - Rever resultados do modelo e explicações</span><span class="sxs-lookup"><span data-stu-id="12877-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="12877-201">Deixe o modelo completar a formação e a pontuação dos dados.</span><span class="sxs-lookup"><span data-stu-id="12877-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="12877-202">Pode agora rever as explicações do modelo de abandono da subscrição.</span><span class="sxs-lookup"><span data-stu-id="12877-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="12877-203">Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="12877-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="12877-204">Tarefa 5 - Criar um segmento de clientes de alto risco de abandono</span><span class="sxs-lookup"><span data-stu-id="12877-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="12877-205">A execução do modelo de produção cria uma nova entidade que se pode ver em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="12877-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="12877-206">Pode criar um novo segmento com base na entidade criada pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="12877-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="12877-207">Aceda a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="12877-207">Go to **Segments**.</span></span> <span data-ttu-id="12877-208">Selecione **Novo** e escolha **Criar a partir de** > **Inteligência**.</span><span class="sxs-lookup"><span data-stu-id="12877-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Criar um segmento com a saída do modelo.":::

1. <span data-ttu-id="12877-210">Selecione o ponto final **OOBSubscriptionChurnPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="12877-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="12877-211">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="12877-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="12877-212">Operador: maior do que</span><span class="sxs-lookup"><span data-stu-id="12877-212">Operator: greater than</span></span>
   - <span data-ttu-id="12877-213">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="12877-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar um segmento de abandono de subscrição.":::

<span data-ttu-id="12877-215">Tem agora um segmento dinamicamente atualizado que identifica clientes com alto risco de abandono para este negócio de subscrições.</span><span class="sxs-lookup"><span data-stu-id="12877-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="12877-216">Para obter mais informações, veja [Criar e gerir segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="12877-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
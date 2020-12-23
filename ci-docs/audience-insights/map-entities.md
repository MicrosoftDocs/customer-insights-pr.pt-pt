---
title: Mapear entidades para unificação de dados
description: Mapear dados para criar perfis unificados de clientes.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406642"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="de6c7-103">Mapear entidades e atributos</span><span class="sxs-lookup"><span data-stu-id="de6c7-103">Map entities and attributes</span></span>

<span data-ttu-id="de6c7-104">**Mapa** é a primeira etapa no processo de unificação de dados de informações de audiência.</span><span class="sxs-lookup"><span data-stu-id="de6c7-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="de6c7-105">O mapeamento consiste em três fases:</span><span class="sxs-lookup"><span data-stu-id="de6c7-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="de6c7-106">*Seleção de Entidades*: identificar as entidades combináveis que levam a uma conjunto de dados com informações mais completas sobre os seus clientes.</span><span class="sxs-lookup"><span data-stu-id="de6c7-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="de6c7-107">*Seleção de atributos*: para cada entidade, identifique as colunas que pretende combinar e reconciliar nas fases de *correspondência* e *intercalação*.</span><span class="sxs-lookup"><span data-stu-id="de6c7-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="de6c7-108">Estas colunas chamam-se *Atributos*.</span><span class="sxs-lookup"><span data-stu-id="de6c7-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="de6c7-109">*Chave primária e seleção de tipo semântico*: para cada entidade, identifique um atributo que pretende definir como a chave primária para essa entidade e, para cada atributo, identifique um tipo semântico que melhor descreve esse atributo.</span><span class="sxs-lookup"><span data-stu-id="de6c7-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="de6c7-110">Para obter mais informações sobre o fluxo geral da unificação de dados, consulte [Unificar](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="de6c7-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="de6c7-111">Selecionar as primeiras entidades</span><span class="sxs-lookup"><span data-stu-id="de6c7-111">Select the first entities</span></span>

1. <span data-ttu-id="de6c7-112">Nas informações de audiência, vá a **Dados** > **Unificar** > **Mapa**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="de6c7-113">Inicie a fase de mapeamento ao selecionar **Selecionar entidades**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="de6c7-114">Selecione as entidades e atributos que pretende utilizar nas fases de *correspondência* e *união*.</span><span class="sxs-lookup"><span data-stu-id="de6c7-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="de6c7-115">Pode selecionar os atributos exigidos individualmente a partir de uma entidade ou incluir todos os atributos de uma entidade selecionando a caixa de verificação **Incluir todos os campos** ao nível da entidade.</span><span class="sxs-lookup"><span data-stu-id="de6c7-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="de6c7-116">Recomendamos que selecione pelo menos duas entidades para beneficiar do processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="de6c7-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de6c7-117">![Exemplo de Adicionar entidades](media/data-manager-configure-map-add-entities-example.png "Exemplo de Adicionar entidades")</span><span class="sxs-lookup"><span data-stu-id="de6c7-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="de6c7-118">Neste exemplo, estamos a adicionar as entidades **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="de6c7-119">Ao escolher estas entidades, pode obter informações sobre quais dos clientes de negócios online são membros do programa de fidelização.</span><span class="sxs-lookup"><span data-stu-id="de6c7-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="de6c7-120">Pode pesquisar palavras-chave em todos os atributos e entidades para selecionar os atributos necessários que pretende mapear.</span><span class="sxs-lookup"><span data-stu-id="de6c7-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de6c7-121">![Exemplo de campos de pesquisa](media/data-manager-configure-map-search-fields-example.png "Exemplo de campos de pesquisa")</span><span class="sxs-lookup"><span data-stu-id="de6c7-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="de6c7-122">Selecione **Aplicar** para confirmar as suas seleções.</span><span class="sxs-lookup"><span data-stu-id="de6c7-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="de6c7-123">Selecionar chave primária e tipo semântico para atributos</span><span class="sxs-lookup"><span data-stu-id="de6c7-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="de6c7-124">Depois de selecionar as suas entidades, a página **Mapa** lista as entidades selecionadas para a sua revisão.</span><span class="sxs-lookup"><span data-stu-id="de6c7-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="de6c7-125">Defina a chave primária para uma entidade e identifique o tipo semântico para um atributo na entidade.</span><span class="sxs-lookup"><span data-stu-id="de6c7-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="de6c7-126">**Chave primária**: selecione um atributo como chave primária para cada uma das entidades.</span><span class="sxs-lookup"><span data-stu-id="de6c7-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="de6c7-127">Para que um atributo seja uma chave primária válida, não deve incluir valores duplicados, valores em falta ou valores nulos.</span><span class="sxs-lookup"><span data-stu-id="de6c7-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="de6c7-128">Os atributos do tipo de dados cadeia, número inteiro e GUID são suportados como chaves primárias e serão exibidos num campo para selecionar.</span><span class="sxs-lookup"><span data-stu-id="de6c7-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="de6c7-129">**Tipo de atributo semântico**: categorias dos seus atributos, tais como endereço de e-mail ou nome.</span><span class="sxs-lookup"><span data-stu-id="de6c7-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="de6c7-130">Para utilizar modelos de IA para predição inteligente de semântica, poupar tempo e melhorar a precisão, defina **Mapeamento inteligente** para **ATIVADO**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="de6c7-131">O mapeamento inteligente destaca a recomendação de semântica baseada em IA no campo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="de6c7-132">Se o definir como **DESATIVADO**, verá as nossas recomendações regulares de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="de6c7-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="de6c7-133">Pode selecionar qualquer tipo semântico da lista de opções disponíveis e anular a seleção sugerida.</span><span class="sxs-lookup"><span data-stu-id="de6c7-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="de6c7-134">![Tipo de atributo e predição semântica](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo de atributo e predição semântica")</span><span class="sxs-lookup"><span data-stu-id="de6c7-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="de6c7-135">Também é possível adicionar um tipo semântico personalizado.</span><span class="sxs-lookup"><span data-stu-id="de6c7-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="de6c7-136">Selecione o campo de tipo para um atributo e escreva o nome do tipo semântico personalizado.</span><span class="sxs-lookup"><span data-stu-id="de6c7-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="de6c7-137">Desta forma, também pode alterar os tipos de atributo que foram identificados pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="de6c7-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="de6c7-138">Todos os atributos para os quais um tipo semântico é automaticamente identificado são agrupados na secção **Rever campos mapeados**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="de6c7-139">Reveja estes atributos e os seus tipos semânticos porque serão usados para combinar as suas entidades no passo de união da unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="de6c7-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="de6c7-140">Os atributos que não são automaticamente mapeados para um tipo semântico são agrupados na secção **Definir dados nos campos não mapeados**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="de6c7-141">Selecione o campo de tipo semântico para os atributos não mapeados ou introduza o seu nome de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="de6c7-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="de6c7-142">![Chave primária e tipo de atributo](media/data-manager-configure-map-add-attributes.png "Chave primária e tipo de atributo")</span><span class="sxs-lookup"><span data-stu-id="de6c7-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="de6c7-143">Um campo deve mapear para o tipo semântico Person.FullName para preencher o nome do cliente no cartão de cliente.</span><span class="sxs-lookup"><span data-stu-id="de6c7-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="de6c7-144">Caso contrário, os cartões do cliente serão apresentados sem nome.</span><span class="sxs-lookup"><span data-stu-id="de6c7-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="de6c7-145">Adicionar e remover atributos e entidades</span><span class="sxs-lookup"><span data-stu-id="de6c7-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="de6c7-146">Em **Unificar** > **Mapa**, selecione **Editar campos**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="de6c7-147">No painel **Editar campos**, adicione ou remova atributos e entidades.</span><span class="sxs-lookup"><span data-stu-id="de6c7-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="de6c7-148">Utilize a pesquisa ou percorra para encontrar e selecionar os seus atributos e entidades de interesse.</span><span class="sxs-lookup"><span data-stu-id="de6c7-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="de6c7-149">Não se pode remover um atributo ou uma entidade se já foram combinados.</span><span class="sxs-lookup"><span data-stu-id="de6c7-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de6c7-150">![Adicionar ou remover atributos](media/configure-data-map-edit.png "Adicionar ou remover atributos")</span><span class="sxs-lookup"><span data-stu-id="de6c7-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="de6c7-151">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="de6c7-152">Adicionar imagens a perfis</span><span class="sxs-lookup"><span data-stu-id="de6c7-152">Add images to profiles</span></span>

<span data-ttu-id="de6c7-153">Se uma entidade contiver URLs para logótipos ou imagens de perfil disponíveis publicamente, poderá adicioná-los ao perfil do cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="de6c7-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="de6c7-154">Selecione a entidade e localize o campo que contém o URL para a imagem de perfil.</span><span class="sxs-lookup"><span data-stu-id="de6c7-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="de6c7-155">No campo de texto **Tipo**, introduza manualmente o seguinte valor:</span><span class="sxs-lookup"><span data-stu-id="de6c7-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="de6c7-156">Para uma pessoa: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="de6c7-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="de6c7-157">Para uma organização: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="de6c7-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="de6c7-158">Continue com os passos de unificação e certifique-se de que o atributo que contém o URL de imagem também é adicionado no passo [Unir](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="de6c7-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="de6c7-159">Definir atributos para as organizações</span><span class="sxs-lookup"><span data-stu-id="de6c7-159">Set attributes for organizations</span></span>

<span data-ttu-id="de6c7-160">Para as organizações (Pré-visualização), o tipo de atributo deve ser mapeado para "Nome.Organização"</span><span class="sxs-lookup"><span data-stu-id="de6c7-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="de6c7-161">![Chave primária e tipo de atributo B2B](media/configure-data-map-edit-b2b.png "Chave primária e tipo de atributo B2B")</span><span class="sxs-lookup"><span data-stu-id="de6c7-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="de6c7-162">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="de6c7-162">Next step</span></span>

<span data-ttu-id="de6c7-163">Como parte do processo de unificação dos dados, vá para a página **Corresponder**.</span><span class="sxs-lookup"><span data-stu-id="de6c7-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="de6c7-164">Visite [**Corresponder**](match-entities.md) para saber mais sobre esta fase.</span><span class="sxs-lookup"><span data-stu-id="de6c7-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="de6c7-165">Veja o seguinte vídeo: [Introdução: Criar um Perfil de Cliente Unificado](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="de6c7-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>

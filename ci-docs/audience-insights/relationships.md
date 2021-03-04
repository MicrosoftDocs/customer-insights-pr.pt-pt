---
title: Relações entre entidades e caminhos de entidades
description: Criar e gerir relações entre entidades a partir de múltiplas origens de dados.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269895"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="02fd1-103">Relação entre entidades</span><span class="sxs-lookup"><span data-stu-id="02fd1-103">Relationships between entities</span></span>

<span data-ttu-id="02fd1-104">As relações ajudam a ligar entidades e a gerar um gráfico dos seus dados quando as entidades partilham um identificador comum (chave externa) que pode ser referenciado de uma entidade para outra.</span><span class="sxs-lookup"><span data-stu-id="02fd1-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="02fd1-105">As entidades ligadas permitem definir segmentos e medidas com base em várias origens de dados.</span><span class="sxs-lookup"><span data-stu-id="02fd1-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="02fd1-106">Existem dois tipos de relações.</span><span class="sxs-lookup"><span data-stu-id="02fd1-106">There are two types of relationships.</span></span> <span data-ttu-id="02fd1-107">As relações do sistema não editáveis, que são criadas automaticamente, e as relações personalizadas criadas e configuradas pelos utilizadores.</span><span class="sxs-lookup"><span data-stu-id="02fd1-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="02fd1-108">Durante os processos de correspondência e intercalação, as relações do sistema são criadas em segundo com base numa correspondência inteligente.</span><span class="sxs-lookup"><span data-stu-id="02fd1-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="02fd1-109">Estes relações ajudam a relacionar os registos do perfil de Cliente com outros registos de entidades correspondentes.</span><span class="sxs-lookup"><span data-stu-id="02fd1-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="02fd1-110">O diagrama seguinte ilustra a criação de três relações do sistema quando a entidade do cliente é correspondida com entidades adicionais para produzir a entidade de Perfil de Cliente final.</span><span class="sxs-lookup"><span data-stu-id="02fd1-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="02fd1-111">![Criação da relação](media/relationships-entities-merge.png "Criação da relação")</span><span class="sxs-lookup"><span data-stu-id="02fd1-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="02fd1-112">A **relação *CustomerToContact*** foi criada entre a entidade Cliente e a entidade Contacto.</span><span class="sxs-lookup"><span data-stu-id="02fd1-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="02fd1-113">A entidade Cliente obtém o campo de chave **Contact_contactId** para estabelecer relação com o campo de chave da entidade Contacto **contactId**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="02fd1-114">A **relação *CustomerToAccount*** foi criada entre a entidade Cliente e a entidade Conta.</span><span class="sxs-lookup"><span data-stu-id="02fd1-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="02fd1-115">A entidade Cliente obtém o campo de chave **Account_accountId** para estabelecer relação com o campo de chave da entidade Conta **accountId**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="02fd1-116">A **relação *CustomerToWebAccount*** foi criada entre a entidade Cliente e a entidade WebAccount.</span><span class="sxs-lookup"><span data-stu-id="02fd1-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="02fd1-117">A entidade Cliente obtém o campo de chave **WebAccount_webaccountId** para estabelecer relação com o campo de chave da entidade WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="02fd1-118">Criar uma relação</span><span class="sxs-lookup"><span data-stu-id="02fd1-118">Create a relationship</span></span>

<span data-ttu-id="02fd1-119">Defina relações personalizadas na página **Relações**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="02fd1-120">Cada relação consiste numa entidade Origem (a entidade que tem a chave externa) e uma Entidade de destino (a entidade para a qual a chave externa da entidade de origem aponta).</span><span class="sxs-lookup"><span data-stu-id="02fd1-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="02fd1-121">Nas informações de audiência, vá a **Dados** > **Relações**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="02fd1-122">Entidade de destino **Nova relação**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="02fd1-123">No painel **Adicionar relação**, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="02fd1-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="02fd1-124">![Introduzir detalhes da relação](media/relationships-add.png "Introduzir detalhes da relação")</span><span class="sxs-lookup"><span data-stu-id="02fd1-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="02fd1-125">**Nome da relação**: nome que reflete o objetivo da relação (por exemplo, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="02fd1-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="02fd1-126">**Descrição**: descrição da relação.</span><span class="sxs-lookup"><span data-stu-id="02fd1-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="02fd1-127">**Entidade de origem**: selecione a entidade que é utilizada como origem na relação (por exemplo, WebLog).</span><span class="sxs-lookup"><span data-stu-id="02fd1-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="02fd1-128">**Cardinalidade**: selecione a cardinalidade dos registos da entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="02fd1-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="02fd1-129">Por exemplo, "muitos" significa que vários registos do Weblog estão relacionados com uma WebAccount.</span><span class="sxs-lookup"><span data-stu-id="02fd1-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="02fd1-130">**Campo de chave de origem**: representa o campo de chave externa na entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="02fd1-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="02fd1-131">Por exemplo, o WebLog tem o campo de chave externa **accountId**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="02fd1-132">**Entidade de destino**: selecione a entidade que é utilizada como destino na relação (por exemplo, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="02fd1-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="02fd1-133">**Cardinalidade de destino**: selecione a cardinalidade dos registos da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="02fd1-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="02fd1-134">Por exemplo, "um" significa que vários registos do Weblog estão relacionados com uma WebAccount.</span><span class="sxs-lookup"><span data-stu-id="02fd1-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="02fd1-135">**Campo de chave de destino**: este campo representa o campo de chave da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="02fd1-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="02fd1-136">Por exemplo, WebAccount tem o campo de chave **accountId**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="02fd1-137">Só são suportadas relações muitos-para-um e um-para-um.</span><span class="sxs-lookup"><span data-stu-id="02fd1-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="02fd1-138">As relações muitos-para-muitos podem ser criadas através de duas relações muitos-para-um e uma entidade de ligação (uma entidade que é utilizada para ligar a entidade de origem e a entidade de destino).</span><span class="sxs-lookup"><span data-stu-id="02fd1-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="02fd1-139">Eliminar uma relação</span><span class="sxs-lookup"><span data-stu-id="02fd1-139">Delete a relationship</span></span>

1. <span data-ttu-id="02fd1-140">Nas informações de audiência, vá a **Dados** > **Relações**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="02fd1-141">Selecione as caixas de verificação para as relações que pretende eliminar.</span><span class="sxs-lookup"><span data-stu-id="02fd1-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="02fd1-142">Selecione **Eliminar** na parte superior da tabela **Relações**.</span><span class="sxs-lookup"><span data-stu-id="02fd1-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="02fd1-143">Confirme a eliminação.</span><span class="sxs-lookup"><span data-stu-id="02fd1-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="02fd1-144">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="02fd1-144">Next step</span></span>

<span data-ttu-id="02fd1-145">As relações do sistema e personalizadas são utilizadas para criar segmentos baseados em várias origens de dados que já não estão repartidas em silos.</span><span class="sxs-lookup"><span data-stu-id="02fd1-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="02fd1-146">Para mais informações, consulte [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="02fd1-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
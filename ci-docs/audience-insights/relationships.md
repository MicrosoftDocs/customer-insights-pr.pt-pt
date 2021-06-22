---
title: Relações entre entidades e caminhos de entidades
description: Criar e gerir relações entre entidades a partir de múltiplas origens de dados.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171178"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="be8bd-103">Relação entre entidades</span><span class="sxs-lookup"><span data-stu-id="be8bd-103">Relationships between entities</span></span>

<span data-ttu-id="be8bd-104">As relações ligam entidades e definem um gráfico dos seus dados quando as entidades partilham um identificador comum, uma chave externa.</span><span class="sxs-lookup"><span data-stu-id="be8bd-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="be8bd-105">Esta chave externa pode ser referenciada de uma entidade para outra.</span><span class="sxs-lookup"><span data-stu-id="be8bd-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="be8bd-106">As entidades ligadas permitem a definição de segmentos e medidas com base em várias origens de dados.</span><span class="sxs-lookup"><span data-stu-id="be8bd-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="be8bd-107">Existem três tipos de relações:</span><span class="sxs-lookup"><span data-stu-id="be8bd-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="be8bd-108">Relações de sistema não editáveis, criadas pelo sistema como parte do processo de unificação de dados</span><span class="sxs-lookup"><span data-stu-id="be8bd-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="be8bd-109">Relações herdados não editáveis, que são criadas automaticamente a partir da ingestão de origens de dados</span><span class="sxs-lookup"><span data-stu-id="be8bd-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="be8bd-110">Relações personalizadas editáveis, criadas e configuradas pelos utilizadores</span><span class="sxs-lookup"><span data-stu-id="be8bd-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="be8bd-111">Relações de sistema não editáveis</span><span class="sxs-lookup"><span data-stu-id="be8bd-111">Non-editable system relationships</span></span>

<span data-ttu-id="be8bd-112">Durante a unificação de dados, as relações de sistema são criadas automaticamente com base em correspondência inteligente.</span><span class="sxs-lookup"><span data-stu-id="be8bd-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="be8bd-113">Estas relações ajudam a relacionar os registos do perfil de cliente com outros registos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="be8bd-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="be8bd-114">O diagrama que se segue ilustra a criação de três relações baseados em sistema.</span><span class="sxs-lookup"><span data-stu-id="be8bd-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="be8bd-115">A entidade de cliente é compatível com outras entidades para produzir a entidade unificada de *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="be8bd-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama com caminhos de relação para a entidade de cliente com três relações 1-n.":::

- <span data-ttu-id="be8bd-117">A **relação *CustomerToContact*** foi criada entre a entidade *Cliente* e a entidade *Contacto*.</span><span class="sxs-lookup"><span data-stu-id="be8bd-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="be8bd-118">A entidade *Cliente* obtém o campo de chave **Contact_contactID** para estabelecer relação com o campo de chave da entidade *Contacto* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="be8bd-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="be8bd-119">A **relação *CustomerToAccount*** foi criada entre a entidade *Cliente* e a entidade *Conta*.</span><span class="sxs-lookup"><span data-stu-id="be8bd-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="be8bd-120">A entidade *Cliente* obtém o campo de chave **Account_accountID** para estabelecer relação com o campo de chave da entidade *Conta* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="be8bd-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="be8bd-121">A **relação *CustomerToWebAccount*** foi criada entre a entidade *Cliente* e a entidade *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="be8bd-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="be8bd-122">A entidade *Cliente* obtém o campo de chave **WebAccount_webaccountID** para estabelecer relação com o campo de chave da entidade *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="be8bd-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="be8bd-123">Relações herdadas não editáveis</span><span class="sxs-lookup"><span data-stu-id="be8bd-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="be8bd-124">Durante o processo de ingestão de dados, o sistema verifica as origens de dados para relações existentes.</span><span class="sxs-lookup"><span data-stu-id="be8bd-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="be8bd-125">Se não existe qualquer relação, o sistema cria-as automaticamente.</span><span class="sxs-lookup"><span data-stu-id="be8bd-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="be8bd-126">Estas relações também são utilizadas em processos a jusante.</span><span class="sxs-lookup"><span data-stu-id="be8bd-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="be8bd-127">Criar uma relação personalizada</span><span class="sxs-lookup"><span data-stu-id="be8bd-127">Create a custom relationship</span></span>

<span data-ttu-id="be8bd-128">A relação consiste numa *entidade fornecida com o programa* que contém a chave externa e uma *entidade de destino* a que a entidade fornecida com o programa aponta.</span><span class="sxs-lookup"><span data-stu-id="be8bd-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="be8bd-129">Nas informações de audiência, vá a **Dados** > **Relações**.</span><span class="sxs-lookup"><span data-stu-id="be8bd-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="be8bd-130">Entidade de destino **Nova relação**.</span><span class="sxs-lookup"><span data-stu-id="be8bd-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="be8bd-131">No painel **Nova relação**, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="be8bd-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Painel lateral de nova relação com campos de entrada vazios.":::

   - <span data-ttu-id="be8bd-133">**Nome da relação**: nome que reflete o propósito da relação.</span><span class="sxs-lookup"><span data-stu-id="be8bd-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="be8bd-134">Exemplo: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="be8bd-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="be8bd-135">**Descrição**: descrição da relação.</span><span class="sxs-lookup"><span data-stu-id="be8bd-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="be8bd-136">**Entidade fornecida com o programa**: entidade que é utilizada como origem na relação.</span><span class="sxs-lookup"><span data-stu-id="be8bd-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="be8bd-137">Exemplo: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="be8bd-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="be8bd-138">**Entidade de destino**: entidade que é utilizada como destino na relação.</span><span class="sxs-lookup"><span data-stu-id="be8bd-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="be8bd-139">Exemplo: Customer.</span><span class="sxs-lookup"><span data-stu-id="be8bd-139">Example: Customer.</span></span>
   - <span data-ttu-id="be8bd-140">**Cardinalidade fornecida com o programa**: especifique a cardinalidade da entidade fornecida com o programa.</span><span class="sxs-lookup"><span data-stu-id="be8bd-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="be8bd-141">Cardinalidade descreve o número de elementos possíveis num conjunto.</span><span class="sxs-lookup"><span data-stu-id="be8bd-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="be8bd-142">Está sempre relacionado com a cardinalidade de destino.</span><span class="sxs-lookup"><span data-stu-id="be8bd-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="be8bd-143">Pode escolher entre **Um** e **Muitos**.</span><span class="sxs-lookup"><span data-stu-id="be8bd-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="be8bd-144">Só são suportadas relações muitos-para-um e um-para-um.</span><span class="sxs-lookup"><span data-stu-id="be8bd-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="be8bd-145">Muitos-para-um: vários registos fornecidos com o programa podem relacionar-se com um registo de destino.</span><span class="sxs-lookup"><span data-stu-id="be8bd-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="be8bd-146">Exemplo: vários casos de suporte de um único cliente.</span><span class="sxs-lookup"><span data-stu-id="be8bd-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="be8bd-147">Um-para-um: um único registo fornecido com o programa relaciona-se com um registo de destino.</span><span class="sxs-lookup"><span data-stu-id="be8bd-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="be8bd-148">Exemplo: um ID de fidelização para um único cliente.</span><span class="sxs-lookup"><span data-stu-id="be8bd-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="be8bd-149">É possível criar relações muitos-para-muitos utilizando duas relações muitos-para-um e uma entidade de ligação, a qual liga a entidade fornecida com o programa e a entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="be8bd-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="be8bd-150">**Cardinalidade de destino**: selecione a cardinalidade dos registos da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="be8bd-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="be8bd-151">**Campo de chave fornecida com o programa**: o campo de chave externa na entidade fornecida com o programa.</span><span class="sxs-lookup"><span data-stu-id="be8bd-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="be8bd-152">Exemplo: SupportCase poderia utilizar CaseID como um campo de chave externa.</span><span class="sxs-lookup"><span data-stu-id="be8bd-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="be8bd-153">**Campo de chave de destino**: o campo de chave da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="be8bd-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="be8bd-154">Exemplo que o Cliente poderia utilizar o campo de chave **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="be8bd-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="be8bd-155">Selecione **Guardar** para criar a relação personalizada.</span><span class="sxs-lookup"><span data-stu-id="be8bd-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="be8bd-156">Ver relações</span><span class="sxs-lookup"><span data-stu-id="be8bd-156">View relationships</span></span>

<span data-ttu-id="be8bd-157">A página Relações lista todas as relações que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="be8bd-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="be8bd-158">Cada linha representa uma relação, que inclui também detalhes sobre a entidade fornecida com o programa, a entidade de destino e a cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="be8bd-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de relações e opções na barra de ação da página Relações.":::

<span data-ttu-id="be8bd-160">Esta página oferece um conjunto de opções para relações existentes e novas:</span><span class="sxs-lookup"><span data-stu-id="be8bd-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="be8bd-161">**Nova Relação**: [Criar uma relação personalizada](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="be8bd-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="be8bd-162">**Visualizador**: [Explore o visualizador de relações](#explore-the-relationship-visualizer) para ver um diagrama de rede de relações existentes e respetiva cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="be8bd-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="be8bd-163">**Filtrar por**: escolha o tipo de relações a apresentar na lista.</span><span class="sxs-lookup"><span data-stu-id="be8bd-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="be8bd-164">**Pesquisar relações**: utilize uma pesquisa baseada em texto sobre as propriedades das relações.</span><span class="sxs-lookup"><span data-stu-id="be8bd-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="be8bd-165">Explore o visualizador de relações</span><span class="sxs-lookup"><span data-stu-id="be8bd-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="be8bd-166">O visualizador de relações mostra um diagrama de rede de relações existentes entre as entidades ligadas e a respetiva cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="be8bd-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="be8bd-167">Para personalizar a vista, pode alterar a posição das caixas arrastando-as na tela.</span><span class="sxs-lookup"><span data-stu-id="be8bd-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de ecrã do diagrama de rede do visualizador de relações com ligações entre entidades relacionadas.":::

<span data-ttu-id="be8bd-169">Opções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="be8bd-169">Available options:</span></span> 
- <span data-ttu-id="be8bd-170">**Exportar como imagem**: guarde a vista atual como um ficheiro de imagem.</span><span class="sxs-lookup"><span data-stu-id="be8bd-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="be8bd-171">**Alterar para esquema horizontal/vertical**: altere o alinhamento das entidades e relações.</span><span class="sxs-lookup"><span data-stu-id="be8bd-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="be8bd-172">**Editar**: atualize as propriedades de relações personalizadas no painel de edição e guarde as alterações.</span><span class="sxs-lookup"><span data-stu-id="be8bd-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="be8bd-173">Gerir relações existentes</span><span class="sxs-lookup"><span data-stu-id="be8bd-173">Manage existing relationships</span></span> 

<span data-ttu-id="be8bd-174">Na página Relações, cada relação é representada por uma linha.</span><span class="sxs-lookup"><span data-stu-id="be8bd-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="be8bd-175">Selecione uma relação e escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="be8bd-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="be8bd-176">**Editar**: atualize as propriedades de relações personalizadas no painel de edição e guarde as alterações.</span><span class="sxs-lookup"><span data-stu-id="be8bd-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="be8bd-177">**Eliminar**: elimine relações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="be8bd-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="be8bd-178">**Ver**: veja relações criadas pelo sistema e herdadas.</span><span class="sxs-lookup"><span data-stu-id="be8bd-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="be8bd-179">Passo seguinte</span><span class="sxs-lookup"><span data-stu-id="be8bd-179">Next step</span></span>

<span data-ttu-id="be8bd-180">As relações do sistema e personalizadas são utilizadas para [criar segmentos](segments.md) baseados em várias origens de dados que já não estão repartidas em silos.</span><span class="sxs-lookup"><span data-stu-id="be8bd-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

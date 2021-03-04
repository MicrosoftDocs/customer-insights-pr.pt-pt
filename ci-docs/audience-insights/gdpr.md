---
title: Pedidos de Direitos de Titulares de Dados (DSR) ao abrigo do RGPD | Microsoft Docs
description: Responder a Pedidos de Titulares de Dados para a capacidade de insights de audiência do Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268700"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="03de2-103">Os pedidos de Direitos de Titulares de Dados (DSR) são pedidos sob RGPD</span><span class="sxs-lookup"><span data-stu-id="03de2-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="03de2-104">Responder ao titular dos dados RGPD elimina os pedidos para a capacidade de insights de audiência do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="03de2-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="03de2-105">O "direito de eliminação" através da remoção de dados pessoais dos dados de cliente de uma organização é uma proteção-chave no Regulamento Geral sobre a Proteção de Dados (RGPD).</span><span class="sxs-lookup"><span data-stu-id="03de2-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="03de2-106">A remoção de dados pessoais inclui a remoção de todos os dados pessoais e registos gerados pelo sistema, exceto as informações de registo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="03de2-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="03de2-107">Gerir pedidos de eliminação do titular de dados</span><span class="sxs-lookup"><span data-stu-id="03de2-107">Manage data subject delete requests</span></span>

<span data-ttu-id="03de2-108">Os insights de audiência oferecem as seguintes experiências no produto para eliminar dados pessoais para um cliente específico ou um utilizador:</span><span class="sxs-lookup"><span data-stu-id="03de2-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="03de2-109">**Gerir pedidos de eliminação de dados de clientes**: os dados dos clientes no Customer Insights são ingeridos a partir das origens de dados originais externas ao Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="03de2-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="03de2-110">Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados na origem de dados original.</span><span class="sxs-lookup"><span data-stu-id="03de2-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="03de2-111">**Gerir pedidos de eliminação de dados de utilizador do Customer Insights**: Os dados para os utilizadores são criados pela Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="03de2-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="03de2-112">Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="03de2-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="03de2-113">Gerir pedidos de eliminação de dados dos clientes</span><span class="sxs-lookup"><span data-stu-id="03de2-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="03de2-114">Um administrador do Customer Insights pode seguir estes passos para remover os dados do cliente que foram eliminados na origem de dados:</span><span class="sxs-lookup"><span data-stu-id="03de2-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="03de2-115">Iniciar sessão no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="03de2-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="03de2-116">Nas informações de audiência, vá a **Dados** > **Origens de dados**</span><span class="sxs-lookup"><span data-stu-id="03de2-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="03de2-117">Para cada origem de dados na lista que contém dados de clientes eliminados:</span><span class="sxs-lookup"><span data-stu-id="03de2-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="03de2-118">Seleccione (...) e, em seguida, selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="03de2-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="03de2-119">Verifique o estado da origem de dados em **Estado**.</span><span class="sxs-lookup"><span data-stu-id="03de2-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="03de2-120">Uma marca de verificação significa que a atualização foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="03de2-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="03de2-121">Um triângulo de aviso significa que algo correu mal.</span><span class="sxs-lookup"><span data-stu-id="03de2-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="03de2-122">Se for apresentado um triângulo de aviso, contacte D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="03de2-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="03de2-123">![Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD](media/gdpr-data-sources.png "Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD")</span><span class="sxs-lookup"><span data-stu-id="03de2-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="03de2-124">Gerir pedidos de eliminação de dados do utilizador</span><span class="sxs-lookup"><span data-stu-id="03de2-124">Manage delete requests for user data</span></span>

<span data-ttu-id="03de2-125">Um administrador do Customer Insights pode seguir estes passos para eliminar dados dos utilizadores do Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="03de2-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="03de2-126">Iniciar sessão no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="03de2-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="03de2-127">Nos insights de audiência, vá a **Admin** > **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="03de2-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="03de2-128">Selecione a caixa de verificação para o utilizador que pretende eliminar.</span><span class="sxs-lookup"><span data-stu-id="03de2-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="03de2-129">Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="03de2-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="03de2-130">![Tratamento dos pedidos de eliminação de dados do utilizador da RGPD](media/gdpr-permissions.png "Tratamento dos pedidos de eliminação de dados do utilizador da RGPD ")</span><span class="sxs-lookup"><span data-stu-id="03de2-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="03de2-131">Responder aos pedidos de exportação dos titulares de dados RGPD</span><span class="sxs-lookup"><span data-stu-id="03de2-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="03de2-132">Como parte do nosso compromisso de parceria consigo no seu percurso para o Regulamento Geral sobre a Proteção de Dados (RGPD), desenvolvemos documentação para o ajudar a preparar-se.</span><span class="sxs-lookup"><span data-stu-id="03de2-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="03de2-133">Esta documentação descreve as medidas que pode tomar hoje para apoiar o cumprimento do RGPD ao utilizar os insights da audiência.</span><span class="sxs-lookup"><span data-stu-id="03de2-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="03de2-134">Gerir pedidos de exportação e visualização</span><span class="sxs-lookup"><span data-stu-id="03de2-134">Manage export and view requests</span></span>

<span data-ttu-id="03de2-135">O direito da portabilidade de dados permite aos titulares de dados solicitar uma cópia dos respetivos dados pessoais num formato eletrónico (um "formato estruturado, de utilização comum, de leitura de máquina e interoperável") que poderá ser transmitido para outro controlador de dados.</span><span class="sxs-lookup"><span data-stu-id="03de2-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="03de2-136">Exportar dados de clientes (administração de inquilinos)</span><span class="sxs-lookup"><span data-stu-id="03de2-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="03de2-137">Um administrador pode seguir estes passos para exportar dados:</span><span class="sxs-lookup"><span data-stu-id="03de2-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="03de2-138">Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do cliente no pedido.</span><span class="sxs-lookup"><span data-stu-id="03de2-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="03de2-139">A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.</span><span class="sxs-lookup"><span data-stu-id="03de2-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="03de2-140">Aceite a confirmação para exportar os dados para o cliente pedido.</span><span class="sxs-lookup"><span data-stu-id="03de2-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="03de2-141">Receba os dados exportados através do endereço de e-mail do administrador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="03de2-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="03de2-142">Exportar dados do utilizador (administração de inquilinos)</span><span class="sxs-lookup"><span data-stu-id="03de2-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="03de2-143">Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do utilizador no pedido.</span><span class="sxs-lookup"><span data-stu-id="03de2-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="03de2-144">A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.</span><span class="sxs-lookup"><span data-stu-id="03de2-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="03de2-145">Aceite a confirmação para exportar os dados para o utilizador pedido.</span><span class="sxs-lookup"><span data-stu-id="03de2-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="03de2-146">Receba os dados exportados através do endereço de e-mail do administrador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="03de2-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
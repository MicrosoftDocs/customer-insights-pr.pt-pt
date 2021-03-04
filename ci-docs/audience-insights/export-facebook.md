---
title: Exportar dados Customer Insights para o Facebook Ads Manager
description: Saiba como configurar a ligação ao Gestor de Anúncios do Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269988"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="abe12-103">Conector para o Gestor de Anúncios do Facebook (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="abe12-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="abe12-104">Exportar segmentos de perfis de cliente unificados para o Gestor de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.</span><span class="sxs-lookup"><span data-stu-id="abe12-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abe12-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="abe12-105">Prerequisites</span></span>

- <span data-ttu-id="abe12-106">Precisa de ter uma [**Conta de Anúncio do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclua uma [**Conta Comercial do Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="abe12-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="abe12-107">Tem de ser um administrador na [**Conta De Anúncio do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="abe12-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="abe12-108">Ligar ao Gestor de Anúncios do Facebook</span><span class="sxs-lookup"><span data-stu-id="abe12-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="abe12-109">Aceda a **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="abe12-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="abe12-110">Em **Gestor de Anúncios do Facebook**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="abe12-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="abe12-111">Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.</span><span class="sxs-lookup"><span data-stu-id="abe12-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="abe12-112">Selecione **Continuar com o Facebook** para iniciar sessão na sua Conta de Anúncio do Facebook.</span><span class="sxs-lookup"><span data-stu-id="abe12-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="abe12-113">Permitir a permissão **ads_management** após autenticação com o Facebook.</span><span class="sxs-lookup"><span data-stu-id="abe12-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="abe12-114">Selecione a **Conta de Anúncios do Facebook** com que pretende trabalhar.</span><span class="sxs-lookup"><span data-stu-id="abe12-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="abe12-115">Selecione uma **Audiência personalizada existente** na lista pendente ou crie uma **Nova audiência personalizada**.</span><span class="sxs-lookup"><span data-stu-id="abe12-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="abe12-116">Para mais informações, consulte [**Audiências no Gestor de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="abe12-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="abe12-117">Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="abe12-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="abe12-118">Selecione **Seguinte** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="abe12-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="abe12-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="abe12-119">Configure the connector</span></span>

1. <span data-ttu-id="abe12-120">Em **Escolher o campo de identificador de chave**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o Gestor de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="abe12-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="abe12-121">Mapeie os atributos correspondentes da entidade de cliente unificada para o identificador-chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="abe12-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="abe12-122">[DICA] As melhores hipóteses para que uma correspondência ocorra é se selecionar **E-mail** como identificador de chave.</span><span class="sxs-lookup"><span data-stu-id="abe12-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="abe12-123">A adição de identificadores adicionais pode melhorar a correspondência.</span><span class="sxs-lookup"><span data-stu-id="abe12-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="abe12-124">Selecione **Adicionar atributo** para mapear atributos adicionais para enviar para o Gestor de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="abe12-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="abe12-125">Atributos do Gestor de Anúncios do Facebook estão a mapear para os seguintes nomes amigáveis de utilizador: **NP** = **Nome Próprio**, **AP** = **Apelido**, **PI** = **Primeira Inicial**, **TELEFONE** = **Telefone**, **SEX** = **Sexo**, **DN** = **Data de nascimento**, **EST** = **Estado**, **CD** = **Cidade**, **CP** = **Código postal**, **PAÍS** = **País / Região**</span><span class="sxs-lookup"><span data-stu-id="abe12-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="abe12-126">Selecione os segmentos que quer exportar.</span><span class="sxs-lookup"><span data-stu-id="abe12-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="abe12-127">Selecione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="abe12-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="abe12-128">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="abe12-128">Export the data</span></span>

<span data-ttu-id="abe12-129">Pode [exportar dados a pedido](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="abe12-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="abe12-130">A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="abe12-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="abe12-131">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="abe12-131">Known limitations</span></span>

- <span data-ttu-id="abe12-132">Até 10 milhões de perfis de clientes por exportação para o Gestor de Anúncios do Facebook</span><span class="sxs-lookup"><span data-stu-id="abe12-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="abe12-133">A exportação para o Gestor de Anúncios do Facebook está limitada a segmentos</span><span class="sxs-lookup"><span data-stu-id="abe12-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="abe12-134">Exportar segmentos com um total de 10 milhões de perfis podem levar até 90 minutos para completar</span><span class="sxs-lookup"><span data-stu-id="abe12-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="abe12-135">Privacidade e conformidade de dados</span><span class="sxs-lookup"><span data-stu-id="abe12-135">Data privacy and compliance</span></span>

<span data-ttu-id="abe12-136">Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Gestor de Anúncios do Facebook, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="abe12-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="abe12-137">A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que os Anúncios do Facebook cumprem quaisquer obrigações de privacidade ou segurança que possa ter.</span><span class="sxs-lookup"><span data-stu-id="abe12-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="abe12-138">Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="abe12-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="abe12-139">O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="abe12-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
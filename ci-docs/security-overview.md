---
title: Definições de segurança no Customer Insights
description: Mais informações sobre definições de segurança no Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947429"
---
# <a name="security-settings-in-customer-insights"></a>Definições de segurança no Customer Insights

A página **Segurança** lista opções para configurar permissões de utilizador e funcionalidades que ajudam a tornar o Dynamics 365 Customer Insights mais seguro. Só os administradores podem aceder a esta página.

Aceda a **Admin** > **Segurança** para configurar as definições.

A página **Segurança** inclui os seguintes separadores:

- [Utilizadores](#users-tab)
- [APIs](#apis-tab)
- [Ligações Privadas](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Aceder com segurança aos dados dos clientes com o Sistema de Proteção de Dados do Cliente (Pré-visualização)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Separador Utilizadores

O acesso ao Customer Insights está restrito a utilizadores da sua organização que foram adicionados à aplicação por um admin. O separador **Utilizadores** permite-lhe gerir o acesso de utilizador e as respetivas permissões. Para obter mais informações, consulte [Permissões de utilizador](permissions.md).

## <a name="apis-tab"></a>Separador APIs

Ver e gerir as chaves a utilizar as [APIs do Customer Insights](apis.md) com os dados do seu ambiente.

Pode criar novas chaves primárias e secundárias selecionando **Regenerar primária** ou **Regenerar secundária**. 

Para bloquear o acesso da API ao ambiente, selecione **Desativar**. Se as APIs estiverem desativadas, pode selecionar **Ativar** para conceder acesso novamente.

## <a name="private-links-tab"></a>Separador Ligações Privadas

O [Azure Private Link](/azure/private-link/private-link-overview) permite ao Customer Insights ligar à sua conta do Azure Data Lake Storage por um ponto final privado na sua rede virtual. Para dados numa conta de armazenamento, que não esteja exposta à Internet pública, a Private Link permite a ligação a essa rede restrita.

> [!IMPORTANT]
> Requisito de função mínimo para configurar uma ligação à Private Link:
>
> - Customer Insights: administrador
> - Função incorporada do Azure: [Contribuidor da Conta de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permissões para a função personalizada do Azure: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

A configuração da Private Link no Customer Insights é um processo de dois passos. Em primeiro lugar, inicia a criação de uma Private Link a partir de **Admin** > **Segurança** > **Ligações Privadas** no Customer Insights. O painel **Adicionar Private Link** lista contas de armazenamento do seu inquilino que tem permissões para ver. Selecione a conta de armazenamento e forneça o consentimento para a criação da Private Link.

Em seguida, tem de aprovar a Private Link no lado da conta do Data Lake Storage. Abra a ligação apresentada no ecrã para aprovar a nova Private Link.

## <a name="key-vault-tab"></a>Separador Key Vault

O separador **Key Vault** permite-lhe ligar e gerir o seu próprio [Azure Key Vault](/azure/key-vault/general/basic-concepts) ao ambiente.
O cofre de chaves dedicado pode ser utilizado para preparar e utilizar segredos no limiar de conformidade de uma organização. O Customer Insights pode utilizar os segredos no Azure Key Vault para [configurar as ligações](connections.md) aos sistemas de terceiros.

Para mais informações, consulte [Trazer o seu próprio Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Aceder com segurança aos dados dos clientes com o Sistema de Proteção de Dados do Cliente (Pré-visualização)

O Customer Insights está a utilizar a capacidade de Sistema de Proteção de Dados do Cliente do Power Platform. O Sistema de Proteção de Dados do Cliente fornece uma interface para rever e aprovar (ou rejeitar) pedidos de acesso a dados. Estes pedidos ocorrem quando o acesso aos dados de clientes é necessário para resolver um caso de suporte. Para utilizar esta caraterística, o Customer Insights têm de ter uma ligação existente a um ambiente do Microsoft Dataverse no inquilino.

Para mais informações sobre o Sistema de Proteção de Dados do Cliente, consulte o [resumo](/power-platform/admin/about-lockbox#summary) de Sistema de Proteção de Dados do Cliente do Power Platform. O artigo também descreve o [fluxo de trabalho](/power-platform/admin/about-lockbox#workflow) e a [configuração](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) necessária para ativar o Sistema de Proteção de Dados do Cliente.

> [!IMPORTANT]
> Os administradores globais para o Power Platform ou os administradores do Power Platform podem aprovar pedidos do Sistema de Proteção de Dados do Cliente emitidos para o Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]

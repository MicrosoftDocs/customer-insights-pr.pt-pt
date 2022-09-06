---
title: Configurar definições de segurança
description: Mais informações sobre definições de segurança no Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387263"
---
# <a name="configure-security-settings"></a>Configurar definições de segurança

Gerir chaves da API, aceder aos dados de clientes e configurar um Azure Private Link.

## <a name="manage-api-keys"></a>Gerir chaves de API

Ver e gerir as chaves a utilizar as [APIs do Customer Insights](apis.md) com os dados no seu ambiente.

1. Aceda a **Admin** > **Segurança** e selecione o separador **API**.

1. Se o acesso da API ao ambiente não tiver sido configurado, selecione **Ativar**. Ou, para bloquear o acesso da API ao ambiente, selecione **Desativar** e confirme.

1. Gerir as chaves de API primárias e secundárias:

   1. Para mostrar a chave da API primária ou secundária, selecione o símbolo **Mostrar**.

   1. Para copiar a chave de API primária ou secundária, selecione o símbolo **Copiar**.

   1. Para criar novas chaves de API primárias e secundárias, selecione **Regenerar primária** ou **Regenerar secundária**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Aceder com segurança aos dados dos clientes com o Sistema de Proteção de Dados do Cliente (Pré-visualização)

O Customer Insights utiliza a capacidade de Sistema de Proteção de Dados do Cliente do Power Platform. O Sistema de Proteção de Dados do Cliente fornece uma interface para rever e aprovar (ou rejeitar) pedidos de acesso a dados. Estes pedidos ocorrem quando o acesso aos dados de clientes é necessário para resolver um caso de suporte. Para utilizar esta caraterística, o Customer Insights têm de ter uma ligação existente a um ambiente do Microsoft Dataverse no inquilino.

Para mais informações sobre o Sistema de Proteção de Dados do Cliente, consulte o [resumo](/power-platform/admin/about-lockbox#summary) de Sistema de Proteção de Dados do Cliente do Power Platform. O artigo também descreve o [fluxo de trabalho](/power-platform/admin/about-lockbox#workflow) e a [configuração](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) necessária para ativar o Sistema de Proteção de Dados do Cliente.

> [!IMPORTANT]
> Os administradores globais para o Power Platform ou os administradores do Power Platform podem aprovar pedidos do Sistema de Proteção de Dados do Cliente emitidos para o Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Configurar um Azure Private Link

O [Azure Private Link](/azure/private-link/private-link-overview) permite ao Customer Insights ligar à sua conta do Azure Data Lake Storage por um ponto final privado na sua rede virtual. Para dados numa conta de armazenamento, que não esteja exposta à Internet pública, a Private Link permite a ligação a essa rede restrita.

> [!IMPORTANT]
> Requisito de função mínimo para configurar uma ligação à Private Link:
>
> - Customer Insights: administrador
> - Função incorporada do Azure: [Contribuidor da Conta de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permissões para a função personalizada do Azure: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. No Customer Insights, vá para **Administrador** > **Segurança** e selecione o separador **Ligações Privadas**.

1. Selecione **Adicionar Ligação Privada**.

   O painel **Adicionar Private Link** lista contas de armazenamento do seu inquilino que tem permissões para ver.

1. Selecione a subscrição, grupo de recursos e conta de armazenamento.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar**.

1. Vá para a sua conta Data Lake Storage e abra a ligação apresentada no ecrã.

1. Aprove a Ligação Privada.


[!INCLUDE [footer-include](includes/footer-banner.md)]

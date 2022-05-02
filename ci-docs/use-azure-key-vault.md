---
title: Traga o seu próprio Azure Key Vault para gerir segredos
description: Aprenda a configurar o Customer Insights para utilizar o seu próprio Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 9eb06a1190fe4e8012ecd3d6742b8b3f5f4d6349
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653491"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Trazer o seu próprio Azure Key Vault (pré-visualização)

A ligação de um [Azure Key Vault](/azure/key-vault/general/basic-concepts) dedicado a um ambiente do Customer Insights ajuda as organizações a cumprir os requisitos de conformidade.
O cofre de chaves dedicado pode ser utilizado para preparar e utilizar segredos no limiar de conformidade de uma organização. O Customer Insights pode utilizar os segredos no Azure Key Vault para [configurar as ligações](connections.md) aos sistemas de terceiros.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Ligue o cofre de chaves ao ambiente do Customer Insights

### <a name="prerequisites"></a>Pré-requisitos

Para configurar o cofre de chaves no Customer Insights, devem ser cumpridos os seguintes pré-requisitos:

- Tem uma subscrição ativa do Azure.

- Tem uma função de [Administrador](permissions.md#admin) no Customer Insights. Saiba mais sobre [as permissões de utilizador no Customer Insights](permissions.md#assign-roles-and-permissions).

- Tem as funções de [Contribuidor](/azure/role-based-access-control/built-in-roles#contributor) e de [Administrador de Acesso ao Utilizador](/azure/role-based-access-control/built-in-roles#user-access-administrator) no cofre de chaves ou no grupo de recursos ao qual o cofre de chaves pertence. Para obter mais informações, aceda a [Adicionar ou remova atribuições de funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal). Se não tiver a função de Administrador de Acesso ao Utilizador no cofre de chaves, tem de configurar as permissões de controlo de acesso baseado em funções para o principal de serviço do Azure para o Dynamics 365 Customer Insights em separado. Siga os passos para [utilizar um principal de serviço do Azure](connect-service-principal.md) para o cofre de chaves que deve ser ligado.

- O cofre de chaves deve ter a firewall do Key Vault **desativada**.

- O cofre de chaves está na mesma [localização do Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que o ambiente do Customer Insights. A região do ambiente nas informações do Customer Insights está listada em **Admin** > **Sistema** > **Acerca de** > **Região**.

### <a name="link-a-key-vault-to-the-environment"></a>Ligar um cofre de chaves ao ambiente

1. Aceda ao **Administrador** > **Segurança** e, em seguida, selecione o separador **Key Vault**.
1. No mosaico **Key Vault**, selecione **Configuração**.
1. Escolha uma **Subscrição**.
1. Escolha um cofre de chaves da lista pendente do **Key Vault**. Se estiverem a aparecer demasiados cofres de chaves, selecione um grupo de recursos para limitar os resultados da pesquisa.
1. Aceite a declaração de **Privacidade e conformidade de dados**.
1. Selecione **Guardar**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Passos para configurar um cofre de chaves ligado no Customer Insights.":::

O mosaico **Key Vault** mostra agora o nome do cofre de chaves, o grupo de recursos e a subscrição ligados. Está pronto para ser utilizado na configuração da ligação.
Para obter detalhes sobre quais permissões no cofre de chaves são concedidas ao Customer Insights, vá para [Permissões concedidas no cofre de chaves](#permissions-granted-on-the-key-vault), posteriormente neste artigo.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilizar o cofre de chaves na configuração da ligação

Ao [configurar ligações](connections.md) aos sistemas de terceiros, os segredos do Key Vault ligado podem ser utilizados para configurar as ligações.

1. Aceda a **Admin** > **Ligações**.
1. Selecione **Adicionar ligação**.
1. Para obter os tipos de ligação suportados, está disponível um seletor **Utilizar Key Vault** se tiver ligado um cofre de chaves.
1. Em vez de introduzir o segredo manualmente, pode escolher o nome do segredo que aponta para o valor de segredo no cofre de chaves.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Painel de ligação com uma ligação SFTP que utiliza um segredo do Cofre de Chaves.":::

## <a name="supported-connection-types"></a>Tipos de ligação suportados

São suportadas as seguintes ligações de [exportação](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Marketing Cloud da Salesforce](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Permissões concedidas no cofre de chaves

As seguintes permissões são concedidas ao Customer Insights num cofre de chaves ligado se a [a política de acesso ao Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [controlo de acesso baseado em funções do Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) estiverem ativados.

### <a name="key-vault-access-policy"></a>Política de acesso ao Key Vault

| Tipo        | Permissões          |
| ----------- | -------------------- |
| Tecla         | [Obter Chaves](/rest/api/keyvault/get-keys), [Obter Chave](/rest/api/keyvault/get-key)                                 |
| Segredo      | [Obter Segredos](/rest/api/keyvault/get-secrets), [Obter Segredo](/rest/api/keyvault/get-secret)                     |
| Certificado | [Obter Certificados](/rest/api/keyvault/get-certificates), [Obter Certificado](/rest/api/keyvault/get-certificate) |

Os valores anteriores são os mínimos para listar e ler durante a execução.

### <a name="azure-role-based-access-control"></a>Controlo de acesso baseado em funções do Azure

As funções de Leitor do Key Vault e Utilizador de Segredos do Key Vault serão adicionadas ao Customer Insights. Para mais detalhes sobre estas funções, vá para [Funções incorporadas do Azure para operações do plano de dados do Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomendações

- Utilize um cofre de chaves separado ou dedicado que contenha apenas os segredos obrigatórios para o Customer Insights. Leia mais sobre o porquê [de serem recomendados cofres de chaves separados](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Siga as [melhores práticas para utilizar o Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para opções de acesso de controlo, cópia de segurança, auditoria e recuperação.

## <a name="frequently-asked-questions"></a>Perguntas mais frequentes

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>O Customer Insights pode escrever segredos ou substituir segredos no cofre de chaves?

N.º Apenas as permissões de leitura e lista descritas na secção de [permissões concedidas](#permissions-granted-on-the-key-vault) anteriormente neste artigo são concedidas ao Customer Insights. O sistema não pode adicionar, eliminar ou substituir segredos no cofre de chaves. Esse é também o motivo pelo qual não pode introduzir credenciais quando uma ligação utiliza o Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Posso alterar uma ligação de segredos do Key Vault para autenticação predefinida?

N.º Não pode voltar a uma ligação predefinida depois de a configurar utilizando um segredo de um cofre de chaves ligado. Crie uma ligação separada e elimine a antiga se já não precisar da mesma.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Como posso revogar o acesso a um cofre de chaves para o Customer Insights?

Dependendo de se a [política de acesso ao Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [controlo de acesso baseado em funções do Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) estão ativados, é necessário remover as permissões para o principal de serviço `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` com o nome `Dynamics 365 AI for Customer Insights`. Todas as ligações que utilizam o cofre de chaves deixarão de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Um segredo utilizado numa ligação foi removido do cofre de chaves. O que posso fazer?

Uma notificação aparece no Customer Insights quando um segredo configurado do cofre de chaves já não está acessível. Ative a [eliminação recuperável](/azure/key-vault/general/soft-delete-overview) no cofre de chaves para restaurar os segredos se forem removidos acidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Uma ligação não funciona, mas o meu segredo está no cofre de chaves. Qual pode ser a causa?

Uma notificação aparece no Customer Insights quando não consegue aceder ao cofre de chaves. A causa pode ser:

- As permissões para o principal de serviço do Customer Insights foram removidas. Precisam de ser restauradas manualmente.

- A firewall no cofre de chaves está ativada. A firewall deve ser desativada para tornar o cofre de chaves acessível para o Customer Insights novamente.

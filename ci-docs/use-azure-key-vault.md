---
title: Trazer o seu próprio Azure Key Vault (pré-visualização)
description: Aprenda a configurar o Customer Insights para utilizar o seu próprio Azure Key Vault para gerir segredos.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246169"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Trazer o seu próprio Azure Key Vault (pré-visualização)

A ligação de um [Azure Key Vault](/azure/key-vault/general/basic-concepts) dedicado a um ambiente do Customer Insights ajuda as organizações a cumprir os requisitos de conformidade.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Ligue o cofre de chaves ao ambiente do Customer Insights

Configure o cofre de chaves dedicado para preparar e utilizar segredos no limiar de conformidade de uma organização.

### <a name="prerequisites"></a>Pré-requisitos

- Uma subscrição ativa do Azure.

- Uma função [Administrador](permissions.md#admin) [atribuída](permissions.md#add-users) no Customer Insights.

- [Contribuidor](/azure/role-based-access-control/built-in-roles#contributor) e [Administrador de Acesso ao Utilizador](/azure/role-based-access-control/built-in-roles#user-access-administrator) no cofre de chaves ou no grupo de recursos ao qual o cofre de chaves pertence. Para obter mais informações, aceda a [Adicionar ou remova atribuições de funções do Azure utilizando o portal do Azure](/azure/role-based-access-control/role-assignments-portal). Se não tiver a função de Administrador de Acesso ao Utilizador no cofre de chaves, configurar as permissões de controlo de acesso baseado em funções para o principal de serviço do Azure para o Dynamics 365 Customer Insights em separado. Siga os passos para [utilizar um principal de serviço do Azure](connect-service-principal.md) para o cofre de chaves que deve ser ligado.

- O cofre de chaves tem de ter a firewall do Key Vault **desativada**.

- O cofre de chaves está na mesma [localização do Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que o ambiente do Customer Insights. No Customer Insights, vá para **Administrador** > **Sistema** e o separador **Acerca de** para ver a região do ambiente.

### <a name="recommendations"></a>Recomendações

- [Utilize um cofre de chaves separado ou dedicado](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) que contenha apenas os segredos obrigatórios para o Customer Insights.

- Siga as [melhores práticas para utilizar o Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para opções de acesso de controlo, cópia de segurança, auditoria e recuperação.

### <a name="link-a-key-vault-to-the-environment"></a>Ligar um cofre de chaves ao ambiente

1. Aceda ao **Administrador** > **Segurança** e, em seguida, selecione o separador **Key Vault**.
1. No mosaico **Key Vault**, selecione **Configuração**.
1. Escolha uma **Subscrição**.
1. Escolha um cofre de chaves da lista pendente do **Key Vault**. Se estiverem disponíveis demasiados cofres de chaves, selecione um grupo de recursos para limitar os resultados da pesquisa.
1. Reveja a [Privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.
1. Selecione **Guardar**.

O mosaico **Key Vault** mostra o nome do cofre de chaves, o grupo de recursos e a subscrição ligados. Está pronto para ser utilizado na configuração da ligação.
Para obter detalhes sobre quais permissões no cofre de chaves são concedidas ao Customer Insights, vá para [Permissões concedidas no cofre de chaves](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilizar o cofre de chaves na configuração da ligação

Ao [configurar ligações](connections.md) aos sistemas de [terceiros suportados](#supported-connection-types), utilize os segredos do Key Vault ligado para configurar as ligações.

1. Aceda a **Admin** > **Ligações**.
1. Selecione **Adicionar ligação**.
1. Para obter os tipos de ligação suportados, está disponível um seletor **Utilizar Key Vault** se tiver ligado um cofre de chaves.
1. Em vez de introduzir o segredo manualmente, escolha o nome do segredo que aponta para o valor de segredo no cofre de chaves.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Painel de ligação com uma ligação SFTP que utiliza um segredo do Cofre de Chaves.":::

1. Selecione **Guardar** para criar a ligação.

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
| Tecla         | [Obter Chaves](/rest/api/keyvault/keys/get-keys/get-keys), [Obter Chave](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Segredo      | [Obter Segredos](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Obter Segredo](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificado | [Obter Certificados](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Obter Certificado](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Os valores anteriores são os mínimos para listar e ler durante a execução.

### <a name="azure-role-based-access-control"></a>Controlo de acesso baseado em funções do Azure

As [funções de Leitor do Key Vault e Utilizador de Segredos do Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli) serão adicionadas ao Customer Insights.

## <a name="frequently-asked-questions"></a>Perguntas mais frequentes

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>O Customer Insights pode escrever segredos ou substituir segredos no cofre de chaves?

Não Apenas as permissões de leitura e lista descritas em [permissões concedidas](#permissions-granted-on-the-key-vault) são concedidas ao Customer Insights. O sistema não pode adicionar, eliminar ou substituir segredos no cofre de chaves. Esse é também o motivo pelo qual não pode introduzir credenciais quando uma ligação utiliza o Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Posso alterar uma ligação de segredos do Key Vault para autenticação predefinida?

N.º Não pode voltar a uma ligação predefinida depois de a configurar utilizando um segredo de um cofre de chaves ligado. Crie uma ligação separada e elimine a antiga se já não precisar da mesma.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Como posso revogar o acesso a um cofre de chaves para o Customer Insights?

Se a [política de acesso ao Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [controlo de acesso baseado em funções do Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) estão ativados, remova as permissões para o principal de serviço `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` com o nome `Dynamics 365 AI for Customer Insights`. Todas as ligações que utilizam o cofre de chaves deixarão de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Um segredo utilizado numa ligação foi removido do cofre de chaves. O que posso fazer?

Uma notificação aparece no Customer Insights quando um segredo configurado do cofre de chaves já não está acessível. Ative a [eliminação recuperável](/azure/key-vault/general/soft-delete-overview) no cofre de chaves para restaurar os segredos se forem removidos acidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Uma ligação não funciona, mas o meu segredo está no cofre de chaves. Qual pode ser a causa?

Uma notificação aparece no Customer Insights quando não consegue aceder ao cofre de chaves. A causa pode ser:

- As permissões para o principal de serviço do Customer Insights foram removidas. Precisam de ser restauradas manualmente.

- A firewall no cofre de chaves está ativada. A firewall deve ser desativada para tornar o cofre de chaves acessível para o Customer Insights novamente.

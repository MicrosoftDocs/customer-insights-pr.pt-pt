---
title: Definições de segurança no Dynamics 365 Customer Insights
description: Mais informações sobre definições de segurança no Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653735"
---
# <a name="security-overview-page"></a>Página Descrição geral de segurança

A página **Segurança** lista opções para configurar permissões de utilizador e funcionalidades que ajudam a tornar o Dynamics 365 Customer Insights mais seguro. Só os administradores podem aceder a esta página. 

Aceda a **Admin** > **Segurança** para configurar as definições.

A página **Segurança** inclui os seguintes separadores:
- [Utilizadores](#users-tab)
- [APIs](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Separador Utilizadores

O acesso ao Customer Insights está restrito a utilizadores da sua organização que foram adicionados à aplicação por um admin. O separador **Utilizadores** permite-lhe gerir o acesso de utilizador e as respetivas permissões. Para obter mais informações, consulte [Permissões de utilizador](permissions.md).

## <a name="apis-tab"></a>Separador APIs

Ver e gerir as chaves a utilizar as [APIs do Customer Insights](apis.md) com os dados do seu ambiente.

Pode criar novas chaves primárias e secundárias selecionando **Regenerar primária** ou **Regenerar secundária**. 

Para bloquear o acesso da API ao ambiente, selecione **Desativar**. Se as APIs estiverem desativadas, pode selecionar **Ativar** para conceder acesso novamente.

## <a name="key-vault-tab"></a>Separador Key Vault

O separador **Key Vault** permite-lhe ligar e gerir o seu próprio [Azure Key Vault](/azure/key-vault/general/basic-concepts) ao ambiente.
O cofre de chaves dedicado pode ser utilizado para preparar e utilizar segredos no limiar de conformidade de uma organização. O Customer Insights pode utilizar os segredos no Azure Key Vault para [configurar as ligações](connections.md) aos sistemas de terceiros.

Para mais informações, consulte [Trazer o seu próprio Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]

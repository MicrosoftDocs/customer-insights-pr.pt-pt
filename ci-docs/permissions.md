---
title: Atribuir permissões de utilizador
description: Mais informações sobre permissões e funções do utilizador.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245433"
---
# <a name="assign-user-permissions"></a>Atribuir permissões de utilizador

O acesso ao Customer Insights está restrito a utilizadores da sua organização que são adicionados à aplicação por um administrador. Um administrador pode adicionar, editar ou remover utilizadores. Um utilizador pode ser um único utilizador, um grupo ou uma aplicação. Existem três tipos de funções que um utilizador pode ter:

## <a name="viewer"></a>Visualizador

- Explore as informações e os segmentos nas páginas **Início** e **Segmentos**.
- Procure e filtre os perfis de cliente através da página **Clientes**. Os campos têm de ser pesquisáveis.
- Ver e explorar a página **Enriquecimento**.
- Explore e exporte as entidades através da página **Entidades**.
- Veja o estado dos processos de sistema através da página **Sistema**.
- Ver exportações na página **Exportações**.
- Instale e utilize o dashboard **Power BI Customer Insights**.

## <a name="contributor"></a>Contribuidor

- Todas as permissões disponíveis para o Visualizador.
- Carregue e transforme os dados através da página **Origens de dados**.
- Conclua a **Unificação de dados**, o que resulta a entidade de perfil de cliente unificado.
- Defina as **Relações** e as **Atividades**.
- Crie segmentos através da página **Segmentos**.
- Crie medidas através da página **Medidas**.
- Gerir a configuração e enriquecer os perfis do cliente a partir da página de **Enriquecimento** (apenas para enriquecimentos de proprietário).
- Gerir e criar exportações com base em [ligações partilhadas com os contribuidores](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin

- Todas as permissões disponíveis para o Contribuidor.
- Altere as definições no **Sistema**, incluindo o idioma de trabalho, atualize as agendas para os seus processos do sistema e exporte os registos de diagnóstico.
- Altere as definições na página **Segurança**, incluindo utilizadores, chaves de API, ligações privadas e cofre de chaves.
- Estabeleça as definições de pesquisa e filtro para a página Clientes através da página **Índice de pesquisas e filtros** (acessível através da página **Clientes**).
- Efetue a gestão de ligações e permita-as para outras funções de utilizador na página **Ligações**.
- Gerir a configuração e enriquecer os perfis do cliente a partir da página de **Enriquecimento** (para todos os enriquecimentos).
- Gerir e criar exportações na página **Exportações**.
- Instale e utilize o **Suplemento Ficha de Cliente**.
- Adicione e utilize o **Power Apps conetor**.
- Permitir o uso de [APIs do Customer Insights](apis.md).
- [Atribuir a propriedade do ambiente](manage-environments.md#change-the-owner-of-an-environment) a outro administrador.

## <a name="admin-owner"></a>Administrador (proprietário)

- Todas as permissões disponíveis para o Administrador.
- [Repor e eliminar](manage-environments.md#reset-an-existing-environment-preview) o ambiente.

## <a name="add-users"></a>Adicionar utilizadores

1. Aceda a **Admin** > **Segurança** e selecione o separador **Utilizadores**.

1. Selecione **Adicionar utilizadores** para abrir o painel **Adicionar/Editar permissões**.

1. Utilize o campo **Procurar** para localizar o utilizador ou grupo do Azure Active Directory que pretende adicionar. Selecione uma **Função** para atribuir a esse utilizador ou grupo.

1. Selecione **Guardar**. O ambiente atual é automaticamente partilhado com o utilizador ou membros do grupo. Os utilizadores podem aceder à aplicação Customer Insights e trabalhar de acordo com a sua função especificada.

## <a name="view-current-permissions"></a>Ver permissões atuais

Vá para **Administrador** > **Segurança** e selecione o separador **Utilizadores** para ver a lista de utilizadores ativos e as respetivas atribuições de funções. Pode ordenar a lista de utilizadores por qualquer coluna ou utilizar a caixa de pesquisa para localizar o utilizador específico.

## <a name="manage-current-users"></a>Gerir utilizadores atuais

Vá para **Administrador** > **Segurança** e selecione o separador **Utilizadores**. Pode ordenar a lista de utilizadores por qualquer coluna ou utilizar a caixa de pesquisa para localizar o utilizador que pretende gerir.

Selecione um utilizador para ver as ações disponíveis.

- **Editar** para editar a função do utilizador no Customer Insights. Selecione **Guardar** para confirmar a alteração.
- **Remover** para remover o utilizador de ter acesso ao Customer Insights. Selecione **Eliminar** para confirmar a eliminação.

[!INCLUDE [footer-include](includes/footer-banner.md)]

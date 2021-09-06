---
title: Gerir permissões de utilizador
description: Mais informações sobre permissões e funções do utilizador.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 430ad902a5a75552243bc4a094361a749364383717278f687dd6e8ef33749c6f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7028328"
---
# <a name="user-permissions"></a>Permissões de utilizador

A página **Permissões** é onde irá definir papéis e permissões para a utilização das informações de audiência.

Precisa de ter permissões de administrador para ver a página. Para aceder à página de permissões em informações de audiência, vá a **Admin** > **Permissões**.

Existem três tipos de funções:

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
- Preencha as secções *Unificação de Dados* (**Mapear**, **Corresponder** e **Intercalar**) que resultam na entidade de perfil do cliente unificado.
- Defina as **Relações** e as **Atividades**.
- Crie segmentos através da página **Segmentos**.
- Crie medidas através da página **Medidas**.
- Gerir a configuração e enriquecer os perfis do cliente a partir da página de **Enriquecimento** (apenas para enriquecimentos de proprietário).
- Gerir e criar exportações com base em ligações partilhadas com os contribuidores. [Saiba mais sobre como os administradores permitem que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Administrador

- Todas as permissões disponíveis para o Contribuidor.
- Altere as definições no **Sistema**, incluindo o idioma de trabalho e atualize as agendas para os seus processos do sistema.
- Veja e adicione permissões através da página **Permissões**.
- Estabeleça as definições de pesquisa e filtro para a página Clientes através da página **Índice de pesquisas e filtros** (acessível através da página **Clientes**).
- Efetue a gestão de ligações e permita-as para outras funções de utilizador na página **Ligações**.
- Gerir a configuração e enriquecer os perfis do cliente a partir da página de **Enriquecimento** (para todos os enriquecimentos).
- Gerir e criar exportações na página **Exportações**.
- Instale e utilize o **Suplemento Ficha de Cliente**.
- Adicione e utilize o **Power Apps conetor**.
- Permitir o uso de [APIs do Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Atribuir funções e permissões

1. Nos insights de audiência, vá a **Admin** > **Permissões**.

1. Selecione **Adicionar utilizadores** para abrir o painel **Adicionar/Editar permissões**.

1. Utilize o campo **Pesquisar** para encontrar o utilizador ou grupo do Azure Active Directory cujas permissões pretende ajustar. Selecione uma **Função** para atribuir a esse utilizador ou grupo.

1. Selecione **Guardar**. O ambiente atual será automaticamente partilhado com o utilizador ou membros do grupo cujas permissões tenham sido alteradas. Os utilizadores podem aceder à aplicação Customer Insights e trabalhar de acordo com a sua função especificada.

## <a name="view-current-permissions"></a>Ver permissões atuais

Nas informações de audiência, vá a **Admin** > **Permissões** para ver que atribuições de funções se encontram atualmente ativas.

- A coluna **Tipo** especifica um único utilizador, grupo ou aplicação. O sistema suporta utilizadores individuais e grupos.
- As funções são especificadas na coluna **Função**.
- Selecione qualquer título de coluna para ordenar os resultados pelo valor dessa coluna.
- Utilize o campo **Pesquisar** na parte superior da página para localizar utilizadores específicos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

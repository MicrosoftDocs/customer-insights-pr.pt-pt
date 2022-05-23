---
title: Ligações a outros serviços do Customer Insights.
description: Partilhar dados com outros serviços.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: d85de28a12565e1a2e36278d0e8b74f6de286b20
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755323"
---
# <a name="connections-preview-overview"></a>Descrição geral das ligações (pré-visualização)

As ligações são a chave para ativar a partilha de dados de e para o Customer Insights. Cada ligação estabelece a partilha de dados com um serviço específico. As ligações são a base para [configurar enriquecimentos de terceiros](enrichment-hub.md) e [configurar exportações](export-destinations.md). A mesma ligação pode ser utilizada várias vezes. Por exemplo, uma ligação ao Dynamics 365 Marketing funciona para múltiplas exportações e uma ligação Leadspace pode ser usada para vários enriquecimentos.

Aceda a **Admin** > **Ligações** para criar e ver ligações.

O separador **Ligações** mostra todas as ligações ativas. A lista mostra uma linha para cada ligação.

Obtenha uma descrição geral rápida, descrição e descubra o que pode fazer com cada opção de extensibilidade no separador **Descobrir**.

## <a name="exports"></a>Exportações

Apenas os administradores podem configurar novas ligações, mas podem conceder acesso aos contribuidores para utilizarem as ligações existentes. Os administradores controlam onde os dados podem ir, os contribuidores definem o payload e a frequência que correspondem às suas necessidades. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Melhoramentos

Apenas os administradores podem configurar novas ligações, mas as ligações criadas estão sempre disponíveis tanto para administradores como para contribuidores. Os administradores gerem credenciais e dão consentimento às transferências de dados. As ligações podem então ser utilizadas para enriquecimentos por administradores e contribuidores.

## <a name="add-a-new-connection"></a>Adicionar uma nova ligação

Para adicionar ligações, precisa de ter [permissões de administrador](permissions.md). Se ligar a outros serviços da Microsoft, assumimos que ambos os serviços estão na mesma organização.

1. Aceda a **Admin** > **Ligações (pré-visualização)**.

1. Vá ao separador **Ligações**.

1. Selecione **Adicionar ligação** para criar uma nova ligação. Escolha do menu pendente que tipo de ligação pretende criar.

1. No painel **Configurar ligação**, forneça os detalhes necessários.
   1. O **Nome a Apresentar** e o tipo de ligação descrevem uma ligação. Recomendamos a escolha de um nome que explique o propósito e o destino desta ligação.
   1. Os campos exatos dependem do serviço ao qual está a ligar. Pode aprender sobre detalhes de um tipo de ligação específico no artigo sobre o serviço de destino.
   1. Se [utilizar o seu próprio Key Vault](use-azure-key-vault.md) para armazenar segredos, ative **Utilizar Key Vault** e escolha o segredo da lista.

1. Para criar a ligação, selecione **Guardar**.

Também pode selecionar **Configurar** num mosaico no separador **Descobrir**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permita que os contribuidores utilizem uma ligação para exportações

Ao definir ou editar uma ligação de exportação, escolha que utilizadores estão autorizados a utilizar esta ligação específica para definir [exportações](export-destinations.md). Por predefinição, está disponível uma ligação para utilizadores com uma função de administrador. Pode alterar esta definição em **Escolher quem pode utilizar esta ligação** e permitir que os utilizadores com a função de contribuidor utilizem esta ligação.

- Os contribuidores não poderão ver ou editar a ligação. Verão apenas o nome a apresentar e o seu tipo ao criar uma exportação.
- Ao partilhar uma ligação, permite que os contribuidores utilizem uma ligação. Os contribuidores verão ligações partilhadas quando configurarem exportações. Podem gerir todas as exportações que utilizam esta ligação específica.
- Pode alterar esta definição mantendo as exportações que já foram definidas pelos contribuidores.

## <a name="edit-a-connection"></a>Editar uma ligação

1. Aceda a **Admin** > **Ligações (pré-visualização)**.

1. Vá ao separador **Ligações**.

1. Selecione as reticências verticais da ligação que pretende editar.

1. Selecione **Editar**.

1. Altere os valores que pretende atualizar e selecione **Guardar**.

## <a name="remove-a-connection"></a>Remover uma ligação

Se a ligação que está a remover for utilizada por melhoramentos ou exportações, primeiro tem de as desanexar ou remover. O diálogo de remoção irá guiá-lo para os enriquecimentos ou exportações relevantes.

Enriquecimentos e exportações separados tornam-se inativos. Reativa-os adicionando-lhes outra ligação na página [Enriquecimentos](enrichment-hub.md) ou [Exportações](export-destinations.md).

1. Aceda a **Admin** > **Ligações (pré-visualização)**.

1. Vá ao separador **Ligações**.

1. Selecione as reticências verticais da ligação que pretende remover.

1. Selecione **Remover** no menu pendente. É apresentado um diálogo de confirmação.

   1. Se houver enriquecimentos ou exportações a utilizar esta ligação, selecione o botão para ver o que está a utilizar a ligação.
      - **Exportações:** pode optar por remover ou desligar as exportações para poder remover a ligação. Para desligar uma exportação, os administradores podem utilizar a ação **Desligar**. Esta ação está disponível para exportações individuais e múltiplas selecionadas. Ao desligar, mantenha a configuração de exportação, mas não será executada até que outra ligação lhe seja adicionada.
      - **Enriquecimentos:** pode optar por remover ou desativar os enriquecimentos para poder remover a ligação.
   1. Quando a ligação não tiver mais dependências, regresse a **Admin** > **Ligações** e tente remover novamente a ligação.

1. Para confirmar a eliminação, selecione **Remover**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurar ligações com segredos geridos pelo seu próprio Key Vault

Algumas ligações precisam de segredos como chaves de API ou palavras-passe. Algumas ligações suportam segredos armazenados no seu próprio Key Vault. Saiba mais sobre as ligações suportadas e como configurar no [seu próprio Key Vault para o Customer Insights](use-azure-key-vault.md).

---
title: Ligações a outros serviços do Customer Insights.
description: Partilhar dados com outros serviços.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896111"
---
# <a name="connections-preview-overview"></a>Descrição geral das ligações (pré-visualização)

As ligações são a chave para ativar a partilha de dados de e para o Customer Insights. Cada ligação estabelece a partilha de dados com um serviço específico. As ligações são a base para [configurar enriquecimentos de terceiros](enrichment-hub.md) e [configurar exportações](export-destinations.md). A mesma ligação pode ser utilizada várias vezes. Por exemplo, uma ligação ao Dynamics 365 Marketing funciona para múltiplas exportações e uma ligação Leadspace pode ser usada para vários enriquecimentos.

Aceda a **Admin** > **Ligações** para criar e ver ligações.

O separador **Ligações** mostra todas as ligações ativas. A lista mostra uma linha para cada ligação. 

Obtenha uma descrição geral rápida, descrição e descubra o que pode fazer com cada opção de extensibilidade no separador **Descobrir**.

### <a name="exports"></a>Exportações

Apenas os administradores podem configurar novas ligações, mas podem conceder acesso aos contribuidores para utilizarem as ligações existentes. Os administradores controlam onde os dados podem ir, os contribuidores definem o payload e a frequência que correspondem às suas necessidades. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Melhoramentos

Apenas os administradores podem configurar novas ligações, mas as ligações criadas estão sempre disponíveis tanto para administradores como para contribuidores. Os administradores gerem credenciais e dão consentimento às transferências de dados. As ligações podem então ser utilizadas para enriquecimentos por administradores e contribuidores.

## <a name="add-a-new-connection"></a>Adicionar uma nova ligação

Para adicionar ligações, precisa de ter [permissões de administrador](permissions.md). Se ligar a outros serviços da Microsoft, assumimos que ambos os serviços estão na mesma organização.

1. Aceda a **Admin** > **Ligações (pré-visualização)**.

1. Vá ao separador **Ligações**.

1. Selecione **Adicionar ligação** para criar uma nova ligação. Escolha do menu suspenso que tipo de ligação pretende criar.

1. No painel **Configurar ligação**, forneça os detalhes necessários. 
   1. O **Nome a Apresentar** e o tipo de ligação descrevem uma ligação. Recomendamos a escolha de um nome que explique o propósito e o destino desta ligação.
   1. Os campos exatos dependem do serviço a que se está a ligar. Pode aprender sobre detalhes de um tipo de ligação específico no artigo sobre o serviço de destino.

1. Para criar a ligação, selecione **Guardar**.

Também pode selecionar **Configurar** num mosaico no separador **Descobrir**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permita que os contribuidores utilizem uma ligação para exportações

Ao definir ou editar uma ligação de exportação, escolha que utilizadores estão autorizados a utilizar esta ligação específica para definir [exportações](export-destinations.md). Por predefinição, está disponível uma ligação para utilizadores com uma função de administrador. Pode alterar esta definição em **Escolher quem pode utilizar esta ligação** e permitir que os utilizadores com a função de contribuidor utilizem esta ligação.

- Os contribuidores não poderão ver ou editar a ligação. Só verão o nome a apresentar e o seu tipo na criação de uma exportação.
- Ao partilhar uma ligação, permite que os contribuidores utilizem uma ligação. Os contribuidores verão ligações partilhadas quando configurarem exportações. Podem gerir todas as exportações que utilizam esta ligação específica.
- Pode alterar esta definição mantendo as exportações que já foram definidas pelos contribuidores.

## <a name="edit-a-connection"></a>Editar uma ligação

1. Aceda a **Admin** > **Ligações (pré-visualização)**.

1. Vá ao separador **Ligações**.

1. Selecione as reticências verticais da ligação que pretende editar.

1. Selecione **Editar**.

1. Altere os valores que pretende atualizar e selecione **Guardar**.

## <a name="remove-a-connection"></a>Remover uma ligação

Se a ligação que está a remover for utilizada por enriquecimentos ou exportações, tem de os separar ou remover primeiro. O diálogo de remoção irá guiá-lo para os enriquecimentos ou exportações relevantes. Enriquecimentos e exportações separados tornam-se inativos. Reativa-os adicionando-lhes outra ligação na página [Enriquecimentos](enrichment-hub.md) ou [Exportações](export-destinations.md).

1. Aceda a **Admin** > **Ligações (pré-visualização)**.

1. Vá ao separador **Ligações**.

1. Selecione as reticências verticais da ligação que pretende remover.

1. Selecione **Remover** no menu pendente. É apresentado um diálogo de confirmação.

   1. Se houver enriquecimentos ou exportações a utilizar esta ligação, selecione o botão para ver o que está a utilizar a ligação.
      - **Exportações:** pode optar por remover ou desligar as exportações para poder remover a ligação. Para desligar uma exportação, os administradores podem utilizar a ação **Desligar**. Esta ação está disponível para exportações individuais e múltiplas selecionadas. Ao desligar, mantenha a configuração de exportação, mas não será executada até que outra ligação lhe seja adicionada.
      - **Enriquecimentos:** pode optar por remover ou desativar os enriquecimentos para poder remover a ligação. 
   1. Quando a ligação não tiver mais dependências, regresse a **Admin** > **Ligações** e tente remover novamente a ligação.

1. Para confirmar a eliminação, selecione **Remover**.


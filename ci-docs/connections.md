---
title: Descrição geral das ligações (pré-visualização)
description: Ligações a outros serviços do Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245525"
---
# <a name="connections-preview-overview"></a>Descrição geral das ligações (pré-visualização)

As ligações são a chave para ativar a partilha de dados de e para o Customer Insights. Cada ligação estabelece a partilha de dados com um serviço específico. Utilize as ligações para [configurar enriquecimentos de terceiros](enrichment-hub.md) e [configurar exportações](export-destinations.md). A mesma ligação pode ser utilizada várias vezes. Por exemplo, uma ligação ao Dynamics 365 Marketing funciona para múltiplas exportações e uma ligação Leadspace pode ser usada para vários enriquecimentos.

## <a name="export-connections"></a>Ligações de exportação

Apenas os administradores podem configurar novas ligações, mas podem [conceder acesso aos contribuidores](#allow-contributors-to-use-a-connection-for-exports) para utilizarem as ligações existentes. Os administradores controlam onde os dados podem ir, os contribuidores definem o payload e a frequência que correspondem às suas necessidades.

## <a name="enrichment-connections"></a>Ligações de enriquecimento

Apenas os administradores podem configurar novas ligações, mas as ligações criadas estão sempre disponíveis tanto para administradores como para contribuidores. Os administradores gerem credenciais e dão consentimento às transferências de dados. As ligações podem então ser utilizadas para enriquecimentos por administradores e contribuidores.

## <a name="add-a-new-connection"></a>Adicionar uma nova ligação

### <a name="prerequisites"></a>Pré-requisitos

- [Permissões de administrador](permissions.md)
- Os outros serviços Microsoft, se existirem, estão na mesma organização

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha o tipo de ligação que pretende criar. Ou vá para o separador **Descobrir** e selecione **Configurar** num mosaico de ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Introduza os detalhes necessários. Os campos exatos dependem do serviço ao qual está a ligar. Para obter os detalhes de um tipo de ligação específico, consulte o artigo sobre o serviço de destino.

1. Se [utilizar o seu próprio Key Vault](use-azure-key-vault.md) para armazenar segredos, ative **Utilizar Key Vault** e escolha o segredo da lista.

1. Reveja a privacidade e conformidade dos dados e selecione **Concordo**.

1. Selecione **Guardar** para criar a ligação.

### <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para terceiros ou outros produtos Microsoft, permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que os terceiros cumprem quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O seu administrador do Dynamics 365 Customer Insights pode remover a ligação em qualquer altura para descontinuar a utilização da funcionalidade.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permita que os contribuidores utilizem uma ligação para exportações

Ao definir ou editar uma ligação de exportação, escolha que utilizadores estão autorizados a utilizar esta ligação específica para definir [exportações](export-destinations.md). Por predefinição, está disponível uma ligação para utilizadores com uma função de administrador. Altere a definição **Escolher quem pode utilizar esta ligação** para permitir que os utilizadores com a função de contribuidor utilizem esta ligação.

- Os contribuidores não poderão ver ou editar a ligação. Verão apenas o nome a apresentar e o seu tipo ao criar uma exportação.
- Ao partilhar uma ligação, permite que os contribuidores utilizem uma ligação. Os contribuidores verão ligações partilhadas quando configurarem exportações. Podem gerir todas as exportações que utilizam esta ligação específica.
- Pode alterar esta definição mantendo as exportações que já foram definidas pelos contribuidores.

## <a name="manage-existing-connections"></a>Gerir ligações existentes

1. Aceda a **Admin** > **Ligações**.

1. Selecione o separador **Melhoramento** ou **Exportações** para ver uma lista de ligações de exportação ou enriquecimento, o tipo de ligação, quando foi criado e quem tem acesso. Pode ordenar a lista de ligações por qualquer coluna.

1. Selecione a ligação para ver as ações disponíveis.

   - **Editar** a ligação.
   - [**Remover**](#remove-a-connection) uma ligação.

### <a name="remove-a-connection"></a>Remover uma ligação

Se a ligação que está a remover for utilizada por melhoramentos ou exportações, primeiro desanexe-os ou remova-os. A caixa de diálogo de remoção guia-o para os enriquecimentos ou exportações relevantes.

> [!TIP]
> Os enriquecimentos desativados e as exportações desanexadas tornam-se inativos. Reativa-os adicionando-lhes outra ligação na página [Enriquecimentos](enrichment-hub.md) ou [Exportações](export-destinations.md).

1. Aceda a **Admin** > **Ligações**.

1. Selecione o separador **Melhoramento** ou **Exportações**.

1. Selecione a ligação que pretende remover.

1. Selecione **Remover** no menu pendente. É apresentado um diálogo de confirmação.

   1. Se houver enriquecimentos ou exportações a utilizar esta ligação, selecione o botão para ver o que está a utilizar a ligação.
      - **Exportações:** opte por **Remover** a exportação ou **Desanexar a ligação**. Desanexar a ligação mantém a configuração de exportação, mas não será executada até que outra ligação lhe seja adicionada.
      - **Melhoramentos:** opte por **Eliminar** ou **Desativar** os melhoramentos.
   1. Quando a ligação não tiver mais dependências, regresse a **Admin** > **Ligações** e tente remover novamente a ligação.

1. Para confirmar a eliminação, selecione **Remover**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurar ligações com segredos geridos pelo seu próprio Key Vault

Algumas ligações precisam de segredos como chaves de API ou palavras-passe. Algumas ligações suportam segredos armazenados no seu próprio Key Vault. Saiba mais sobre as ligações suportadas e como configurar no [seu próprio Key Vault para o Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]

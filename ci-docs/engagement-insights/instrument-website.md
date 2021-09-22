---
title: Adicionar código ao seu site
description: Como adicionar um fragmento de código para recolher eventos no seu site.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035108"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalar o código de fragmento num site

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo descreve como um administrador instala o fragmento de código num website. Começará a ver eventos na sua área de trabalho pouco depois de adicionar o script ao seu website. Para obter mais informações, consulte [Gerir áreas de trabalho e ambientes](manage-environments-workspaces.md). Para capturar eventos em aplicações móveis, consulte [Descrição geral dos recursos do programador](developer-resources.md).


### <a name="prerequisites"></a>Pré-requisitos

* Deve ter permissões de administrador para a área de trabalho armazenar os dados.
* O seu site ou projeto deve ser alojado online para enviar dados de atividade. Os dados enviados a partir de um ficheiro local não serão aceites pelo servidor.


## <a name="add-code-to-your-website"></a>Adicionar código ao seu site
1.  Vá ao **Administrador** > **Área de trabalho** e, em seguida, selecione **Guia de instalação**.
1. Selecione **Copiar código** para copiar o fragmento de código. Por predefinição, a chave de ingestão da sua área de trabalho está incorporada no fragmento de código.
:::image type="content" source="media/copy-code.png" alt-text="Captura de ecrã da página de fragmento de código.":::
3. Adicione o fragmento de código copiado ao seu site, perto da <head> etiqueta e antes de qualquer outro script ou etiquetas CSS.
4.  Publique o seu site atualizado e aguarde alguns minutos para capturar o tráfego web que está a chegar.
5.  Para ver os seus dados, selecione a sua área de trabalho a partir do comutador de área de trabalho no painel de navegação. Em seguida, selecione um dos relatórios na secção **Descobrir**.

## <a name="configuration-options"></a>Opções de configuração

Pode alterar as seguintes opções de configuração no fragmento de código:

- **ingestionKey**: A chave de ingestão usada para enviar eventos para a sua área de trabalho. Pode alterar a chave de ingestão para enviar eventos para uma área de trabalho diferente. Uma chave de ingestão é exclusiva de cada área de trabalho. 
- **autoCapture**: Especifica se as visualizações da página e as interações com o site são capturadas. Tem duas opções:
    - **ver**: Definir para *verdadeiro* para capturar vistas de página. As vistas da página são captadas como *Ver* [eventos](glossary.md#event), um tipo de [evento base](glossary.md#base-event).
    - **clique**: Definir para *verdadeiro* para capturar interações de visitantes no site. As interações são captadas como *Ação* [eventos](glossary.md#event), um tipo de [evento base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]

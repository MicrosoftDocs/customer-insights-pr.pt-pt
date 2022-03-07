---
title: Adicionar código ao seu site
description: Como adicionar um fragmento de código para recolher eventos do Dynamics 365 Customer Insights no seu site.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231036"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instalar o SDK Web num site

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo descreve como um administrador instala o conjunto de ferramentas de programação de software Web (SDK) num site. Começará a ver eventos na sua área de trabalho pouco depois de instrumentalizar o seu site. Para obter mais informações, consulte [Gerir áreas de trabalho e ambientes](manage-environments-workspaces.md). Para capturar eventos em aplicações móveis, consulte [Descrição geral dos recursos do programador](developer-resources.md).


### <a name="prerequisites"></a>Pré-requisitos

* Deve ter permissões de administrador para a área de trabalho armazenar os dados.
* O seu site ou projeto deve ser alojado online para enviar dados de atividade. Os dados enviados a partir de um ficheiro local não serão aceites pelo servidor.


## <a name="add-web-sdk-to-your-website"></a>Adicionar SDK Web ao seu site

Vá ao **Administrador** > **Área de trabalho** e, em seguida, selecione **Guia de instalação**. Existem duas opções para instalar o SDK Web. A primeira é usar uma ligação de transferência e a segunda é instalar um pacote de gestor de pacotes de nó (NPM).

### <a name="option-1-using-the-download-link"></a>Opção 1: Utilizar a ligação de transferência

1. Selecione **Copiar código** para copiar o fragmento de código. Por predefinição, a chave de ingestão da sua área de trabalho está incorporada no fragmento de código.
  :::image type="content" source="media/copy-code.png" alt-text="Captura de ecrã da página de fragmento de código.":::

1. Adicione o código copiado no seu site, perto da <head> etiqueta e antes de qualquer outro script ou etiquetas CSS.
1. Publique o seu site atualizado e aguarde alguns minutos para capturar o tráfego web que está a chegar.
1. Para ver os seus dados, selecione a sua área de trabalho a partir do comutador de área de trabalho no painel de navegação. Em seguida, selecione um dos relatórios na secção **Descobrir**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Opção 2: Utilizar o pacote NPM (recomendado para aplicações Web baseadas em JavaScript)

1. Vá à nossa [página Web NPM](https://www.npmjs.com/package/engagementinsights-web) e siga as instruções para instalar e configurar o pacote NPM SDK Web.
1. Publique o seu site atualizado e aguarde alguns minutos para capturar o tráfego web que está a chegar.
1. Para ver os seus dados, selecione a sua área de trabalho a partir do comutador de área de trabalho no painel de navegação. Em seguida, selecione um dos relatórios na secção **Descobrir**.

## <a name="configuration-options"></a>Opções de configuração

Pode alterar as seguintes opções de configuração no fragmento de código:

- **ingestionKey**: A chave de ingestão usada para enviar eventos para a sua área de trabalho. Pode alterar a chave de ingestão para enviar eventos para uma área de trabalho diferente. Uma chave de ingestão é exclusiva de cada área de trabalho.
- **autoCapture**: Especifica se as visualizações da página e as interações com o site são capturadas. Tem duas opções:
    - **ver**: Definir para *verdadeiro* para capturar vistas de página. As vistas da página são captadas como *Ver* [eventos](glossary.md#event), um tipo de [evento base](glossary.md#base-event).
    - **clique**: Definir para *verdadeiro* para capturar interações de visitantes no site. As interações são captadas como *Ação* [eventos](glossary.md#event), um tipo de [evento base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]

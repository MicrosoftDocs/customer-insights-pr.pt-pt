---
title: Exportar segmentos para o LiveRamp (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196730"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segmentos para o LiveRamp&reg; (pré-visualização)

Ative os seus dados no LiveRamp para se ligar a mais de 500 plataformas através de canais digitais, sociais e TVs. Trabalhar com os seus dados no LiveRamp para campanhas publicitárias com alvo, supressão e personalizar.

## <a name="prerequisites"></a>Pré-requisitos

- Uma subscrição do LiveRamp para utilizar este conector. Para obter uma subscrição, [contacte a LiveRamp](https://liveramp.com/contact/) diretamente. [Obtenha mais informações sobre a Inclusão do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação LiveRamp está a utilizar uma exportação SFTP. Os destinos SFTP por trás de firewalls não são atualmente suportados.
- Se utilizar uma chave SSH para autenticação, certifique-se de que [cria a sua chave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) de acordo com o formato PEM ou SSH.COM. Se estiver a utilizar o Putty, converta a sua chave privada ao exportá-la como Open SSH. São suportados os seguintes formatos de chave privada:
  - RSA em formato OpenSSL PEM e ssh.com
  - DSA em formato OpenSSL PEM e ssh.com
  - ECDSA 256/384/521 em formato OpenSSL PEM
  - ED25519 e RSA em formato de chave OpenSSH
- O runtime de uma exportação depende do desempenho do seu sistema. Recomendamos dois núcleos CPU e 1 Gb de memória como configuração mínima do seu servidor.
- As entidades exportadoras com até 100 milhões de perfis de clientes podem demorar 90 minutos quando utilizam a configuração mínima recomendada de dois núcleos CPU e 1 Gb de memória.
- O número real de perfis (ou dados) que pode exportar para LiveRamp depende da sua subscrição com o LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Configurar ligação ao LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **LiveRamp**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escolha se pretende autenticar através de SSH ou nome de utilizador/palavra-passe para a sua ligação e forneça os detalhes necessários.

1. Selecione **Verificar** para testar a ligação ao LiveRamp.

1. Após uma verificação com êxito, reveja a [conformidade e privacidade de dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção LiveRamp. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. No campo **Ligar dados**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o LiveRamp para a resolução de identidades.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Conector do LiveRamp com mapeamento de atributos.":::

1. Mapeie os atributos correspondentes da sua entidade *Cliente* para o identificador de chave selecionado.

1. Selecione **Adicionar atributo** para mapear mais atributos para enviar para o LiveRamp.

   > [!TIP]
   > É provável que o envio de atributos de identificador-chave para o LiveRamp tenha uma taxa de correspondência superior.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

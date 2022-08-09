---
title: Exportar dados para os anfitriões do SFTP (pré-visualização) (contém vídeo)
description: Aprenda a configurar a ligação e exportar para uma localização SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207243"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Exportar dados para anfitriões SFTP (pré-visualização)

Utilize os dados dos seus clientes em aplicações de terceiros exportando-os para uma localização do SFTP (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Pré-requisitos

- Disponibilidade de um anfitrião SFTP e credenciais correspondentes.

## <a name="known-limitations"></a>Limitações conhecidas

- Os destinos SFTP por trás de firewalls não são atualmente suportados.
- O runtime de uma exportação depende do desempenho do seu sistema. Recomendamos dois núcleos CPU e 1 Gb de memória como configuração mínima do seu servidor.
- Até 100 milhões de perfis de clientes, que podem demorar 90 minutos quando utilizam a configuração mínima recomendada de dois núcleos de CPU e 1 Gb de memória.
- Se utilizar uma chave SSH para autenticação, certifique-se de que [cria a sua chave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) de acordo com o formato PEM ou SSH.COM. Se estiver a utilizar o Putty, converta a sua chave privada ao exportá-la como Open SSH. São suportados os seguintes formatos de chave privada:
  - RSA em formato OpenSSL PEM e ssh.com
  - DSA em formato OpenSSL PEM e ssh.com
  - ECDSA 256/384/521 em formato OpenSSL PEM
  - ED25519 e RSA em formato de chave OpenSSH

## <a name="set-up-connection-to-sftp"></a>Configurar ligação ao SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **SFTP**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escolha se pretende autenticar através de SSH ou nome de utilizador/palavra-passe para a sua ligação e forneça os detalhes necessários. Se utilizar uma chave SSH para autenticação, certifique-se de que [cria a sua chave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) de acordo com o formato PEM ou SSH.COM. Se estiver a utilizar o Putty, converta a sua chave privada ao exportá-la como Open SSH. São suportados os seguintes formatos de chave privada:
   - RSA em formato OpenSSL PEM e ssh.com
   - DSA em formato OpenSSL PEM e ssh.com
   - ECDSA 256/384/521 em formato OpenSSL PEM
   - ED25519 e RSA em formato de chave OpenSSH

1. Selecione **Verificar** para testar a ligação.

1. Reveja a [privacidade e conformidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Aceda a **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção SFTP. Contacte um administrador se não houver nenhuma ligação disponível.

1. Introduza um nome para a exportação.

1. Escolha se pretende exportar os seus dados em **Gzip** ou **Deszipados** e o **delimitador de campo** para os ficheiros exportados.

1. Selecione as entidades, para segmentos de exemplo, que quer exportar.

   > [!NOTE]
   > Cada entidade selecionada será dividida num máximo de cinco ficheiros de saída quando exportada.

1. Selecione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> A exportação de entidades que contenham uma grande quantidade de dados pode levar a vários ficheiros CSV na mesma pasta para cada exportação. A divisão de exportações ocorre por razões de desempenho que minimizam o tempo que demora a conclusão de uma exportação.

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Exportar dados Customer Insights para anfitriões SFTP
description: Aprenda a configurar a ligação e exportar para uma localização SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124333"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Exportar segmentos e outros dados para o SFTP (pré-visualização)

Utilize os dados dos seus clientes em aplicações de terceiros exportando-os para uma localização do SFTP (Secure File Transfer Protocol).

## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

- Disponibilidade de um anfitrião SFTP e credenciais correspondentes.

## <a name="known-limitations"></a>Limitações conhecidas

- O runtime de uma exportação depende do desempenho do seu sistema. Recomendamos dois núcleos CPU e 1 Gb de memória como configuração mínima do seu servidor. 
- As entidades exportadoras com até 100 milhões de perfis de clientes podem demorar 90 minutos quando utilizam a configuração mínima recomendada de dois núcleos CPU e 1 Gb de memória. 

## <a name="set-up-connection-to-sftp"></a>Configurar ligação ao SFTP

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **SFTP** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça um **Nome de utilizador**, **Palavra-passe**, **Nome do anfitrião** e **Pasta de exportação** para a sua conta SFTP.

1. Selecione **Verificar** para testar a ligação.

1. Escolha se pretende exportar os seus dados em **Gzip** ou **Deszipados** e o **delimitador de campo** para os ficheiros exportados.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção SFTP. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Selecione as entidades, para segmentos de exemplo, que quer exportar.

   > [!NOTE]
   > Cada entidade selecionada será dividida em até cinco ficheiros de saída quando exportada. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados através de SFTP, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o destino de exportação cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

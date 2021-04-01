---
title: Exportar dados Customer Insights para anfitriões SFTP
description: Saiba como configurar a ligação a um anfitrião SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598399"
---
# <a name="connector-for-sftp-preview"></a>Conector para SFTP (pré-visualização)

Utilize os seus dados de clientes em aplicações de terceiros, exportando-os para um anfitrião SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Pré-requisitos

- Disponibilidade de um anfitrião SFTP e credenciais correspondentes.

## <a name="connect-to-sftp"></a>Ligar à SFTP

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Em **SFTP**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.

1. Forneça um **Nome de utilizador**, **Palavra-passe**, **Nome do anfitrião** e **Pasta de exportação** para a sua conta SFTP.

1. Selecione **Verificar** para testar a ligação.

1. Após uma verificação bem sucedida, escolha se pretende exportar os seus dados **Comprimidos por G** ou **Não comprimidos** e selecione o **delimitador de campo** para os ficheiros exportados.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Seguinte** para começar aconfigurar a exportação.

## <a name="configure-the-export"></a>Configurar a exportação

1. Selecione as entidades, para segmentos de exemplo, que quer exportar.

   > [!NOTE]
   > Cada entidade selecionada terá até cinco ficheiros de saída quando exportado. 

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitações conhecidas

- O runtime de uma exportação depende do desempenho do seu sistema. Recomendamos dois núcleos CPU e 1 Gb de memória como configuração mínima do seu servidor. 
- As entidades exportadoras com até 100 milhões de perfis de clientes podem demorar 90 minutos quando utilizam a configuração mínima recomendada de dois núcleos CPU e 1 Gb de memória. 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados através de SFTP, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o destino de exportação cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
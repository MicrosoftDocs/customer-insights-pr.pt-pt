---
title: Conector do LiveRamp
description: Aprenda a configurar a ligação e exportar para o LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4c0f58083e8486d2042d8efcc8b3690020efb1c3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226366"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segmentos para o LiveRamp&reg; (pré-visualização)

Ative os seus dados no LiveRamp para se ligar a mais de 500 plataformas através de canais digitais, sociais e TVs. Trabalhar com os seus dados no LiveRamp para campanhas publicitárias com alvo, supressão e personalizar.

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

- Necessita de uma subscrição do LiveRamp para utilizar este conector.
- Para obter uma subscrição, [contacte a LiveRamp](https://liveramp.com/contact/) diretamente. [Obtenha mais informações sobre a Inclusão do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Configurar ligação ao LiveRamp

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **LiveRamp** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça um **Nome de utilizador** e **Palavra-passe** para a sua conta LiveRamp Secure FTP (SFTP).
Estas credenciais podem ser diferentes das suas credenciais de Integração do LiveRamp.

1. Selecione **Verificar** para testar a ligação ao LiveRamp.

1. Após uma verificação com êxito, forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção LiveRamp. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. No campo **Escolher o identificador-chave**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o LiveRamp para a resolução de identidades.
   > [!div class="mx-imgBorder"]
   > ![Conector do LiveRamp com mapeamento de atributos.](media/export-liveramp-segments.png "Conector do LiveRamp com mapeamento de atributos")

1. Mapeie os atributos correspondentes da sua entidade *Cliente* para o identificador de chave selecionado.

1. Selecione **Adicionar atributo** para mapear mais atributos para enviar para o LiveRamp.

   > [!TIP]
   > É provável que o envio de atributos de identificador-chave para o LiveRamp tenha uma taxa de correspondência superior.

1. Selecione os segmentos que pretende exportar para o LiveRamp.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Liveramp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Liveramp cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

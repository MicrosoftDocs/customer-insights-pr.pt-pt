---
title: Conector do LiveRamp
description: Obter informações sobre como exportar dados para o LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667198"
---
# <a name="liverampreg-connector-preview"></a>Conector do LiveRamp&reg; (pré-visualização)

Ativar os seus dados no LiveRamp para ligar a mais de 500 plataformas em ecossistemas digitais, de redes sociais e de TV. Trabalhar com os seus dados no LiveRamp para campanhas publicitárias com alvo, supressão e personalizar.

## <a name="prerequisites"></a>Pré-requisitos

- Necessita de uma subscrição do LiveRamp para utilizar este conector.
- Para obter uma subscrição, [contacte a LiveRamp](https://liveramp.com/contact/) diretamente. [Obtenha mais informações sobre a Inclusão do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Ligar ao LiveRamp

1. Nos insights de audiência, vá a **Admin** > **Destinos de exportação**.

1. No mosaico **LiveRamp**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.

1. Forneça um **Nome de utilizador** e **Palavra-passe** para a sua conta LiveRamp Secure FTP (SFTP).
Estas credenciais podem ser diferentes das suas credenciais de Integração do LiveRamp.

1. Selecione **Verificar** para testar a ligação ao LiveRamp.

1. Após uma verificação com êxito, forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**.

1. Selecione **Seguinte** para configurar o conector do LiveRamp.

## <a name="configure-the-connector"></a>Configurar o conector

1. No campo **Escolher o identificador-chave**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o LiveRamp para a resolução de identidades.

1. Mapeie os atributos correspondentes da entidade de cliente unificada para o identificador-chave selecionado.

1. Selecione **Adicionar atributo** para mapear atributos adicionais a enviar para o LiveRamp.

   > [!TIP]
   > É provável que o envio de atributos de identificador-chave para o LiveRamp tenha uma taxa de correspondência superior.

1. Selecione os segmentos que pretende exportar para o LiveRamp.

1. Selecione **Guardar**.

> [!div class="mx-imgBorder"]
> ![Conector do LiveRamp com mapeamento de atributos](media/export-liveramp-segments.png "Conector do LiveRamp com mapeamento de atributos")

## <a name="export-the-data"></a>Exportar os dados

A exportação será iniciada em breve se todos os pré-requisitos para exportação tiverem sido concluídos. A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).
Quando a exportação tiver sido concluída com êxito, pode iniciar sessão na Inclusão do LiveRamp para ativar e distribuir os seus dados.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Liveramp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o Liveramp cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.
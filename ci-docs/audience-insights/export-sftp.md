---
title: Exportar dados Customer Insights para anfitriões SFTP
description: Saiba como configurar a ligação a um anfitrião SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643517"
---
# <a name="connector-for-sftp-preview"></a>Conector para SFTP (pré-visualização)

Utilize os seus dados de clientes em aplicações de terceiros, exportando-os para um anfitrião SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Pré-requisitos

- Disponibilidade de um anfitrião SFTP e credenciais correspondentes.

## <a name="connect-to-sftp"></a>Ligar ao SFTP

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Em **SFTP**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino no campo **Nome a apresentar**.

1. Forneça um **nome de utilizador**, **palavra-passe** e **nome do anfitrião** para a sua conta SFTP. Exemplo: Se a pasta raiz do seu servidor SFTP é /root/folder, e gostaria que os dados fossem exportados para /root/folder/ci_export_destination_folder, o anfitrião deve ser sftp://<server_address>/ci_export_destination_folder".

1. Selecione **Verificar** para testar a ligação.

1. Após uma verificação bem sucedida, escolha se pretende exportar os seus dados **Em zip** ou **Sem zip** e selecione o **delimitador de campo** para os ficheiros exportados.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Seguinte** para começar aconfigurar a exportação.

## <a name="configure-the-connection"></a>Configurar a ligação

1. Selecione os **atributos do cliente** que quer exportar. Pode exportar um ou vários atributos.

1. Selecione **Seguinte**.

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados através de SFTP, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o destino de exportação cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

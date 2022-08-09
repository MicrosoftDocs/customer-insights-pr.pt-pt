---
title: Exportar dados para o Marketing Cloud da Salesforce (pré-visualização)
description: Aprenda a configurar a ligação e a exportar para o Marketing Cloud da Salesforce.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197052"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportar dados para o Marketing Cloud da Salesforce (pré-visualização)

Utilize os dados dos seus clientes no Marketing Cloud da Salesforce exportando-os através de uma localização do SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Pré-requisitos

- Um [Anfitrião SFTP para o Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) e credenciais de administrador correspondentes.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Configurar ligação ao Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Salesforce Marketing Cloud**.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Por predefinição, são apenas administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça um **Nome de utilizador**, **Palavra-passe**, **Nome do anfitrião** e **Pasta de exportação** para a sua conta SFTP.

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

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar dados do Customer Insights da localização SFTP para o Marketing Cloud da Salesforce

1. Crie [extensões de dados no Marketing Cloud da Salesforce](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o ficheiro de dados do Customer Insights a partir da localização SFTP.

2. [Importe os dados da localização SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) para a extensão de dados do Marketing Cloud da Salesforce.

3. Configure a automatização para importar os dados para as extensões de dados. Saiba mais sobre [automatizações de largada de ficheiros e automatizações agendadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Defina uma [automatização de largada de ficheiros](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou uma [automatização agendada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Eis um exemplo de [uma automatização com SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]

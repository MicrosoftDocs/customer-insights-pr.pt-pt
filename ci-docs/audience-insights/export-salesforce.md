---
title: Exportar dados do Customer Insights para o Marketing Cloud da Salesforce
description: Aprenda a configurar a ligação e a exportar para o Marketing Cloud da Salesforce.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b50539d6478a8fe196048f0fb421e5856f713a3ddc6577a637e593f90857ae8b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035567"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Exporte segmentos e outros dados para o Marketing Cloud da Salesforce (pré-visualização)

Utilize os dados dos seus clientes no Marketing Cloud da Salesforce exportando-os através de uma localização do SFTP (Secure File Transfer Protocol).

## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

- Disponibilidade de um anfitrião SFTP e credenciais de admin correspondentes. [Como configurar localizações SFTP para o Marketing Cloud da Salesforce](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Configurar a ligação ao Marketing Cloud da Salesforce

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Marketing Cloud da Salesforce** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça um **Nome de utilizador**, **Palavra-passe**, **Nome do anfitrião** e **Pasta de exportação** para a sua conta SFTP.

1. Selecione **Verificar** para testar a ligação.

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção SFTP. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Escolha se pretende exportar os seus dados em **Gzip** ou **Deszipados** e o **delimitador de campo** para os ficheiros exportados.

1. Selecione as entidades, para segmentos de exemplo, que quer exportar.

   > [!NOTE]
   > Cada entidade selecionada será dividida em até cinco ficheiros de saída quando exportada. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar dados do Customer Insights da localização SFTP para o Marketing Cloud da Salesforce

1. Crie [extensões de dados no Marketing Cloud da Salesforce](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o ficheiro de dados do Customer Insights a partir da localização SFTP.

2. [Importe os dados da localização SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) para a extensão de dados do Marketing Cloud da Salesforce. 

3. Configure a automatização para importar os dados para as extensões de dados. Saiba mais sobre [automatizações de largada de ficheiros e automatizações agendadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Defina uma [automatização de largada de ficheiros](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou uma [automatização agendada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Eis um exemplo de [uma automatização com SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados através de SFTP, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que o destino de exportação cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

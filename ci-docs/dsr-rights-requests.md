---
title: Pedidos de Direitos de Titulares de Dados (DSR) ao abrigo do RGPD | Microsoft Docs
description: Responder a Pedidos de Titulares de Dados para a capacidade de insights de audiência do Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350283"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Os pedidos de Direitos de Titulares de Dados (DSR) são pedidos sob RGPD

O Regulamento Geral de Proteção de Dados (RGPD) da União Europeia está em vigor desde 25 de maio de 2018. Confere direitos significativos aos indivíduos relativamente aos seus dados. O RGPD consiste em proteger e ativar os direitos de privacidade de indivíduos. Pode ler mais sobre o compromisso da Microsoft com a segurança e a conformidade no [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Estamos empenhados em ajudar os nossos clientes a cumprir os seus requisitos de RGPD. Inclui o direito de eliminar e exportar dados que incluam informações pessoais, tais como ID de utilizador, números de telefone e endereços de e-mail. Os administradores podem implementar pedidos de utilizador para eliminar ou exportar dados pessoais.

## <a name="audience-insights"></a>Informações de Audiência

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Responder ao titular dos dados RGPD elimina os pedidos para a capacidade de insights de audiência do Dynamics 365 Customer Insights

O "direito de eliminação" através da remoção de dados pessoais dos dados de cliente de uma organização é uma proteção-chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e registos gerados pelo sistema, exceto as informações de registo de auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Gerir pedidos de eliminação do titular de dados

Os insights de audiência oferecem as seguintes experiências no produto para eliminar dados pessoais para um cliente específico ou um utilizador:

- **Gerir pedidos de eliminação de dados de clientes**: os dados dos clientes no Customer Insights são ingeridos a partir das origens de dados originais externas ao Customer Insights. Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados na origem de dados original.
- **Gerir pedidos de eliminação de dados de utilizador do Customer Insights**: Os dados para os utilizadores são criados pela Customer Insights. Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados no Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gerir pedidos para eliminar dados dos clientes

Um administrador do Customer Insights pode seguir estes passos para remover os dados do cliente que foram eliminados na origem de dados:

1. Iniciar sessão no Dynamics 365 Customer Insights.
2. Nas informações de audiência, vá a **Dados** > **Origens de dados**
3. Para cada origem de dados na lista que contém dados de clientes eliminados:
   1. Seleccione (...) e, em seguida, selecione **Atualizar**.
   2. Verifique o estado da origem de dados em **Estado**. Uma marca de verificação significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo correu mal. Se for apresentado um triângulo de aviso, contacte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD.](audience-insights/media/gdpr-data-sources.png "Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD")

##### <a name="manage-delete-requests-for-user-data"></a>Gerir pedidos de eliminação de dados do utilizador

Um administrador do Customer Insights pode seguir estes passos para eliminar dados dos utilizadores do Customer Insights:

1. Iniciar sessão no Dynamics 365 Customer Insights.
2. Nos insights de audiência, vá a **Admin** > **Permissões**.
3. Selecione a caixa de verificação para o utilizador que pretende eliminar.
4. Selecione **Remover**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder aos pedidos de exportação dos titulares de dados RGPD

Como parte do nosso compromisso de parceria consigo no seu percurso para o Regulamento Geral sobre a Proteção de Dados (RGPD), desenvolvemos documentação para o ajudar a preparar-se. Esta documentação descreve as medidas que pode tomar hoje para apoiar o cumprimento do RGPD ao utilizar os insights da audiência.

#### <a name="manage-export-and-view-requests"></a>Gerir pedidos de exportação e visualização

O direito da portabilidade de dados permite aos titulares de dados solicitar uma cópia dos respetivos dados pessoais num formato eletrónico (um "formato estruturado, de utilização comum, de leitura de máquina e interoperável") que poderá ser transmitido para outro controlador de dados.

##### <a name="export-customer-data-tenant-admin"></a>Exportar dados de clientes (administração de inquilinos)

Um administrador pode seguir estes passos para exportar dados:

1. Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do cliente no pedido. A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.
2. Aceite a confirmação para exportar os dados para o cliente pedido.
3. Receba os dados exportados através do endereço de e-mail do administrador de inquilino.

##### <a name="export-user-data-tenant-admin"></a>Exportar dados do utilizador (administração de inquilinos)

1. Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do utilizador no pedido. A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.
2. Aceite a confirmação para exportar os dados para o utilizador pedido.
3. Receba os dados exportados através do endereço de e-mail do administrador de inquilino.

## <a name="consent-management-preview"></a>Gestão de consentimento (pré-visualização)

A capacidade de gestão de consentimento não recolhe os dados dos utilizadores diretamente. Apenas importa e processa os dados de consentimento fornecidos pelos utilizadores noutras aplicações.

Para remover dados de consentimento sobre utilizadores específicos, remova-os nas origens de dados ingeridas para a capacidade de gestão de consentimento. Após atualizar a origem de dados, os dados removidos também serão eliminados no Centro de Consentimento. As aplicações que utilizam a entidade de consentimento também eliminarão os dados que foram removidos na origem após uma [atualização](audience-insights/system.md#refresh-processes). Recomendamos atualizar as origens de dados rapidamente após responder a um pedido individual de acesso a dados para remover os dados do utilizador de todos os outros processos e aplicações.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]
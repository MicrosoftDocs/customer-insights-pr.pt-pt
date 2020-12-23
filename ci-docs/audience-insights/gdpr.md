---
title: Pedidos de Direitos de Titulares de Dados (DSR) ao abrigo do RGPD | Microsoft Docs
description: Responder a Pedidos de Titulares de Dados para a capacidade de insights de audiência do Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406636"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Os pedidos de Direitos de Titulares de Dados (DSR) são pedidos sob RGPD

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Responder ao titular dos dados RGPD elimina os pedidos para a capacidade de insights de audiência do Dynamics 365 Customer Insights

O "direito de eliminação" através da remoção de dados pessoais dos dados de cliente de uma organização é uma proteção-chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e registos gerados pelo sistema, exceto as informações de registo de auditoria.

### <a name="manage-data-subject-delete-requests"></a>Gerir pedidos de eliminação do titular de dados

Os insights de audiência oferecem as seguintes experiências no produto para eliminar dados pessoais para um cliente específico ou um utilizador:

- **Gerir pedidos de eliminação de dados de clientes**: os dados dos clientes no Customer Insights são ingeridos a partir das origens de dados originais externas ao Customer Insights. Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados na origem de dados original.
- **Gerir pedidos de eliminação de dados de utilizador do Customer Insights**: Os dados para os utilizadores são criados pela Customer Insights. Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados no Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Gerir pedidos de eliminação de dados dos clientes

Um administrador do Customer Insights pode seguir estes passos para remover os dados do cliente que foram eliminados na origem de dados:

1. Iniciar sessão no Dynamics 365 Customer Insights.
2. Nas informações de audiência, vá a **Dados** > **Origens de dados**
3. Para cada origem de dados na lista que contém dados de clientes eliminados:
   1. Seleccione (...) e, em seguida, selecione **Atualizar**.
   2. Verifique o estado da origem de dados em **Estado**. Uma marca de verificação significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo correu mal. Se for apresentado um triângulo de aviso, contacte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD](media/gdpr-data-sources.png "Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD")

#### <a name="manage-delete-requests-for-user-data"></a>Gerir pedidos de eliminação de dados do utilizador

Um administrador do Customer Insights pode seguir estes passos para eliminar dados dos utilizadores do Customer Insights:

1. Iniciar sessão no Dynamics 365 Customer Insights.
2. Nos insights de audiência, vá a **Admin** > **Permissões**.
3. Selecione a caixa de verificação para o utilizador que pretende eliminar.
4. Selecione **Remover**.

> [!div class="mx-imgBorder"]
> ![Tratamento dos pedidos de eliminação de dados do utilizador da RGPD](media/gdpr-permissions.png "Tratamento dos pedidos de eliminação de dados do utilizador da RGPD ")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder aos pedidos de exportação dos titulares de dados RGPD

Como parte do nosso compromisso de parceria consigo no seu percurso para o Regulamento Geral sobre a Proteção de Dados (RGPD), desenvolvemos documentação para o ajudar a preparar-se. Esta documentação descreve as medidas que pode tomar hoje para apoiar o cumprimento do RGPD ao utilizar os insights da audiência.

### <a name="manage-export-and-view-requests"></a>Gerir pedidos de exportação e visualização

O direito da portabilidade de dados permite aos titulares de dados solicitar uma cópia dos respetivos dados pessoais num formato eletrónico (um "formato estruturado, de utilização comum, de leitura de máquina e interoperável") que poderá ser transmitido para outro controlador de dados.

#### <a name="export-customer-data-tenant-admin"></a>Exportar dados de clientes (administração de inquilinos)

Um administrador pode seguir estes passos para exportar dados:

1. Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do cliente no pedido. A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.
2. Aceite a confirmação para exportar os dados para o cliente pedido.
3. Receba os dados exportados através do endereço de e-mail do administrador de inquilino.

#### <a name="export-user-data-tenant-admin"></a>Exportar dados do utilizador (administração de inquilinos)

1. Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do utilizador no pedido. A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.
2. Aceite a confirmação para exportar os dados para o utilizador pedido.
3. Receba os dados exportados através do endereço de e-mail do administrador de inquilino.

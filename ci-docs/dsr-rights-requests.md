---
title: Pedidos de Direitos de Titulares de Dados (DSR) ao abrigo do RGPD | Microsoft Docs
description: Responda aos Pedidos de Titulares de Dados para o Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808575"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Os pedidos de Direitos de Titulares de Dados (DSR) são pedidos sob RGPD

O Regulamento Geral de Proteção de Dados (RGPD) da União Europeia está em vigor desde 25 de maio de 2018. Confere direitos significativos aos indivíduos relativamente aos seus dados. O RGPD consiste em proteger e ativar os direitos de privacidade de indivíduos. Pode ler mais sobre o compromisso da Microsoft com a segurança e a conformidade no [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Estamos empenhados em ajudar os nossos clientes a cumprir os seus requisitos de RGPD. Inclui o direito de eliminar e exportar dados que incluam informações pessoais, tais como ID de utilizador, números de telefone e endereços de e-mail. Os administradores podem implementar pedidos de utilizador para eliminar ou exportar dados pessoais.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Responder aos pedidos de eliminação do titular de dados ao abrigo do RGPD para o Dynamics 365 Customer Insights

O "direito de eliminação" através da remoção de dados pessoais dos dados de cliente de uma organização é uma proteção-chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e registos gerados pelo sistema, exceto as informações de registo de auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Gerir pedidos de eliminação do titular de dados

O Customer Insights oferece as seguintes experiências no produto para eliminar dados pessoais para um cliente ou um utilizador específico:

- **Gerir pedidos de eliminação de dados de clientes**: os dados dos clientes no Customer Insights são ingeridos a partir das origens de dados originais externas ao Customer Insights. Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados na origem de dados original.
- **Gerir pedidos de eliminação de dados de utilizador do Customer Insights**: Os dados para os utilizadores são criados pela Customer Insights. Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados no Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gerir pedidos para eliminar dados dos clientes

Um administrador do Customer Insights pode seguir estes passos para remover os dados do cliente que foram eliminados na origem de dados:

1. Iniciar sessão no Dynamics 365 Customer Insights.
2. Aceder a **Dados** > **Origens de dados**
3. Para cada origem de dados na lista que contém dados de clientes eliminados:
   1. Selecione as reticências verticais (&vellip;) e, em seguida, selecione **Atualizar**.
   2. Verifique o estado da origem de dados em **Estado**. Uma marca de verificação significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo correu mal. Se for apresentado um triângulo de aviso, contacte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD.](media/gdpr-data-sources.png "Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD")

##### <a name="manage-delete-requests-for-user-data"></a>Gerir pedidos de eliminação de dados do utilizador

Um administrador do Customer Insights pode seguir estes passos para eliminar dados dos utilizadores do Customer Insights:

1. Iniciar sessão no Dynamics 365 Customer Insights.
2. Aceda a **Admin** > **Segurança** > **Permissões**.
3. Selecione a caixa de verificação para o utilizador que pretende eliminar.
4. Selecione **Remover**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder aos pedidos de exportação dos titulares de dados RGPD

Como parte do nosso compromisso de parceria consigo no seu percurso para o Regulamento Geral sobre a Proteção de Dados (RGPD), desenvolvemos documentação para o ajudar a responder a pedidos de titulares de dados.

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

Para remover dados de consentimento sobre utilizadores específicos, remova-os nas origens de dados ingeridas para a capacidade de gestão de consentimento. Após atualizar a origem de dados, os dados removidos também serão eliminados no Centro de Consentimento. As aplicações que utilizam a entidade de consentimento também eliminarão os dados que foram removidos na origem após uma [atualização](system.md#refresh-processes). Recomendamos atualizar as origens de dados rapidamente após responder a um pedido individual de acesso a dados para remover os dados do utilizador de todos os outros processos e aplicações.

[!INCLUDE [footer-include](includes/footer-banner.md)]
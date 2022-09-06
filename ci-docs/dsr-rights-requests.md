---
title: Pedidos de Direitos de Titulares de Dados (DSR) ao abrigo do RGPD | Microsoft Docs
description: Responda aos Pedidos de Titulares de Dados para o Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387125"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Os pedidos de Direitos de Titulares de Dados (DSR) são pedidos sob RGPD

O Regulamento Geral de Proteção de Dados (RGPD) da União Europeia está em vigor desde 25 de maio de 2018. Confere direitos significativos aos indivíduos relativamente aos seus dados. O RGPD consiste em proteger e ativar os direitos de privacidade de indivíduos. Leia mais sobre o compromisso da Microsoft com a segurança e conformidade no [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Estamos empenhados em ajudar os nossos clientes a cumprir os seus requisitos de RGPD. Inclui o direito de eliminar ou exportar dados que incluam informações pessoais, tais como ID de utilizador, números de telefone e endereços de e-mail. Os administradores podem implementar pedidos de utilizador para eliminar ou exportar dados pessoais.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Responder ao titular dos dados RGPD elimina os pedidos para Customer Insights

O "direito de eliminação" através da remoção de dados pessoais dos dados de cliente de uma organização é uma proteção-chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e registos gerados pelo sistema, exceto as informações de registo de auditoria.

### <a name="manage-data-subject-delete-requests"></a>Gerir pedidos de eliminação do titular de dados

O Customer Insights oferece as seguintes experiências no produto para eliminar dados pessoais para um cliente ou um utilizador específico:

- **Gerir pedidos de eliminação de dados de clientes**: os dados dos clientes no Customer Insights são ingeridos a partir das origens de dados originais externas ao Customer Insights. Execute primeiro os pedidos de eliminação ao abrigo do RGPD na origem de dados original.
- **Gerir pedidos de eliminação de dados de utilizador do Customer Insights**: Os dados para os utilizadores são criados pela Customer Insights. Realize todos os pedidos de eliminação no Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Gerir pedidos para eliminar dados dos clientes

Como administrador do Customer Insights, remova os dados do cliente do Customer Insights que foram eliminados na origem de dados- Verifique se os pedidos de eliminação do RGPD foram efetuados na origem de dados original.

1. Iniciar sessão no Dynamics 365 Customer Insights.

1. Aceda a **Dados** > **Origens de dados**.

1. Para cada origem de dados na lista que contém dados de clientes eliminados:
   1. Selecione a origem de dados e selecione **Atualizar**.
   1. Verifique o estado da origem de dados em **Estado**. Uma marca de verificação significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo correu mal. Se for apresentado um triângulo de aviso, contacte D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD.":::

1. Depois de uma atualização de origens de dados bem-sucedida, execute também as atualizações a jusante. Sobretudo, se não tiver uma atualização completa recorrente do Customer Insights agendada.

   > [!IMPORTANT]
   > Os segmentos estáticos não estão incluídos numa atualização completa nem uma execução a jusante é atualizada após um pedido de eliminação. Para assegurar que os dados dos clientes também são removidos dos segmentos estáticos, recrie os segmentos estáticos com os dados de origem atualizados.

#### <a name="manage-delete-requests-for-user-data"></a>Gerir pedidos de eliminação de dados do utilizador

Como administrador do Customer Insights elimine os dados de utilizadores do Customer Insights.

1. Iniciar sessão no Dynamics 365 Customer Insights.

1. Aceda a **Admin** > **Segurança** > e selecione o separador **Utilizadores**.

1. Selecione a caixa de verificação para os utilizadores que pretende eliminar.

1. Selecione **Remover**.

1. Confirme a eliminação.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder aos pedidos de exportação dos titulares de dados RGPD

O direito da portabilidade de dados permite aos titulares de dados solicitar uma cópia dos respetivos dados pessoais num formato eletrónico (um "formato estruturado, de utilização comum, de leitura de máquina e interoperável") que poderá ser transmitido para outro controlador de dados.

### <a name="manage-export-and-view-requests"></a>Gerir pedidos de exportação e visualização

Faça a gestão dos pedidos para exportar dados de clientes ou de utilizadores.

#### <a name="export-customer-data-tenant-admin"></a>Exportar dados de clientes (administração de inquilinos)

Como administrador inquilino, exporte dados dos clientes.

1. Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do cliente no pedido. A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.
2. Aceite a confirmação para exportar os dados para o cliente pedido.
3. Receba os dados exportados através do endereço de e-mail do administrador de inquilino.

#### <a name="export-user-data-tenant-admin"></a>Exportar dados do utilizador (administração de inquilinos)

Como administrador inquilino, exporte dados dos utilizadores.

1. Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do utilizador no pedido. A equipa do Customer Insights envia um e-mail para o endereço de e-mail do administrador inquilino registado, pedindo confirmação para exportar os dados.
1. Aceite a confirmação para exportar os dados para o utilizador pedido.
1. Receba os dados exportados através do endereço de e-mail do administrador de inquilino.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Tratamento da eliminação de dados no Dynamics 365 Customer Insights

Os dados são eliminados (partições de dados e instantâneos de dados) se as partições de dados e os instantâneos de dados estiverem inativos durante mais de 30 dias, o que significa que foram substituídos por uma nova partição de dados e instantâneo através de uma atualização de origens de dados.

Nem todos os dados e instantâneos são eliminados. A partição de dados e o instantâneo de dados mais recentes estão ativos porque são utilizados no Customer Insights. Para os dados mais recentes, não interessa se as origens de dados não foram atualizadas nos últimos 30 dias.

[!INCLUDE [footer-include](includes/footer-banner.md)]

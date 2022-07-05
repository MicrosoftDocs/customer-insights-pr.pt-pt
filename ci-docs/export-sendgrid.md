---
title: Exportar segmentos para o SendGrid (pré-visualização)
description: Aprenda a configurar a ligação e exportar para o SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 669f0fb48b095f6a9faeebf257ee9df3d1c580c7
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081666"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segmentos para o SendGrid (pré-visualização)

Exportar segmentos de perfis unificados de clientes para listas de contactos do SendGrid e utilizá-los para campanhas e marketing de e-mail no SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma ligação

-   Tem uma [conta do SendGrid](https://sendgrid.com/) e credenciais de administrador correspondentes.
-   Existem listas de contactos existentes no SendGrid e IDs correspondentes. Para mais informações, consulte [SendGrid – Gerir contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis unificados dos clientes nos segmentos exportados contêm um campo que representam um endereço de correio eletrónico.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 100.000 perfis de clientes no total para o SendGrid.
- A exportação para o SendGrid está limitada a segmentos.
- A exportação de até 100.000 perfis de clientes para o SendGrid pode levar até algumas horas para ficar concluída. 
- O número de perfis de clientes que pode exportar para o SendGrid está dependente e limitado no seu contrato com o SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Configurar ligação ao SendGrid

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **SendGrid** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira a sua **Chave de API do SendGrid** [Chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Ligar** para inicializar a ligação ao SendGrid.

1. Selecione **Adicione-se como utilizador de exportação** e fornecer as suas credenciais Customer Insights.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Ligação para a exportação**, escolha uma ligação a partir da secção SendGrid. Se não vir este nome de secção, não existem ligações deste tipo disponíveis para si.

1. Insira o seu **[ID da lista SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Na secção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente. Repita os mesmos passos para outros campos opcionais como **Nome próprio**, **Apelido**, **País/Região**, **Estado**, **Cidade** e **Código Postal**.

1. Selecione os segmentos que quer exportar. **Recomendamos que não exporte mais de 100.000 perfis de clientes no total** para o SendGrid. 

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para o SendGrid, permite a transferência de dados fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados a seu pedido, mas você é responsável por garantir que o SendGrid cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Exportar dados do Customer Insights para o Facebook Ads Manager (contém vídeo)
description: Aprenda a configurar a ligação e exportar para o Gestor de Anúncios do Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce1e63f7b20b757780f05895b725003e286f9dac
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/18/2021
ms.locfileid: "7935038"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Lista de segmentos de exportação para o Gestor de Anúncios do Facebook (pré-visualização)

Exportar segmentos de perfis de cliente unificados para o Gestor de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Pré-requisitos para a ligação

- Necessita de ter uma [**Conta Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclua uma [**Conta Empresarial do Facebook**](https://business.facebook.com/).
- Tem de ser um administrador na [**Conta Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 10 milhões de perfis de clientes por exportação para o Gestor de Anúncios do Facebook.
- A exportação para o Gestor de Anúncios do Facebook está limitada a segmentos.
- Crie ou atualize audiências personalizadas apenas no Facebook do tipo *lista de clientes* apenas.
- A exportação de segmentos com um total de 10 milhões de perfis de clientes pode levar até 90 minutos para ficar concluída.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurar ligação ao Gestor de Anúncios do Facebook

Antes de os utilizadores poderem criar uma exportação, um administrador tem de configurar a ligação ao serviço e permitir que os contribuidores utilizem a ligação.

1. Aceda a **Admin** > **Ligações**.

1. Selecione **Adicionar ligação** e escolha **Gestor de Anúncios do Facebook** para configurar a ligação.

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**. O nome e o tipo de ligação descrevem esta ligação. Recomendamos a escolha de um nome que explique o propósito e o destino da ligação.

1. Escolher quem pode utilizar esta ligação. Se não tomar nenhuma ação, a predefinição será Administradores. Para mais informações, consulte [Permitir que os contribuidores utilizem uma ligação para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autenticar com os Anúncios do Facebook: 

   1. Selecione **Continuar com o Facebook** para iniciar sessão na sua conta Facebook Ads.

   1. Permitir a permissão **ads_management** após autenticação com o Facebook.

   1. Selecione a **Conta de Anúncios do Facebook** com que pretende trabalhar.

   1. Selecione uma **Audiência personalizada existente** na lista pendente ou crie uma **Nova audiência personalizada**. Para mais informações, consulte [**Audiências no Gestor de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Com esta exportação, só é possível criar ou atualizar audiências personalizadas no Facebook do tipo *lista de clientes*. Em alguns casos, vê audiências personalizadas de diferentes tipos na lista pendente. A seleção de um tipo diferente de *lista de clientes* resultará numa exportação falhada. 

1. Reveja a **Privacidade e conformidade dos dados** e selecione **Concordo**.

1. Selecione **Guardar** para concluir a ligação.

## <a name="configure-an-export"></a>Configurar uma exportação

Pode configurar esta exportação se tiver acesso a uma ligação deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Aceda a **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**. 

1. Em **Ligação para a exportação**, escolha uma ligação a partir da secção **Gestor de Anúncios do Facebook**. Se não vir este nome de secção, não há ligações deste tipo disponíveis para si.

1. Em **Escolher o campo de identificador de chave**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o Gestor de Anúncios do Facebook. 

1. Forneça um nome reconhecível à ligação no campo **Nome a apresentar**.

1. Mapeie os atributos correspondentes da entidade de cliente unificada para o identificador-chave selecionado.
   > [!TIP]
   > As melhores hipóteses para que uma correspondência ocorra é se selecionar **E-mail** como identificador de chave. A adição de identificadores adicionais pode melhorar a correspondência.

1. Selecione **Adicionar atributo** para mapear mais atributos para enviar para o Gestor de Anúncios do Facebook. Atributos do Gestor de Anúncios do Facebook estão a mapear para os seguintes nomes amigáveis de utilizador: **NP** = **Nome Próprio**, **AP** = **Apelido**, **PI** = **Primeira Inicial**, **TELEFONE** = **Telefone**, **SEX** = **Sexo**, **DN** = **Data de nascimento**, **EST** = **Estado**, **CD** = **Cidade**, **CP** = **Código postal**, **PAÍS** = **País / Região**

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

Guardar uma exportação não executa a exportação imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). 

Também pode [exportar dados a pedido](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Gestor de Anúncios do Facebook, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que os Anúncios do Facebook cumprem quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

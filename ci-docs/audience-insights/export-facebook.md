---
title: Exportar dados Customer Insights para o Facebook Ads Manager
description: Saiba como configurar a ligação ao Gestor de Anúncios do Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596697"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Conector para o Gestor de Anúncios do Facebook (pré-visualização)

Exportar segmentos de perfis de cliente unificados para o Gestor de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.

## <a name="prerequisites"></a>Pré-requisitos

- Precisa de ter uma [**Conta de Anúncio do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclua uma [**Conta Comercial do Facebook**](https://business.facebook.com/).
- Tem de ser um administrador na [**Conta De Anúncio do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Ligar ao Gestor de Anúncios do Facebook

1. Aceda a **Administrador** > **Destinos de exportação**.

1. Em **Gestor de Anúncios do Facebook**, selecione **Configurar**.

1. Forneça um nome reconhecível ao destino de exportação no campo **Nome a apresentar**.

1. Selecione **Continuar com o Facebook** para iniciar sessão na sua Conta de Anúncio do Facebook.

1. Permitir a permissão **ads_management** após autenticação com o Facebook.

1. Selecione a **Conta de Anúncios do Facebook** com que pretende trabalhar.

1. Selecione uma **Audiência personalizada existente** na lista pendente ou crie uma **Nova audiência personalizada**. Para mais informações, consulte [**Audiências no Gestor de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados**.

1. Selecione **Seguinte** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Em **Escolher o campo de identificador de chave**, selecione **E-mail**, **Nome e endereço** ou **Telefone** para enviar para o Gestor de Anúncios do Facebook.

1. Mapeie os atributos correspondentes da entidade de cliente unificada para o identificador-chave selecionado.
   > [DICA] As melhores hipóteses para que uma correspondência ocorra é se selecionar **E-mail** como identificador de chave. A adição de identificadores adicionais pode melhorar a correspondência.

1. Selecione **Adicionar atributo** para mapear atributos adicionais para enviar para o Gestor de Anúncios do Facebook. Atributos do Gestor de Anúncios do Facebook estão a mapear para os seguintes nomes amigáveis de utilizador: **NP** = **Nome Próprio**, **AP** = **Apelido**, **PI** = **Primeira Inicial**, **TELEFONE** = **Telefone**, **SEX** = **Sexo**, **DN** = **Data de nascimento**, **EST** = **Estado**, **CD** = **Cidade**, **CP** = **Código postal**, **PAÍS** = **País / Região**

1. Selecione os segmentos que quer exportar.

1. Selecione **Guardar**.

## <a name="export-the-data"></a>Exportar os dados

Pode [exportar dados a pedido](export-destinations.md). A exportação também será executada com cada [atualização agendada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 10 milhões de perfis de clientes por exportação para o Gestor de Anúncios do Facebook 
- A exportação para o Gestor de Anúncios do Facebook está limitada a segmentos
- Exportar segmentos com um total de 10 milhões de perfis podem levar até 90 minutos para completar

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Gestor de Anúncios do Facebook, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que os Anúncios do Facebook cumprem quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este destino de exportação em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
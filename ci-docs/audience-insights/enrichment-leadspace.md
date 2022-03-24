---
title: Melhoramento dos perfis de empresas com o melhoramento de terceiros Leadspace
description: Informação geral sobre o melhoramento de terceiros Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 0db0c984f6bf9f7ded0704b6fa0caf39c7dace3a
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376798"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecimento de perfis da empresa com Leadspace (pré-visualização)

A Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B. Permite que ambientes com perfis de clientes unificados com base em contas melhorem os seus dados. Melhore os *Perfis de clientes* com atributos como o tamanho da empresa, a localização ou a indústria. Melhore os *Perfis de contacto* com atributos como o cargo, a persona ou a verificação de e-mail.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o Leadspace, devem ser cumpridos os seguintes pré-requisitos:

- Tem uma licença de Leadspace ativa.
- Tem [perfis de clientes unificados](customer-profiles.md) com base em contas.
- Uma ligação Leadspace já foi configurada por um administrador ou tem permissões de [administrador](permissions.md#admin) e a "chave perpétua" (designada por **token Leadspace**). Contacte a [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) diretamente para obter mais detalhes sobre o respetivo produto.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Nos insights de audiência, vá a **Dados** > **Melhoramento**.

1. Selecione **Enriquecer os meus dados** no mosaico da Leadspace e selecione **Começar**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de ecrã do mosaico Leadscape.":::

1. Selecione uma [ligação](connections.md) na lista pendente. Contacte um administrador se não houver nenhuma ligação disponível. Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação** e escolhendo a **Leadspace**. 

1. Selecione **Ligar à Leadspace** para confirmar a ligação.

1. Selecione **Seguinte** e escolha o **Conjunto de dados de cliente** que pretende enriquecer com os dados da empresa da Leadspace. Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. Selecione **Seguinte** e defina que campos dos seus perfis unificados são utilizados para procurar dados da empresa correspondentes a partir da Leadspace. O campo **Nome da empresa** é necessário. Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Website da empresa** e **Localização da empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo Leadspace.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Selecione a caixa de verificação se tiver *Perfis de contacto* que pretendesse melhorar. As informações de audiência mapearão automaticamente os campos obrigatórios.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Melhoramento de registos de contacto Leadspace.":::
 
1. Forneça um nome para o enriquecimento e selecione **Guardar enriquecimento** depois de rever as suas escolhas.


## <a name="configure-the-connection-for-leadspace"></a>Configurar a ligação para a Leadspace 

Tens de ser um administrador para configurar ligações. Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico da Leadspace.

1. Selecione **Começar**. 

1. Introduza um nome para a ligação na caixa **Nome a Apresentar**.

1. Forneça um token da Leadspace válido.

1. Reveja e forneça o seu consentimento para a **Privacidade e conformidade dos dados** selecionando **Concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Guardar**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuração de ligação à Leadspace.":::

## <a name="enrichment-results"></a>Resultados do enriquecimento

Depois de atualizar o enriquecimento, pode rever os dados da empresa recentemente enriquecidos em [Os meus enriquecimentos](enrichment-hub.md). Pode encontrar a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

Para mais informações, consulte [APIs do Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Passos seguintes


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à Leadspace, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Leadspace cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

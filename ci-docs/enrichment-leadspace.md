---
title: Melhoramento dos perfis de empresas com o melhoramento de terceiros Leadspace
description: Informação geral sobre o melhoramento de terceiros Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ca53f15bd7c71b3b4acb396c4daf52d7c7aff9eb
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954193"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecimento de perfis da empresa com Leadspace (pré-visualização)

A Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B. Permite que ambientes com perfis de clientes unificados com base em contas melhorem os seus dados. Melhore os *Perfis de clientes* com atributos como o tamanho da empresa, a localização ou a indústria. Melhore os *Perfis de contacto* com atributos como o cargo, a persona ou a verificação de e-mail.

## <a name="prerequisites"></a>Pré-requisitos

- Uma licença da Leadspace ativa.
- [Perfis de clientes unificados](customer-profiles.md) com base em contas.
- Uma [ligação](connections.md) Leadspace é [configurada](#configure-the-connection-for-leadspace) por um administrador. Contacte a [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) diretamente para obter mais detalhes sobre o respetivo produto.

## <a name="configure-the-connection-for-leadspace"></a>Configurar a ligação para a Leadspace

Tem de ser um [administrador](permissions.md#admin) no Customer Insights e ter a "chave perpétua" (referida como **token da Leadspace**).

1. Selecione **Adicionar ligação** ao configurar um enriquecimento ou vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico da Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuração de ligação à Leadspace.":::

1. Introduza um nome para a ligação e um token da Leadspace válido.

1. Reveja e forneça o seu consentimento para a [Privacidade e conformidade dos dados](#data-privacy-and-compliance) selecionando **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Guardar**.

### <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à Leadspace, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Leadspace cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Melhorar os meus dados** no mosaico **Dados da empresa** da Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de ecrã do mosaico Leadscape.":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione a ligação. Contacte um administrador, caso não esteja nenhuma disponível.

1. Selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar com os dados da empresa da Leadspace. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. Defina o tipo de campos dos seus perfis unificados a utilizar para correspondência: o endereço primário e/ou secundário. Pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis de ambos os endereços separadamente. Por exemplo, para um endereço doméstico e um endereço empresarial. Selecione **Seguinte**.

1. Mapeie os campos para o dados da empresa a partir da Leadspace. O campo **Nome da empresa** é necessário. Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Website da empresa** e **Localização da empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo Leadspace.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Selecione a caixa de verificação se tiver *Perfis de contacto* que pretendesse melhorar. O Customer Insights irá mapear automaticamente os campos necessários.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Melhoramento de registos de contacto Leadspace.":::

1. Selecione **Seguinte**.

1. Forneça um **Nome** para o melhoramento e o **Nome da entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

## <a name="enrichment-results"></a>Resultados do enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Para mais informações, consulte [APIs do Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Próximos passos

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

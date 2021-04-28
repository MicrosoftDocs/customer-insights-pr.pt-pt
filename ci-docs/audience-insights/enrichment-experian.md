---
title: Enriquecimento com o enriquecimento de terceiros Experian
description: Informação geral sobre o enriquecimento de terceiros Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896387"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquecer perfis de clientes com dados demográficos da Experian (pré-visualização)

A Experian é líder global em serviços de marketing e relatórios de crédito para consumidor e empresas. Com os serviços de enriquecimento de dados da Experian, pode criar uma compreensão mais profunda dos seus clientes enriquecendo os seus perfis de clientes com dados demográficos como tamanho da casa, rendimento e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a Experian, devem ser cumpridos os seguintes pré-requisitos:

- Tem uma subscrição ativa da Experian. Para obter uma subscrição, [contacte a Experian](https://www.experian.com/marketing-services/contact) diretamente. [Saiba mais sobre o Enriquecimento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Uma ligação Experian já foi configurada por um administrador *ou* tem permissões de [administrador](permissions.md#administrator). Também precisa do ID de Utilizador, ID de Parte e Número de Modelo para a sua conta ST (Secure Transport) compatível com SSH que a Experian criou para si.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Enriquecer os meus dados** no mosaico da Experian.

   > [!div class="mx-imgBorder"]
   > ![Mosaico da Experian](media/experian-tile.png "Mosaico da Experian")
   > 

1. Selecione uma [ligação](connections.md) na lista pendente. Contacte um administrador se não houver nenhuma ligação disponível. Se for um administrador, pode criar uma ligação selecionando **Adicionar ligação** e escolhendo a Experian na lista pendente. 

1. Selecione **Ligar à Experian** para confirmar a seleção da ligação.

1.  Selecione **Seguinte** e escolha o **Conjunto de dados de cliente** que pretende enriquecer com dados demográficos da Experian. Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. Selecione **Seguinte** e defina que tipos de campos dos seus perfis unificados devem ser utilizados para procurar dados demográficos correspondentes a partir da Experian. Pelo menos, um dos campos **Nome e endereço**, **Telefone** ou **E-mail** é obrigatório. Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos. Esta seleção irá afetar os campos de mapeamento a que tem acesso no próximo passo.

    > [!TIP]
    > Mais atributos de identificadores chave enviados à Experian provavelmente produzem uma taxa de correspondência mais alta.

1. Selecione **Seguinte** para iniciar o mapeamento de campos.

1. Defina que campos dos seus perfis unificados devem ser utilizados para procurar dados demográficos correspondentes a partir da Experian. Os campos obrigatórios estão marcados.

1. Forneça um nome para o enriquecimento e um nome para a entidade de saída.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

## <a name="configure-the-connection-for-experian"></a>Configurar a ligação para a Experian 

Tens de ser um administrador para configurar ligações. Selecione **Adicionar ligação** ao configurar um enriquecimento *ou* vá a **Admin** > **Ligações** e selecione **Configurar** no mosaico da Experian.

1. Selecione **Começar**.

1. Introduza um nome para a ligação na caixa **Nome a Apresentar**.

1. Introduza o ID de Utilizador, o ID de Parte e o Número de Modelo válidos para a sua conta de Experian Secure Transport.

1. Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Guardar**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Painel de configuração de ligação à Experian.":::

## <a name="enrichment-results"></a>Resultados do enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comando. Também pode deixar o sistema executar o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados do seu cliente e dos processos de enriquecimento criados para a sua conta pela Experian.

Após o processo de enriquecimento concluído, pode rever os dados de perfis de clientes recentemente enriquecidos nos **Meus enriquecimentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

## <a name="next-steps"></a>Passos seguintes

Desenvolva a partir dos seus dados de clientes melhorados. Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao Experian, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Experian cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Enriquecimento com o enriquecimento de terceiros Experian
description: Informação geral sobre o enriquecimento de terceiros Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597801"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquecer perfis de clientes com dados demográficos da Experian (pré-visualização)

A Experian é líder global em serviços de marketing e relatórios de crédito para consumidor e empresas. Com os serviços de enriquecimento de dados da Experian, pode criar uma compreensão mais profunda dos seus clientes enriquecendo os seus perfis de clientes com dados demográficos como tamanho da casa, rendimento e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a Experian, devem ser cumpridos os seguintes pré-requisitos:

- Tem uma subscrição ativa da Experian. Para obter uma subscrição, [contacte a Experian](https://www.experian.com/marketing-services/contact) diretamente. [Saiba mais sobre o Enriquecimento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Tem o ID de Utilizador, ID de Grupo e Número de Modelo para a sua conta de Transporte Seguro (ST) ativada por SSH que a Experian criou para si.
- Tem permissões de [Administrador](permissions.md#administrator) nos insights de audiência.

## <a name="configuration"></a>Configuração

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Enriquecer os meus dados** no mosaico da Experian.

   > [!div class="mx-imgBorder"]
   > ![Mosaico da Experian](media/experian-tile.png "Mosaico da Experian")

1. Selecione **Começar** e introduza o ID de Utilizador, o ID de Grupo e o Número de Modelo para a sua conta de Transporte Seguro da Experian. Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**. Confirme todas as entradas selecionando **Aplicar**.

## <a name="map-your-fields"></a>Mapear os seus campos

1.  Selecione **Adicionar dados** e escolha **Conjunto de dados do cliente** que pretende melhorar com os dados demográficos da Experian. Pode selecionar a entidade **Cliente** para melhorar todos os seus perfis de cliente ou selecionar uma entidade de segmento para melhorar apenas os perfis de cliente contidos nesse segmento.

1. Selecione os seus identificadores chave a partir de **Nome e Endereço**, **E-mail** ou **Telefone** para enviar à Experian para a resolução de identidade.

   > [!TIP]
   > Mais atributos de identificadores chave enviados à Experian provavelmente produzem uma taxa de correspondência mais alta.

1. Selecione **Seguinte** e mapeie os atributos correspondentes da sua entidade de cliente unificada para os campos de identificação chave selecionados.

1. Selecione **Adicionar atributo** para mapear quaisquer atributos adicionais que gostaria de enviar à Experian.

1.  Selecione **Guardar** para concluir o mapeamento de campos.

    > [!div class="mx-imgBorder"]
    > ![Mapeamento de campos da Experian](media/experian-field-mapping.png "Mapeamento de campos da Experian")

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
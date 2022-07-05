---
title: Melhore perfis do cliente com demografia a partir da Experian (pré-visualização)
description: Informações gerais sobre o melhoramento de terceiros da Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053035"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Melhore perfis do cliente com demografia a partir da Experian (pré-visualização)

A Experian é um líder global em serviços de relatórios e marketing de crédito ao consumo e às empresas. Com os serviços de melhoramento de dados da Experian, pode obter uma compreensão mais profunda dos seus clientes melhorando os seus perfis com dados demográficos, tal como agregado familiar, rendimento e muito mais.

## <a name="supported-countriesregions"></a>Países/regiões suportados

Atualmente, suportamos apenas o melhoramento de perfis de clientes nos Estados Unidos.

## <a name="prerequisites"></a>Pré-requisitos

- Uma subscrição da Experian ativa. Para obter uma subscrição, [contacte a Experian](https://www.experian.com/marketing-services/contact) diretamente. [Mais informações sobre o Melhoramento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Uma [ligação](connections.md) Experian é [configurada](#configure-the-connection-for-experian) por um administrador.

- ID de Utilizador da Experian, ID da Parte e Número do Modelo da sua conta de Transporte Seguro (ST) compatível com SSH que a Experian criou para si.

## <a name="configure-the-connection-for-experian"></a>Configurar a ligação à Experian

Tem de ser um [administrador](permissions.md#admin) no Customer Insights e ter um ID de Utilizador da Experian, ID de Parte e um Número de Modelo.

1. Selecione **Adicionar ligação** ao configurar um melhoramento ou aceda a **Admin** > **Ligações** e selecione **Configurar** no mosaico da Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Painel de configuração da ligação à Experian.":::

1. Introduza um nome para a ligação e um ID de Utilizador, ID de Parte e Número de Modelo válidos para a sua conta de Transporte Seguro da Experian.

1. Reveja e forneça o seu consentimento para a [Privacidade e conformidade dos dados](#data-privacy-and-compliance) selecionando **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Guardar**.

### <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa o Dynamics 365 Customer Insights para transmitir dados para a Experian, permite a transferência de dados para fora do limite de conformidade para o Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, como Dados Pessoais. A Microsoft transferirá esses dados conforme as suas instruções, mas você é responsável por garantir que a Experian cumpre quaisquer obrigações de privacidade ou de segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). O seu administrador do Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**.

1. Selecione **Melhorar os meus dados** no mosaico **Demografia** da Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Mosaico da Experian na página de descrição geral do melhoramento.":::

1. Reveja a descrição geral e, em seguida, selecione **Seguinte**.

1. Selecione a ligação. Contacte um administrador, caso não esteja nenhuma disponível.

1. Selecione **Seguinte**.

1. Selecione o **Conjunto de dados de clientes** e escolha o perfil ou segmento que pretende melhorar com os dados demográficos da Experian. A entidade *Cliente* melhora todos os seus perfis de cliente, enquanto um segmento melhora apenas os perfis de cliente contidos nesse segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de ecrã de quando escolhe o conjunto de dados do cliente.":::

1. Defina que tipos de campos dos seus perfis unificados utilizar para corresponder dados demográficos da Experian. Pelo menos, um dos campos **Nome e endereço**, **Telefone** ou **E-mail** é obrigatório. Para maior precisão de correspondência, adicione outros campos. Selecione **Seguinte**.

1. Mapeie os seus campos para os dados demográficos a partir da Experian.

1. Selecione **Seguinte** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o melhoramento e o **Nome da entidade de saída**.

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas.

1. Selecione **Executar** para iniciar o processo de melhoramento ou Fechar para regressar à página **Melhoramentos**.

## <a name="view-enrichment-results"></a>Ver resultados de melhoramento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes melhorados por campo** proporciona uma desagregação da cobertura de cada campo melhorado.

## <a name="next-steps"></a>Próximos passos

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]

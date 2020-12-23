---
title: Melhoramento dos perfis de empresas com o melhoramento de terceiros Leadspace
description: Informação geral sobre o melhoramento de terceiros Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668737"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecimento de perfis da empresa com Leadspace (pré-visualização)

A Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B. Permite que os clientes com perfis de clientes unificados para as empresas enriqueçam os seus dados. Os melhoramentos incluem atributos adicionais tais como tamanho da empresa, localização, indústria, e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o Leadspace, devem ser cumpridos os seguintes pré-requisitos:

- Tem uma licença Leadspace ativa e a "chave perpétua" (referida como **token Leadspace**). Contacte diretamente a [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obter mais detalhes sobre o seu produto.
- Tem permissões de [Administrador](permissions.md#administrator).
- Tem [perfis de clientes unificados](customer-profiles.md) para empresas.

## <a name="configuration"></a>Configuração

1. Nos insights de audiência, vá a **Dados** > **Melhoramento**.

1. Selecione **Enriquecer os meus dados** no mosaico Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de ecrã do mosaico Leadscape.":::

1. Selecione **Iniciar** e depois introduzir um **token Leadspace** ativo (chave perpétua). Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**. Confirmar ambas as entradas, selecionando **Ligar a Leadspace**.

1. Selecione **Dados do mapa** e definir quais os campos dos seus perfis unificados que devem ser utilizados para procurar os dados correspondentes da empresa a partir da Leadspace. O campo **Nome da empresa** é necessário. Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Website da empresa** e **Localização da empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo Leadspace.":::
   
1. Selecione **Aplicar** para completar o mapeamento de campo.

1. Selecione **Executar** para enriquecer os perfis da empresa. A duração de um melhoramento depende do número de perfis unificados de clientes.

## <a name="enrichment-results"></a>Resultados do enriquecimento

Depois de atualizar o enriquecimento, pode rever os dados da empresa recentemente enriquecidos em [Os meus enriquecimentos](enrichment-hub.md). Pode encontrar a hora da última atualização e o número de perfis enriquecidos.

Pode aceder a uma visão detalhada de cada perfil enriquecido selecionando **Ver dados enriquecidos**.

Para mais informações, consulte [APIs do Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Passos seguintes

Desenvolva a partir dos seus dados de clientes melhorados. Crie [segmentos](segments.md), [medidas](measures.md) e até [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados

Quando ativa Dynamics 365 Customer Insights para transmitir dados à Leadspace, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá tais dados sob as suas instruções, mas o utilizador é responsável por assegurar que a Leadspace cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para obter mais informações, consulte [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade.
---
title: Conector do Power Apps (pré-visualização)
description: Ligar com o Power Apps e Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196914"
---
# <a name="power-apps-connector-preview"></a>Conector do Power Apps (pré-visualização)

Integre os perfis de clientes unificados nas suas aplicações personalizadas com o Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Ligar ao Power Apps e a Dynamics 365 Customer Insights

O Customer Insights é uma das muitas [origens disponíveis para os dados no Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte a documentação do Power Apps para saber como [adicionar uma ligação de dados a uma aplicação](/powerapps/maker/canvas-apps/add-data-connection). Recomendamos que também reveja [como o Power Apps usa a delegação usa para lidar com grandes conjuntos de dados em Aplicações de tela](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades disponíveis

Depois de adicionar o Customer Insights como uma ligação de dados, escolha as seguintes entidades no Power Apps:

- **Cliente**: para utilizar os dados do [perfil do cliente unificado](customer-profiles.md).
- **UnifiedActivity**: para apresentar a [linha cronológica da atividade](activities.md) na aplicação.
- **ContactProfile**: para apresentar os contactos de um cliente. Esta entidade está disponível apenas em ambientes do Customer Insights para contas empresariais.

## <a name="limitations"></a>Limitações

### <a name="retrievable-entities"></a>Entidades que pode obter

Só pode obter as entidades **Cliente**, **UnifiedActivity**, **Segmentos** e **ContactProfile** através do conector do Power Apps. ContactProfile está disponível apenas em ambientes do Customer Insights para contas empresariais. Outras entidades são mostradas porque o conector subjacente as suporta através de acionadores no Power Automate.

Pode fazer um máximo de 100 chamadas por cada 60 segundos. Pode chamar o ponto final de API várias vezes ao utilizar o parâmetro $skip. [Saiba mais sobre o parâmetro $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegação

A delegação trabalha para a entidade **Cliente** e entidade **UnifiedActivity**.

- Delegação para a entidade **Cliente**: Para utilizar a delegação para esta entidade, os campos precisam de ser indexados em [Índice procurar e filtrar](search-filter-index.md).  
- Delegação para **UnifiedActivity**: a delegação para esta entidade só funciona para os campos **ActivityId** e **CustomerId**.  
- Delegação para **ContactProfile**: a delegação para esta entidade só funciona para os campos **ContactId** e **CustomerId**. ContactProfile está disponível apenas em ambientes do Customer Insights para contas empresariais.

Para mais informações sobre a delegação, aceda a [funções e operações delegáveis do Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Exemplo de controlo de galeria

Opcionalmente, adicione perfis de clientes a um [controlo de galeria](/powerapps/maker/canvas-apps/add-gallery).

1. Adicione um controlo de **galeria** a uma aplicação que esteja a criar.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Adicionar um elemento de galeria.":::

1. Selecione **Cliente** como origem de dados para os itens.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Selecionar uma origem de dados.":::

1. Altere o painel de dados à direita para selecionar o campo que a entidade Cliente vai mostrar na galeria.

1. Se pretende mostrar qualquer campo do cliente selecionado na galeria, preencha a propriedade **Texto** de uma etiqueta utilizando **{Name_of_the_gallery}.Selecionado.{property_name}**  
    - Por exemplo: _Gallery1.Selected.address1_city_

1. Para apresentar a linha cronológica unificada para um cliente, adicione um elemento de galeria e adicione a propriedade **Itens** utilizando **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Por exemplo: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]

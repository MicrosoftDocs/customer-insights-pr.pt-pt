---
title: Conector do Power Apps
description: Ligar com o Power Apps e Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031809"
---
# <a name="microsoft-power-apps-connector-preview"></a>Conector do Microsoft Power Apps (pré-visualização)

Integre os perfis de clientes unificados nas suas aplicações personalizadas com o Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Ligar ao Power Apps e a Dynamics 365 Customer Insights

O Customer Insights é uma das muitas [origens disponíveis para os dados no Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte a documentação do Power Apps para saber como [adicionar uma ligação de dados a uma aplicação](/powerapps/maker/canvas-apps/add-data-connection). Recomendamos que também reveja [como o Power Apps usa a delegação usa para lidar com grandes conjuntos de dados em Aplicações de tela](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades disponíveis

Depois de adicionar o Customer Insights como uma ligação de dados, poderá escolher as seguintes entidades no Power Apps:

- Cliente: para utilizar os dados do [perfil de cliente unificado](customer-profiles.md).
- UnifiedActivity: para apresentar a [linha cronológica de atividade](activities.md) na aplicação.

## <a name="limitations"></a>Limitações

### <a name="retrievable-entities"></a>Entidades que pode obter

Só é possível obter as entidades **Cliente**, **UnifiedActivity** e **Segmentos** através do conector Power Apps. Outras entidades são mostradas porque o conector subjacente as suporta através de acionadores no Power Automate.  

### <a name="delegation"></a>Delegação

A delegação trabalha para a entidade Cliente e entidade UnifiedActivity. 

- Delegação para a entidade **Cliente**: Para utilizar a delegação para esta entidade, os campos precisam de ser indexados em [Índice procurar e filtrar](search-filter-index.md).  

- Delegação para **UnifiedActivity**: a delegação para esta entidade só funciona para os campos **ActivityId** e **CustomerId**.  

- Para obter mais informações sobre a delegação, consulte [Funções e operações delegatáveis do Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Exemplo de controlo de galeria

Por exemplo, adiciona perfis de clientes a um [controlo da galeria](/powerapps/maker/canvas-apps/add-gallery).

1. Adicione um controlo **Galeria** a uma aplicação que esteja a criar.

> [!div class="mx-imgBorder"]
> ![Adicionar um elemento de galeria.](media/connector-powerapps9.png "Adicionar um elemento de galeria")

1. Selecione **Cliente** como origem de dados para os itens.

    > [!div class="mx-imgBorder"]
    > ![Selecionar uma origem de dados.](media/choose-datasource-powerapps.png "Selecionar uma origem de dados")

1. Pode alterar o painel de dados à direita para selecionar o campo que a entidade Cliente vai mostrar na galeria.

1. Se pretende mostrar qualquer campo do cliente selecionado na galeria, preencha a propriedade Texto de uma etiqueta:  **{Name_of_the_gallery}.Selecionado.{property_name}**

    Exemplo: Galeria1.Selecionada.address1_city

1. Para apresentar a linha cronológica unificada para um cliente, adicione um elemento Galeria e adicione a propriedade Itens: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Exemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
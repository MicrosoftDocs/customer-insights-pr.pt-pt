---
title: Conector do Power Apps
description: Ligar com o Power Apps e Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 18cc32a169e79794d2d3203d462620ab41efaafe
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455966"
---
# <a name="microsoft-power-apps-connector-preview"></a>Conector do Microsoft Power Apps (pré-visualização)

Integre os perfis de clientes unificados nas suas aplicações personalizadas com o Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Ligar ao Power Apps e a Dynamics 365 Customer Insights

O Customer Insights é uma das muitas [origens disponíveis para os dados no Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte a documentação do Power Apps para saber como [adicionar uma ligação de dados a uma aplicação](/powerapps/maker/canvas-apps/add-data-connection). Recomendamos que também reveja [como o Power Apps usa a delegação usa para lidar com grandes conjuntos de dados em Aplicações de tela](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades disponíveis

Depois de adicionar o Customer Insights como uma ligação de dados, poderá escolher as seguintes entidades no Power Apps:

- **Cliente**: para utilizar os dados do [perfil do cliente unificado](customer-profiles.md).
- **UnifiedActivity**: para apresentar a [linha cronológica da atividade](activities.md) na aplicação.
- **ContactProfile**: para apresentar os contactos de um cliente. Esta entidade está disponível apenas em ambientes de informações de audiência para contas empresariais.

## <a name="limitations"></a>Limitações

### <a name="retrievable-entities"></a>Entidades que pode obter

Só pode obter as entidades **Cliente**, **UnifiedActivity**, **Segmentos** e **ContactProfile** através do conector do Power Apps. ContactProfile está disponível apenas na instância das informações de audiência para contas empresariais. Outras entidades são mostradas porque o conector subjacente as suporta através de acionadores no Power Automate.

Pode fazer um máximo de 100 chamadas por cada 60 segundos. Pode chamar o ponto final de API várias vezes ao utilizar o parâmetro $skip. [Saiba mais sobre o parâmetro $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegação

A delegação trabalha para a entidade **Cliente** e entidade **UnifiedActivity**. 

- Delegação para a entidade **Cliente**: Para utilizar a delegação para esta entidade, os campos precisam de ser indexados em [Índice procurar e filtrar](search-filter-index.md).  
- Delegação para **UnifiedActivity**: a delegação para esta entidade só funciona para os campos **ActivityId** e **CustomerId**.  
- Delegação para **ContactProfile**: a delegação para esta entidade só funciona para os campos **ContactId** e **CustomerId**. ContactProfile está disponível apenas em ambientes de informações de audiência para contas empresariais.

Para mais informações sobre a delegação, aceda a [funções e operações delegáveis do Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Exemplo de controlo de galeria

Pode adicionar perfis de clientes a um [controlo de galeria](/powerapps/maker/canvas-apps/add-gallery).

1. Adicione um controlo de **galeria** a uma aplicação que esteja a criar.

    > [!div class="mx-imgBorder"]
    > ![Adicionar um elemento de galeria.](media/connector-powerapps9.png "Adicione um elemento de galeria.")

2. Selecione **Cliente** como origem de dados para os itens.

    > [!div class="mx-imgBorder"]
    > ![Selecionar uma origem de dados.](media/choose-datasource-powerapps.png "Selecione uma origem de dados.")

3. Pode alterar o painel de dados à direita para selecionar o campo que a entidade Cliente vai mostrar na galeria.

4. Se pretende mostrar qualquer campo do cliente selecionado na galeria, preencha a propriedade **Texto** de uma etiqueta utilizando **{Name_of_the_gallery}.Selecionado.{property_name}**  
    - Por exemplo: _Gallery1.Selected.address1_city_

5. Para apresentar a linha cronológica unificada para um cliente, adicione um elemento de galeria e adicione a propriedade **Itens** utilizando **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Por exemplo: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]

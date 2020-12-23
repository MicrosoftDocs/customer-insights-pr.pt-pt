---
title: Mapear entidades para unificação de dados
description: Mapear dados para criar perfis unificados de clientes.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406642"
---
# <a name="map-entities-and-attributes"></a>Mapear entidades e atributos

**Mapa** é a primeira etapa no processo de unificação de dados de informações de audiência. O mapeamento consiste em três fases:

- *Seleção de Entidades*: identificar as entidades combináveis que levam a uma conjunto de dados com informações mais completas sobre os seus clientes.
- *Seleção de atributos*: para cada entidade, identifique as colunas que pretende combinar e reconciliar nas fases de *correspondência* e *intercalação*. Estas colunas chamam-se *Atributos*.
- *Chave primária e seleção de tipo semântico*: para cada entidade, identifique um atributo que pretende definir como a chave primária para essa entidade e, para cada atributo, identifique um tipo semântico que melhor descreve esse atributo.

Para obter mais informações sobre o fluxo geral da unificação de dados, consulte [Unificar](data-unification.md).

## <a name="select-the-first-entities"></a>Selecionar as primeiras entidades

1. Nas informações de audiência, vá a **Dados** > **Unificar** > **Mapa**.

2. Inicie a fase de mapeamento ao selecionar **Selecionar entidades**.

3. Selecione as entidades e atributos que pretende utilizar nas fases de *correspondência* e *união*. Pode selecionar os atributos exigidos individualmente a partir de uma entidade ou incluir todos os atributos de uma entidade selecionando a caixa de verificação **Incluir todos os campos** ao nível da entidade. Recomendamos que selecione pelo menos duas entidades para beneficiar do processo de unificação de dados.

   > [!div class="mx-imgBorder"]
   > ![Exemplo de Adicionar entidades](media/data-manager-configure-map-add-entities-example.png "Exemplo de Adicionar entidades")

   Neste exemplo, estamos a adicionar as entidades **eCommerceContacts** e **loyCustomers**. Ao escolher estas entidades, pode obter informações sobre quais dos clientes de negócios online são membros do programa de fidelização.
   
   Pode pesquisar palavras-chave em todos os atributos e entidades para selecionar os atributos necessários que pretende mapear.
   
     > [!div class="mx-imgBorder"]
   > ![Exemplo de campos de pesquisa](media/data-manager-configure-map-search-fields-example.png "Exemplo de campos de pesquisa")

4. Selecione **Aplicar** para confirmar as suas seleções.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selecionar chave primária e tipo semântico para atributos

Depois de selecionar as suas entidades, a página **Mapa** lista as entidades selecionadas para a sua revisão. Defina a chave primária para uma entidade e identifique o tipo semântico para um atributo na entidade.

- **Chave primária**: selecione um atributo como chave primária para cada uma das entidades. Para que um atributo seja uma chave primária válida, não deve incluir valores duplicados, valores em falta ou valores nulos. Os atributos do tipo de dados cadeia, número inteiro e GUID são suportados como chaves primárias e serão exibidos num campo para selecionar.

- **Tipo de atributo semântico**: categorias dos seus atributos, tais como endereço de e-mail ou nome. Para utilizar modelos de IA para predição inteligente de semântica, poupar tempo e melhorar a precisão, defina **Mapeamento inteligente** para **ATIVADO**. O mapeamento inteligente destaca a recomendação de semântica baseada em IA no campo **Tipo**. Se o definir como **DESATIVADO**, verá as nossas recomendações regulares de mapeamento. Pode selecionar qualquer tipo semântico da lista de opções disponíveis e anular a seleção sugerida.

> [!div class="mx-imgBorder"]
> ![Tipo de atributo e predição semântica](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo de atributo e predição semântica")

Também é possível adicionar um tipo semântico personalizado. Selecione o campo de tipo para um atributo e escreva o nome do tipo semântico personalizado. Desta forma, também pode alterar os tipos de atributo que foram identificados pelo sistema.

Todos os atributos para os quais um tipo semântico é automaticamente identificado são agrupados na secção **Rever campos mapeados**. Reveja estes atributos e os seus tipos semânticos porque serão usados para combinar as suas entidades no passo de união da unificação de dados.

Os atributos que não são automaticamente mapeados para um tipo semântico são agrupados na secção **Definir dados nos campos não mapeados**. Selecione o campo de tipo semântico para os atributos não mapeados ou introduza o seu nome de atributo personalizado.

> [!div class="mx-imgBorder"]
> ![Chave primária e tipo de atributo](media/data-manager-configure-map-add-attributes.png "Chave primária e tipo de atributo")

> [!NOTE]
> Um campo deve mapear para o tipo semântico Person.FullName para preencher o nome do cliente no cartão de cliente. Caso contrário, os cartões do cliente serão apresentados sem nome. 

## <a name="add-and-remove-attributes-and-entities"></a>Adicionar e remover atributos e entidades

1. Em **Unificar** > **Mapa**, selecione **Editar campos**.

2. No painel **Editar campos**, adicione ou remova atributos e entidades. Utilize a pesquisa ou percorra para encontrar e selecionar os seus atributos e entidades de interesse. Não se pode remover um atributo ou uma entidade se já foram combinados.

   > [!div class="mx-imgBorder"]
   > ![Adicionar ou remover atributos](media/configure-data-map-edit.png "Adicionar ou remover atributos")

3. Selecione **Aplicar**.

## <a name="add-images-to-profiles"></a>Adicionar imagens a perfis

Se uma entidade contiver URLs para logótipos ou imagens de perfil disponíveis publicamente, poderá adicioná-los ao perfil do cliente unificado.

Selecione a entidade e localize o campo que contém o URL para a imagem de perfil. No campo de texto **Tipo**, introduza manualmente o seguinte valor: 
- Para uma pessoa: Person.ProfileImage
- Para uma organização: Organization.LogoImage

Continue com os passos de unificação e certifique-se de que o atributo que contém o URL de imagem também é adicionado no passo [Unir](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Definir atributos para as organizações

Para as organizações (Pré-visualização), o tipo de atributo deve ser mapeado para "Nome.Organização"
> [!div class="mx-imgBorder"]
> ![Chave primária e tipo de atributo B2B](media/configure-data-map-edit-b2b.png "Chave primária e tipo de atributo B2B")

## <a name="next-step"></a>Passo seguinte

Como parte do processo de unificação dos dados, vá para a página **Corresponder**. Visite [**Corresponder**](match-entities.md) para saber mais sobre esta fase.

> [!TIP]
> Veja o seguinte vídeo: [Introdução: Criar um Perfil de Cliente Unificado](https://youtu.be/oBfGEhucAxs).

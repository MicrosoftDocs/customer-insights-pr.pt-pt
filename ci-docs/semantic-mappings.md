---
title: Mapeamentos de semânticas (pré-visualização)
description: Descrição geral dos mapeamentos semânticos e como utilizá-los.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303890"
---
# <a name="semantic-mappings-preview"></a>Mapeamentos de semânticas (pré-visualização)

> [!NOTE]
> A página **Mapeamentos semânticos** só está disponível para ambientes de negócio (B2B) nos quais os perfis de contacto já tenham sido criados utilizando esta página. Pode continuar a criar e gerir os perfis de contactos individuais utilizando a página **Mapeamentos semânticos**. Ou [unificar os dados dos seus contactos](data-unification-contacts.md) para remover duplicados, identificar correspondências entre entidades e criar um perfil de contacto unificado. Pode então utilizar o perfil de contacto unificado para criar atividades ao nível do contacto.

Os mapeamentos semânticos permitem mapear os seus dados de não atividade para esquemas predefinidos. Estes esquemas ajudam o Customer Insights a compreender melhor os seus atributos de dados. O mapeamento semântico e os dados fornecidos permitem novas informações e funcionalidades no Customer Insights. Para mapear os seus dados de atividade para os esquemas, reveja a documentação das [atividades](activities.md).

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir um mapeamento de entidade semântico ContactProfile

1. Aceda a **Dados** > **Mapeamentos de semânticas (pré-visualização)**.

1. Selecione **Adicionar mapeamento semântico** para iniciar a experiência guiada.

1. No passo **Dados da entidade**, defina os valores para os seguintes campos:

   - **Nome do mapeamento de entidades de semântica**: nome para o o mapeamento de entidades de semântica.
   - **Entidade de Origem**: entidade que inclui dados de contacto.
   - **Chave primária**: campo que identifica exclusivamente um registo de contacto. Não deve conter valores duplicados, valores vazios ou valores em falta.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configure o mapeamento de entidade semântico com o nome, a entidade de origem e a chave primária.":::

1. Selecione **Seguinte**.

1. No passo **Relações**, configure os detalhes para ligar os dados de contacto aos respetivos dados da conta. Este passo visualiza a ligação entre entidades.  

   Existem dois tipos de caminhos de relação que podem ser implementados: **Relações diretas** e **Relações indiretas**. Para mais informações, aceda a [caminhos de relação direta e indireta](relationships.md#relationship-paths).

   1. Selecione **Adicionar Relação** para configurar a relação.
   1. Escolha o atributo da sua entidade de origem que liga a sua entidade de contacto a outra entidade.
   1. Escolha a entidade para ligar a sua entidade de contacto. Escolha uma entidade a partir da secção **Entidades de conta** ou **Entidades intermediárias**. Se selecionar uma entidade intermediária, defina uma segunda relação para se ligar à sua entidade de conta de destino.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selecione uma entidade de Conta ou uma entidade Intermediária.":::

   1. Forneça um **Nome da relação**. Se já existir uma relação entre as suas entidades, o nome da relação é só de leitura. Se não existir uma relação, será criada uma nova relação com o nome que fornecer.
   1. Selecione **Aplicar** para terminar a configuração da relação.

   > [!NOTE]
   > Pode configurar mais relações entre a entidade de contacto e outras entidades de conta com entidades intermediárias.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="A visualização de várias relações que ligam as entidades de contacto a entidades de conta.":::

1. Selecione **Seguinte**.

1. No passo **Definir o tipo semântico**, escolha um **Tipo semântico**. Atualmente, existe um **Tipo Semântico** chamado *ContactProfile*.

1. Mapeie o seu ID de contacto para o **ID de Contacto** com o tipo de semântica *ContactProfile*. Opcionalmente, mapeie outros campos, como o nome próprio, o apelido, o sexo ou o e-mail.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapeie os seus atributos de dados de contacto para os campos obrigatórios e opcionais.":::

1. Selecione **Seguinte**.

1. No passo **Revisão**, reveja a configuração do mapeamento de semânticas. Para fazer alterações, selecione **Editar** para a secção correspondente.

1. Selecione **Guardar**.

1. Para processar o mapeamento de semânticas, selecione **Executar**. Ou selecione **Fechar** para guardar o mapeamento de semânticas sem o processar. Para o executar num momento posterior, selecione o mapeamento de semânticas e selecione **Atualizar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Gerir mapeamentos semânticos existentes

Vá para **Dados** > **Mapeamentos de semânticas (pré-visualização)** para ver os mapeamentos de semânticas guardados, a respetiva entidade de origem, o tipo de semântica, o tipo de mapeamento e o estado.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opções para gerir mapeamentos semânticos.":::

Selecione o mapeamento de semânticas para ver as ações disponíveis.
- **Editar** a configuração atual. Selecione **Guardar** e **Executar** para processar as alterações.
- **Atualizar** o mapeamento de semânticas para incluir os dados mais recentes. A atualização de qualquer mapeamento semântico irá atualizar todos os mapeamentos semânticos do mesmo tipo.
- **Mudar o nome** do mapeamento de semânticas. Selecione **Guardar**.
- **Eliminar** o mapeamento de semânticas. Para eliminar mais de um mapeamento de semânticas ao mesmo tempo, selecione os mapeamentos de semânticas e o ícone de eliminação. Selecione **Eliminar** para confirmar a eliminação.

[!INCLUDE [footer-include](includes/footer-banner.md)]

---
title: Mapeamentos semânticos (pré-visualização)
description: Descrição geral dos mapeamentos semânticos e como utilizá-los.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622949"
---
# <a name="semantic-mappings"></a>Mapeamentos semânticos

Os mapeamentos semânticos permitem mapear os seus dados de não atividade para esquemas predefinidos. Estes esquemas ajudam as informações de audiência a compreender melhor os seus atributos de dados. O mapeamento semântico e os dados fornecidos permitem novas informações e funcionalidades nas informações de audiência. Para mapear os seus dados de atividade para os esquemas, reveja a documentação das [atividades](activities.md).

**Os mapeamentos semânticos estão atualmente ativados para os ambientes baseados em contas empresariais**. *ContactProfile* é o único tipo de mapeamento semântico atualmente disponível nas informações de audiência.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir um mapeamento de entidade semântico ContactProfile

1. Em informações de audiência, aceda a **Dados** > **Mapeamentos semânticos (pré-visualização)**.

1. Selecione **Adicionar mapeamento semântico** para iniciar a experiência guiada.

1. No passo **Dados da entidade**, defina os valores para os seguintes campos:

   - **Nome do mapeamento de entidade semântico**: forneça um nome ao mapeamento de entidade semântico.
   - **Entidade de Origem**: selecione uma entidade que inclua dados de contacto.
   - **Chave primária**: selecione o campo que identifica exclusivamente um registo de contacto. Não deve conter valores duplicados, valores vazios ou valores em falta.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configure o mapeamento de entidade semântico com o nome, a entidade de origem e a chave primária.":::

1. Selecione **Seguinte** para continuar.

1. No passo **Relações**, configure os detalhes para ligar os dados de contacto aos respetivos dados da conta. Este passo visualiza a ligação entre entidades.  

   Existem dois tipos de caminhos de relação que podem ser implementados: **Relações diretas** e **Relações indiretas**. Para mais informações, aceda a [caminhos de relação direta e indireta](relationships.md#relationship-paths).

   1. Selecione **Adicionar Relação** para configurar a relação.
   1. Escolha o atributo da sua entidade de origem que liga a sua entidade de contacto a outra entidade.
   1. Escolha a entidade para ligar a sua entidade de contacto. Pode escolher uma entidade a partir da secção **Entidades de conta** ou **Entidades intermediárias**. Se selecionar uma entidade intermediária, tem de definir uma segunda relação para se ligar à sua entidade de conta de destino.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selecione uma entidade de Conta ou uma entidade Intermediária.":::

   1. Forneça um **Nome da relação**. Se já existir uma relação entre as suas entidades, o nome da relação é só de leitura. Se não existir uma relação, será criada uma nova relação com o nome que fornecer.
   1. Selecione **Aplicar** para terminar a configuração da relação.

   > [!NOTE]
   > Pode configurar mais relações entre a entidade de contacto e outras entidades de conta com entidades intermediárias.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="A visualização de várias relações que ligam as entidades de contacto a entidades de conta.":::

1. Selecione **Seguinte** quando concluir a configuração da relação.

1. No passo **Definir o tipo semântico**, escolha um **Tipo semântico**. Atualmente, existe um **Tipo Semântico** chamado *ContactProfile*.

1. Mapeie os seus dados para o **Tipo semântico** *ContactProfile* para os campos mostrados.
   - Campo obrigatório: ID do Contacto
   - Campos Opcionais: Nome próprio, Apelido, Data de nascimento, Sexo, E-mail principal e Telefone principal

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapeie os seus atributos de dados de contacto para os campos obrigatórios e opcionais.":::

1. Selecione **Seguinte** para continuar.

1. No passo **Revisão**, veja a configuração do mapeamento semântico. Selecione **Editar** para a secção correspondente para efetuar alterações.

1. Selecione **Guardar** para guardar o seu novo **Mapeamento semântico**.

1. Depois de guardar, pode selecionar **Executar** para processar o mapeamento semântico ou pode selecionar **Fechar** para guardar o mapeamento semântico sem o processar.

1. Para executar um mapeamento semântico num momento posterior, selecione o mapeamento semântico e selecione **Atualizar**.

> [!TIP]
> Há [seis tipos de estados](system.md#status-types) para tarefas/processos. Além disso, a maior parte dos processos [depende de outros processos a jusante](system.md#refresh-policies). Poderá selecionar o estado de um processo para ver os detalhes do progresso de toda a tarefa. Depois de selecionar **Ver detalhes** de uma das tarefas do trabalho, encontra informações adicionais: tempo de processamento, última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="manage-existing-semantic-mappings"></a>Gerir mapeamentos semânticos existentes

Em **Dados** > **Mapeamentos semânticos (pré-visualização)**, pode ver todos os seus mapeamentos semânticos guardados e geri-los. Cada mapeamento semântico é representado por uma linha separada. Encontrará os detalhes sobre a entidade de origem, o tipo semântico, o tipo de mapeamento e o respetivo estado.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opções para gerir mapeamentos semânticos.":::

- **Editar**: abre a configuração do mapeamento semântico no passo de revisão. Pode alterar a configuração atual. Selecione **Guardar** e **Executar** para processar as alterações.

- **Atualizar**: atualiza o mapeamento semântico selecionado com os dados mais atualizados das entidades que fazem parte da sua configuração. A atualização de qualquer mapeamento semântico irá atualizar todos os mapeamentos semânticos do mesmo tipo.

- **Mudar o nome**: abre um diálogo onde pode introduzir um nome diferente para o mapeamento semântico selecionado. Selecione **Guardar** para aplicar as alterações.

- **Eliminar**: abre um diálogo para confirmar a eliminação do mapeamento semântico selecionado. Também pode eliminar mais de um mapeamento semântico ao mesmo tempo, selecionando os mapeamentos semânticos e o ícone de eliminação. Selecione **Eliminar** para confirmar a eliminação.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

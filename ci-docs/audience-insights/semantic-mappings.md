---
title: Mapeamentos semânticos (pré-visualização)
description: Descrição geral dos mapeamentos semânticos e como utilizá-los.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 37696f3e82eb9b75fbf9f78363adc890891efcc3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353971"
---
# <a name="semantic-mappings-preview"></a>Mapeamentos semânticos (pré-visualização)

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Gerir mapeamentos semânticos existentes

Em **Dados** > **Mapeamentos semânticos (pré-visualização)**, pode ver todos os seus mapeamentos semânticos guardados e geri-los. Cada mapeamento semântico é representado por uma linha separada. Encontrará os detalhes sobre a entidade de origem, o tipo semântico, o tipo de mapeamento e o respetivo estado.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opções para gerir mapeamentos semânticos.":::

- **Editar**: abre a configuração do mapeamento semântico no passo de revisão. Pode alterar a configuração atual. Selecione **Guardar** e **Executar** para processar as alterações.

- **Atualizar**: atualiza o mapeamento semântico selecionado com os dados mais atualizados das entidades que fazem parte da sua configuração. A atualização de qualquer mapeamento semântico irá atualizar todos os mapeamentos semânticos do mesmo tipo.

- **Mudar o nome**: abre um diálogo onde pode introduzir um nome diferente para o mapeamento semântico selecionado. Selecione **Guardar** para aplicar as alterações.

- **Eliminar**: abre um diálogo para confirmar a eliminação do mapeamento semântico selecionado. Também pode eliminar mais de um mapeamento semântico ao mesmo tempo, selecionando os mapeamentos semânticos e o ícone de eliminação. Selecione **Eliminar** para confirmar a eliminação.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utilize um mapeamento de entidades de semântica ContactProfile para criar atividades de nível de contacto

Depois de criar um *ContactProfile* mapeamento de entidades de semântica, pode capturar as atividades dos contactos. Permite-lhe ver na linha cronológica da atividade para uma conta cujo contacto foi responsável por cada atividade. A maioria dos passos segue a configuração típica do mapeamento de atividades.

   > [!NOTE]
   > Para as atividades de nível de contacto funcionarem, tem de ter os atributos **AccountID** e **ContactID** para cada registo nos seus dados de atividade.

1. [Definir um mapeamento de entidades de semântica *ContactProfile*.](#define-a-contactprofile-semantic-entity-mapping) e executar o mapeamento de semânticas.

1. Em informações de audiência, aceda a **Dados** > **Atividades**.

1. Selecione **Adicionar Atividade** para criar uma nova atividade.

1. Atribua um nome à atividade, selecione a entidade de atividade de origem e selecione a chave primária da entidade de atividade.

1. No passo **Relações**, crie uma relação indireta entre os dados de origem da sua atividade para as contas, utilizando os seus dados de contacto como uma entidade intermediária. Para mais informações, consulte os [caminhos de relação direta e indireta](relationships.md#relationship-paths).
   - Relação de exemplo para uma atividade denominada *Compras*:
      - **Dados de Atividade da Origem das Compras** > **Dados do Contacto** no atributo **ContactID**
      - **Dados do Contacto** > **Dados da Conta** no atributo **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Configuração de uma relação de exemplo.":::

1. Depois de configurar as relações, selecione **Seguinte** e conclua a configuração do mapeamento da sua atividade. Para obter os passos detalhados na criação da atividade, consulte [definir uma atividade](activities.md).

1. Execute os seus mapeamentos de atividades.

1. As suas atividades de nível de contacto estarão agora visíveis na linha cronológica do seu cliente.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultado final depois de configurar as atividade do contacto":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtragem da linha cronológica das atividades a nível do contacto

Depois de configurar um mapeamento de atividade a nível do contacto e executá-lo, será atualizada a cronologia de atividades para os seus clientes. Inclui os respetivos IDs ou nomes, consoante a sua configuração *ContactProfile* para as atividades nas quais atuaram. Poderá filtrar as atividades por contactos na linha cronológica para ver contactos específicos em que está interessado. Além disso, pode ver todas as atividades que não estão atribuídas a um contacto específico ao selecionar **Atividades não mapeadas para um Contacto**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opções de filtragem disponíveis para as atividades a nível do contacto.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]

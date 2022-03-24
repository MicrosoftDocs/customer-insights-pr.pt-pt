---
title: Criar e gerir ambientes
description: Saiba como se inscrever no serviço e como gerir ambientes.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376890"
---
# <a name="manage-environments"></a>Gerir ambientes

## <a name="switch-environments"></a>Mudar de ambientes

Selecione o controlo **Ambiente** no canto superior direito da página para mudar de ambiente.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de ecrã do controlo para mudar de ambiente.":::

Os administradores podem [criar](create-environment.md) e gerir ambientes.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Pode editar alguns dos detalhes de ambientes existentes.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação.

2.  Selecione o ícone **Editar**.

3. Na caixa **Editar ambiente**, pode atualizar as definições do ambiente.

Para obter mais informações sobre as definições do ambiente, consulte [Criar um novo ambiente](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Ligar ao Microsoft Dataverse
   
O passo **Microsoft Dataverse** permite-lhe ligar o Customer Insights ao ambiente do Dataverse.

Para utilizar [modelos de predição fornecidos com o programa](predictions-overview.md#out-of-box-models), configure a partilha de dados com o Dataverse. Ou pode ativar a ingestão de dados a partir de origens de dados no local, fornecendo o URL do ambiente do Microsoft Dataverse que a sua organização administra.

> [!IMPORTANT]
> O Customer Insights e o Dataverse têm de estar na mesma região para permitir a partilha de dados.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Opções de configuração para ativar a partilha de dados com o Microsoft Dataverse.":::

> [!NOTE]
> O Customer Insights não suporta os seguintes cenários de partilha de dados:
> - Se guardar todos os dados no Azure Data Lake Storage, não poderá permitir a partilha de dados com um data lake gerido do Dataverse.
> - Se ativar a partilha de dados com o Dataverse, não poderá [criar valores previsíveis ou em falta numa entidade](predictions.md).

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Quando criar um novo ambiente, pode optar por copiar a configuração a partir de um ambiente existente. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de ecrã das opções de definições nas definições do ambiente.":::

Verá uma lista de todos os ambientes disponíveis na sua organização de onde pode copiar dados.

As seguintes definições de configuração são copiadas:

- Origens de dados ingeridas/importadas
- Configuração de unificação de dados (Mapa, Corresponder, Unir)
- Segmentos
- Medições
- Relações
- Atividades
- Índice de pesquisas e filtros
- Destinos de exportação
- Atualização agendada
- Melhoramentos
- Gestão de modelos
- Atribuições de funções

Os dados seguintes *não* são copiados:

- Perfis de cliente.
- Credenciais da origem de dados. Terá de fornecer as credenciais para cada origem de dados e atualizar manualmente as origens de dados.

- Origens de dados da pasta Common Data Model e data lake gerido do Dataverse. Terá de criar manualmente essas origens de dados com o mesmo nome que no ambiente de origem.

Quando copia um ambiente, verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para origens de dados** para ver a lista de origens de dados.

Todas as origens de dados apresentarão um estado de **Credenciais Obrigatórias**. Edite as origens de dados e introduza as credenciais para as atualizar.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de origens de dados que foram copiadas e precisam de autenticação.":::

Depois de atualizar as fontes de dados, aceda ao **Dados** > **Unificar**. Aqui encontrará definições do ambiente de origem. Edite-as conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade de cliente unificada.

Quando a unificação de dados estiver concluída, aceda a **Medidas** e **Segmentos** para atualizá-los também.

## <a name="change-the-owner-of-an-environment"></a>Alterar o proprietário de um ambiente

Apesar de vários utilizadores poderem ter permissões de administrador no Customer Insights, apenas um utilizador é o proprietário de um ambiente. Por predefinição, é o administrador quem cria inicialmente um ambiente. Como administrador de um ambiente, pode atribuir a propriedade a outro utilizador com permissões de administrador.

1. Selecione o seletor **Ambiente** no cabeçalho da aplicação.

1. Selecione o ícone **Editar**.

1. Na caixa de **Editar ambiente**, vá para o passo **Informações básicas**.

1. No campo **Alterar proprietário do ambiente**, escolha o novo proprietário do ambiente.  

1. Selecione **Rever e concluir** e, em seguida, **Atualizar** para aplicar as alterações. 

## <a name="claim-ownership-of-an-environment"></a>Reclamar a propriedade de um ambiente

Se o proprietário de um ambiente sair da organização ou se a respetiva conta de utilizador for eliminada, o ambiente não terá proprietário. Um utilizador com permissões de administrador pode reclamar a propriedade e tornar-se o novo proprietário. Pode continuar a ser o proprietário do ambiente ou [alterar a propriedade para outro administrador](#change-the-owner-of-an-environment). 

Para reclamar a propriedade, selecione o botão **Assumir propriedade** que é apresentado no início de cada página no Customer Insights quando o proprietário original deixou a organização.

## <a name="reset-an-existing-environment"></a>Repor um ambiente existente

Como proprietário de um ambiente, pode repor um ambiente para um estado vazio se quiser eliminar todas as configurações e remover os dados ingeridos.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação. 

2.  Selecione o ambiente que pretende repor e selecione as reticências (**...**). 

3. Escolha a opção **Repor**. 

4.  Para confirmar a eliminação, introduza o nome do ambiente e selecione **Repor**.

## <a name="delete-an-existing-environment"></a>Eliminar um ambiente existente

Como proprietário de um ambiente, pode eliminar um ambiente que administra.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação.

2.  Selecione o ambiente que pretende repor e selecione as reticências (**...**). 

3. Escolha a opção **Eliminar**. 

4.  Para confirmar a eliminação, introduza o nome do ambiente e selecione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

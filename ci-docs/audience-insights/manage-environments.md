---
title: Criar e gerir ambientes
description: Saiba como se inscrever no serviço e como gerir ambientes.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683487"
---
# <a name="manage-environments"></a>Gerir ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Mudar de ambientes

Selecione o controlo **Ambiente** no canto superior direito da página para mudar de ambiente.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de ecrã do controlo para mudar de ambiente.":::

Os administradores podem [criar](get-started-paid.md) e gerir ambientes.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Pode editar alguns dos detalhes de ambientes existentes.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação.

2.  Selecione o ícone **Editar**.

3. Na caixa **Editar ambiente** pode atualizar o **Nome a apresentar** do ambiente, mas não pode alterar a **Região** ou o **Tipo**.

4. Se um ambiente estiver configurado para armazenar dados no Azure Data Lake Storage, pode atualizar a **Chave da Conta**. No entanto, não é possível alterar o **Nome da conta** ou do **Recipiente**.

5. Opcionalmente, pode atualizar a partir de uma ligação baseada em chave de conta para uma ligação baseada em recursos ou em subscrição. Uma vez atualizado, não se pode voltar à chave de conta após a atualização. Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md). Não é possível alterar as informações do **Recipiente** ao atualizar a ligação.

6. Opcionalmente, pode fornecer um URL de ambiente Microsoft Dataverse sob **Configurar partilha de dados com o Microsoft Dataverse e ativar capacidades adicionais**. Estas capacidades incluem a partilha de dados com aplicações e soluções baseadas no Microsoft Dataverse, a ingestão de dados a partir de origens de dados no local ou a utilização de [predições](predictions.md). Selecione **Ativar partilha de dados** para partilhar dados de saída do Customer Insights com um Data Lake Gerido do Microsoft Dataverse.

   > [!NOTE]
   > - A partilha de dados com o Data Lake Gerido do Microsoft Dataverse não é atualmente suportada quando guarda todos os dados para o seu próprio Azure Data Lake Storage.
   > - [Predição de valores em falta numa entidade](predictions.md) e relatórios Incorporados do PowerBI em informações de audiência (se ativados no seu ambiente) não são atualmente suportados quando ativa a partilha de dados com o data lake gerido da Microsoft Dataverse.

   Depois de ativar a partilha de dados com o Microsoft Dataverse, começará uma atualização completa das origens de dados e outros processos. Se os processos estiverem atualmente em execução, não vê a opção de permitir a partilha de dados com o Microsoft Dataverse. Espere que esses processos sejam concluídos ou cancele-os para ativar a partilha de dados. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opções de configuração para ativar a partilha de dados com o Microsoft Dataverse.":::
   
   Quando executa processos, tais como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento que especificou acima. Os ficheiros de dados e os ficheiros model.json serão criados e adicionados às respetivas subpastas, dependendo do processo que executar.

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
- Origens de dados da pasta do Common Data Model e do Data Lake gerido do Dataverse. Terá de criar manualmente essas origens de dados com o mesmo nome que no ambiente de origem.

Quando copia um ambiente, verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para origens de dados** para ver a lista de origens de dados.

Todas as origens de dados apresentarão um estado de **Credenciais Obrigatórias**. Edite as origens de dados e introduza as credenciais para as atualizar.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de origens de dados que foram copiadas e precisam de autenticação.":::

Depois de atualizar as fontes de dados, aceda ao **Dados** > **Unificar**. Aqui encontrará definições do ambiente de origem. Edite-as conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade de cliente unificada.

Quando a unificação de dados estiver concluída, aceda a **Medidas** e **Segmentos** para atualizá-los também.

## <a name="reset-an-existing-environment"></a>Repor um ambiente existente

Como administrador, pode repor um ambiente para um estado vazio se quiser eliminar todas as configurações e remover os dados ingeridos.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação. 

2.  Selecione o ambiente que pretende repor e selecione as reticências (**...**). 

3. Escolha a opção **Repor**. 

4.  Para confirmar a eliminação, introduza o nome do ambiente e selecione **Repor**.

## <a name="delete-an-existing-environment"></a>Eliminar um ambiente existente

Como administrador, pode eliminar um ambiente que administra.

1.  Selecione o seletor **Ambiente** no cabeçalho da aplicação.

2.  Selecione o ambiente que pretende repor e selecione as reticências (**...**). 

3. Escolha a opção **Eliminar**. 

4.  Para confirmar a eliminação, introduza o nome do ambiente e selecione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

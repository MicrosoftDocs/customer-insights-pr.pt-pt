---
title: Ligar a uma pasta do Common Data Model com uma conta Azure Data Lake
description: Trabalhe com dados do Common Data Model utilizando Azure Data Lake Storage.
ms.date: 09/29/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: c12603b9ed8a814356a0f8d0137e97afc749b87c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609962"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Ligar a dados no Azure Data Lake Storage

Ingerir dados para o Dynamics 365 Customer Insights utilizando a sua conta do Azure Data Lake Storage Gen2. A ingestão de dados pode ser total ou incremental.

## <a name="prerequisites"></a>Pré-requisitos

- A ingestão de dados suporta exclusivamente contas do Azure Data Lake Storage *Gen2*. Não pode utilizar contas de armazenamento do Data Lake Storage Gen1 para ingerir dados.

- A conta do Azure Data Lake Storage têm de ter um [espaço de nomes hierárquico ativado](/azure/storage/blobs/data-lake-storage-namespace). Os dados têm de ser armazenados num formato de pasta hierárquica que defina a pasta raiz e que tenha subpastas para cada entidade. As subpastas podem ter pastas de dados totais ou incrementais.

- Para autenticar com um principal de serviço do Azure, certifique-se de que está configurado no seu inquilino. Para obter mais informações, consulte [Ligar a uma conta do Azure Data Lake Storage Gen2 com um principal do serviço do Azure](connect-service-principal.md).

- O Azure Data Lake Storage de onde pretende ligar e ingerir dados tem de estar na mesma região do Azure que o ambiente do Dynamics 365 Customer Insights. As ligações a uma pasta Common Data Model a partir de um data lake numa região do Azure diferente não são suportadas. Para saber qual a região do Azure do ambiente, aceda a **Admin** > **Sistema** > **Acerca de** no Customer Insights.

- Os dados armazenados em serviços online podem ser armazenados numa localização diferente do local onde os dados são tratados ou armazenados em Dynamics 365 Customer Insights. Ao importar, ou ligar a, os dados armazenados em serviços online, como o , concorda que os dados podem ser transferidos para, e armazenados com o Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft](https://www.microsoft.com/trust-center).

- O principal de serviço do Customer Insights tem de ter uma das funções que seguem para aceder à conta de armazenamento. Para mais informações, consulte [Conceder permissões ao principal de serviço para aceder à conta de armazenamento](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Leitor de Dados de Blobs de Armazenamento
  - Proprietário de Dados de Blobs de Armazenamento
  - Contribuidor de Dados de Blobs de Armazenamento

- O utilizador que configura a ligação de origem de dados necessita do mínimo de permissões de contribuidor de dados de armazenamento de blobs na conta de armazenamento.

- Os dados no Data Lake Storage devem seguir o padrão do Common Data Model para armazenamento dos seus dados e ter o manifesto do Common Data Model para representar o esquema dos ficheiros de dados (*.csv ou *.parquet). O manifesto tem de fornecer os detalhes das entidades, tais como colunas de entidade e tipos de dados, bem como a localização do ficheiro de dados e o tipo de ficheiro. Para mais informações, consulte sobre [O manifesto do Common Data Model](/common-data-model/sdk/manifest). Se o manifesto não estiver presente, os Utilizadores administradores com o acesso de Proprietário de Dados de Blob de Armazenamento ou de Contribuidor de Dados de Blob de Armazenamento podem definir o esquema durante a ingestão dos dados.

## <a name="recommendations"></a>Recomendações

Para um desempenho ideal, o Customer Insights recomenda que o tamanho de uma partição seja de 1 GB ou menos e o número de ficheiros de partição numa pasta não pode exceder 1000.

## <a name="connect-to-azure-data-lake-storage"></a>Ligar ao Azure Data Lake Storage

1. Aceda a **Dados** > **Origens de dados**.

1. Selecione **Adicionar origem de dados**.

1. Selecione **Azure Data Lake Storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Caixa de diálogo para introduzir detalhes de ligação para o Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Introduza um **Nome** para a origem de dados e uma **Descrição** opcional. O nome identifica exclusivamente a origem de dados e é referenciado em processos jusante e não pode ser alterado.

1. Escolha uma das seguintes opções para **Ligar o armazenamento utilizando**. Para obter mais informações, consulte [Ligar o Customer Insights a uma conta do Azure Data Lake Storage Gen2 com um principal de serviço do Azure](connect-service-principal.md).

   - **Recurso do Azure**: introduza o **ID do Recurso**. Opcionalmente, se pretender ingerir dados de uma conta de armazenamento através de uma Azure Private Link, selecione **Ativar Private Link**. Para obter mais informações, consulte [Private Links](security-overview.md#set-up-an-azure-private-link).
   - **Subscrição do Azure**: selecione a **Subscrição** e, em seguida, o **Grupo de recursos** e a **Conta de armazenamento**. Opcionalmente, se pretender ingerir dados de uma conta de armazenamento através de uma Azure Private Link, selecione **Ativar Private Link**. Para obter mais informações, consulte [Private Links](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Necessita de uma das seguintes funções para o contentor ou a conta de armazenamento para criar a origem de dados:
   >
   >  - O Leitor de Dados de Blobs de Armazenamento é suficiente para ler a partir de uma conta de armazenamento e ingerir os dados para o Customer Insights.
   >  - É necessário o Contribuidor ou Proprietário de Dados de Blobs de Armazenamento se quiser editar os ficheiros de manifesto diretamente no Customer Insights.  
  
1. Escolha o nome do **Contentor** que contém os dados e o esquema (ficheiro model.json ou manifest.json) a partir do qual os dados serão importados e selecione **Seguinte**.
   > [!NOTE]
   > Qualquer ficheiro model.json ou manifest.json associado a outra origem de dados no ambiente não aparecerá na lista. No entanto, o mesmo ficheiro model.json ou manifest.json pode ser usado para origens de dados em vários ambientes.

1. Para criar um novo esquema, aceda a [Criar um novo ficheiro de esquema](#create-a-new-schema-file).

1. Para utilizar um esquema existente, navegue para a pasta que contém o ficheiro model.json ou manifest.cdm.json. Pode pesquisar num diretório para encontrar o ficheiro.

1. Selecione o ficheiro json e selecione **Seguinte**. É apresentada uma lista de entidades disponíveis.

   :::image type="content" source="media/review-entities.png" alt-text="Caixa de diálogo de uma lista de entidades a selecionar":::

1. Selecione as entidades que pretende incluir.

   :::image type="content" source="media/ADLS_required.png" alt-text="Caixa de diálogo a mostrar Obrigatório para Chave primária":::

   > [!TIP]
   > Para editar uma entidade numa interface de edição JSON, selecione a entidade e, em seguida, **Editar ficheiro de esquema**. Efetue as alterações e selecione **Guardar**.

1. Para as entidades selecionadas que necessitam de ingestão incremental, é apresentado **Obrigatório** sob **Atualização incremental**. Para cada uma destas entidades, consulte [Configurar uma atualização incremental para origens de dados do Azure Data Lake](incremental-refresh-data-sources.md).

1. Para entidades selecionadas onde uma chave primária não tenha sido definida, é apresentado **Obrigatório** sob **Chave primária**. Para cada uma destas entidades:
   1. Selecione **Obrigatória**. É apresentado o painel **Editar entidade**.
   1. Escolha a **Chave primária**. A chave primária é um atributo exclusivo da entidade. Para que um atributo seja uma chave primária válida, não deve incluir valores duplicados, valores em falta ou valores nulos. Os atributos de cadeia, número inteiro e tipo de dados GUID são suportados como chaves primárias.
   1. Opcionalmente, altere o padrão de partição.
   1. Selecione **Fechar** para guardar e fechar o painel.

1. Selecione o número de **Atributos** para cada entidade incluída. É apresentada a página **Gerir atributos**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Caixa de diálogo para selecionar a análise para otimização de dados.":::

   1. Criar novos atributos, edite ou elimine atributos existentes. Pode alterar o nome, o formato de dados ou adicionar um tipo de semântica.
   1. Para ativar a análise e outras capacidades, selecione **Análise para otimização de dados** para toda a entidade ou para atributos específicos. Por defeito, nenhuma entidade está habilitada para a criação de perfis de dados.
   1. Selecionar **Concluído**.

1. Selecione **Guardar**. A página **Origens de dados** é aberta a mostrar a origem de dados novas no estado **A atualizar**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revistos na página [**Entidades**](entities.md).

### <a name="create-a-new-schema-file"></a>Criar um novo ficheiro de esquema

1. Selecione **Novo ficheiro de esquema**.

1. Introduza um nome para o ficheiro e selecione **Guardar**.

1. Selecione **Nova entidade**. É apresentado o painel **Nova entidade**.

1. Introduza o nome da entidade e escolha a **Localização dos ficheiros de dados**.
   - **Vários ficheiros .csv ou .parquet**: navegue para a pasta raiz, selecione o tipo de padrão e introduza a expressão.
   - **Ficheiros .csv ou .parquet únicos**: navegue para o ficheiro .csv ou .parquet e selecione-o.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Caixa de diálogo para criar uma nova entidade com a Localização dos ficheiros de dados realçada.":::

1. Selecione **Guardar**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Caixa de diálogo para definir ou gerar automaticamente atributos.":::

1. Selecione **definir os atributos** para adicionar manualmente os atributos ou selecione **gerá-los automaticamente**. Para definir os atributos, introduza um nome, selecione o formato de dados e o tipo de semântica opcional. Para atributos gerados automaticamente:

   1. Depois de os atributos serem gerados automaticamente, selecione **Rever atributos**. É apresentada a página **Gerir atributos**.

   1. Certifique-se de que o formato de dados está correto para cada atributo.

   1. Para ativar a análise e outras capacidades, selecione **Análise para otimização de dados** para toda a entidade ou para atributos específicos. Por defeito, nenhuma entidade está habilitada para a criação de perfis de dados.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Caixa de diálogo para selecionar a análise para otimização de dados.":::

   1. Selecionar **Concluído**. A página **Selecionar entidades** é apresentada.

1. Continue a adicionar entidades e atributos, se aplicável.

1. Depois de todas as entidades terem sido adicionadas, selecione **Incluir** para incluir as entidades na ingestão de origem de dados.

   :::image type="content" source="media/ADLS_required.png" alt-text="Caixa de diálogo a mostrar Obrigatório para Chave primária":::

1. Para as entidades selecionadas que necessitam de ingestão incremental, é apresentado **Obrigatório** sob **Atualização incremental**. Para cada uma destas entidades, consulte [Configurar uma atualização incremental para origens de dados do Azure Data Lake](incremental-refresh-data-sources.md).

1. Para entidades selecionadas onde uma chave primária não tenha sido definida, é apresentado **Obrigatório** sob **Chave primária**. Para cada uma destas entidades:
   1. Selecione **Obrigatória**. É apresentado o painel **Editar entidade**.
   1. Escolha a **Chave primária**. A chave primária é um atributo exclusivo da entidade. Para que um atributo seja uma chave primária válida, não deve incluir valores duplicados, valores em falta ou valores nulos. Os atributos de cadeia, número inteiro e tipo de dados GUID são suportados como chaves primárias.
   1. Opcionalmente, altere o padrão de partição.
   1. Selecione **Fechar** para guardar e fechar o painel.

1. Selecione **Guardar**. A página **Origens de dados** é aberta a mostrar a origem de dados novas no estado **A atualizar**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revistos na página [**Entidades**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Editar uma origem de dados do Azure Data Lake Storage

Pode atualizar a opção *Ligar a conta de armazenamento utilizando*. Para obter mais informações, consulte [Ligar o Customer Insights a uma conta do Azure Data Lake Storage Gen2 com um principal de serviço do Azure](connect-service-principal.md). Para ligar a um contentor diferente da conta de armazenamento ou alterar o nome da conta, tem de [criar uma nova ligação à origem de dados](#connect-to-azure-data-lake-storage).

1. Aceda a **Dados** > **Origens de dados**.

1. Junto da origem de dados que pretende atualizar, selecione **Editar**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Caixa de diálogo para editar a origem de dados do Azure Data Lake.":::

1. Altere quaisquer das seguintes informações:

   - **Descrição**
   - **Ligar o armazenamento utilizando** e informações de ligação. Não é possível alterar as informações do **Recipiente** ao atualizar a ligação.
      > [!NOTE]
      > Uma das seguintes funções tem de ser atribuída à conta ou armazenamento ou contentor:
        > - Leitor de Dados de Blobs de Armazenamento
        > - Proprietário de Dados de Blobs de Armazenamento
        > - Contribuidor de Dados de Blobs de Armazenamento

   - **Ativar Private Link** se pretender ingerir dados de uma conta de armazenamento através de uma Azure Private Link. Para obter mais informações, consulte [Private Links](security-overview.md#set-up-an-azure-private-link).

1. Selecione **Seguinte**.
1. Altere qualquer um dos seguintes:
   - Navegue para um ficheiro model.json ou manifest.json diferente com um conjunto diferente de entidades do contentor.
   - Para adicionar entidades adicionais a ingerir, selecione **Nova entidade**.
   - Para remover quaisquer entidades já selecionadas, se não existirem dependências, selecione a entidade e selecione **Eliminar**.
      > [!IMPORTANT]
      > Se houver dependências do ficheiro model.json ou manifest.json existente e do conjunto de entidades, verá uma mensagem de erro e não poderá selecionar um ficheiro model.json ou manifest.json diferente. Remova essas dependências antes de alterar o ficheiro model.json ou manifest.json ou criar uma nova origem de dados com o ficheiro model.json ou manifest.json que pretende utilizar para evitar a remoção das dependências.
   - Para alterar a localização do ficheiro de dados ou a chave primária, selecione **Editar**.
   - Para alterar os dados de ingestão incremental, consulte [Configurar uma atualização incremental para origens de dados do Azure Data Lake](incremental-refresh-data-sources.md).
   - Altere apenas o nome de entidade para corresponder ao nome de entidade no ficheiro .json.

     > [!NOTE]
     > Mantenha sempre o nome da entidade no Customer Insights igual ao nome de entidade no ficheiro model.json ou manifest.json após a ingestão. O Customer Insights valida todos os nomes de entidade com model.json ou manifest.json durante cada atualização do sistema. Se um nome de entidade for alterado dentro ou fora do Customer Insights, ocorre um erro porque o Customer Insights não consegue localizar o novo nome de entidade no ficheiro .json. Se um nome de entidade ingerido tiver sido alterado acidentalmente, edite o nome de entidade no Customer Insights para corresponder ao nome no ficheiro .json.

1. Selecione **Atributos** para adicionar ou alterar atributos, ou para ativar a análise para otimização de dados. Em seguida, selecione **Concluir**.

1. Clique em **Guardar** para aplicar as alterações e regressar à página **Origens de dados**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Razões comuns para erros de ingestão ou dados danificados

Durante a ingestão de dados, algumas das razões mais comuns para que um registo possa ser considerado danificado incluem:

- Os tipos de dados e os valores de campo não corresponderem entre o ficheiro de origem e o esquema
- O número de colunas no ficheiro de origem não corresponde ao esquema
- Os campos contêm carateres que fazem com que as colunas se desviem em comparação ao esquema esperado. Por exemplo: aspas mal formatadas, aspas não fechadas, carateres de nova linha ou carateres com separadores.
- Faltam ficheiros de partição
- Se existirem as colunas datetime/date/datetimeoffset, o respetivo formato tem de ser especificado no esquema se não seguir o formato padrão.

### <a name="schema-or-data-type-mismatch"></a>Erro de correspondência de esquema ou de tipo de dados

Se os dados não se conformarem com o esquema, o processo de ingestão é concluído com erros. Corrija os dados de origem ou o esquema e volte a ingerir os dados.

### <a name="partition-files-are-missing"></a>Faltam ficheiros de partição

- Se a ingestão tiver sido bem sucedida sem quaisquer registos danificados, mas não vir quaisquer dados, edite o ficheiro model.json ou manifest.json para se certificar de que são especificadas partições. Em seguida, [atualize a origem de dados](data-sources.md#refresh-data-sources).

- Se a ingestão de dados ocorrer ao mesmo tempo que as origens de dados estão a ser atualizadas durante uma atualização automática da agenda, os ficheiros de partição poderão estar vazios ou não disponíveis para processamento pelo Customer Insights. Para alinhar com a agenda de atualização a jusante, altere a [agenda de atualização do sistema](schedule-refresh.md) ou a agenda de atualização para a origem de dados. Alinhe a temporização de modo a que as atualizações não ocorram de uma só vez e fornece os dados mais recentes a serem processados no Customer Insights.

### <a name="datetime-fields-in-the-wrong-format"></a>Campos datetime no formato errado

Os campos datetime na entidade não estão em formato ISO 8601 ou en-US. O formato datetime predefinido no Customer Insights está no formato en-US. Todos os campos datetime numa entidade devem estar no mesmo formato. O Customer Insights suporta outros formatos, desde que as anotações ou caraterísticas sejam feitas ao nível da origem ou da entidade no model ou manifest.json. Por exemplo: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Num manifest.json, o formato datetime pode ser especificado ao nível da entidade ou ao nível do atributo. Ao nível da entidade, utilize "exhibitsTraits" na entidade no *.manifest.cdm.json para definir o formato datetime. Ao nível do atributo, utilize "appliedTraits" no atributo em the entityname.cdm.json.

**Manifest.json ao nível da entidade**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json ao nível do atributo**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]

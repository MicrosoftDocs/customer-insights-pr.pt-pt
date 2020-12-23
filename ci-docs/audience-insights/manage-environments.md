---
title: Criar e gerir ambientes
description: Saiba como se inscrever no serviço e como gerir ambientes.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644147"
---
# <a name="manage-environments"></a>Gerir ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artigo explica como criar uma nova organização e como providenciar um ambiente.

## <a name="sign-up-and-create-an-organization"></a>Inscreva-se e crie uma organização

1. Aceder ao site [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Selecione **Começar**.

3. Escolha o cenário de inscrição preferencial e selecione a ligação correspondente.

4. Aceite os termos e condições e selecione **Continuar** para começar a criar a organização.

5. Após a criação do ambiente, será redirecionado para o [Customer Insights](https://home.ci.ai.dynamics.com).

6. Use o ambiente de demonstração para explorar a aplicação ou crie um novo ambiente seguindo os passos na secção seguinte.

7. Depois de especificar as definições de ambiente, selecione **Criar**.

8. Será registado depois de o ambiente ter sido criado com sucesso.

## <a name="create-an-environment-in-an-existing-organization"></a>Criar um ambiente numa organização existente

Existem duas formas de criar um novo ambiente. Pode especificar uma configuração totalmente nova ou pode copiar algumas definições de configuração a partir de um ambiente existente.

Para criar um ambiente:

1. Selecione o símbolo de **Definições** no cabeçalho da aplicação.

1. Selecione **Novo ambiente**.

   > [!div class="mx-imgBorder"]
   > ![Definições de ambiente](media/environment-settings-dialog.png)

1. No diálogo **Criar novo ambiente**, selecione **Novo ambiente**.

   Se pretender [copiar dados do ambiente atual](#additional-considerations-for-copy-configuration-preview), selecione **Copiar do ambiente atual**. Verá uma lista de todos os ambientes disponíveis na sua organização de onde pode copiar dados.

1. Forneça os seguintes detalhes:
   - **Nome**: O nome para este ambiente. Este campo já está preenchido se copiou de um ambiente existente, mas pode alterá-lo.
   - **Região**: a região na qual o serviço é implementado e hospedado.
   - **Tipo**: selecione se pretende criar um ambiente de Produção ou Sandbox.

2. Opcionalmente, pode selecionar **Definições avançadas**:

   - **Guardar todos os dados para**: Especifica onde pretende armazenar os dados de saída gerados a partir do Customer Insights. Terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerido pela equipa do Customer Insights) e **Azure Data Lake Storage Gen2** (o seu próprio Azure Data Lake Storage). Por predefinição, a opção de armazenamento do Customer Insights está selecionada.

   > [!NOTE]
   > Ao guardar dados no Azure Data Lake Storage, aceita que os dados serão transferidos e armazenados na localização geográfica adequada para essa apropriada para essa conta de armazenamento do Azure, que pode ser diferente daquela na qual os dados estão armazenados no Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft.](https://www.microsoft.com/trust-center)
   >
   > Atualmente, as entidades incluídas são sempre armazenadas no data Lake gerido pelo Customer Insights.
   > Apoiamos apenas contas de armazenamento Azure Data Lake Gen2 da mesma região Azure que selecionou ao criar o ambiente.
   > Só oferecemos suporte a contas de armazenamento com o Espaço de Nome Hierárquico (HNS) do Azure Data Lake Gen2 ativadas.

   - Para a opção Azure Data Lake Storage Gen2, pode escolher entre uma opção baseada em recursos e uma opção baseada em subscrições para autenticação. Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md). O nome do **Recepiente** não pode ser alterado e será "customerinsights".
   
   - Se quiser usar [predições](predictions.md), introduza o URL da instância Common Data Service no campo **endereço do servidor** em **Usar predições**.

   Quando executa processos, tais como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento que especificou acima. Os ficheiros de dados e os ficheiros model.json serão criados e adicionados às respetivas subpastas com base no processo que é executado.

   Se criar vários ambientes de Customer Insights e optar por guardar as entidades de saída desses ambientes na sua conta de armazenamento, serão criadas pastas separadas para cada ambiente com ci_<environmentid> no recipiente.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Considerações adicionais para a configuração da cópia (pré-visualização)

As seguintes definições de configuração são copiadas:

- Configurações de funcionalidades
- Fontes de dados ingeridas/importadas
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

As seguintes definições *não* são copiadas:

- Perfis de cliente.
- Credenciais da origem de dados. Terá de fornecer as credenciais para cada origem de dados e atualizar manualmente as origens de dados.
- Origens de dados da pasta modelo do Common Data Model e Lake gerido do Common Data Service. Terá de criar manualmente essas origens de dados com o mesmo nome que no ambiente de origem.

Quando copia um ambiente, verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para origens de dados** para ver a lista de origens de dados.

Todas as origens de dados apresentarão um estado de **Credenciais Obrigatórias**. Edite as origens de dados e introduza as credenciais para as atualizar.

> [!div class="mx-imgBorder"]
> ![Origens de dados copiadas](media/data-sources-copied.png)

Depois de atualizar as fontes de dados, aceda ao **Dados** > **Unificar**. Aqui encontrará definições do ambiente de origem. Edite-as conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade de cliente unificada.

Quando a unificação de dados estiver concluída, aceda a **Medidas** e **Segmentos** para atualizá-los também.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Pode editar alguns dos detalhes de ambientes existentes.

1. Aceda a **Administração** > **Sistema** > **Sobre**.

2. Selecione **Editar**.

3. Pode atualizar o **Nome a apresentar** do ambiente, mas não pode alterar a **Região** ou o **Tipo**.

4. Se um ambiente estiver configurado para armazenar dados no Azure Data Lake Storage Gen2, poderá atualizar a **Chave da conta**. No entanto, não é possível alterar o **Nome da conta** ou do **Recipiente**.

5. Opcionalmente, pode atualizar a partir de uma ligação baseada em chave de conta para uma ligação baseada em recursos ou em subscrição. Uma vez atualizado, não se pode voltar à chave de conta após a atualização. Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md). Não é possível alterar as informações do **Recipiente** ao atualizar a ligação.

## <a name="reset-an-existing-environment"></a>Repor um ambiente existente

Pode repor um ambiente para um estado vazio se quiser apagar todas as configurações e remover os dados ingeridos.

1.  Aceda a **Administração** > **Sistema** > **Sobre**.

2.  Selecione **Repor**. 

3.  Para confirmar a eliminação, introduza o nome do ambiente e selecione **Repor**.


## <a name="delete-an-existing-environment"></a>Eliminar um ambiente existente

1. Aceda a **Administração** > **Sistema** > **Sobre**.

1. Selecione **Eliminar**.

1. Para confirmar a eliminação, introduza o nome do ambiente e selecione **Eliminar**.

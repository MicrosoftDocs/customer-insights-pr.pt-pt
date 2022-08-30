---
title: Criar um novo ambiente
description: Etapas para criar ambientes no Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304258"
---
# <a name="create-a-new-environment"></a>Criar um novo ambiente

Depois de [comprar uma licença de subscrição para o Dynamics 365 Customer Insights](paid-license.md), o administrador global do inquilino do Microsoft 365 recebe um e-mail que o convida a criar o ambiente. Para começar, aceda a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). Neste cenário, comece com o [Passo 1: Fornecer informações básicas](#step-1-provide-basic-information).

Após a criação do primeiro ambiente, o administrador global do inquilino do Microsoft 365 pode [adicionar utilizadores a partir das respetivas organizações como administradores](permissions.md). Estes administradores podem, então, gerir utilizadores e ambientes. Se a sua organização comprar mais de uma licença para o Customer Insights, [contacte a nossa equipa de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade de suplementos, consulte [o guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Depois de ter a capacidade de criar ambientes adicionais, aceda a [Iniciar o processo de criação do ambiente](#start-the-environment-creation-process).

> [!TIP]
> Se procura experimentar o serviço, consulte [Configurar um ambiente de avaliação](trial-signup.md).

## <a name="prerequisites"></a>Pré-requisitos

[Permissões de administrador](permissions.md) no Customer Insights.

## <a name="start-the-environment-creation-process"></a>Iniciar o processo de criação de ambiente

1. Abra o seletor de ambientes e selecione **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Selecione o seletor de ambientes.":::

1. Siga a experiência guiada descrita nas secções que se seguem para fornecer todas as informações necessárias para um novo ambiente.

## <a name="step-1-provide-basic-information"></a>Passo 1: Fornecer informações básicas

1. Escolha se pretende criar um ambiente do zero ou copiar dados de outro ambiente. [A cópia de dados a partir de outro ambiente](#copy-the-environment-configuration) requer passos adicionais.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diálogo para criar um novo ambiente do Customer Insights.":::

1. Forneça os seguintes detalhes:

   - **Nome**: o nome para este ambiente. Este campo já está preenchido se copiou de um ambiente existente, mas pode alterá-lo.
   - **Escolha o seu negócio**: a audiência primária para o novo ambiente: consumidores individuais (B2C) ou [contas empresariais](work-with-business-accounts.md) (B2B). Se a sua organização fizer sobretudo negócios com indivíduos, como um revendedor ou uma loja de café, escolha consumidores individuais. Se a sua audiência principal for outras empresas, tais como um fabricantes de automóveis ou uma empresa de papel, escolha contas empresariais.
   - **Tipo**: tipo de ambiente: produção ou sandbox. Os ambientes de sandbox não permitem a atualização de dados agendados e destinam-se a pré-implementação e testes. Os ambientes de Sandbox utilizam a mesma audiência principal que o ambiente de produção que está atualmente selecionado.
   - **Região**: região na qual o serviço é implementado e alojado. Para [utilizar a sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md) ou [ligar a uma organização existente do Microsoft Dataverse](customer-insights-dataverse.md), o ambiente do Customer Insights tem de estar na mesma região.

1. Selecione **Seguinte**.

## <a name="step-2-configure-data-storage"></a>Passo 2: configurar armazenamento de dados

1. Escolha onde armazenar os dados do Customer Insights:

   - **Armazenamento do Customer Insights**: o armazenamento de dados é gerido automaticamente. É a opção predefinida e, a menos que haja requisitos específicos para armazenar dados na sua própria conta de armazenamento, recomendamos que utilize esta opção.
   - **Azure Data Lake Storage**: a sua própria conta do Azure Data Lake Storage para armazenar os dados, de modo a ter controlo total sobre onde os dados são armazenados. Siga os passos em [Utilizar a sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Escolher a opção preferida para armazenar os seus dados.":::

1. Selecione **Seguinte**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Passo 3: ligar ao Microsoft Dataverse

Se tiver um ambiente do Dataverse, ligue-se ao Customer Insights. Partilhe dados com o Dataverse para utilizá-lo com aplicações empresarias baseadas no Dataverse, como o Dynamics 365 Marketing ou aplicações condicionadas por modelo no Power Apps.

1. Siga os passos descritos em [Trabalhar com dados do Customer Insights no Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="partilha de dados com Microsoft Dataverse ativado automaticamente para novos ambientes de rede.":::

1. Selecione **Seguinte**.

## <a name="step-4-finalize-the-settings"></a>Passo 4: finalizar as definições

Rever as definições especificadas. Quando tudo estiver concluído, selecione **Criar** para configurar o ambiente.

Para alterar algumas das definições mais tarde, consulte [Gerir ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabalhar com o seu novo ambiente

Reveja os seguintes artigos para o ajudar a começar com a configuração do Customer Insights:

- [Adicionar mais utilizadores e atribuir permissões](permissions.md).
- [Ingerir as suas origens de dados](data-sources.md) e executá-las através do [processo de unificação de dados](data-unification.md) para obter [perfis de clientes unificados](customer-profiles.md).
- [Enriquecer os perfis de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Crie segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para rever KPIs.
- [Configure ligações](connections.md) e [exportações](export-destinations.md) para processar os subconjuntos dos seus dados noutras aplicações.

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Como administrador, se optar por copiar a configuração a partir de um ambiente existente, selecione a partir da lista de todos os ambientes disponíveis na organização.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de ecrã das opções de definições nas definições do ambiente.":::

As seguintes definições de configuração são copiadas:

- Origens de dados importadas através do Power Query
- Configuração da unificação de dados
- Segmentos
- Medições
- Relações
- Atividades
- Índice de pesquisas e filtros
- Exportações
- Agenda de atualização
- Melhoramentos
- Modelos de predição
- Atribuições de funções

### <a name="set-up-a-copied-environment"></a>Configurar um ambiente copiado

Quando copia a configuração do ambiente, é apresentada uma mensagem de confirmação quando o ambiente copiado é criado. Execute os seguintes passos para confirmar as credenciais.

1. Selecione **Ir para origens de dados** para ver a lista de origens de dados. Todas as origens de dados apresentam o estado **Credenciais obrigatórias**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lista de origens de dados que foram copiadas e precisam de autenticação.":::

1. Edite as origens de dados e introduza as credenciais para as atualizar. Origens de dados da pasta Common Data Model do Dataverse e têm de ser criadas manualmente com o mesmo nome que no ambiente de origem.

1. Depois de atualizar as fontes de dados, aceda ao **Dados** > **Unificar**. Aqui encontrará definições do ambiente de origem. Edite-as conforme necessário ou selecione **Unificar** > **Unificar perfis e dependências de cliente** para iniciar o processo de unificação de dados e criar a entidade de cliente unificada.

   > [!TIP]
   > Para contas e contactos, selecione **Unificar contas** > **Unificar perfis e dependências**.

1. Quando a unificação de dados estiver concluída, aceda a **Medidas** e **Segmentos** para os atualizar também.

1. Aceda a **Admin** > **Ligações** para voltar a autenticar as ligações no seu novo ambiente.

1. Aceda a **Dados** > **Melhoramento** e **Dados** > **Exportações** para os reativar.

[!INCLUDE [footer-include](includes/footer-banner.md)]

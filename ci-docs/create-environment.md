---
title: Como – Criar um novo ambiente
description: Passos para criar ambientes com o Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011625"
---
# <a name="how-to-create-a-new-environment"></a>Como: criar um novo ambiente

Depois de [comprar uma licença de subscrição para o Dynamics 365 Customer Insights](paid-license.md), o administrador global do inquilino do Microsoft 365 recebe um e-mail que o convida a criar o ambiente. Para começar, aceda a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). Neste cenário, pode ir diretamente para o [Passo 1: Fornecer informações básicas](#step-1-provide-basic-information).

Após a criação do primeiro ambiente, o administrador global do inquilino do Microsoft 365 pode [adicionar utilizadores a partir das respetivas organizações como administradores](permissions.md). Daqui para a frente, estes administradores podem gerir utilizadores e ambientes. Se a sua organização comprar mais de uma licença para o Customer Insights, [contacte a nossa equipa de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade de suplementos, consulte [o guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Se procura experimentar o serviço, consulte [Configurar um ambiente de avaliação](trial-signup.md).

## <a name="prerequisites"></a>Pré-requisitos

Precisa de [permissões de administrador](permissions.md) no Customer Insights para criar ou gerir ambientes.

## <a name="start-the-environment-creation-process"></a>Iniciar o processo de criação de ambiente

1. Abra o seletor de ambientes e selecione **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Selecione o seletor de ambientes.":::

1. Siga a experiência guiada descrita nas secções que se seguem para fornecer todas as informações necessárias para um novo ambiente. Se tiver configurado um ambiente anteriormente, também pode [copiar a configuração](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Passo 1: Fornecer informações básicas

No passo **Informações básicas**, escolha se pretende criar um ambiente do zero ou [copiar dados de outro ambiente](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diálogo para criar um novo ambiente do Customer Insights.":::

Forneça os seguintes detalhes:

- **Nome**: O nome para este ambiente. Este campo já está preenchido se copiou de um ambiente existente, mas pode alterá-lo.
- **Escolha o seu negócio**: escolha a audiência principal para o novo ambiente. Pode trabalhar com consumidores individuais (B2C) ou [contas empresariais](work-with-business-accounts.md) (B2B). Se a sua organização fizer sobretudo negócios com indivíduos, como um revendedor ou uma loja de café, escolha consumidores individuais. No caso de a sua audiência principal ser outras empresas, tais como um fabricantes de automóveis ou uma empresa de papel, escolha contas empresariais.
- **Tipo**: selecione se pretende criar um ambiente de produção ou de sandbox. Os ambientes de sandbox não permitem a atualização de dados agendados e destinam-se a pré-implementação e testes. Os ambientes de Sandbox utilizam a mesma audiência principal que o ambiente de produção que está atualmente selecionado.
- **Região**: a região na qual o serviço é implementado e hospedado. Para [utilizar a sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md) ou [ligar a uma organização existente do Microsoft Dataverse](customer-insights-dataverse.md), o ambiente do Customer Insights tem de estar na mesma região.

## <a name="step-2-configure-data-storage"></a>Passo 2: configurar armazenamento de dados

No passo **Armazenamento de dados**, escolha onde armazenar os dados do Customer Insights.

Existem duas opções a partir das quais pode escolher:

- **Armazenamento de Customer Insights**: o armazenamento de dados é gerido pela equipa do Customer Insights. É a opção predefinida e, a menos que haja requisitos específicos para armazenar dados na sua própria conta de armazenamento, recomendamos que utilize esta opção.
- **Azure Data Lake Storage**: especifique a sua própria conta do Azure Data Lake Storage para armazenar os dados, de modo a ter controlo total sobre onde os dados são armazenados. Para obter mais informações, consulte [Utilizar a sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Escolher a opção preferida para armazenar os seus dados.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Passo 3: ligar ao Microsoft Dataverse

O passo **Microsoft Dataverse** permite-lhe ligar o Customer Insights ao ambiente do Dataverse. Partilhe dados com o Dataverse para utilizá-lo com aplicações empresarias baseadas no Dataverse, como o Dynamics 365 Marketing ou aplicações condicionadas por modelo no Power Apps.


Deixe este campo vazio se não tiver o seu próprio ambiente do Dataverse e nós iremos criar um para si.

Para obter mais informações, consulte [Trabalhar com dados do Customer Insights no Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="partilha de dados com Microsoft Dataverse ativado automaticamente para novos ambientes de rede.":::

### <a name="step-4-finalize-the-settings"></a>Passo 4: finalizar as definições

No passo **Revisão**, passe por todas as definições especificadas. Quando tudo estiver concluído, selecione **Criar** para configurar o ambiente.

Também pode alterar algumas das definições mais tarde. Para mais informações, consulte [Gerir ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabalhar com o seu novo ambiente

Reveja os seguintes artigos para o ajudar a começar com a configuração do Customer Insights:

- [Adicionar mais utilizadores e atribuir permissões](permissions.md).
- [Ingerir as suas origens de dados](data-sources.md) e executá-las através do [processo de unificação de dados](data-unification.md) para obter [perfis de clientes unificados](customer-profiles.md).
- [Enriquecer os perfis de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Crie segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para rever KPIs.
- [Configure ligações](connections.md) e [exportações](export-destinations.md) para processar os subconjuntos dos seus dados noutras aplicações.

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Como admin, pode optar por copiar a configuração de um ambiente existente quando cria um novo.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de ecrã das opções de definições nas definições do ambiente.":::

Verá uma lista de todos os ambientes disponíveis na sua organização de onde pode copiar dados.

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

## <a name="set-up-a-copied-environment"></a>Configurar um ambiente copiado

Quando copia a configuração do ambiente, tem de passar por alguns passos adicionais para confirmar as credenciais:

- Perfis de cliente. Primeiro, autentique e ingira as suas origens de dados e execute a unificação de dados para recriar os perfis de clientes.
- Credenciais da origem de dados. Tem de fornecer as credenciais de cada origem de dados para autenticar e atualizar as origens de dados manualmente.
- Origens de dados da pasta Common Data Model e do Dataverse. Tem de criar manualmente essas origens de dados com o mesmo nome que no ambiente de origem.
- Segredos de ligação que são utilizados para exportações e melhoramentos. Tem de voltar a autenticar as ligações e, em seguida, reativar melhoramentos e exportações.

Verá uma mensagem de confirmação quando o ambiente copiado tiver sido criado. Selecione **Ir para origens de dados** para ver a lista de origens de dados.

Todas as origens de dados apresentarão um estado de **Credenciais Obrigatórias**. Edite as origens de dados e introduza as credenciais para as atualizar.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de origens de dados que foram copiadas e precisam de autenticação.":::

Depois de atualizar as fontes de dados, aceda ao **Dados** > **Unificar**. Aqui encontrará definições do ambiente de origem. Edite-as conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade de cliente unificada.

Quando a unificação de dados estiver concluída, aceda a **Medidas** e **Segmentos** para atualizá-los também.

Antes de reativar exportações e melhoramentos, vá à **Admin** > **Ligações** para voltar a autenticar as ligações no seu novo ambiente.

[!INCLUDE [footer-include](includes/footer-banner.md)]

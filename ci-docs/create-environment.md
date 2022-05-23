---
title: Criar ambientes no Customer Insights
description: Passos para criar ambientes com uma subscrição licenciada para o Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c64ac94a7e0e743d3c13e32e394cc5d409420622
ms.sourcegitcommit: c00441bc60b978e25f930b06c9d97b46fe462538
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712916"
---
# <a name="create-an-environment-in-customer-insights"></a>Criar um ambiente no Customer Insights

Este artigo explica como criar um novo ambiente depois da sua organização ter comprado uma subscrição do Dynamics 365 Customer Insights. 

As organizações podem criar vários ambientes para cada licença do Customer Insights. Se a sua organização comprar mais de uma licença, [contacte a nossa equipa de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade de suplementos, consulte [o guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Se procura experimentar o serviço, consulte [Configurar um ambiente de avaliação](trial-signup.md).

## <a name="create-a-new-environment"></a>Criar um novo ambiente

Depois de comprar uma licença de subscrição para o Customer Insights, o administrador global do inquilino do Microsoft 365 recebe um e-mail que o convida a criar o ambiente. Para começar, aceda a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Uma experiência guiada ajuda-o através dos passos para reunir todas as informações necessárias para um novo ambiente. Precisa de [permissões de administrador](permissions.md) no Customer Insights para criar ou gerir ambientes.

1. Abra o seletor de ambientes e selecione **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Selecione o seletor de ambientes.":::

1. Siga a experiência guiada descrita nas seguintes secções.

### <a name="step-1-provide-environment-information"></a>Passo 1: fornecer informações sobre o ambiente

No passo **Informações básicas**, escolha se pretende criar um ambiente do zero ou [copiar dados de outro ambiente](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diálogo para criar um novo ambiente do Customer Insights.":::

Forneça os seguintes detalhes:
   - **Nome**: O nome para este ambiente. Este campo já está preenchido se copiou de um ambiente existente, mas pode alterá-lo.
   - **Escolha o seu negócio**: escolha a audiência principal para o novo ambiente. Pode trabalhar com consumidores individuais (B2C) ou [contas empresariais](work-with-business-accounts.md) (B2B).
   - **Tipo**: selecione se pretende criar um ambiente de produção ou de sandbox. Os ambientes de sandbox não permitem a atualização de dados agendados e destinam-se a pré-implementação e testes. Os ambientes de Sandbox utilizam a mesma audiência principal que o ambiente de produção que está atualmente selecionado.
   - **Região**: a região na qual o serviço é implementado e hospedado.

### <a name="step-2-configure-data-storage"></a>Passo 2: configurar armazenamento de dados

No passo **Armazenamento de dados**, escolha onde armazenar os dados do Customer Insights.

Terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerido pela equipa do Customer Insights) e **Azure Data Lake Storage** (o seu próprio Azure Data Lake Storage). Por predefinição, a opção de armazenamento do Customer Insights está selecionada.

:::image type="content" source="media/data-storage-environment.png" alt-text="Escolher o Azure Data Lake Storage para armazenar os seus dados.":::

Ao guardar dados no Azure Data Lake Storage, concorda que os dados serão transferidos para a localização geográfica apropriada e armazenados na mesma para essa conta de armazenamento do Azure. Esta localização pode diferir do local onde os dados são armazenados no Dynamics 365 Customer Insights. Saber mais no [Centro de Fidedignidade da Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> O Customer Insights suporta atualmente o seguinte:  
> - As contas do Azure Data Lake Storage da mesma região do Azure que selecionou ao criar o ambiente.
> - As contas do Azure Data Lake Storage que são Gen2 e têm um *espaço de nomes hierárquico* ativado. As contas de armazenamento do Azure Data Lake Gen1 não são suportadas.

Para a opção do Azure Data Lake Storage, pode escolher entre uma opção baseada em recursos e uma opção baseada em subscrições para autenticação. Para obter mais informações, consulte [Ligar a uma conta do Azure Data Lake Storage utilizando um principal de serviço do Azure](connect-service-principal.md). Um contentor chamado `customerinsights` tem de existir na conta de armazenamento.

Quando os processos do sistema, como a ingestão de dados, estão concluídos, o sistema cria pastas correspondentes na conta de armazenamento especificada. Os ficheiros de dados e os ficheiros *model.json* são criados e adicionados a pastas com base no nome do processo.

Se criar vários ambientes do Customer Insights e optar por guardar as entidades de saída desses ambientes na sua conta de armazenamento, o Customer Insights cria pastas separadas para cada ambiente com `ci_environmentID` no contentor.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Passo 3: ligar ao Microsoft Dataverse
   
O passo **Microsoft Dataverse** permite-lhe ligar o Customer Insights ao ambiente do Dataverse.

Forneça o seu próprio ambiente Microsoft Dataverse para partilhar dados (perfis e informações) com aplicações de negócio baseadas em Dataverse, como o Dynamics 365 Marketing ou aplicações orientadas por modelos no Power Apps. Deixe este campo vazio se não tiver o seu próprio ambiente Dataverse para lhe fornecermos um.

A ligação ao seu ambiente Dataverse também permite-lhe [ingerir dados de origens de dados no local utilizando fluxos de dados e gateways do Power Platform](data-sources.md#add-data-from-on-premises-data-sources).

> [!IMPORTANT]
> 1. O Customer Insights e o Dataverse têm de estar na mesma região para permitir a partilha de dados.
> 1. Tem de ter uma função de administrador global no ambiente do Dataverse. Verifique se este [ambiente do Dataverse está associado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de segurança e certifique-se de que é adicionado a esses grupos de segurança.
> 1. Nenhum ambiente existente do Customer Insights está já associado a esse ambiente do Dataverse. Saiba como [remover uma ligação existente a um ambiente do Dataverse](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="partilha de dados com Microsoft Dataverse ativado automaticamente para novos casos.":::

Para obter mais informações sobre como ativar a partilha de dados com o Microsoft Dataverse a partir do seu próprio Azure Data Lake Storage, consulte [Ligar ao Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

O Customer Insights não suporta os seguintes cenários de partilha de dados:
- Se ativar a partilha de dados com o Dataverse, não poderá [criar valores previsíveis ou em falta numa entidade](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Passo 4: finalizar as definições

No passo **Revisão**, passe por todas as definições especificadas. Quando tudo estiver concluído, selecione **Criar** para configurar o ambiente. 

Também pode alterar a maioria das definições mais tarde. Para mais informações, consulte [Gerir ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabalhar com o seu novo ambiente

Reveja os seguintes artigos para o ajudar a começar com a configuração do Customer Insights: 

- [Adicionar mais utilizadores e atribuir permissões](permissions.md).
- [Ingerir as suas origens de dados](data-sources.md) e executá-las através do [processo de unificação de dados](data-unification.md) para obter [perfis de clientes unificados](customer-profiles.md).
- [Enriquecer os perfis de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Crie segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para rever KPIs.
- [Configure ligações](connections.md) e [exportações](export-destinations.md) para processar os subconjuntos dos seus dados noutras aplicações.

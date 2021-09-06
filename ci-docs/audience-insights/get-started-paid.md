---
title: Criar e configurar uma licença paga do Customer Insights
description: Passos para obter uma subscrição paga para o Dynamics 365 Customer Insights e configurá-lo.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034466"
---
# <a name="get-started-with-a-paid-subscription"></a>Começar a utilizar uma subscrição paga

Este artigo explica como criar um novo ambiente depois da sua organização ter comprado uma subscrição do Dynamics 365 Customer Insights. Se pretender comprar o Customer Insights, as nossas opções de contacto estão listadas no [Site do Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Se está à procura de experimentar o serviço e as funcionalidades, consulte [Configurar um ambiente de avaliação](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Criar um ambiente numa organização existente

Após a compra de uma licença de subscrição para o Customer Insights, o administrador global do inquilino Microsoft 365 recebe um e-mail que o convida a criar o ambiente. Para começar, aceda a [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start). 

O Customer Insights não é licenciado por utilizador, pelo que não aparece na área de Licenças. Se procura a licença no centro de administração do Microsoft 365, vá aos **Seus produtos**. 

> [!NOTE]
> As organizações podem criar *dois* ambientes para cada licença do Customer Insights. Se a sua organização comprar mais de uma licença, [contacte a nossa equipa de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade de suplementos, transfira o [Guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Para criar um ambiente:

1. No diálogo **Criar um ambiente**, selecione **Novo ambiente**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diálogo para criar um novo ambiente do Customer Insights.":::

   Recomendamos que comece a configurar um ambiente a partir do zero. No entanto, se for admin ou membro de um ambiente de avaliação, pode [copiar dados de outro ambiente](manage-environments.md#copy-the-environment-configuration), escolhendo **Copiar do ambiente existente**. Verá uma lista de todos os ambientes disponíveis na sua organização de onde pode copiar dados.

1. Forneça os seguintes detalhes:
   - **Nome**: O nome para este ambiente. Este campo já está preenchido se copiou de um ambiente existente, mas pode alterá-lo.
   - **Região**: a região na qual o serviço é implementado e hospedado.
   - **Tipo**: selecione se pretende criar um ambiente de produção ou de sandbox. Os ambientes de sandbox não permitem a atualização de dados agendados e destinam-se a pré-implementação e testes.
   
1. Opcionalmente, pode selecionar **Definições avançadas**:

   - **Guardar todos os dados para**: Especifica onde pretende armazenar os dados de saída gerados a partir do Customer Insights. Terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerido pela equipa do Customer Insights) e **Azure Data Lake Storage** (o seu próprio Azure Data Lake Storage). Por predefinição, a opção de armazenamento do Customer Insights está selecionada.

     > [!NOTE]
     > Ao guardar dados no Azure Data Lake Storage, aceita que os dados serão transferidos e armazenados na localização geográfica adequada para essa apropriada para essa conta de armazenamento do Azure, que pode ser diferente daquela na qual os dados estão armazenados no Dynamics 365 Customer Insights. [Saber mais no Centro de Fidedignidade da Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Atualmente, as entidades ingeridas de fluxos de dados do Power BI são armazenadas no Data Lake gerido pelo Microsoft Dataverse. 
     > 
     > Suportamos apenas contas do Azure Data Lake Storage da mesma região do Azure que selecionou na criação do ambiente. 
     > 
     > Suportamos apenas as contas do Azure Data Lake Storage que tenham o espaço de nomes hierárquico ativado.


   - Para a opção do Azure Data Lake Storage, pode escolher entre uma opção baseada em recursos e uma opção baseada em subscrições para autenticação. Para obter mais informações, consulte [ligar informações de audiência a uma conta Gen2 do Azure Data Lake Storage com um principal de serviço Azure](connect-service-principal.md). O nome do **Contentor** não pode ser alterado e será `customerinsights`.
   
   - Se pretender utilizar [modelos de origem](predictions-overview.md#out-of-box-models), configure a partilha de dados com o Microsoft Dataverse ou permita a ingestão de dados a partir de origens de dados no local, forneça o URL do ambiente Microsoft Dataverse sob **Configurar partilha de dados com o Microsoft Dataverse e permitir capacidades adicionais**. Selecione **Ativar partilha de dados** para partilhar dados de saída do Customer Insights com um Data Lake Gerido do Microsoft Dataverse.

     > [!NOTE]
     > - A partilha de dados com o Data Lake Gerido do Microsoft Dataverse não é atualmente suportada quando guarda todos os dados para o seu próprio Azure Data Lake Storage.
     > - Atualmente, a [Predição de valores em falta numa entidade](predictions.md) não é suportado quando permite a partilha de dados com Data Lake Gerido do Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opções de configuração para ativar a partilha de dados com o Microsoft Dataverse.":::

   Quando os processos do sistema como a ingestão de dados estão completos, o sistema cria pastas correspondentes na conta de armazenamento especificada. Os ficheiros de dados e os ficheiros model.json são criados e adicionados a pastas com base no nome do processo.

   Se criar vários ambientes de Customer Insights e optar por guardar as entidades de saída desses ambientes na sua conta de armazenamento, serão criadas pastas separadas para cada ambiente com ci_<environmentid> no recipiente.

1. Selecione **Criar** para configurar o ambiente. 

## <a name="configure-an-environment"></a>Configurar um ambiente

Reveja os seguintes artigos para ajudá-lo a começar com a configuração do Customer Insights. 

- [Adicionar mais utilizadores e atribuir permissões](permissions.md).
- [Ingerir as suas origens de dados](data-sources.md) e executá-las através do [processo de unificação de dados](data-unification.md) para obter [perfis de clientes unificados](customer-profiles.md).
- [Enriquecer os perfis de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- Crie [segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para rever KPIs.
- Configure [ligações](connections.md) e [exportações](export-destinations.md) para processar subconjuntos dos seus dados noutras aplicações.

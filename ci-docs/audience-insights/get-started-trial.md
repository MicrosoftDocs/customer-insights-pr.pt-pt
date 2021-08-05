---
title: Criar e configurar uma versão de avaliação do Customer Insights
description: Passos para obter uma subscrição da versão de avaliação para o Dynamics 365 Customer Insights e configurá-lo.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650499"
---
# <a name="set-up-a-trial-environment"></a>Configurar um ambiente de avaliação 

Uma versão de avaliação do Dynamics 365 Customer Insights permite-lhe rever capacidades chave e saber mais sobre as várias funcionalidades. Uma subscrição da versão de avaliação é eliminada após a expiração. Os ambientes de avaliação são criados por utilizadores individuais que se tornam administradores do seu ambiente de avaliação. Podem convidar mais utilizadores para a sua avaliação e configurar as várias funcionalidades.

## <a name="create-a-trial-environment"></a>Criar um ambiente de avaliação

Pode inscrever-se para uma avaliação na [página de inscrição da avaliação](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Escolha a opção **Inscrever para uma avaliação gratuita** e **Inscrever agora**.

1. Forneça o seu endereço de e-mail escolar ou profissional, conte-nos um pouco mais sobre si mesmo e selecione **Começar**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Caixa de diálogo para se inscrever numa instância de avaliação":::

1. Reveja os termos e condições e selecione **Continuar** para confirmar.

1. Forneça um **Nome** para o seu novo ambiente. 

1. Defina o **Tipo** de ambiente como **Avaliação**.

1. No campo **Selecionar uma demonstração do setor**, pode escolher opcionalmente um conjunto de dados específico do setor. Também pode [mudar para uma demonstração do setor](#use-industry-specific-demo-data-sets-in-audience-insights) mais tarde e começar com o conjunto de dados predefinido.

1. Escolha a **Região** para o seu ambiente.

1. Opcionalmente, se é o admin de uma organização Dynamics 365: selecione **Definições avançadas** e forneça o URL da sua organização para usar funcionalidades de predição como predição de abandono de clientes. 

1. Selecione **Criar**. 

A configuração do ambiente demora alguns momentos a concluir. Após a conclusão, é redirecionado para o ambiente de demonstração ou para a demonstração do setor que escolhe no passo acima. Agora pode explorar a aplicação com dados de demonstração só de leitura. Para adicionar os seus próprios dados ao ambiente, consulte [Criar dados de demonstração específicos do cenário no seu próprio ambiente](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Captura de ecrã de um ambiente de avaliação recém-criado.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Utilize conjuntos de dados de demonstração específicos do setor em informações de audiência

A ligação de origens de dados reais é um dos passos críticos na utilização do poder de Customer Insights. Para experimentar funcionalidades sem interferir com os seus próprios dados, pode utilizar opcionalmente dados de demonstração específicos do setor. Existem alguns conjuntos de dados de demonstração disponíveis para os seguintes setores: 

-   Indústria Automóvel
-   Banca
-   Bens de consumo
-   Administração Pública
-   Cuidados de Saúde
-   Hotelaria
-   Seguros
-   Indústria Transformadora
-   Serviços profissionais
-   Comércio a retalho

### <a name="see-industry-specific-demo-data-in-trials"></a>Consulte dados de demonstração específicos de setor em versões de avaliação

Para uma versão só de leitura do Customer Insights, personalizada a um setor ou cenário específicos, comece no ambiente de Demonstração. 
 
1.  Em informações de audiência, escolha o ambiente de **Demonstração** no seletor de ambientes.

2.  Em **Base**, escolha uma opção no menu pendente Selecionar uma demonstração de setor.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Escolha um setor para o ambiente de avaliação.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Crie dados de demonstração específicos de cenário no seu próprio ambiente

Como administrador, selecione o seletor de ambientes no cabeçalho da aplicação para criar um novo ambiente. No novo ambiente, pode configurar as suas próprias origens de dados e configurar a aplicação de acordo com os seus requisitos. 

1.  Em informações de audiência, aceda a **Dados** > **Origens de dados**.

2.  Para importar as suas próprias origens de dados, vá ao [guia sobre ingestão de dados](data-sources.md).     
   Se preferir trabalhar com dados de exemplo que lhe permitam experimentar a ingestão de dados, pode ingerir os dados de demonstração de setor no seu ambiente. Escolha a opção **Importar a partir do Datahub** e siga os passos abaixo.

3.  Selecione o cartão do setor que se adequa ao seu cenário. 

4.  Reveja e, opcionalmente, atualize o nome sugerido da origem de dados. 

5.  Selecione **Seguinte** para ingerir os dados de exemplo. 

Pode agora utilizar os dados ingeridos para adaptar o Customer Insights ao seu cenário. Para ver um ambiente específico dos dados de demonstração ingeridos, escolha a opção **Demonstração de <Industry>** no seletor do ambiente.

## <a name="limitations-in-trials"></a>Limitações das versões de avaliação

- Por predefinição, as versões de avaliação estão ativas por 30 dias. No entanto, pode prolongá-la após o dia 23 quando iniciar sessão na sua versão de avaliação.
- Não pode usar a sua própria conta de armazenamento do Azure Data Lake para armazenar dados de produção durante uma avaliação. No entanto, pode ingerir dados a partir de uma conta de armazenamento do Data Lake.
- Pode armazenar dados de até 3 GB no ambiente Dataverse que é aprovisionado automaticamente quando iniciar uma versão de avaliação do Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Copiar dados de uma versão de avaliação para uma subscrição paga

Geralmente, recomendamos começar de novo com os seus próprios dados ao atualizar para a versão paga do Customer Insights. 

Opcionalmente, pode copiar os seus dados de um ambiente de avaliação se comprar o Customer Insights. Tem de ser o administrador da avaliação do Customer Insights e o admin global do seu inquilino do Microsoft 365 ou o administrador do Dynamics 365 na sua organização para migrar as definições de um ambiente de avaliação para um ambiente pago. 

Depois de iniciar sessão na sua instância paga do Customer Insights pela primeira vez, é-lhe pedido que crie um novo ambiente. Neste processo, pode optar por copiar a configuração de um ambiente existente e migrar a maioria das definições. Se tiver as permissões acima mencionadas, o ambiente de avaliação aparecerá nesta lista. Para obter mais informações, consulte [Copiar a configuração do ambiente](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Passos seguintes

Reveja os seguintes artigos para ajudá-lo a começar com a configuração do Customer Insights. 

- [Adicionar mais utilizadores e atribuir permissões](permissions.md).
- [Ingerir as suas origens de dados](data-sources.md) e executá-las através do [processo de unificação de dados](data-unification.md) para obter [perfis de clientes unificados](customer-profiles.md).
- [Enriquecer os perfis de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- Crie [segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para rever KPIs.
- Configure [ligações](connections.md) e [exportações](export-destinations.md) para processar subconjuntos dos seus dados noutras aplicações.
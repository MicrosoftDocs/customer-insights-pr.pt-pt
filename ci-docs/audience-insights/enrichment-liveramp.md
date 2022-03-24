---
title: Melhoramento de dados de identidade da LiveRamp
description: Melhore os perfis de clientes com dados do LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373045"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Melhore os perfis de clientes com os dados de identidade da LiveRamp (Pré-visualização) 

A LiveRamp fornece uma resolução de identidade offline determinística e a consolidação dos dados de clientes. Pode mapear identificadores pessoais nos seus dados de clientes para o gráfico de identidade da AbiliTec e receber os IDs da AbiliTec. Em seguida, pode utilizar estes IDs para melhorar a unificação dos seus dados de clientes. 

## <a name="prerequisites"></a>Pré-requisitos 

Para configurar o melhoramento, devem ser cumpridos os seguintes pré-requisitos: 

- Tem uma subscrição da LiveRamp ativa. Para obter uma subscrição, contacte a sua equipa da conta LiveRamp ou [dynamics@liveramp.com](mailto:dynamics@liveramp.com) para obter mais informações.   

- Uma subscrição ativa da AbiliTec com um ID de cliente e segredo para aceder à API. Para mais informações, consulte [Hub de Programadores da API AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Países/regiões suportados 

Atualmente, suportamos o melhoramento de perfis de clientes com dados da LiveRamp apenas nos Estados Unidos. 

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento 

1. Aceda a **Dados** > **Enriquecimento** e selecione o separador **Descobrir**. 

1. Selecione **Melhorar os meus dados** no mosaico **Identidade**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Mosaico Identidade na página de descrição geral do melhoramento. ":::

1. Selecione uma [ligação](connections.md) na lista pendente. Contacte um administrador se não houver nenhuma ligação disponível. Se for administrador, poderá criar uma ligação ao selecionar **Adicionar ligação**. Escolha **LiveRamp** a partir da lista pendente. 

1. Selecione **Seguinte** e escolha o **Conjunto de dados do cliente** que pretende melhorar com dados de identidade da LiveRamp. Pode selecionar a entidade *Cliente* para melhorar todos os seus perfis de cliente ou selecionar uma entidade *segmento* para melhorar apenas os perfis de cliente contidos nesse segmento. 

1. Selecione **Seguinte** e defina o tipo de campos dos seus perfis unificados que devem ser usados para procurar dados de identidade correspondentes da LiveRamp. É necessário pelo menos um dos campos **Nome e endereço**, **Telefone** ou **E-mail**. 

   > [!TIP]
   > Quanto mais identificadores e campos de chave mapear, maior será a probabilidade de uma taxa de correspondência mais alta 

1. Mapeie os campos da sua entidade *Cliente* unificada que será usada para fazer a correspondência com o gráfico de IDs AbiliTec da LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opções de mapeamento de dados para o melhoramento da LiveRamp.":::

1. Selecione **Seguinte** para concluir o mapeamento de campos. 

1. Forneça um **Nome** para o melhoramento e a **Entidade de saída**. 

1. Selecione **Guardar enriquecimento** depois de rever as suas escolhas. 

## <a name="configure-the-connection-for-liveramp"></a>Configurar a ligação para a LiveRamp 

Tens de ser um administrador para [configurar ligações](connections.md). Selecione **Adicionar ligação** ao configurar o melhoramento ou vá para **Admin** > **Ligações** e selecione **Configurar** no mosaico **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Painel de configuração para configurar a ligação ao serviço AbiliTec da LiveRamp. ":::

1. Para **Nome a apresentar**, insira o nome da ligação. 

1. Forneça um ID de cliente e um segredo da LiveRamp válidos. 

1. Reveja e forneça o seu consentimento para a **Privacidade e conformidade de dados** selecionando a caixa de verificação **Concordo**. 

1. Selecione **Verificar** para validar a configuração. 

1. Para concluir a ligação, selecione **Guardar**. 

## <a name="enrichment-results"></a>Resultados do enriquecimento 

Para iniciar o processo de melhoramento, selecione Executar na barra de comando. Também pode deixar o sistema executar o melhoramento automaticamente como parte de uma  [atualização agendada](system.md#schedule-tab). O tempo de processamento depende do tamanho dos dados do seu cliente. 

Após a conclusão do processo de melhoramento, pode rever os dados de perfis de clientes recentemente melhorados em  **Os meus melhoramentos**. Além disso, encontrará a hora da última atualização e o número de perfis enriquecidos. 

Pode aceder a uma vista detalhada de cada perfil melhorado ao selecionar  **Ver dados melhorados**. 

## <a name="next-steps"></a>Passos seguintes

Desenvolva a partir dos seus dados de clientes melhorados. Utilize os IDs da AbiliTec para consolidar os perfis de clientes numa vista baseada na pessoa. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privacidade e conformidade de dados 

Quando ativa Dynamics 365 Customer Insights para transmitir dados ao LiveRamp, permite a transferência de dados fora dos limites de conformidade para Dynamics 365 Customer Insights, incluindo dados potencialmente sensíveis, tais como Dados Pessoais. A Microsoft transferirá estes dados após a sua instrução, mas fica responsável por assegurar que a LiveRamp cumpre quaisquer obrigações de privacidade ou segurança que possa ter. Para mais informações, consulte a [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). O seu administrador Dynamics 365 Customer Insights pode remover este melhoramento em qualquer altura para descontinuar a utilização desta funcionalidade. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

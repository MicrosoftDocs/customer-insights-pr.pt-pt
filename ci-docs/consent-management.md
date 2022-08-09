---
title: Utilizar consentimento do cliente
description: Honre as preferências de consentimento dos clientes no Customer Insights importando dados de consentimento.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188062"
---
# <a name="use-customer-consent"></a>Utilizar consentimento do cliente

Os regulamentos de proteção de dados e de privacidade oferecem às pessoas o direito de governar a forma como uma organização utiliza os seus dados pessoais. Exemplos desses regulamentos são o Regulamento Geral sobre a Proteção de Dados na União Europeia ou a Lei de Privacidade do Consumidor nos Estados Unidos. Estes regulamentos permitem que as pessoas optem ativamente por não ter os dados pessoais recolhidos, processados por, ou partilhados com, terceiros.  

Os clientes podem optar por retirar ou reter o seu consentimento para formas de contacto específicas. Também poderão pedir-lhe que os remova da coleção, armazenamento, utilização ou venda dos respetivos dados pessoais. É importante que a sua organização honre o consentimento e as preferências de privacidade de todos os clientes.  

O Dynamics 365 Customer Insights ajuda-o a honrar os pedidos dos seus clientes importando e armazenamento as suas preferências como parte dos perfis de cliente unificado.

Se os dados de consentimento forem armazenados separadamente dos perfis de cliente, [adicione os seus dados de consentimento como uma nova origem de dados](#import-and-unify-consent-data). A origem de dados que contém os dados de consentimento são adicionados ao processo de unificação de dados. A unificação bem sucedida de dados de consentimento e perfis de cliente leva a perfis de clientes unificados que contêm as informações de consentimento. Para perfis de cliente que já contenham informações de consentimento, vá diretamente para a secção [utilizar dados de consentimento](#use-consent-data).

## <a name="prerequisites"></a>Pré-requisitos

As informações seguintes têm de estar disponíveis nos dados de origem para unificar dados de consentimento com outros perfis de cliente:

- Chave alternativa para mapear as informações de consentimento para perfis de utilizador no Customer Insights. Por exemplo, um endereço de e-mail ou um número de telefone.
- Valor do consentimento para determinar o estado do consentimento do cliente.

Considere adicionar as seguintes informações *opcionais*:

- Chave primária para atualizar o estado de consentimento se um cliente pedir uma alteração.
- Tipo de consentimento, se houver mais do que uma forma de processar informações de clientes.
- Data do consentimento ou quaisquer outros tipos de dados relevantes para os seus cenários de consentimento.

Exemplo de tabela de uma base de dados de consentimento simples com várias opções de consentimento:

|ID do Consentimento (chave primária)   |E-mail (chave alternativa)  |Opção de consentimento  |Valor do consentimento  |
|---------|---------|---------|---------|
|5    |  holly@contoso.com       |  Newsletter       |  False       |
|2    |  holly@contoso.com       |  Atualizações de produtos       |  True       |
|3    |  frank@contoso.com       |  Newsletter       | True        |
|4    |  frank@contoso.com       |  Atualizações de produtos       |  False       |

## <a name="import-and-unify-consent-data"></a>Importar e unificar dados de consentimento

Importe os dados de consentimento da mesma forma que ingere outras origens de dados para o Customer Insights. Para mais informações sobre as origens de dados suportadas e como importá-las, consulte [Descrição geral de origens de dados](data-sources.md).

Para mais informações sobre como unificar as suas origens de dados, consulte [Descrição geral da unificação de dados](data-unification.md).

## <a name="use-consent-data"></a>Utilizar dados de consentimento

Depois de os dados de consentimento fazerem parte dos perfis de cliente unificados, podem ser utilizadas no Customer Insights. Por exemplo, crie um segmento com uma regra para garantir que honra as preferências de privacidade e proteção de dados dos seus clientes. As regras que suportam preferências de consentimento são utilizadas para excluir utilizadores de um segmento com base em atributos de perfil. Adicione uma regra a um segmento que exclui perfis de clientes que não forneceram consentimento para contacto.

Consultando a tabela de amostra acima, um segmento poderá conter esta regra: `Consent option=Newsletter & Consent value=True`. Esta configuração faz com que um segmento que honre preferências de contacto para enviar um boletim.

Para mais informações sobre a criação de segmentos, consulte [Criar segmentos](segment-builder.md).

Após o segmento ser criado, pode utilizar uma das muitas [opções de exportação](export-destinations.md) para utilizar o segmento noutras aplicações.

## <a name="ensure-updated-consent-status"></a>Garantir o estado de consentimento atualizado

É importante manter o estado de consentimento dos clientes atualizado. A atualização agendada no Customer Insights importa sempre o estado mais recente das suas origens de dados. Estas informações são processadas através da unificação de dados e resulta em perfis de clientes atualizados. Em seguida, estes perfis atualizados são utilizados para atualizar segmentos, para se certificar de que trabalha com as informações mais atualizadas.

Por outras palavras, certifique-se de que os dados de origem que são importados para o Customer Insights têm sempre as informações mais recentes.

Para mais informações, consulte [Atualizar segmentos manualmente](segments.md#refresh-segments) ou [Configurar uma atualização agendada](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]

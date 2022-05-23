---
title: Funcionalidades novas e para breve
description: Informações sobre as novas funcionalidades, melhoramentos e correções de erros.
ms.date: 05/03/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 386198c838929a20e136288fffb1015707654d8d
ms.sourcegitcommit: 9f256af5c4f7e99305bf09087f7ec05eebeae6a0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8700951"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novidades do Dynamics 365 Customer Insights

É com entusiasmo que anunciamos as nossas mais recentes atualizações! Este artigo resume as funcionalidades de pré-visualização públicas, melhorias gerais de disponibilidade e atualizações de funcionalidades. Para conhecer os planos de funcionalidades a longo prazo, consulte os [Planos de versão do Dynamics 365 e do Power Platform](/dynamics365/release-plans/).

Implementamos as atualizações numa base por região. Assim, certas regiões podem ver características antes de outras. A menos que seja especificado de forma diferente, não precisa de tomar nenhuma ação e atualizaremos a aplicação automaticamente sem tempo de inatividade.

> [!TIP]
> Para enviar e votar em pedidos de funcionalidades e sugestões para produtos, vá para o [portal de ideias de aplicação do Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="april-2022-updates"></a>Atualizações de abril de 2022

As atualizações em abril de 2022 incluem novas funcionalidades, atualizações de desempenho e correções de erros.

### <a name="dun--bradstreet-enrichment-preview"></a>Melhoramento da Dun & Bradstreet (Pré-visualização)

A Dun & Bradstreet fornece dados, análises e informações comerciais para empresas. Permite que os clientes com perfis de clientes unificados para as empresas enriqueçam os seus dados. Os melhoramentos incluem atributos como o número DUNS, o tamanho da empresa, a localização, o setor e muito mais.

Para mais informações, consulte [Melhoramento de perfis de empresa com Dun & Bradstreet (pré-visualização)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definir o tipo de medida ao criar uma nova medida

Agora, pode distinguir medidas para perfis individuais e medidas para toda a empresa. Enquanto as medidas de negócio são mostradas na página inicial do Customer Insights, as medidas de cliente encontram-se nas vistas de cliente detalhadas.

Para mais informações, consulte [Utilizar o construtor de medidas para criar medidas de raiz](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidação de da documentação do Customer Insights

Revimos os nossos artigos de documentação e removemos as menções de capacidades de informações de cativação e de informações de audiência. A partir de agora, iremos referir-nos sempre ao nome de produto Customer Insights quando escrevermos sobre as funcionalidades principais da aplicação. Esta alteração também leva a uma restruturação significativa do índice, da estrutura do URL e dos caminhos de ficheiro no repositório de documentação subjacente. Todos os marcadores ou ligações existentes continuam a funcionar e a redirecionar para os URLs atualizados.

Se quiser partilhar connosco o que acha sobre esta alteração ou identificar algo que não esteja a funcional como esperado [submeta os seus comentários nesta página](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Atualizações de março de 2022

As atualizações em março de 2022 incluem novas funcionalidades, atualizações de desempenho e correções de erros.

### <a name="liveramp-abilitec-enrichment-preview"></a>Melhoramento da AbiliTec LiveRamp (Pré-visualização)

A LiveRamp fornece uma resolução de identidade e a consolidação dos dados de clientes. Pode mapear identificadores pessoais nos seus dados de clientes para o gráfico de identidade da AbiliTec e receber os IDs da AbiliTec. Em seguida, pode utilizar estes IDs para melhorar a unificação dos seus dados de clientes.

Para obter mais informações, consulte [Melhorar os perfis de clientes com dados de identidade da LiveRamp (Pré-visualização)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizar segmentos e medidas com etiquetas e filtros
Se a sua organização mantiver muitos segmentos ou medidas, localizar o correto pode, por vezes, ser sentido como um desafio. Esta nova funcionalidade permite-lhe organizar listas utilizando etiquetas e colunas. Ajuda a encontrar dados de forma rápida e fácil e a personalizar as vistas.

Para mais informações, veja [Trabalhar com etiquetas e colunas](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Ativar a partilha de dados com o Dataverse ao utilizar a sua própria conta de armazenamento

Se o seu ambiente utilizar o Azure Data Lake Storage para armazenar dados do Customer Insights, a partilha de dados com o Microsoft Dataverse necessita de alguma configuração adicional.
Anteriormente, só era possível ativar a partilha de dados com o Dataverse quando os seus dados estavam armazenados no nosso data lake gerido. 

Para obter mais informações, consulte [Ativar a partilha de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage (Pré-visualização)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Novos destinos de exportação: Iterable e Braze

Continuaremos a expandir o nosso ecossistema de destinos de exportação com novas ligações. Agora, já é possível exportar segmentos para a Iterable e Braze para utilizar os respetivos serviços de ativação.

Para obter mais informações, consulte [Exportar segmentos para a Iterable (pré-visualização)](export-iterable.md) e [Exportar segmentos para a Braze (pré-visualização)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Melhoramentos à exportação do Marketo e Google Ads

A alteração de APIs em serviços ligados leva a atualizações para que os conectores sejam executados de forma fiável e sem problemas. Lançámos algumas atualizações para as exportações para serviços do Marketo e Google Ads:

- Google Ads: a nova versão do conector de exportação do Google Ads simplifica a experiência de autenticação e agora permite-lhe criar automaticamente novas audiências do Google Ads. 
- Marketo: a nova versão do conector de exportação do Marketo fornece suporte para o ID do Marketo, permitindo-lhe evitar a duplicação de dados, atualizar registos existentes e criar novos registos no Marketo. 


## <a name="february-2022-updates"></a>Atualizações de fevereiro de 2022

As atualizações em fevereiro de 2022 incluem novas funcionalidades, atualizações de desempenho e correções de erros.

### <a name="general-availability-for-prediction-models"></a>Disponibilidade geral para modelos predição

Os modelos de predição prontos a utilizar, incluindo **abandono de subscrições**, **abandono transacional** e **valor vitalício do cliente(CLV)** ficam em disponibilidade geral como parte do Customer Insights. 

Para mais informações, consulte [Descrição geral das predições](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nova origem de dados: Integração com o Azure Synapse Analytics (Pré-visualização)

Azure Synapse Analytics é um serviço de análise empresarial que acelera o tempo para insights em armazéns de dados e sistemas de macrodados.

As organizações que já utilizam o Azure Synapse Analytics podem ingerir esses dados para o Customer Insights. 

Para obter mais informações, consulte [Ligar uma origem de dados do Azure Synapse (Pré-visualização)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Melhoramento da LiveRamp (Pré-visualização)

A LiveRamp fornece uma resolução de identidade e a consolidação dos dados de clientes. Pode mapear identificadores pessoais nos seus dados de clientes para o gráfico de identidade da AbiliTec e receber os IDs da AbiliTec. Em seguida, pode utilizar estes IDs para melhorar a unificação dos seus dados de clientes.

Para obter mais informações, consulte [Melhorar os perfis de clientes com dados de identidade da LiveRamp (Pré-visualização)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Melhoramento de origens de dados (Pré-visualização)

Utilize dados de origens como a Microsoft e outros parceiros para melhorar os dados dos seus clientes antes da unificação de dados. Os melhoramentos de origens de dados ajudam a produzir uma maior qualidade e integralidade de dados que podem ajudar a obter melhores resultados quando unificar os seus dados.

Para obter mais informações, consulte [Melhoramento para origens de dados (Pré-visualização)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Alterar proprietário do ambiente

Apesar de vários utilizadores poderem ter permissões de administrador no Customer Insights, apenas um utilizador é o proprietário de um ambiente. Uma experiência melhorada permite alterar os proprietários de um ambiente e reclamar a propriedade se um antigo proprietário sair da organização. 

Para mais informações, consulte [Alterar o proprietário de um ambiente](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>O processo de preparação de dados lista a razão dos danos aos registos danificados

A preparação de dados agora mostra a razão de corrupção de todos os campos com dados corrompidos. As informações são fornecidas ao nível do registo individual para facilitar a identificação. 

Para obter mais informações, consulte [Origens de dados danificadas](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Fim da pré-visualização para as funcionalidades de relatórios na capacidade de informações de interação

A pré-visualização da capacidade informações de interação do Dynamics 365 Customer Insights terminou em 15 de fevereiro de 2022.  
Esta alteração significa que a experiência de avaliação do Customer Insights já não inclui a capacidade de criar funis ou outras funcionalidades de relatórios.

Convidámo-lo a explorar e a avaliar as muitas outras funcionalidades do [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), a plataforma de dados de clientes da Microsoft (CDP).    
 
Durante um período de transição, os participantes de pré-visualização existentes ainda têm acesso a algumas capacidades e funcionalidades de pré-visualização:

- Obtenha código para instrumentar um site ou aplicação móvel 
- Ver eventos e propriedades de eventos 
- Melhorar perfis unificados com eventos ingeridos e refinados para beneficiar do valor total dos dados dos seus clientes
  
Durante o período de transição, os eventos capturados ainda são transmitidos para o Data Lake ligado. Assim que esta funcionalidade for desativada, a partilha de dados será interrompida e nenhum evento novo será enviado para o armazenamento ligado.
Contacte diretamente a sua equipa da Conta Microsoft se tiver dúvidas sobre o final da pré-visualização da capacidade. A sua equipa de Contas vai mantê-lo atualizado sobre os próximos lançamentos. 

## <a name="january-2022-updates"></a>Atualizações de janeiro de 2022

As atualizações em janeiro de 2022 incluem novas funcionalidades, atualizações de desempenho e correções de erros.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Análise de sentimentos do feedback do seu cliente

O Customer Insights fornece uma nova funcionalidade com tecnologia de IA para sintetizar o sentimento do cliente e identificar aspetos de negócio específicos como oportunidades para melhorias direcionadas. Ao analisar o feedback escrito dos seus clientes, pode obter informações precisas a baixo custo. A Análise de sentimentos com tecnologia de modelos de Processamento de Linguagem Natural (NLP) que geram duas informações derivadas para cada ID do cliente. Uma classificação de sentimentos (de –5 a 5) e uma lista de aspetos comerciais aplicáveis. 

Para obter mais informações, consulte [Analisar sentimentos em feedback de clientes (Pré-visualização)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
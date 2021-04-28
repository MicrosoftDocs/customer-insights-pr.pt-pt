---
title: Funcionalidades novas e para breve
description: Informações sobre as novas funcionalidades, melhoramentos e correções de erros.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 2159481f9355de738a7b457dcf0849a45c3e08db
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896249"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>O que há de novo na capacidade de informações de audiência do Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

É com entusiasmo que anunciamos as nossas mais recentes atualizações! Este artigo resume as funcionalidades de pré-visualização públicas, melhorias gerais de disponibilidade e atualizações de funcionalidades. Para conhecer os planos de funcionalidades a longo prazo, consulte os [Planos de versão do Dynamics 365 e do Power Platform](/dynamics365/release-plans/).

Implementamos as atualizações numa base por região. Assim, certas regiões podem ver características antes de outras. A menos que seja especificado de forma diferente, não precisa de tomar nenhuma ação e atualizaremos a aplicação automaticamente sem tempo de inatividade.

> [!TIP]
> Para enviar e votar em pedidos de funcionalidades e sugestões para produtos, vá para o [portal de ideias de aplicação do Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="march-2021-updates"></a>Atualizações de março de 2021

As atualizações em março de 2021 incluem várias atualizações de versão de funcionalidades e de desempenho, bem como correções de erros.

### <a name="activities"></a>Atividades

- **Assistente de atividade e tipos semânticos** Melhorámos e atualizámos a nossa experiência de mapeamento de atividades para orientar e simplificar a criação do mapeamento de atividades. Nesta nova experiência, os utilizadores obtêm uma experiência guiada para ajudar a completar cada passo do processo. No passo de mapeamento de atividades, além de escolher entre muitos tipos de atividade, o utilizador pode optar por mapear semanticamente dados para *Subscription* e/ou *SalesOrderLine* para esquemas de norma do setor, que podem ser usados para consumo a jusante.    
  Para mais informações, veja [Atividades de cliente](activities.md).

### <a name="data-ingestion"></a>Ingestão de dados

- **Ligar a origens de dados no local utilizando fluxos de dados e gateways do Power Platform** Temos o prazer de anunciar a pré-visualização de fluxos de dados e conectividade no local do Power Platform utilizando gateways no Customer Insights com um ambiente Power Platform ou Dataverse associado. Quaisquer novas origens de dados criadas num ambiente do Customer Insights com um ambiente Dataverse associado irão assumir a predefinição dos fluxos de dados do Power Platform que trazem a conectividade de dados no local e um rico conjunto de conectores e capacidades de transformação.

### <a name="extensibility"></a>Extensibilidade

- **Exportações organizadas em ligações e exportações** Mudámos o nome da página **Exportar destinos** para **Ligações** e adicionámos uma página separada para **Exportações**. Como parte desta atualização, vamos transitar as exportações existentes para pares de uma ligação e uma exportação utilizando essa ligação. Os administradores têm agora mais clareza sobre os dados de saída na página **Ligações**. Todas as funções de utilizador têm acesso à página **Exportações**, mas apenas os administradores podem optar por permitir que os contribuidores editem exportações específicas com ligações partilhadas.     
  Para mais informações, consulte [Descrição geral das ligações](connections.md) e [Descrição geral das exportações](export-destinations.md).

- **Exportar segmentos para a Campaign Monitor** Alargámos os nossos destinos de exportação para incluir a Campaign Monitor. Agora, pode exportar segmentos do Customer Insights para listas da Campaign Monitor e utilizá-los como a linha de base para as suas campanhas de marketing.    
   Para mais informações, consulte [Exportar para a Campaign Monitor](export-campaign-monitor.md).

- **Exportar segmentos para a Constant Contact** Alargámos os nossos destinos de exportação para incluir a Constant Contact. Agora, pode exportar segmentos do Customer Insights para listas da Constant Contact e utilizá-los como a linha de base para as suas campanhas de marketing.   
   Para mais informações, consulte [Exportar para a Constant Contact](export-constant-contact.md).

- **Exportar segmentos para o RollWorks** Alargámos os nossos destinos de exportação para incluir o RollWorks. Agora, pode exportar segmentos do Customer Insights para audiências do RollWorks e utilizá-los como a linha de base para a sua publicidade B2B.    
   Para mais informações, consulte [Exportar para o RollWorks](export-rollworks.md).

- **Exportar segmentos para o Snapchat** Alargámos os nossos destinos de exportação para incluir o Snapchat. Agora, pode exportar segmentos do Customer Insights para audiências do Snapchat e utilizá-los como a linha de base para a sua publicidade.     
   Para mais informações, consulte [Exportar para o Snapchat](export-snapchat.md).

### <a name="predictions"></a>Predições

- **Utilizar filtros de produtos em recomendações de produtos preditivas** Adicionámos a capacidade de utilização de filtros de produtos no nosso modelo de recomendação de produtos. Agora, pode criar um predição que utiliza apenas um subconjunto dos seus produtos.    
   Para obter mais informações, consulte [Configurar filtros de produtos](predict-product-recommendation.md#configure-product-filters).

- **Criar segmentos a partir de predições de modelos** Adicionámos uma forma rápida de criar segmentos utilizando os resultados de um modelo de predição. A partir da página de resultados do modelo, pode facilmente criar um novo segmento selecionando a nova opção **Criar segmento**.    
  Para obter mais informações, consulte [Criar um segmento baseado num modelo de predição](prediction-based-segment.md).

- **Explicações para recomendações de produtos** Adicionámos informações que explicam os fatores principais aprendidos pelo modelo de IA para gerar recomendações de produtos e até que ponto esses fatores contribuem para as recomendações de produtos. Estas informações são adicionadas ao ecrã de resultados do modelo.    
   Para obter mais informações, consulte [Rever um estado de predição e resultados](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Atualizações de fevereiro de 2021

As atualizações em fevereiro de 2021 incluem várias atualizações de versão de funcionalidades, de desempenho e correções de erros.

#### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos para o AdRoll**

  Expandimos os nossos destinos de exportação para incluir o AdRoll. Agora pode exportar segmentos do Customer Insights para audiências do AdRoll e usá-los como base para a sua publicidade. Para mais informações, consulte [Conector para AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmentos
 
- **Duplicar um segmento**
  
  Para criar um novo segmento baseado num existente, pode agora duplicar um segmento e editar o segmento duplicado para refiná-lo ainda mais. 

- **Adicionar atributos adicionais a um segmento**

  Agora pode incluir atributos na saída do segmento, mesmo que estes atributos não façam parte do perfil do cliente. Por exemplo, inclua ID de subscrição num segmento, mesmo que faça parte da entidade de subscrição que tem uma relação M:1 com a entidade do cliente. Desde que o atributo pertença a uma entidade relacionada com a entidade cliente, pode agora incluir estes atributos.  

#### <a name="predictions"></a>Predições

- **Criar recomendações de produtos preditivas**

  Compreender o que os clientes estão interessados em comprar é um dos primeiros passos necessários para melhorar as receitas do negócio e conquistar a fidelização do cliente através da personalização e cativação. Fornecer recomendações para produtos que não estejam alinhados com os interesses do seu cliente pode criar uma sensação de afastamento entre o cliente e o seu negócio e, por fim, limitar a receita e experiência potencial global para um cliente. 

  Utilizando os seus próprios dados, pode agora criar previsões para que produtos os seus clientes poderão adquirir no futuro. Para mais informações, consulte [Predição de recomendação de produtos](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administração de sistema

- **Copiar ambiente suporta mais tipos de origens de dados**

  Os administradores podem copiar as configurações de ambientes para um novo ambiente na mesma organização. Esta funcionalidade expande a funcionalidade de cópia de ambiente para casos em que são utilizadas origens de dados com base num data lake do Common Data Service ou numa pasta Common Data Model.

## <a name="january-2021-updates"></a>Atualizações de janeiro de 2021

As atualizações em janeiro de 2021 incluem várias atualizações de versão de funcionalidades, de desempenho e correções de erros.

#### <a name="extensibility"></a>Extensibilidade

- **Funcionalidade alargada e desempenho melhorado para exportação SFTP** Pode agora exportar todas as entidades de saída do Customer Insights para um anfitrião SFTP. Anteriormente, a exportação limitava-se a entidades de segmento. Além disso, o desempenho da exportação SFTP permite mais volume de dados em menos tempo, dependendo do desempenho do seu anfitrião SFTP.    
  Para mais informações, consulte [Conector para SFTP (pré-visualização)](export-sftp.md).  

#### <a name="segments"></a>Segmentos

- **Os segmentos sugeridos com tecnologia de aprendizagem automática para melhorar métricas** Há uma nova forma de descobrir e criar segmentos. O sistema utiliza um modelo de IA para sugerir segmentos que podem ajudar a melhorar um KPI (medida) que já está a monitorizar. Mostramos a extensão da influência dos atributos que seleciona numa medida ou noutro atributo principal. Estas informações ajudam a encontrar potenciais segmentos que apresentem oportunidades.    
  Para mais informações, consulte [Segmentos sugeridos (pré-visualização)](suggested-segments.md).

#### <a name="data-unification"></a>Unificação de dados

- **Experiência de correspondência melhorada** Na área de unificação de dados, a experiência de correspondência foi atualizada. Permite-lhe configurar e ver as regras de correspondência, incluindo estatísticas detalhadas para explicar em mais detalhe como funciona a correspondência. Existem opções para desativar uma regra de correspondência, para que deixe de estar ativa, mantendo as regras de configuração, arrastar e largar e de correspondência, e muito mais.
  Para mais informações, consulte [Entidades de correspondência](match-entities.md).

- **A saída de eliminação de duplicados do processo de correspondência está disponível como uma entidade** A saída do processo de eliminação de duplicados do processo de correspondência está agora escrita numa entidade separada para análise posterior. Esta entidade é constituída pelos campos utilizados no processo de eliminação de duplicados e no registo de vencedor e nos registos alternativos correspondentes que são unidos com o registo de vencedor.
  Para obter mais informações, consulte [Saída de eliminação de duplicados como uma entidade](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administração de sistema

- **Partilhar dados com o Microsoft Dataverse sem problemas** Agora pode partilhar a saída do Customer Insights com aplicações Microsoft Dataverse utilizando o Data Lake Gerido do Microsoft Dataverse. Uma vez associado a um ambiente Dataverse com o Customer Insights, obtém a opção de ativar a partilha de dados.
  Para mais informações, consulte [Gerir ambientes](manage-environments.md).


## <a name="december-2020-updates"></a>Atualizações de dezembro de 2020

As atualizações em dezembro de 2020 incluem várias atualizações de versão de funcionalidades, de desempenho e correções de erros.

### <a name="new-and-updated-features-in-december-2020"></a>Funcionalidades novas e atualizadas em dezembro de 2020

#### <a name="data-enrichment"></a>Melhoramento de dados

- **Melhoramentos de afinidade de Marca e Interesse melhorados**
  
  Simplificámos as nossas pontuações de afinidade para torná-las mais fáceis de entender e utilizar. Agora pode identificar rapidamente os clientes com base na afinidade que têm com uma determinada marca ou interesse.

  Além disso, adicionámos novas opções de configuração para controlar melhor a forma como pretende que os perfis do seu cliente sejam melhorados. 

  Para mais informações, consulte [Enriquecer perfis de clientes com afinidades de marca e interesse](enrichment-microsoft.md).

- **Controle que perfis melhorar**

  Agora pode melhorar apenas um subconjunto dos perfis do seu cliente com a opção de selecionar uma entidade de segmento em vez da entidade cliente predefinida. Crie um segmento com os perfis de cliente que gostaria de melhorar e selecione-o na configuração de melhoramento para o seu conjunto de dados de cliente.
  Atualmente, esta funcionalidade está disponível apenas para melhoramentos fornecidos pela Experian e pela HERE Technologies. Em breve, estaremos a permitir mais melhoramentos.

  Para mais informações, consulte [Melhorar perfis de clientes com dados demográficos da Experian](enrichment-experian.md) ou [Melhorar perfis de clientes com a HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Extensibilidade

- **Ative os seus segmentos através do Autopilot**

  Exporte segmentos para o Autopilot e utilize-os para fins de marketing. Para mais informações, consulte [Conector para Autopilot (pré-visualização)](export-autopilot.md).

- **Ative os seus segmentos através do SendGrid**

  Exporte segmentos para o SendGrid e utilize-os para fins de marketing. Para mais informações, consulte [Conector para SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Administração de sistema

- **Experiência de gestão de ambientes atualizada**
  
  Agora pode criar, editar, eliminar e repor ambientes diretamente do seletor de ambientes no cabeçalho da aplicação. 
  
  Além disso, o ambiente que está a usar será afixado no topo do painel do ambiente para que não precise procurá-lo mais.

  Para mais informações, consulte [Gerir ambientes](manage-environments.md).

## <a name="november-2020-updates"></a>Atualizações de novembro de 2020

As atualizações em novembro de 2020 incluem várias características, atualizações de desempenho, e correções de erros.

### <a name="new-and-updated-features-in-november-2020"></a>Características novas e atualizadas em novembro de 2020

#### <a name="data-enrichment"></a>Melhoramento de dados

- **Apresente os seus próprios dados de melhoramento através da importação personalizada SFTP (Secure File Transfer Protocol)**
  
  A importação personalizada de SFTP permite-lhe importar dados de melhoramento que não tenham de passar pelo processo de unificação de dados. Mais informações sobre a importação personalizada SFTP.

  Para mais informações, consulte [Melhorar perfis de clientes com dados personalizados (pré-visualização)](enrichment-SFTP-custom-import.md).
 
- **Melhorar os seus dados de clientes com os dados de localização da HERE Technologies**

  Com os serviços de melhoramento de dados da HERE Technologies, pode construir uma compreensão mais precisa da localização dos seus clientes com normalização de endereços, extração de latitude e longitude, e muito mais. Saiba mais sobre o melhoramento com a HERE Technologies.

  Para mais informações, consulte [Melhorar perfis de clientes com HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Unificação de dados

- **Flexibilidade para permitir a criação de perfis de dados sobre entidades e campos selecionados a partir da sua conta de armazenamento**

  Pode indicar quais as entidades e campos de dados de uma pasta Modelo de Dados Comum na sua conta de armazenamento do Azure Data Lake que pretende habilitar para o perfil de dados como parte do processo de ingestão de dados.

  Para mais informações, consulte [Estabelecer a ligação à pasta Modelo de Dados Comum](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Extensibilidade

- **Ative os seus segmentos através do Google Ads**

  Exportar segmentos das listas de audiência do Google Ads e utilizar estas listas para publicitar no Google Search, Google Display Network, YouTube e Gmail. Saiba mais sobre como ativar os seus segmentos através do Google Ads.

  Para mais informações, consulte [Conector para Google Ads](export-google-ads.md).

- **Ative os seus segmentos através do Marketo**

  Exportar segmentos para as audiências do Marketo e utilizar estas audiências para a automatização do marketing. Saiba mais sobre como ativar os seus segmentos através do Marketo. 

  Para mais informações, consulte [Conector para Marketo](export-marketo.md).

- **Ative os seus segmentos através do DotDigital**

  Exportar segmentos para a DotDigital e utilizá-los para fins de marketing. Saiba mais sobre como ativar os seus segmentos através do DotDigital. 

  Para mais informações, consulte [Conector para DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predições

- **Prever abandono transacional**

  A funcionalidade de predição de abandono da transação permite-lhe, sem a ajuda de um cientista de dados, prever a probabilidade de um cliente deixar de comprar produtos ou serviços.  Usando a pontuação de predição, é possível combinar outras informações sobre os seus clientes, como o valor do cliente, para criar segmentos de alto risco de abandono ou clientes de alto valor. Utilizar este segmento para atingir diretamente os clientes através de atividades de marketing, apoio ao cliente, e outros cenários para reduzir o risco de abandono.
 
  Configure a definição de abandono como uma janela temporal específica para o seu negócio e defina quando os clientes são considerados abandonados. Por exemplo, uma mercearia pode querer considerar um cliente em abandono se não tiver comprado nada nos últimos 30 dias.
 
  Ao continuar a criar a predição, guiá-lo-emos quanto aos dados necessários, e permitir-lhe-emos mapear dados sobre o seu negócio para os campos necessários para prever o abandono dos seus clientes. Também pode definir um horário para a reciclagem do modelo com base em novas informações no seu sistema para se adaptar à evolução das circunstâncias comerciais.
 
  Para obter mais informações, consulte [Predição de abandono transacional (pré-visualização)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administração de sistema

- **Repor ambiente**

  Reiniciar tudo num ambiente de uma instância selecionada para começar de novo.

  Para obter mais informações, consulte [Repor um ambiente existente](manage-environments.md#reset-an-existing-environment).


- **Estabelecer ligação à sua conta de armazenamento do Azure Data Lake utilizando um principal de serviço**

  Escreva e leia os dados da sua conta de armazenamento usando um principal de serviço Azure. As ligações de contas de armazenamento existentes podem continuar a utilizar a chave de conta. Oferecem também uma opção de atualização para utilizar o serviço principal a avançar. As novas ligações serão baseadas no método de autenticação do serviço principal da sua conta de armazenamento.

  Para mais informações, consulte [Estabelecer ligação a uma conta Azure Data Lake Storage Gen2 com um principal de serviço Azure para informações de audiência](connect-service-principal.md).

## <a name="october-2020-updates"></a>Atualizações de outubro de 2020

As atualizações em outubro de 2020 incluem várias características, atualizações de desempenho, e correções de erros.

### <a name="new-and-updated-features-in-october-2020"></a>Características novas e atualizadas em outubro de 2020

#### <a name="extensibility"></a>Extensibilidade

- **Exportar para Mailchimp**

Exportar segmentos para listas de audiência existentes no Mailchimp para fornecer uma experiência de correio eletrónico personalizada aos seus clientes.

Para mais informações, consulte [Conector para Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Melhoramento de dados

- **Duplicar os registos da origem numa entidade Corresponder**

Especificar regras de duplicação sobre as entidades utilizadas no processo de correspondência para identificar registos duplicados. Intercalá-los num único registo e ligar todos os registos de origem a este registo intercalado. Este registo duplicado será então utilizado no processo de correspondência entre entidades.

Para mais informações, consulte [Definir a duplicação numa entidade correspondente](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administração de sistema

- **Orquestração: Nova opção de atualização em Corresponder**

Até hoje, quando se executa o processo de intercalar, o sistema executava todos os processos a jusante que dependem do intercalar e processos subsequentes. Pode agora verificar o resultado do processo de intercalar (a entidade unificada do cliente) antes de o utilizar no processamento a jusante como segmentos ou medidas.
Na página de intercalar, pode agora optar por executar apenas a etapa de intercalar e executar apenas este processo. Para atualizar também todos os processos a jusante, pode escolher executar processos de intercalar e processos a jusante. 

## <a name="september-2020-updates"></a>Atualizações de setembro de 2020

As atualizações em setembro de 2020 incluem várias funcionalidades, atualizações de desempenho e correções de erros.

### <a name="new-and-updated-features-in-september-2020"></a>Novidades e funcionalidades atualizadas em setembro de 2020

#### <a name="activities"></a>Atividades

- **Predição inteligente de semântica de atributo**

Esta nova funcionalidade prevê os tipos semânticos de atributos de entrada que são transmitidos ao processo de unificação de dados. Utiliza modelos de aprendizagem automática que melhoram a precisão e poupam tempo.

#### <a name="enrichments"></a>Melhoramentos

- **Enriquecimento de dados demográficos da Experian**

O enriquecimento de dados demográficos da Experian está agora disponível na pré-visualização. A Experian é líder global em serviços de marketing e relatórios de crédito para consumidor e empresas. Com [os serviços de enriquecimento de dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), pode criar uma compreensão mais profunda dos seus clientes enriquecendo os seus perfis de clientes com dados demográficos como tamanho da casa, rendimento e muito mais.

Para utilizar esta funcionalidade, tem de ter uma subscrição ativa da Experian.

Para mais informações, consulte [Enriquecer perfis de clientes com dados demográficos da Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administração de sistema

- **Painel de detalhes da tarefa**

O painel de detalhes da tarefa permite-lhe ver detalhes sobre as tarefas que o sistema executa. É uma forma útil de identificar problemas com a configuração e encontrar soluções.
Reveja as mensagens de erro para ver como aborda potenciais problemas.
 
- **Informações de processamento adicionadas a mais páginas**

Esta melhoria adiciona informações sobre o estado das suas entidades na página **Entidades** e **Clientes**.
 
Além disso, pode encontrar detalhes sobre o progresso dos processos, juntamente com os detalhes da tarefa, em ambas as páginas.

- **Melhorias à página de estado do sistema**

Melhorámos a estrutura da tabela de detalhes de estado em **Sistema** > **Estado** ao rever as exportações de dados.
 
Além disso, os erros na coluna **Detalhes** são agora mais detalhados e com ações. 
 
- **Cancelar reverte a tarefa de volta ao estado anterior**

Quando cancela uma tarefa, por exemplo, no processo de correspondência, ela reverterá ao seu estado mais recente. Por exemplo, se o processo de Correspondência foi concluído ontem e o cancelar hoje, reverterá para o estado de sucesso de ontem.


## <a name="august-2020-updates"></a>Atualizações de agosto de 2020

As atualizações em agosto de 2020 incluem várias funcionalidades, atualizações de desempenho e correções de erros.

### <a name="new-and-updated-features-in-august-2020"></a>Novidades e funcionalidades atualizadas em agosto de 2020

#### <a name="data-unification"></a>Unificação de dados

- **Experiência melhorada para a fase do mapa durante a unificação de dados**

  A experiência para a fase do mapa no processo de unificação de dados permite selecionar entidades, atributos e definir semântica de uma forma mais perfeita.

  As alterações incluem:
  
  - menos interações necessárias para adicionar entidades e campos
  - capacidades de pesquisa melhoradas na página do mapa
  - identificação visual e fácil do tipo de campo sugerido

#### <a name="enrichment"></a>Melhoramento

- **Melhoramento de afinidades de interesses disponível em mais mercados**

  Estamos a alargar a disponibilidade do melhoramento de afinidades de interesses para além dos Estados Unidos para outros cinco mercados: Canadá, Austrália, Reino Unido, França e Alemanha. Com esta extensão, pode melhorar os dados do seu cliente com mais interesses aplicáveis a estes mercados. Também enriqueceremos os perfis dos seus clientes localizados nestes mercados utilizando dados de propriedade da Microsoft locais.
  Para mais informações, consulte [Enriquecer perfis de clientes com afinidades de marca e interesse](enrichment-microsoft.md)


## <a name="july-2020-updates"></a>Atualizações de julho de 2020

As atualizações em julho de 2020 incluem várias funcionalidades, atualizações de desempenho e correções de erros.

### <a name="new-and-updated-features-in-july-2020"></a>Novas e atualizadas funcionalidades em julho de 2020

#### <a name="extensibility"></a>Extensibilidade

- **Acionador do Power Automate para processo de unificação concluído**

  Alargámos os nossos acionadores para o Power Automate e permitimos criar uma notificação ou ação quando uma atualização do processo de unificação (mapa, correspondência, união) estiver concluída.    
  Para mais informações, consulte [Conector do Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Melhoramento

- **Melhoramento de afinidades de marcas disponível em mais mercados**

  Estamos a alargar a disponibilidade do melhoramento de afinidades de marcas para além dos Estados Unidos para outros cinco mercados: Canadá, Austrália, Reino Unido, França e Alemanha. Com esta extensão, pode enriquecer os dados dos seus clientes com marcas locais nestes mercados. Também enriqueceremos os perfis dos seus clientes localizados nestes mercados utilizando dados de propriedade da Microsoft locais.
  Para mais informações, consulte [Enriquecer perfis de clientes com afinidades de marca e interesse](enrichment-microsoft.md)

## <a name="june-2020-updates"></a>Atualizações de junho de 2020

As atualizações em junho de 2020 incluem várias funcionalidades, atualizações de desempenho e correções de erros.

### <a name="new-and-updated-features-in-june-2020"></a>Novas e atualizadas funcionalidades em junho de 2020

#### <a name="enrichment"></a>Melhoramento

- **Enriquecimento com dados da empresa da Leadspace**
  
  Defina campos em perfis de clientes unificados que são usados para procurar dados relacionados da empresa a partir do Leadspace. Após a execução do processo de melhoramento, os perfis B2B são melhorados com mais atributos, incluindo tamanho da empresa, localização, setor e muito mais.    
  Esta colaboração permite-lhe melhorar a qualidade dos seus dados com a entrada de serviços de terceiros. Para utilizar este enriquecimento, precisará de uma licença da Leadspace para aceder aos dados da empresa B2B. O sistema utilizará essa licença para manter os seus dados continuamente melhorados.    
  Para mais informações, consulte [Enriquecimento dos perfis da empresa com o Leadspace](enrichment-leadspace.md).

- **Página do Hub de enriquecimento**

  Todo o enriquecimento de dados disponível de fornecedores de enriquecimento de primeiros e terceiros é configurado no mesmo local. Configurar o enriquecimento de dados é uma experiência totalmente integrada que é gerida a partir de um lugar comum.    
  Para mais informações, consulte [Enriquecimento para perfis de clientes](enrichment-hub.md).

- **Enriquecimento de afinidade de marca e interesse em separado**

  As marcas e interesses estão agora disponíveis como dois enriquecimentos independentes. Os enriquecimentos separados conferem-lhe a flexibilidade para os configurar e gerir individualmente, dependendo dos requisitos ou necessidades do seu negócio.    
  Para mais informações, consulte [Enriquecer perfis de clientes com afinidades de marca e interesse](enrichment-microsoft.md).

#### <a name="extensibility"></a>Extensibilidade

- **URLs clicáveis para atividades unificadas no Suplemento de Cartão de Cliente do Dynamics 365**

  As atividades unificadas no Suplemento de Cartão de Cliente estão agora a mostrar URLs clicáveis se tais URLs tiverem sido definidas durante a configuração das atividades.    
  Para mais informações, veja [Suplemento de Cartão de Cliente](customer-card-add-in.md).

- **Afinidades de marca e interesse disponíveis no Suplemento de Cartão de Cliente do Dynamics 365**

  Um novo controlo sobre Suplemento de Cartão de Cliente do Dynamics 365 permite-lhe mostrar enriquecimentos de marca e interesse nos seus contactos em aplicações de Customer Engagement no Dynamics 365.    
  Para mais informações, veja [Suplemento de Cartão de Cliente](customer-card-add-in.md).

- **Mais acionadores do Power Automate**

  Alargámos os nossos acionadores para o Power Automate e adicionámos os seguintes acionadores:
  - Obtenha uma notificação ou realize uma ação quando uma atualização completa automatizada (fontes de dados, unificação, segmentos, medidas, exportações) concluir
  - Defina um limiar para uma medida de negócio. Por exemplo, pode criar uma notificação que é enviada quando o limiar definido é passado. Além disso, o acionador traz informações que lhe permitem construir fluxos de trabalho mais complexos no Power Automate.    
  Para mais informações, consulte [Conector do Power Automate](export-power-automate.md)

- **Exportar para Gestor de Anúncios do Facebook**
  
  Esta capacidade permite-lhe exportar segmentos para o Ads Manager do Facebook. Os segmentos são exportados como audiências personalizadas para utilizar perfis unificados de clientes em campanhas de marketing e anúncios no Facebook. O público personalizado também é utilizável para criar campanhas no Instagram através do Gestor de Anúncios do Facebook.    
  Para obter mais informações, consulte [Conector para o Gestor de Anúncios do Facebook](export-facebook.md).

#### <a name="predictions"></a>Predições

- **Predição de abandono de subscrição**

  Siga uma experiência guiada para criar predição de abandono em áreas de subscrição como serviços cloud, associação do cliente e outros setores. 

  A funcionalidade de predição de abandono de subscrição permite-lhe prever a probabilidade de um cliente parar o uso de produtos ou serviços baseados em subscrições sem envolver um cientista de dados. Utilizando a classificação de predição, pode combinar outras informações sobre os seus clientes para criar segmentos de alto risco de abandono. Com a ajuda deste segmento, pode visar diretamente clientes em marketing, apoio ao cliente, e outros cenários para reduzir o risco de abandono para clientes específicos para melhorar as receitas e reduzir os custos.

  Dentro da experiência, pode configurar a definição de abandono como uma janela baseada no tempo específica para o seu negócio. Por exemplo, um negócio de streaming de vídeo que tenha um processo de subscrição mensal pode querer considerar um cliente ter abandonado 15 dias após o termo da sua subscrição.

  À medida que prossegue com a predição, vamos guiá-lo através dos dados necessários e permitir-lhe mapear dados sobre o seu negócio para campos necessários para prever o abandono para os seus clientes. À medida que a informação do negócio muda, também pode definir um calendário para retreinar novas informações no seu sistema para se adaptar às circunstâncias de negócio em mudança.    
  Para obter mais informações, consulte [Predição de abandono de subscrição (pré-visualização)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmentos

- **Encontrar clientes semelhantes**
  
  Encontre clientes semelhantes na sua base de clientes usando inteligência artificial. Um modelos de aprendizagem automática de classificação binária atribui uma classificação de semelhança aos clientes do segmento expandido. A pontuação baseia-se na semelhança com os clientes do segmento de origem. Dependendo da classificação de semelhança, os perfis do cliente são adicionados a um segmento recém-criado.

  Por vezes referido como modelagem de sósia em marketing digital, utiliza um modelo de IA para ajudar a encontrar clientes que são semelhantes a outro segmento dos seus clientes, tendo em conta mais atributos. Não só lhe permite escolher os atributos, como também lhe permite especificar o número máximo de clientes que deveriam estar neste novo segmento. O modelo de IA irá então calcular classificações de semelhança para cada cliente com base nos seus atributos selecionados e encontrar clientes com a classificação de semelhança média mais alta. O segmento resultante incluirá clientes que se parecem com o cliente no seu segmento original.    
  Para mais informações, consulte [Clientes Semelhantes](find-similar-customer-segments.md).

- **Sobreposição de segmentos e diferenciadores**

  A sobreposição de segmentos permite-lhe ver quantos e quais os clientes comuns a dois ou mais segmentos. Por exemplo, como um segmento de clientes com gastos elevados se sobrepõe a um segmento de clientes com alta satisfação ou como um segmento de clientes agitados se sobrepõe a um segmento de clientes com baixa satisfação. Além disso, pode analisar como a sobreposição muda com base num atributo extra à sua escolha.

  Os diferenciadores de segmento revelam o que diferencia um segmento do resto dos seus clientes ou de outro segmento. Tudo o que precisa de fazer é identificar um segmento e o sistema identificará atributos de perfil e medidas que distinguem o segmento sob a forma de uma lista classificada de diferenciadores — do diferenciador mais forte para o mais fraco.    
  Para mais informações, consulte [Informações sobre segmentos (pré-visualização)](segment-insights.md).

- **Vida útil do segmento**
  
  Definir uma agenda para ativar ou desativar um segmento.    
  Para mais informações, consulte [Gerir segmentos existentes](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Atualizações de maio de 2020

As atualizações em maio de 2020 incluem várias atualizações de funcionalidades, de desempenho e correções de erros.

### <a name="new-and-updated-features-in-may-2020"></a>Funcionalidades novas e atualizadas em maio de 2020

#### <a name="data-ingestion"></a>Ingestão de dados

- **Ingestão de dados em tempo real: vistas de histórico**

  Ao utilizar a nossa API para ingerir atualizações em tempo real, pode ver até 30 dias de histórico agregado para estas atualizações. Tem acesso a agregados de todas as chamadas API bem sucedidas ou falhadas, incluindo o seu resultado, sistema de origem e outros metadados úteis.    
  Para mais informações, consulte [Ingestão de dados em tempo real](real-time-data-ingestion.md).

- **Ingestão de dados em tempo real: atualizações de perfis**

  Esta extensão da ingestão de dados em tempo real permite-lhe ver, em segundos, alterações em campos específicos de perfil do utilizador.    
  Para além da funcionalidade em tempo real para as atividades, o sistema suporta atualizações de baixa latência para campos de perfil. As atualizações em tempo real para os campos de perfil têm um tempo de validade e, portanto, não são um substituto para atualizações programadas.    
  Para mais informações, consulte [Ingestão de dados em tempo real](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Extensibilidade

- **Linha cronológica e paginação atualizadas no Suplemento do Cartão de Cliente**

  A cronologia da solução Suplemento do Cartão de Cliente corresponde à cronologia da atividade. A paginação da linha cronológica melhorou, aparecendo até 50 atividades ao mesmo tempo. Também permite carregar mais atividades na linha cronológica.    
  Para mais informações, veja [Suplemento de Cartão de Cliente](customer-card-add-in.md).

- **Acionador do Power Automate para alterações de segmentos**

  Acionadores para o Power Automate definem a partir do que se pode construir um fluxo. O acionador recém-adicionado permite definir um limiar para um segmento. Por exemplo, pode criar uma notificação que é enviada quando o limiar definido é passado.    
  Para mais informações, consulte [Conector do Power Automate](export-power-automate.md).

- **Suporte multi-inquilino para modelos personalizados**

  Configure fluxos de trabalho para modelos personalizados com um serviço Web de um inquilino do Azure Machine Learning diferente. Pode inscrever-se no inquilino do Azure Machine Learning ao criar um novo fluxo de trabalho para modelos personalizados. Esta capacidade é uma adição à capacidade existente de integração com o seu próprio serviço Web do Azure Machine Learning personalizado.    
  Para mais informações, consulte [Modelos personalizados de aprendizagem automática](custom-models.md).

#### <a name="segments"></a>Segmentos

- **Automatização de caminhos de entidade**

  Ao criar um segmento, os utilizadores precisam de definir o caminho da entidade. Esta capacidade dá um primeiro passo na automatização da definição de trajetória da entidade para que possa focar-se nos critérios de segmentação que tem em mente.    
  Se a entidade pela qual pretende segmentar os seus clientes estiver diretamente relacionada com a entidade de cliente unificada, já não terá de definir o caminho da entidade. No entanto, se houver mais do que um possível caminho de entidade, ainda precisa de defini-lo manualmente.

- **Ações em vários segmentos**
  
  Os utilizadores podem selecionar vários segmentos e tomar ações sobre eles, como atualizar os segmentos, com um único clique.    

- **Atualizar segmentos**

  Os utilizadores podem atualizar um único segmento ou selecionar apenas os segmentos que querem atualizar.    

  
- **Melhorias nos segmentos compostos**

  Os utilizadores podem criar, editar e eliminar segmentos que se baseiam em outros segmentos. Por exemplo, um segmento construído noutro segmento que foi construído num terceiro segmento.    

- **Página de lista de segmentos**

  O novo design da página de segmentos utiliza um formato de lista que permite ver mais segmentos ao mesmo tempo. Um campo de pesquisa é adicionado para encontrar segmentos rapidamente. Os utilizadores podem agora aplicar ações como transferir ou eliminar em vários segmentos ao mesmo tempo. Uma nova experiência de tendência é introduzida para identificar rapidamente mudanças significativas em segmentos.    
  Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

#### <a name="system-administration"></a>Administração de sistema

- **Customer Insights disponível no Microsoft Dynamics 365 Online Government**

  Com cada vez mais canais para interações, os dados dos cidadãos estão espalhados por vários sistemas, levando a dados isolados e uma visão fragmentada da informação sobre as interações dos cidadãos. Sem uma visão completa das interações de cada cidadão através dos canais, é impossível para os governos modernizar em escala. A Microsoft está empenhada em apoiar as necessidades tecnológicas do governo para acompanhar as expectativas dos cidadãos de experiências consistentes e responsivas.    
  Com a fase 1 da versão de 2020, o Dynamics 365 Customer Insights estará disponível para a Nuvem da Comunidade Governamental (GCC), um ambiente criado para atender às necessidades de maior conformidade das agências governamentais dos Estados Unidos. As agências ganham uma visão unificada dos cidadãos e usam a IA pré-criada para obter informações que melhorem as interações, capacitem os colaboradores e transformem comunidades, reduzindo a complexidade das TI e cumprindo os padrões de conformidade e segurança dos Estados Unidos. O Dynamics 365 Government cumpre os exigentes requisitos do Federal Risk and Authorization Management Program (FedRAMP), permitindo que as agências federais dos Estados Unidos beneficiem da poupança de custos e da segurança rigorosa da Microsoft Cloud.

## <a name="april-2020-updates"></a>Atualizações de abril de 2020

As atualizações em abril de 2020 incluem várias atualizações de funcionalidades, de desempenho e correções de erros.

### <a name="new-and-updated-features-in-april-2020"></a>Funcionalidades novas e atualizadas em abril de 2020

#### <a name="activities"></a>Atividades

- **Entidade de atividade do mapa para o tipo de atividade padrão**
  
  A configuração e armazenamento de atividade são atualmente baseados num design estático para vê-los numa linha cronológica. O significado semântico das atividades, que tem potencial para múltiplos incidentes de utilização em modelos de IA, não é totalmente usado no momento. Pretendemos tornar a linha cronológica de atividade mais dinâmica, com base no tipo de atividade e melhor compreensão semântica das atividades. Esta funcionalidade visa identificar o tipo de atividade tal como definido no Common Data Model para qualquer atividade ingerida.
  Para mais informações, veja [Atividades de cliente](activities.md).

#### <a name="data-ingestion"></a>Ingestão de dados

- **Ingestão de dados em tempo real: atividades**
  
  A ingestão de dados em tempo real fornece dados imediatamente para consumo, até a subsequente atualização programada extrair estes dados da origem de dados.    
  Para mais informações, consulte [Ingestão de dados em tempo real](real-time-data-ingestion.md).

- **Melhorias à preparação de dados**
  
  Saiba mais sobre os dados ingeridos numa entidade. Com o resumo dos dados, pode compreender as características de qualidade dos dados que podem ajudar a tomar as medidas adequadas.    
  Para mais informações, consulte [Explorar dados de entidades](entities.md#exploring-a-specific-entitys-data).

- **Ingerir dados analíticos do Dynamics 365 com o Common Data Service**
  
  O Common Data Service está disponível como uma forma de criar origens de dados. Os clientes existentes do Dynamics 365 podem ingerir entidades analíticas do Common Data Service para o Customer Insights. Uma única fonte de dados pode utilizar simultaneamente o mesmo lake gerido pelo Common Data Service num ambiente de Customer Insights.    
  Para obter mais informações, consulte [Ligar a dados num data lake gerido do Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Extensibilidade

- **Exportar para o LiveRamp**

  Ativar os seus dados no LiveRamp® para ligar a mais de 500 plataformas em ecossistemas digitais, de redes sociais e de TV. Utilize os seus dados no LiveRamp para direcionar, suprimir e personalizar campanhas publicitárias.    
  Para mais informações, consulte [Conector do LiveRamp&reg;](export-liveramp.md).

- **Suplementos de Equipas do Customer Insights**
  
  O bot fornece capacidades de pesquisa para perfis de cliente unificados. Mostrará um cartão com até 15 campos do perfil de cliente resultante. Várias correspondências devolvem uma lista de resultados onde pode selecionar um perfil.    
  Para mais informações, consulte [Bot do Teams para o Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Medidas

- **Página de lista de medidas**
  
  As melhorias à página das medidas incluem o suporte a ações numa única medida e a várias medidas ao mesmo tempo. Além disso, encontrará um campo de pesquisa para encontrar e monitorizar medidas rapidamente.    
  Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

- **Melhorias a medidas compostas**
  
  Os utilizadores podem criar, editar e eliminar medidas que se baseiam em outras medidas. Por exemplo, uma medida construída noutra medida que foi construída numa terceira medida.

#### <a name="segments"></a>Segmentos

- **Outro operador**
  
  O operador In-set permite a segmentação para os clientes por vários valores de cadeia possíveis. Antes deste operador ser adicionado, teve que construir tais segmentos com múltiplas condições de OR. O operador In-set permite-lhe fazê-lo com uma única condição.    
  Para obter mais informações, veja [Criar e gerir segmentos](segments.md).

#### <a name="system-administration"></a>Administração de sistema

- **Copiar definições de configuração para um novo ambiente**
  
  Copie a sua configuração de um ambiente para outro. Ao criar um novo ambiente, pode selecionar um ambiente existente a partir do qual pretende copiar a configuração. Atualmente, suportamos origens de dados, unificação de dados, relações, medidas e segmentos a serem copiados. As credenciais das origens de dados e os dados reais não são copiados.    
  Para mais informações, consulte [Gerir ambientes](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
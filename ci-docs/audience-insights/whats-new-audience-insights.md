---
title: Funcionalidades novas e para breve
description: Informações sobre as novas funcionalidades, melhoramentos e correções de erros.
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 5262ad20019e90e73ab121a5ab90e602c1a32b7e
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606116"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>O que há de novo na capacidade de informações de audiência do Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

É com entusiasmo que anunciamos as nossas mais recentes atualizações! Este artigo resume as funcionalidades de pré-visualização públicas, melhorias gerais de disponibilidade e atualizações de funcionalidades. Para conhecer os planos de funcionalidades a longo prazo, consulte os [Planos de versão do Dynamics 365 e do Power Platform](/dynamics365/release-plans/).

Implementamos as atualizações numa base por região. Assim, certas regiões podem ver características antes de outras. A menos que seja especificado de forma diferente, não precisa de tomar nenhuma ação e atualizaremos a aplicação automaticamente sem tempo de inatividade.

> [!TIP]
> Para enviar e votar em pedidos de funcionalidades e sugestões para produtos, vá para o [portal de ideias de aplicação do Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="september-2021-updates"></a>Atualizações de setembro de 2021

As atualizações em setembro de 2021 incluem novas funcionalidades, atualizações de desempenho e correções de erros.

### <a name="activities"></a>Atividades

- **Melhorias na linha cronológica da atividade** Ampliámos os filtros para a linha cronológica da atividade nos perfis de clientes. Além disso, pode utilizar o novo painel de filtro para filtrar por tipo de atividade e por data. As datas podem ser filtradas com diferentes condições. Para obter mais informações, consulte [Ver linhas cronológicas de atividades nos perfis de clientes](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relações

- **Suporte de relação de múltiplos saltos** Utilize relações de múltiplos saltos ao configurar atividades e definir relações entre entidades. As relações de múltiplos saltos utilizam uma entidade intermediária para ligar as duas entidades. Ao configurar uma atividade, pode utilizar uma relação de múltiplos saltos para ligar a sua entidade de atividade a uma entidade intermediária e, em seguida, a uma entidade do cliente. Pode combinar relações de múltiplos saltos com relações de múltiplos caminhos. Para obter mais informações, consulte [Relação de múltiplos saltos](relationships.md#multi-hop-relationship).

- **Suporte de relação de múltiplos caminhos** Utilize relações de múltiplos caminhos ao configurar atividades e definir relações entre entidades. As relações de múltiplos caminhos relacionam uma entidade de origem com mais de uma entidade. Ao configurar uma atividade, pode utilizar uma relação de múltiplos caminhos para ligar a sua entidade de atividade a mais de uma entidade do cliente. Pode combinar relações de múltiplos caminhos com relações de múltiplos saltos. Para obter mais informações, consulte [Relação de múltiplos caminhos](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Atualizações de agosto de 2021

As atualizações em julho e agosto de 2021 incluem uma nova funcionalidade, atualizações de desempenho e correções de erros.

### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos para Klaviyo** Alargámos os nossos [destinos de exportação para incluir o Klaviyo](export-klaviyo.md). Pode agora exportar segmentos para criar campanhas, efetuar marketing por e-mail e utilizar grupos de clientes específicos com o Klaviyo. 


## <a name="june-2021-updates"></a>Atualizações de junho de 2021

As atualizações em junho de 2021 incluem várias funcionalidades, atualizações de desempenho e correções de erros.

### <a name="data-ingestion"></a>Ingestão de dados

- **Atualizações ao progresso de unificação de dados melhoradas** Pode agora ver atualizações de estado dinâmicas e mais granulares e melhoradas nos passos do [processo de unificação de dados](data-unification.md). Esta funcionalidade permite-lhe acompanhar o progresso detalhado para compreender o fluxo do processo e tomar medidas se algum passo precisar de atenção.

### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos e outros dados para a Salesforce Marketing Cloud** Alargámos os nossos destinos de exportação para incluir a [Salesforce Marketing Cloud](export-salesforce.md). Agora pode exportar segmentos e outros tipos de dados para a Salesforce Marketing Cloud através de uma exportação SFTP com marca. A importação de dados pode ser totalmente automatizada no Salesforce e usada para criar campanhas de marketing mais eficazes.  
 
- **Exportar segmentos para ActiveCampaign** Alargámos os nossos destinos de exportação para incluir o [ActiveCampaign](export-active-campaign.md). Pode agora exportar segmentos para gerar campanhas, executar marketing por e-mail e trabalhar com grupos de clientes específicos no ActiveCampaign.
 
- **Exportar segmentos para Sendinblue** Alargámos os nossos destinos de exportação para incluir o [Sendinblue](export-sendinblue.md). Pode agora exportar segmentos para gerar campanhas, executar marketing por e-mail e trabalhar com grupos de clientes específicos com o Sendinblue.
 
### <a name="ux-updates"></a>Atualizações UX 

- **Página Clientes e detalhes de perfil novos e melhorados** Voltámos a conceber a página Clientes e as páginas de detalhe de perfil para uma melhor experiência do utilizador e melhor desempenho. Estas alterações permitem-lhe ver, ordenar, pesquisar e filtrar clientes. Os filtros estão agora representados no URL para partilhar os resultados da pesquisa com outros utilizadores de forma totalmente integrada. Os resultados da pesquisa também podem ser guardados como um segmento.    
  A página de detalhes para perfis de clientes agora agrupa dados em várias subsecções, tais como dados demográficos, IDs e outros atributos de perfil para uma melhor legibilidade. Outras secções na página de detalhes do perfil são agora mais interativas. Por exemplo, a secção de atividades permite agora filtrar e ordenar.


## <a name="may-2021-updates"></a>Atualizações de maio de 2021

As atualizações em maio de 2021 incluem várias atualizações de versão de funcionalidades e de desempenho, bem como correções de erros.

### <a name="data-ingestion"></a>Ingestão de dados

- **Ver ou modificar metadados ou definição de entidade ao anexar dados do seu Azure Data Lake Storage** Pode agora ver e editar metadados ou definição de entidade em informações de audiência ao anexar dados de uma pasta do Common Data Model no seu Azure Data Lake Storage. Esta capacidade fornece comentários, validação de modelos e verificação de erros em tempo real. Permite-lhe editar tanto o model.json como manifest.json de forma totalmente integrada.

### <a name="extensibility"></a>Extensibilidade

- **Exportações de segmentos, agenda personalizada e duplicação melhorados** Pode agora [ver todas as exportações para um segmento específico](export-destinations.md#view-exports-and-export-details) numa lista. Esta nova vista ajuda a gerir a forma como um segmento específico é usado e adaptar as exportações existentes ou criar novas.    
  Pode [definir agendas de atualização personalizadas](export-destinations.md#schedule-and-run-exports) para exportações individuais ou várias exportações ao mesmo tempo. Até agora, todas as exportações eram executadas em todas as atualizações do sistema.    
  Em vez de criar uma nova exportação do zero, pode começar com base numa existente para poupar algum tempo.

- **Exportar segmentos para o Microsoft Advertising** Alargámos os nossos destinos de exportação para incluir o Microsoft Advertising. Crie audiências de Correspondências de Clientes no Microsoft Advertising com os seus dados de perfil de cliente unificados e utilize estas audiências para campanhas de publicidade. Para mais informações, consulte [Exportar segmentos para o Microsoft Advertising](export-microsoft-advertising.md).

- **Exportar segmentos para o LinkedIn Ads** Alargámos os nossos destinos de exportação para incluir o LinkedIn Ads e permitir-lhe desbloquear o Direcionamento de Contactos, bem como o Direcionamento de Empresas através do LinkedIn ao exportar os seus dados de perfil de cliente unificado. Para mais informações, consulte [Exportar segmentos para o LinkedIn Ads](export-linkedin-ads.md).


- **Exportar segmentos para o Omnisend** Alargámos os nossos destinos de exportação para incluir o Omnisend. Utilize os segmentos criados nas informações de audiência para gerar campanhas, fornecer marketing por e-mail e utilizar grupos de clientes específicos com o Omnisend. Para mais informações, consulte [Exportar segmentos para o Omnisend](export-omnisend.md)

### <a name="predictions"></a>Predições

- **Relatório de capacidade de utilização de Dados de Entrada** O relatório de capacidade de utilização de dados de entrada fornece uma vista consolidada dos erros e avisos que as suas predições fornecidas com o programa podem estar a gerar. Também apresenta recomendações sobre como melhorar o desempenho do modelo.    
  O relatório está disponível depois de um modelo ter concluído o seu processo de preparação. É criado para cada modelo separadamente, independentemente de ter sido concluído com sucesso ou não.
  Atualmente, esta funcionalidade está apenas disponível para o modelo Abandono de Transações. Para mais informações, consulte o [Relatório de capacidade de utilização de dados de entrada](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relações

- **Visualizador de relações** A vista do visualizador de relações permite-lhe ver todas as relações existentes entre entidades e a respetiva cardinalidade. As relações estão agora organizadas em grupos: utilizador criado, sistema e relações herdadas. Também pode exportar uma vista como uma imagem. Para mais informações, consulte [Ver relações](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Atualizações de abril de 2021

As atualizações em abril de 2021 incluem várias atualizações de versão de funcionalidades e de desempenho, bem como correções de erros.

### <a name="data-unification"></a>Unificação de dados
 
- **Experiência de união melhorada para unificação de dados**    
  
   Dispomos agora de uma experiência de utilizador melhorada na configuração de união do processo de unificação de dados. As alterações incluem a ordenação intuitiva dos campos unidos e estatísticas detalhadas sobre os campos combinados e singleton.

- **Reordenar entidades e configurar todos os registos de origem na entidade Cliente**  
      
   Pode agora reordenar e remover entidades de um plano de confluência existente no processo de unificação de dados. Dá flexibilidade para reordenar as entidades no processo de correspondência de acordo com as necessidades do negócio. Adicionalmente, ativamos a inclusão de todos os registos não correspondidos na entidade *Cliente* final, o que lhes permite definir a sua definição de conjunto de dados de perfil de cliente.

### <a name="enrichments"></a>Melhoramentos

 - **Novo enriquecimento: endereços melhorados**    
  
   Estamos entusiasmados por introduzir um novo enriquecimento para melhorar endereços nos dados dos seus clientes. Os endereços nos seus dados podem não estar estruturados, estar incompletos ou incorretos. Esta funcionalidade utiliza os modelos da Microsoft para normalizar e enriquecer os seus endereços no formato do Common Data Model para uma melhor precisão e informações.
 
   Para mais informações, consulte [Enriquecimento de perfis de clientes com endereços melhorados](enrichment-enhanced-addresses.md).

- **Experiência de configuração guiada para enriquecimentos**    
  
   Revisitámos a experiência de configuração para enriquecimentos com uma experiência simples e guiada. Tem agora um processo passo a passo claro para criar e editar enriquecimentos.
 
   Adicionalmente, separámos a configuração de ligações para enriquecimentos de terceiros para permitir que a mesma ligação seja usada por vários enriquecimentos. Apenas os administradores podem configurar novas ligações, mas as ligações criadas estão disponíveis tanto para administradores como para contribuidores.    

   Para mais informações, consulte [Descrição geral das ligações](connections.md).

- **Múltiplos enriquecimentos do mesmo tipo**    
  
   Agora permitimos que os utilizadores criem e efetuem a gestão de vários enriquecimentos do mesmo tipo de enriquecimento. Por exemplo, agora pode criar dois enriquecimentos de endereços separados para enriquecer dois segmentos de cliente diferentes. Os limites aplicam-se ao número de enriquecimentos do mesmo tipo que podem ser criados e variam consoante o tipo de enriquecimento.
  
   Para mais informações, consulte [Enriquecimento para perfis de clientes](enrichment-hub.md).

## <a name="march-2021-updates"></a>Atualizações de março de 2021

As atualizações em março de 2021 incluem várias atualizações de versão de funcionalidades e de desempenho, bem como correções de erros.

### <a name="activities"></a>Atividades

- **Assistente de atividade e tipos semânticos**

   Melhorámos e atualizámos a nossa experiência de mapeamento de atividades para orientar e simplificar a criação do mapeamento de atividades. Nesta nova experiência, os utilizadores obtêm uma experiência guiada para ajudar a completar cada passo do processo. No passo de mapeamento de atividades, além de escolher entre muitos tipos de atividade, o utilizador pode optar por mapear semanticamente dados para *Subscription* e/ou *SalesOrderLine* para esquemas de norma do setor, que podem ser usados para consumo a jusante.   

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

  Os administradores podem copiar as configurações de ambientes para um novo ambiente na mesma organização. Esta funcionalidade alarga a funcionalidade do ambiente de cópia para casos em que são utilizadas origens de dados baseadas num data lake gerido do Microsoft Dataverse ou numa pasta do Common Data Model.

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




[!INCLUDE[footer-include](../includes/footer-banner.md)]
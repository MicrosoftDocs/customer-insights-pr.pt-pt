---
title: Funcionalidades novas e para breve
description: Informações sobre as novas funcionalidades, melhoramentos e correções de erros.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988934"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>O que há de novo na capacidade de informações de audiência do Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

É com entusiasmo que anunciamos as nossas mais recentes atualizações! Este artigo resume as funcionalidades de pré-visualização públicas, melhorias gerais de disponibilidade e atualizações de funcionalidades. Para conhecer os planos de funcionalidades a longo prazo, consulte os [Planos de versão do Dynamics 365 e do Power Platform](/dynamics365/release-plans/).

Implementamos as atualizações numa base por região. Assim, certas regiões podem ver características antes de outras. A menos que seja especificado de forma diferente, não precisa de tomar nenhuma ação e atualizaremos a aplicação automaticamente sem tempo de inatividade.

> [!TIP]
> Para enviar e votar em pedidos de funcionalidades e sugestões para produtos, vá para o [portal de ideias de aplicação do Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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




[!INCLUDE[footer-include](../includes/footer-banner.md)]
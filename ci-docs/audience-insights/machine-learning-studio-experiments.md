---
title: Experiências com o Machine Learning Studio (clássico)
description: Utilize os modelos Machine Learning Studio (clássico) no Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 8a861d62bdfee6a3a82468fe1ab4a3fbbdad43d4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270218"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Utilize os modelos com base no Azure Machine Learning Studio (clássico)

Os dados unificados em Dynamics 365 Customer Insights são uma origem para a construção de modelos de aprendizagem automática que podem gerar conhecimentos empresariais adicionais. O Customer Insights integra-se com o Machine Learning Studio (clássico) para utilizar os seus próprios modelos personalizados. Para ver como os modelos desenvolvidos em Azure Machine Learning estão integrados com o Customer Insights, consulte as [experiências Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Pré-requisitos

- Aceda ao Customer Insights
- Subscrição do Azure Enterprise ativa
- [Perfis de cliente unificados](data-unification.md)
- Configuração da [Exportação de entidades para Armazenamento de Blobs do Azure](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Configurar o Machine Learning Studio clássico

Num primeiro passo, precisamos de criar uma área de trabalho para e abrir o Machine Learning Studio (clássico).

1. Vá para [https://www.portal.azure.com](https://www.portal.azure.com/) e inicie sessão.

1. Selecione **Criar um recurso**.

1. Procure **Área de Trabalho do Machine Learning Studio** e selecione **Criar**.

1. Introduza os detalhes necessários para [criar a área de trabalho](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace). Escolha o **Plano de preços do plano de serviço Web** com base na quantidade de dados que pretende importar. Para melhor desempenho, selecione a **Localização** que é geograficamente mais próxima de si.

1. Depois de criar o recurso, aparecerá o dashboard da área de trabalho do Machine Learning Studio. Selecione **Iniciar Machine Learning Studio**.

   ![Interface de utilizador do Azure Machine Learning Studio](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Trabalhar com o Azure Machine Learning Studio

Pode agora criar uma nova experimentação, ou importar um modelo de experimento existente a partir da galeria de exemplo. Há exemplos de experiências para três cenários padrão:

- [Predição de abandono](#churn-analysis)

- [Valor vitalício do cliente](#customer-lifetime-value-prediction)

- [Recomendação do produto ou próxima melhor ação](#productrecommendation-or-next-best-action)

1. Se criar um novo experimento ou utilizar um modelo de experimento a partir da galeria, tem de configurar as propriedades de **Importar Dados**. Utilize a experiência guiada ou forneça diretamente detalhes para aceder ao Armazenamento de Blobs do Azure que contém os seus dados.  

   ![Experimento do Azure Machine Learning Studio](media/azure-machine-learning-studio-experiment.png)

1. Agora pode criar um pipeline de processamento personalizado para limpar e pré-processar os dados, extrair funcionalidades e treinar um modelo adequado.

1. Teste e otimize o desempenho do modelo.

1. Quando estiver satisfeito com a qualidade de um modelo, selecione **Configurar serviço Web** > **Serviço Web Preditivo**. Esta opção importa o modelo treinado e o pipeline de personalização da experimentação de preparação para um serviço preditivo. O serviço preditivo pode levar outro conjunto de dados de entrada com o esquema usado na experimentação de preparação para fazer previsões.

   ![Criar um serviço Web preditivo](media/predictive-webservice-control.png)

1. Uma vez que o experimento de serviço Web preditivo seja bem sucedido, pode implementá-lo para agendamento automático. Para que o serviço Web funcione com o Customer Insights, selecione **Implementar o Serviço Web** > **Implementar o Serviço Web [Novo] Pré-visualização**. [Obter mais informações sobre implementar o serviço Web](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Implementar um serviço Web preditivo](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modelos de exemplo da galeria

Vamos usar um cenário fictício do Hotel Contoso para os modelos deste artigo. O Hotel Contoso reúne os seguintes dados:

- Dados de CRM que consistem na atividade de estadia no hotel. O conjunto de dados inclui informações sobre as datas de estadia para cada cliente registado. Também contém informações sobre a reserva, tipos de quartos, detalhes de gastos, e assim por diante. Os dados estendem-se por quatro anos, de janeiro de 2014 a janeiro de 2018.
- Perfis de clientes de hóspedes do hotel. Estes perfis contêm informações sobre cada cliente, incluindo o seu nome, data de nascimento, endereço postal, sexo e número de telefone.
- Uso de serviços oferecidos pelo hotel, como spa, lavandaria, Wi-Fi ou estafeta. Esta informação é registada para cada cliente registado. Normalmente, o uso de serviços está ligado à estadia. Em alguns casos, os serviços podem ser usados por clientes sem ficar no hotel.

## <a name="churn-analysis"></a>Análise de Abandono

A análise de abandono aplica-se a diferentes áreas de negócio. Neste exemplo, vamos olhar para o abandono de serviço, especificamente no contexto dos serviços hoteleiros, como descrito acima. Fornece um exemplo de trabalho de um pipeline de modelo de ponta a ponta que pode ser usado como ponto de partida para qualquer outro tipo de modelo de abandono.

### <a name="definition-of-churn"></a>Definição de Abandono

A definição de abandono pode diferir com base no cenário. Neste exemplo, um hóspede que não tenha visitado o hotel no ano passado deve ser etiquetado como abandono.  

O modelo de experiência pode ser importado da galeria. Em primeiro lugar, certifique-se de que importa os dados para **Atividade de Estadia no Hotel**, **Dados de cliente** e **Dados de Utilização de Serviços** do Armazenamento de Blobs do Azure.

   ![Importar dados para o modelo de abandono](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Caracterização

Com base na definição de abandono, identificamos primeiro as funcionalidades não processadas que influenciarão a etiqueta. Em seguida, processamos estas funcionalidades não processadas em funcionalidades numéricas que podem ser usadas com modelos de aprendizagem automática. A integração de dados acontece no Customer Insights para que possamos juntar-nos a estas tabelas, utilizando o *ID de cliente*.

   ![Unir dados importados](media/join-imported-data.png)

A caracterização para a criação do modelo de análise de abandono pode ser um pouco complicada. Os dados são uma função do tempo com a nova atividade hoteleira registada diariamente. Durante a caracterização, queremos gerar funcionalidades estáticas a partir dos dados dinâmicos. Neste caso, geramos múltiplas funcionalidades da atividade hoteleira com uma janela deslizante de um ano. Também expandimos as funcionalidades categóricas, como o tipo de quarto ou o tipo de reserva, em funcionalidades separadas usando codificação de uma frequência.  

Lista final de funcionalidades:

| **Número**  | **Original_Column**          | **Funcionalidades derivadas**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Tipo de Quarto                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Tipo de Reserva                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Categoria de Viagem              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dólares Gastos                | TotalDollarSpent                                                                                                                          |
| 5           | Datas de entrada e de saída  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Utilização de Serviço                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Seleção de Modelo

Agora, temos de escolher o algoritmo ideal a usar. Neste caso, a maioria das funcionalidades baseia-se em funcionalidades categóricas. Tipicamente, os modelos baseados em árvores de decisão funcionam bem. Se houver apenas funcionalidades numéricas, as redes neurais podem ser uma escolha melhor. A máquina vetorial de suporte (SVM) também é um bom candidato nestas situações; no entanto, precisa de um pouco de sintonização para extrair o melhor desempenho. Escolhemos **Árvore de Decisão Reforçada de Duas Classes** como o primeiro modelo de eleição seguido por **SVM de Duas Classes** como o segundo modelo. O Azure Machine Learning Studio permite-lhe fazer testes A/B, por isso é benéfico começar com dois modelos em vez de um.

A imagem a seguir mostra o pipeline de formação e avaliação do modelo do Azure Machine Learning Studio:

![Modelo de abandono do Azure Machine Learning Studio](media/azure-machine-learning-model.png)

Também aplicamos uma técnica chamada **Importância de Permutação De Funcionalidades**, um aspeto importante da otimização do modelo. Os modelos incorporados têm pouca ou nenhuma informação sobre o impacto de qualquer funcionalidade específica na predição final. A calculadora de importância de funcionalidades usa um algoritmo personalizado, para calcular a influência das funcionalidades individuais no resultado de um modelo específico. A importância de funcionalidades é normalizada entre +1 e -1. Uma influência negativa significa que a funcionalidade correspondente tem influência contraintuitiva no resultado e deve ser removida do modelo. Uma influência positiva indica que a funcionalidade está a contribuir fortemente para a predição. Estes valores não são coeficientes de correlação, pois são métricas diferentes. Para mais informações, consulte [Importância da Permutação de Funcionalidades](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Toda a [experiência de abandono está disponível na Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predição de valor vitalício do cliente

O cálculo do valor vitalício do cliente (CLTV) é uma das métricas-chave que uma empresa pode usar para avaliar e segmentar os seus clientes. Para o negócio hoteleiro, é fundamental conhecer os seus clientes. Por exemplo, compreender fatores que compõem bons clientes é informação crucial. Ajuda a administração do hotel a avaliar quais as funcionalidades em que precisam de se concentrar e melhorar para satisfazer os seus clientes que mais pagam. Estas decisões podem ter um impacto direto nas vendas e nos ganhos.  

### <a name="definition-of-cltv"></a>Definição de CLTV

Para este exemplo, definimos o CLTV de um cliente como o valor total em dólares que o cliente deverá gastar nos próximos 365 dias. Vamos usar os últimos três anos de dados para todos os clientes para prever este valor.

### <a name="featurization"></a>Caracterização

Neste caso, a caracterização vai ser como o cenário de abandono. No entanto, as etiquetas e os valores previstos são diferentes do acima definido.

### <a name="model-selection"></a>Seleção de Modelo

Prever o CLTV é um problema de regressão, uma vez que o valor previsto é uma variável contínua valorizada positivamente. Com base nas propriedades da funcionalidade, selecionamos a **Regressão da Árvore de Decisão Reforçada** como um algoritmo e a **Regressão da Rede Neural** como outro algoritmo para preparar o modelo.

## <a name="product-recommendation-or-next-best-action"></a>Recomendação do produto ou Próxima Melhor Ação

A recomendação do produto num cenário hoteleiro é interpretada como recomendando serviços oferecidos pelo hotel aos clientes. O objetivo é escolher os serviços adequados para os clientes para que a sua utilização seja maximizada. É semelhante às recomendações de filmes para utilizadores de serviços de streaming de vídeo.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definição de Recomendação do Produto ou Próxima Melhor Ação

Definimos o objetivo como maximizando a quantidade de dólares de uso do serviço, oferecendo os melhores serviços de correspondência aos clientes do hotel de acordo com o seu interesse.

### <a name="featurization"></a>Caracterização

Tal como o modelo de abandono, estamos a juntar ServiceCustomerID aoCustomerID de forma a criar recomendações de forma consistente por CustomerID.

![Caracterização do modelo de recomendação](media/azure-machine-learning-model-featurization.png)

Os dados são provenientes de três entidades diferentes e as funcionalidades são derivadas deles. A caracterização para o problema da recomendação é diferente em comparação com os cenários de abandono ou CLTV. O modelo de recomendação necessita de dados de entrada sob a forma de três conjuntos de funcionalidades.

### <a name="model-selection"></a>Seleção de Modelo

Prevemos produtos ou serviços usando o algoritmo chamado **Train Matchbox Recommender** para treinar o modelo de recomendação.

![Algoritmo de recomendação de produtos](media/azure-machine-learning-model-recommendation-algorithm.png)

As três portas de entrada para o modelo **Train Matchbox Recommender** requerem os dados de utilização do serviço de formação, a descrição do cliente (opcional) e a descrição do serviço. Há três maneiras diferentes de classificar o modelo. Uma delas é para avaliação de modelos onde uma pontuação de Ganho Cumulativo Com Desconto Normalizado (NDCG) é calculada para classificar os itens classificados. Nesta experiência, temos a pontuação NDCG como 0,97. As outras duas opções são classificar o modelo em todo o catálogo de serviços recomendável, ou classificar apenas em itens que os utilizadores não utilizaram antes.

Olhando mais adiante sobre as distribuições das recomendações em todo o catálogo de serviços, notamos que telefone, Wi-Fi e correio são os principais serviços a recomendar. Isto é consistente com o que encontramos a partir das distribuições dos dados de consumo de serviço:

![Saída do modelo de recomendação](media/azure-machine-learning-model-output.png)

Toda a [experiência de recomendação do produto pode ser acedida no Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrar modelos personalizados

Para utilizar estas previsões no Customer Insights, é necessário **exportar** as previsões juntamente com os IDs de cliente. [Exporte-os para o mesmo local de armazenamento de Blobs do Azure](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs) para o qual exporta os dados de origem. O serviço Web preditivo pode ser programado para ser executado regularmente e atualizar as classificações.

Os dados gerados pelo modelo personalizado podem ser utilizados para melhorar ainda mais os dados dos seus clientes. Para mais informações, consulte [Modelos personalizados de aprendizagem automática](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
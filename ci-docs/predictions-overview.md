---
title: Descrição geral das predições
description: Cenários de predição e opções abrangidas pela aplicação Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610204"
---
# <a name="predictions-overview"></a>Descrição geral das predições

O Dynamics 365 Customer Insights vem com uma variedade de opções que tiram proveito da IA e aprendizagem automática para prever dados.

## <a name="out-of-box-models"></a>Modelos fornecidos com o programa

A maneira mais fácil de começar com a previsão de dados são os modelos predefinidos, muitas vezes referidos como modelos fornecidos com o programa. Só requerem certos dados e estrutura para gerar informações rapidamente. Estão disponíveis os seguintes modelos:

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- [Valor vitalício do cliente](predict-customer-lifetime-value.md): prevê a receita potencial de um cliente ao longo de toda a interação com um negócio.
- [Recomendação do produto](predict-product-recommendation.md): sugere conjuntos de recomendações preditivas do produto com base no comportamento de compra e clientes com padrões de compra semelhantes.
- [Abandono de subscrições](predict-subscription-churn.md): prevê se um cliente está em risco por ter deixado de utilizar os produtos ou serviços de subscrição da sua empresa.
- [Abandono transacional](predict-transactional-churn.md): prevê se um cliente individual deixará de comprar os seus produtos ou serviços num determinado período de tempo.
- [Análise de sentimentos](sentiment-analysis.md): analisa o sentimento do feedback de clientes e identifica aspetos de negócio que são frequentemente mencionados.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- [Abandono transacional](predict-transactional-churn.md): prevê se uma conta de cliente deixará de comprar os seus produtos ou serviços num determinado período de tempo.

---

> [!TIP]
> Recomendamos que atualize regularmente os modelos de caixa de origem com dados atualizados para garantir que informam com precisão o caso de utilização do seu negócio. Os dados são atualizados ad hoc quando o sistema ingere origens de dados novas ou atualizadas. No entanto, os modelos apenas voltarão a classificar neste caso e continuarão a utilizar os dados de formação existentes.
>
> Configure uma **Agenda de atualização** definindo a agenda de reeducação do modelo durante a configuração. O modelo irá reeducar e voltar a classificar nesta agenda, que pode alterar a qualquer momento.

## <a name="azure-machine-learning-integration"></a>Integração do Azure Machine Learning

Se uma organização já utiliza cenários aprendizagem automática baseados em experiências do Azure Machine Learning, a funcionalidade de modelos personalizados no Customer Insights ajuda a interligá-los. Crie fluxos de trabalho que o ajudem a escolher os dados de que pretende gerar informações e mapeie os resultados para os seus perfis de clientes unificados. Para mais informações, consulte [Modelos personalizados de aprendizagem automática](custom-models.md).

## <a name="manage-existing-predictions"></a>Gerir predições existentes

Aceda à página **Inteligência** > **Predições**. No separador **As minhas predições**, veja as previsões que criou, o respetivo tipo de predição, o nome da entidade de saída, o estado, a última vez que a predição foi editada e a última vez que os dados foram atualizados. Pode ordenar a lista de predições por qualquer coluna.

Selecione uma predição para ver as ações disponíveis.

:::image type="content" source="media/predictions.png" alt-text="Página As minhas predições.":::

- **Editar** a predição para alterar as respetivas propriedades.
- [**Atualizar**](#refresh-a-prediction) a predição para incluir os dados mais recentes.
- **Ver** os detalhes da predição.
- [**Relatório de utilização de dados de entrada**](#view-the-input-data-usability-report) to ver erros, avisos e recomendações.
- **Eliminar** a predição.

### <a name="refresh-a-prediction"></a>Atualizar uma previsão

As predições podem ser atualizadas com agendamento automático ou atualizadas manualmente a pedido. Para atualizar manualmente todas as predições, selecione **Atualizar tudo**. Para atualizar manualmente uma predição, selecione-a e selecione **Atualizar**. Para [agendar uma atualização automática](schedule-refresh.md), aceda a **Admin** > **Sistema** > **Agendar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Ver o relatório de capacidade de utilização de dados de entrada

O relatório de capacidade de utilização de dados de entrada fornece uma vista consolidada dos erros e avisos que as suas predições fornecidas com o programa podem estar a gerar. Também apresenta recomendações sobre como melhorar o desempenho do modelo.

O relatório está disponível depois de um modelo ter concluído o seu processo de preparação. É criado para cada modelo separadamente, independentemente de ter concluído a preparação com sucesso ou não.

No separador **As minhas predições**, selecione a predição e escolha **Relatório de utilização de dados de entrada**. Ou, da vista de detalhes da predição, selecione **Relatório de utilização de dados de entrada**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo de um relatório de capacidade de utilização de dados de entrada a mostrar uma tabela com erros, avisos e recomendações.":::

O relatório inclui:

- **Nome:** nome descritivo do erro, aviso ou recomendação.
- **Passo:** fase do modelo, preparação ou classificação, a que as informações se referem.
- **Estado:** gravidade das informações (erro, aviso, recomendação).
- **Nome da coluna:** coluna numa entidade que precisa de ser modificada para melhorar o desempenho do modelo.
- **Nome da entidade:** nome da entidade que precisa de ser modificada para melhorar o desempenho do modelo.
- **Detalhes:** detalhes sobre o erro, aviso ou recomendação.

[!INCLUDE [footer-include](includes/footer-banner.md)]

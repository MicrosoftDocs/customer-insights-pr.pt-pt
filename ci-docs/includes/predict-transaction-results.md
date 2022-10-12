---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611109"
---
- **Desempenho do modelo de preparação**: as notas A, B e C indicam o desempenho da predição e podem ajudá-lo a tomar a decisão de utilizar os resultados armazenados na entidade de saída.

  Os níveis são determinados com base nas seguintes regras:
  - **A** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é superior à base de referência em pelo menos 10%.
  - **B** quando o modelo previu com precisão pelo menos 50% do total das predições, e quando a percentagem de predições exatas para os clientes que abandonaram é até 10% superior à base de referência.
  - **C** quando o modelo previu com precisão menos de 50% do total das predições, ou quando a percentagem de predições exatas para os clientes que abandonaram é inferior à base de referência.
  - **Linha de base** toma a entrada do período de predição para o modelo (por exemplo, um ano) e cria diferentes frações de tempo dividindo-o por 2 até chegar a um mês ou menos. Utiliza estas frações para criar uma regra de negócio para clientes que não tenham efetuado compras neste período de tempo. Estes clientes são considerados como tendo abandonado. A regra empresarial baseada no tempo com a maior capacidade de predição de quem é suscetível de abandono é escolhida como o modelo de linha de base.

- **Probabilidade de abandono (número de clientes)**: grupos de clientes com base no risco previsto de abandono. Opcionalmente, pode [criar segmentos de clientes](../prediction-based-segment.md) com risco de abandono elevado. Estes segmentos ajudam a entender onde o seu limite dever ser para a adesão ao segmento.

- **Fatores mais influentes**: há muitos fatores que são tidos em conta na criação da sua previsão. Cada um dos fatores tem a sua importância calculada para as predições agregadas que um modelo cria. Utilize estes fatores para ajudar a validar os resultados da sua predição. Ou utilize estas informações mais tarde para [criar segmentos](../prediction-based-segment.md) que possam ajudar a influenciar o risco de abandono para os clientes.
---
title: Enriquecer os perfis dos clientes com dados do Microsoft Office 365
description: Utilize dados próprios a partir do Microsoft Office para enriquecer os seus perfis de cliente com dados de interação.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 938a9de83fd8f5ff0c9ae815d626cdfa35228aba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228488"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Enriquecer os perfis dos clientes com dados de interação (pré-visualização)

Utilize os dados do Microsoft Office 365 para enriquecer os seus perfis de conta de cliente com informações sobre as interações através das aplicações do Office 365. Os dados de interação são compostos por atividade de e-mail e reunião, que são agregados a nível da conta. Por exemplo, o número de e-mails de uma conta profissional ou o número de reuniões com a conta. Não são disponibilizados dados sobre os utilizadores individuais. 

Este melhoramento está disponível nas seguintes regiões: Reino Unido, Europa, América do Norte.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o melhoramento, devem ser cumpridos os seguintes pré-requisitos:

- Tem uma licença de cloud do Office 365 ativa.
- Tem [perfis de clientes unificados](customer-profiles.md) com base em [contas empresariais](work-with-business-accounts.md).
- O ambiente do Customer Insights tem de ter uma [organização do Microsoft Dataverse anexada](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Tem permissões de [administrador](permissions.md#administrator).
- Tem, ou pode obter, o consentimento do seu administrador de inquilinos do Office 365 para utilizar os dados do Office 365 para fornecer **Informações para a Organização** nas aplicações do Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Nos insights de audiência, vá a **Dados** > **Melhoramento**.

1. Vá para o separador **Descobrir** e selecione **Melhorar os meus dados** no mosaico **Interação de contas**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Mosaico Interação de contas":::
   
1. Selecione **Seguinte** no passo **Descrição geral** e introduza os endereços de e-mail da sua organização para a qual os dados do Office vão ser agregados. Só os dados dos endereços de e-mail listados são processados para comunicação relevante. Uma melhor prática consiste em utilizar grupos de e-mail, por exemplo, *Equipa de vendas dos EUA*, que são geridos facilmente no Office 365. O número de endereços de e-mail nos grupos é resolvido e mostrado. O número total de endereços de e-mail tem de ser pelo menos de 2 e não pode exceder 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Endereços de e-mail de interação de contas.":::

1. Reveja a declaração de consentimento, selecione a caixa de verificação **Aceito** e selecione **Seguinte**.

1. Selecione o conjunto de dados do cliente e selecione **Seguinte**.

1. Mapeie o campo de endereço de e-mail de contato e selecione **Seguinte**.

1. Reveja a configuração do melhoramento, atribua um nome ao melhoramento e selecione **Guardar melhoramento** para guardar o melhoramento.

## <a name="office-365-tenant-administrator-consent"></a>Consentimento do administrador de inquilinos do Office 365

É necessário o consentimento de um administrador de inquilinos do Office 365 para ativar o melhoramento. É enviado um e-mail para os administradores de inquilinos do Office 365 quando o melhoramento é guardado, que lhe solicita para rever e dar o consentimento para permitir que as aplicações do Dynamics 365 utilizem os dados do Office 365 das empresas para fornecer **Informações para a Organização**. O administrador de inquilinos do Office 365 também pode dar o consentimento diretamente na respetiva consola de administração do Office 365 ao selecionar **Informações para a Organização**.

## <a name="running-the-enrichment-for-the-first-time"></a>Executar o melhoramento pela primeira vez

Quando o enriquecimento é iniciado pela primeira vez, depois de o administrador de inquilinos do Office 365 ter dado o seu consentimento, começa a transferência de dados do Office 365. Este processo demora algum tempo. A primeira execução do melhoramento será agendada com um atraso de seis horas. Poderá ver o número de dias que os dados cobrem na página de descrição geral de interação de contas após a conclusão do melhoramento. Com um grande volume de dados, volte a executar o melhoramento após alguns dias. Assegura que os dados estão completos para toda a janela de tempo, que é de um ano.

Para iniciar o processo, selecione **Executar** na página de configuração da Interação de contas. Para além disso, pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). Por predefinição, o melhoramento é executado uma vez por semana.

Consoante o volume dos seus dados do Office, poderá demorar várias horas para uma execução de melhoramento ser concluída.

Quando executar um melhoramento, a Microsoft irá processar os dados dentro do limite de conformidade do Office 365 para criar informações agregadas, que depois são adicionadas ao seu ambiente do Customer Insights. Nenhum dado a nível individual (por exemplo, o corpo de qualquer e-mail ou convite de calendário) fica disponível para os utilizadores do Customer Insights. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultados do enriquecimento

Após a execução do processo de melhoramento, vá para **Os meus melhoramentos** para rever os resultados do melhoramento. Encontrará o número total de clientes melhorados e uma descrição geral dos resultados do melhoramento. Inclui o número de e-mails e reuniões processados, o número de dias para os quais os dados foram agregados, e muito mais.

Encontrará também um gráfico com o número de clientes melhorados ao longo do tempo e uma pré-visualização dos dados melhorados.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pré-visualização dos resultados depois de executar o processo de enriquecimento.":::

Todos os dados são agregados até ao nível da conta. O sistema calcula uma pontuação de interação, que varia entre 0 a 100, para cada conta. A pontuação de interação fornece uma medida composta da envolvimento da interação de contas nos e-mails e nas reuniões relativos às suas outras contas. A lista seguinte contém os dados agregados que o melhoramento das interações de contas fornece:



| Dados                                                                              | Nome da coluna                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Pontuação de interação                                                                  |  EngagementScore                         |
| Número de e-mails para a conta                                                       |  NoOfEmails_ToAccount                    |
| Número de e-mails da conta                                                     |  NoOfEmails_FromAccount                  | 
| Número de reuniões iniciadas pela conta                                           |  NoOfMeetings_FromAccount                | 
| Número de reuniões iniciadas pela sua organização                                 |  NoOfMeetings_ToAccount                  | 
| Número de pessoas da sua organização em reuniões com a conta                  |  NoOfContactsInvolved_Meetings           | 
| Número de pessoas da sua organização em conversações por e-mail com a conta       |  NoOfContactsInvolved_Emails             | 
| Número de pessoas da conta em reuniões com a sua organização                  |  NoOfAccountContactsInvolved_Meetings    | 
| Número de pessoas da conta em conversações por e-mail com a sua organização       |  NoOfAccountContactsInvolved_Emails      | 
| Data de início da interação (primeiro e-mail ou reunião nos dados)                        |  EngagementStartDate                     | 
| Dias desde o último e-mail                                                             |  DaysSinceLastEmail                      | 
| Dias desde a última reunião                                                           |  DaysSinceLastMeeting                    | 
| Duração média das reuniões                                                      |  AverageDuration_Of_Meetings             | 
| Duração média das respostas a emails da conta                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Data de início da agregação                                                            |  AggregationStartDate                    | 
| Nível de agregação (ano, mês ou semana)                                          |  AggregationLevel                        | 


Reveja os dados melhorados ao selecionar **Ver mais** na secção de pré-visualização. Abre a entidade *Office*. Também pode localizar a entidade listada no grupo **Melhoramento** em **Dados** > **Entidades**. Também encontrará *Office_UserEntity*, que contém os IDs do Active Directory para os endereços de e-mail que foram escolhidos durante a configuração do melhoramento 

## <a name="see-enrichment-data-on-the-customer-card"></a>Ver dados de enriquecimento no cartão de cliente

A Interação de contas também pode vista em cartões de clientes individuais. Aceda a **Clientes** e selecione um perfil de cliente. No cartão de cliente, encontrará a pontuação de interação da conta, o número total de e-mails e o número total de reuniões agregadas ao longo do último ano. Também encontrará gráficos que mostram o histórico de e-mail e reuniões.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Criar segmentos e medidas baseadas nos dados melhorados

Os dados melhorados podem ser utilizados para criar segmentos e medidas, conforme descrito abaixo. Por exemplo, um segmento que contém todos os clientes que têm um valor superior a 60 para *dias desde o último e-mail* e *dias desde a última reunião*. Esse segmento contém contas obsoletas que pode experimentar para reativar. 

## <a name="next-steps"></a>Passos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Suplemento de Cartões de Cliente para aplicações do Dynamics 365 (pré-visualização) (contém vídeo)
description: Mostrar dados de perfil de cliente do Customer Insights em aplicações Dynamics 365 com este suplemento.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 65fd80cc563b8b3b8c8874b66f179f8b0c7a19f0
ms.sourcegitcommit: fe33cc76d015232ff8737f77193f44f2b884bb6b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473656"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Suplemento de Cartões de Cliente para Aplicações do Dynamics 365 (pré-visualização)

Obtenha uma visão de 360 graus dos seus clientes diretamente nas aplicações Dynamics 365. Com o Suplemento de Cartões de Cliente instalado numa aplicação do Dynamics 365 suportada, pode optar por apresentar campos do perfil do cliente, informações e a linha cronológica da atividade. O suplemento irá obter dados do Customer Insights sem afetar os dados na aplicação ligada do Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Pré-requisitos

- As aplicações condicionadas por modelo do Dynamics 365, como o Sales ou o Customer Service, versão 9.0 e posterior.
- Para que os seus dados do Dynamics 365 mapeiem para perfis de clientes do Customer Insights, recomendamos que sejam [ingeridos a partir da aplicação do Dynamics 365 utilizando o conector do Microsoft Dataverse](connect-power-query.md). Se utilizar um método diferente para ingerir contactos do Dynamics 365 (ou contas), certifique-se de que o campo `contactid` (ou `accountid`) é definido como a [chave primária para essa origem de dados durante o processo de unificação de dados](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Todos os utilizadores do Dynamics 365 do Suplemento de Cartões de Cliente têm de ser [adicionados como utilizadores](permissions.md) no Customer Insights para verem os dados.
- [Capacidades de pesquisa e de filtro configuradas](search-filter-index.md) no Customer Insights.
- Alguns dados e controlos só estão disponíveis em ambientes de tipos específicos. A configuração do suplemento informá-lo-á se não estiver disponível um controlo devido ao tipo de ambiente selecionado. Este erro será apresentado no controlo aquando da sua composição. Mais informações sobre [casos de utilização do ambiente](work-with-business-accounts.md).
- Cada controlo de suplemento baseia-se em dados específicos no Customer Insights.
  - **Controlo da medida**: requer [medidas de atributo de cliente configuradas](measures.md).
  - **Controlo de inteligência**: requer dados gerados utilizando [predições ou modelos personalizados](predictions-overview.md).
  - **Controlo de detalhes do cliente**: mostra todos os campos do perfil disponíveis no perfil do cliente unificado.
  - **Controlo do melhoramento**: requer [melhoramentos](enrichment-hub.md) ativos aplicados aos perfis de clientes. O suplemento do cartão suporta estes melhoramentos: as [Marcas](enrichment-microsoft.md) fornecidas pela Microsoft, os [Interesses](enrichment-microsoft.md) fornecidos pela Microsoft e os [Dados de interação do Office](enrichment-office.md) fornecidos pela Microsoft.
  - **Controlo de contactos**: requer um tipo de entidade de semântica de contacto.
  - **Controlo da linha cronológica**: requer [atividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar o Suplemento Ficha de Cliente

O Suplemento do Cartão de Cliente é uma solução para aplicações Customer Engagement no Dynamics 365. Para instalar a solução:

1. Vá para AppSource e procure **Ficha de Cliente do Dynamics**.

1. Selecione o [Suplemento de Cartões de Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.

Poderá ter de iniciar sessão com as suas credenciais de administrador para a aplicação Dynamics 365 para instalar a solução. Poderá demorar algum tempo a instalar a solução no seu ambiente.

## <a name="configure-the-customer-card-add-in"></a>Configurar o Suplemento de Cartões de Cliente

1. Como administrador, vá para a secção **Definições** no Dynamics 365 e selecione **Soluções**.

1. Selecione a ligação **Nome a Apresentar** para a solução **Suplemento de Cartões de Cliente do Dynamics 365 Customer Insights (Pré-visualização)**.

   > [!div class="mx-imgBorder"]
   > ![Selecionar nome a apresentar.](media/select-display-name.png "Selecione o nome a apresentar.")

1. Selecione **Iniciar sessão** e introduza as credenciais da conta de administrador que utiliza para configurar o Customer Insights.

   > [!NOTE]
   > Verifique se o bloqueador de janelas de pop-up do browser não bloquear a janela de autenticação quando seleciona o botão **Iniciar sessão**.

1. Selecione o ambiente do Customer Insights a partir do qual pretende obter dados.

1. Defina o mapeamento de campo para registos na aplicação Dynamics 365. Dependendo dos seus dados no Customer Insights, pode optar por mapear as seguintes opções:
   - Para mapear com um contacto, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade de contacto.
   - Para mapear com uma conta, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade da conta.

   > [!div class="mx-imgBorder"]
   > ![Campo ID do Contacto.](media/contact-id-field.png "Campo ID do Contacto.")

1. Selecione **Guardar configuração** para guardar as definições.

1. Em seguida, tem de atribuir direitos de acesso no Dynamics 365 para os utilizadores poderem personalizar e ver o cartão de cliente. No Dynamics 365, aceda a **Definições** > **Segurança** > **Utilizadores**. Selecione os utilizadores para os direitos de utilizador e selecione **Gerir funções**.

1. Atribua a função **Personalizador do Cartão Customer Insights** aos utilizadores que personalizem o conteúdo apresentado no cartão para toda a organização.

## <a name="add-customer-card-controls-to-forms"></a>Adicionar cartão de cliente aos formulários

Dependendo do seu cenário, pode optar por adicionar controlos ao formulário de **Contacto** ou ao formulário de **Conta**. Se o ambiente do Customer Insights se destinar a contas empresariais, recomendamos a adição dos controlos ao formulário de Conta. Nesse caso, substitua o "contacto" por "conta" nos passos abaixo.

1. Para adicionar os controlos da Ficha de Cliente ao seu formulário Contacto, aceda a **Definições** > **Personalizações** no Dynamics 365.

1. Selecione **Personalizar o Sistema**.

1. Navegue para a entidade **Contacto**, expanda-a e selecione **Formulários**.

1. Selecione o formulário de contacto ao qual pretende adicionar controlos da Ficha de Cliente.

    > [!div class="mx-imgBorder"]
    > ![Selecionar formulário Contacto.](media/contact-active-forms.png "Selecione o formulário de Contacto.")

1. Para adicionar um controlo, no editor de formulários, arraste qualquer campo do **Explorador de Campos** para onde pretende que o controlo seja apresentado.

1. Selecione o campo no formulário que acabou de adicionar e selecione **Alterar Propriedades**.

1. Aceda ao separador **Controlos** e selecione **Adicionar Controlo**. Escolha um dos controlos personalizados disponíveis e selecione **Adicionar**.

1. Na caixa de diálogo **Propriedades do Campo**, desmarque a caixa de verificação **Apresentar etiqueta no formulário**.

1. Selecione a opção **Web** para o controlo. Para o controlo de Enriquecimento, selecione o tipo de enriquecimento que pretende visualizar configurando o campo **enrichmentType**. Adicione um controlo de melhoramento separado para cada tipo de melhoramento.

1. Selecione **Guardar** e **Publicar** para publicar o formulário de contacto atualizado.

1. Vá para o formulário de contacto publicado. Verá o controlo adicionado recentemente. Poderá ter de iniciar sessão quando o utiliza pela primeira vez.

1. Para personalizar o que pretende mostrar no controlo personalizado, selecione o botão de editação no canto superior direito.

## <a name="upgrade-customer-card-add-in"></a>Atualizar Versão do Suplemento Ficha de Cliente

O Suplemento da Ficha de Cliente não atualiza a versão automaticamente. Para atualizar para a versão mais recente, siga estes passos na aplicação do Dynamics 365 que tem o suplemento instalado.

1. Na aplicação Dynamics 365, vá a **Definições** > **Personalização** e selecione **Soluções**.

1. Na tabela de suplementos, procure **CustomerInsightsCustomerCard** e selecione a linha.

1. Selecione a **Aplicar Atualização da Versão da Solução** na barra de ação.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atualize a versão da solução na área Personalização das aplicações Dynamics 365.":::

1. Depois de iniciar o processo de atualização de versão, verá um indicador de carregamento até que a atualização esteja concluída. Se não houver uma versão mais recente, a atualização mostrará uma mensagem de erro.

## <a name="troubleshooting"></a>Resolução de Problemas

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Os controlos do Suplemento de Cartões de Cliente não encontram dados

**Problema:**

Mesmo com campos de ID corretamente configurados, os controlos não conseguem encontrar os dados de nenhum cliente.  

**Resolução:**

1. Certifique-se de que configura o Suplemento de Cartões de acordo com as instruções: [Configurar o Suplemento de Cartões de Cliente](#configure-the-customer-card-add-in)

1. Reveja a configuração de ingestão de dados. Edite a origem de dados para o sistema Dynamics 365 que contém o GUID ID do contacto. Se o GUID ID do contacto for mostrado com carateres em maiúsculas no editor do Power Query, experimente os passos seguintes:
    1. Edite a origem de dados para abrir a origem de dados no Editor do Power Query.
    1. Selecione a coluna de ID do contacto.
    1. Selecione **Transformar** na barra de cabeçalho para ver as ações disponíveis.
    1. Selecione **em minúsculas**. Valide se os GUIDs na tabela estão agora em minúsculas.
    1. Guardar a origem dos dados.
    1. Execute processos de ingestão de dados, unificação e a jusante para propagar as alterações ao GUID.

Quando o sistema terminar a atualização completa, os controlos do Suplemento de Cartões de Cliente devem mostrar os dados esperados.

[!INCLUDE [footer-include](includes/footer-banner.md)]

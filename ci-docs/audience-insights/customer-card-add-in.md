---
title: Suplemento de Cartões de Cliente para aplicações Dynamics 365
description: Mostrar dados de informações de audiência em aplicações Dynamics 365 com este suplemento.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9c7cfbf9f47cca53e5543e2cda2584e25ad855d
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643444"
---
# <a name="customer-card-add-in-preview"></a>Suplemento de Cartões de Cliente (pré-visualização)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obtenha uma visão de 360 graus dos seus clientes diretamente nas aplicações Dynamics 365. Com o Suplemento de Cartões de Cliente instalado numa aplicação do Dynamics 365 suportada, pode optar por apresentar campos do perfil do cliente, informações e a linha cronológica da atividade. O suplemento irá obter dados do Customer Insights sem afetar os dados na aplicação ligada do Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Pré-requisitos

- O suplemento funciona apenas com aplicações condicionadas por modelo do Dynamics 365, como o Sales ou o Customer Service, versão 9.0 e posterior.
- Para que os seus dados do Dynamics 365 mapeiem para perfis de clientes de informações de audiência, precisam de ser [ingeridos a partir da aplicação do Dynamics 365 utilizando o conector do Microsoft Dataverse](connect-power-query.md).
- Todos os utilizadores do Dynamics 365 do Suplemento de Cartões de Cliente têm de ser [adicionados como utilizadores](permissions.md) nas informações de audiência para ver os dados.
- As [capacidades de pesquisa e de filtragem configuradas](search-filter-index.md) nas informações de audiência são necessárias para que a pesquisa de dados funcione.
- Cada controlo de suplemento baseia-se em dados específicos em informações de audiência. Alguns dados e controlos só estão disponíveis em ambientes de tipos específicos. A configuração do suplemento informá-lo-á se não estiver disponível um controlo devido ao tipo de ambiente selecionado. Mais informações sobre [casos de utilização do ambiente](work-with-business-accounts.md).
  - **Controlo da medida**: requer [medidas configuradas](measures.md) do tipo de atributos do cliente.
  - **Controlo de inteligência**: requer dados gerados utilizando [predições](predictions.md) ou [modelos personalizados](custom-models.md).
  - **Controlo de detalhes do cliente**: todos os campos do perfil estão disponíveis no perfil do cliente unificado.
  - **Controlo do melhoramento**: requer [melhoramentos](enrichment-hub.md) ativos aplicados aos perfis de clientes.
  - **Controlo de contactos**: requer a definição de entidade semântica do tipo de contactos.
  - **Controlo da linha cronológica**: requer [atividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar o Suplemento Ficha de Cliente

O Suplemento do Cartão de Cliente é uma solução para aplicações Customer Engagement no Dynamics 365. Para instalar a solução, aceda a AppSource e procure **Ficha de Cliente do Dynamics**. Selecione o [Suplemento de Cartões de Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.

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

Dependendo do seu cenário, pode optar por adicionar controlos ao formulário de **Contacto** ou ao formulário de **Conta**. Se o ambiente de informações de audiência se destinar às contas empresariais, recomendamos a adição dos controlos ao formulário de Conta. Nesse caso, substitua o "contacto" por "conta" nos passos abaixo.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]

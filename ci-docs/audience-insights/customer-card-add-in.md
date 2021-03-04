---
title: Instale e configure o Suplemento Ficha de Cliente
description: Instalar e configurar o suplemento Ficha de Cliente para o Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268058"
---
# <a name="customer-card-add-in-preview"></a>Suplemento de Cartões de Cliente (pré-visualização)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obtenha uma visão de 360 graus dos seus clientes diretamente nas aplicações Dynamics 365. Veja dados demográficos, informações e linhas cronológicas de atividades com o Suplemento de Cartões de Cliente.

## <a name="prerequisites"></a>Pré-requisitos

- Aplicação Dynamics 365 (como Hub de Vendas ou Hub do Customer Service), versão 9.0 e posterior com a Interface Unificada ativada.
- Perfis de clientes [ingerido a partir da aplicação Dynamics 365 utilizando Common Data Service](connect-power-query.md).
- Os utilizadores do Suplemento Cartão de Cliente têm de ser [adicionados como utilizadores](permissions.md) em insights da audiência.
- [Capacidades de pesquisa e filtragem configuradas](search-filter-index.md).
- Controlo demográfico: Campos demográficos (tais como idade ou sexo) estão disponíveis no perfil unificado do cliente.
- Controlo do enriquecimento: Requer [enriquecimentos](enrichment-hub.md) ativos aplicados aos perfis do cliente.
- Controlo da inteligência: Necessita de dados gerados através do Azure Machine Learning ([Predições](predictions.md) ou [Modelos Personalizados](custom-models.md))
- Controlo das medidas: Requer [medidas configuradas](measures.md).
- Controlo da linha cronológica: Requer [atividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar o Suplemento Ficha de Cliente

O Suplemento do Cartão de Cliente é uma solução para aplicações Customer Engagement no Dynamics 365. Para instalar a solução, aceda a AppSource e procure **Ficha de Cliente do Dynamics**. Selecione o [Suplemento de Cartões de Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.

Poderá ter de iniciar sessão com as suas credenciais de administrador para a aplicação Dynamics 365 para instalar a solução.

Poderá demorar algum tempo a instalar a solução no seu ambiente.

## <a name="configure-the-customer-card-add-in"></a>Configurar o Suplemento de Cartões de Cliente

1. Como administrador, vá para a secção **Definições** no Dynamics 365 e selecione **Soluções**.

1. Selecione a ligação **Nome a Apresentar** para a solução **Suplemento de Cartões de Cliente do Dynamics 365 Customer Insights (Pré-visualização)**.

   > [!div class="mx-imgBorder"]
   > ![Selecionar nome a apresentar](media/select-display-name.png "Selecionar nome a apresentar")

1. Selecione **Iniciar sessão** e introduza as credenciais da conta de administrador que utiliza para configurar o Customer Insights.

   > [!NOTE]
   > Verifique se o bloqueador de janelas de pop-up do browser não bloquear a janela de autenticação quando seleciona o botão **Iniciar sessão**.

1. Selecione o ambiente a partir da qual pretende obter dados.

1. Definir qual o mapeamento de campo a registar na aplicação Dynamics 365.
   - Para mapear com um contacto, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade de contacto.
   - Para mapear com uma conta, selecione o campo na entidade Cliente que corresponda à identificação da sua entidade da conta.

   > [!div class="mx-imgBorder"]
   > ![Campo ID do Contacto](media/contact-id-field.png "Campo ID do Contacto")

1. Selecione **Guardar configuração** para guardar as definições.

1. Em seguida, tem de atribuir direitos de acesso no Dynamics 365 para os utilizadores poderem personalizar e ver o cartão de cliente. No Dynamics 365, aceda a **Definições** > **Segurança** > **Utilizadores**. Selecione os utilizadores para os direitos de utilizador e selecione **Gerir funções**.

1. Atribua a função **Personalizador do Cartão Customer Insights** aos utilizadores que personalizem o conteúdo apresentado no cartão para toda a organização.

## <a name="add-customer-card-controls-to-forms"></a>Adicionar cartão de cliente aos formulários
  
1. Para adicionar os controlos da Ficha de Cliente ao seu formulário Contacto, aceda a **Definições** > **Personalizações** no Dynamics 365.

1. Selecione **Personalizar o Sistema**.

1. Navegue para a entidade **Contacto**, expanda-a e selecione **Formulários**.

1. Selecione o formulário de contacto ao qual pretende adicionar controlos da Ficha de Cliente.

    > [!div class="mx-imgBorder"]
    > ![Selecionar formulário Contacto](media/contact-active-forms.png "Selecionar formulário Contacto")

1. Para adicionar um controlo, no editor de formulários, arraste qualquer campo do **Explorador de Campos** para onde pretende que o controlo seja apresentado.

1. Selecione o campo no formulário que acabou de adicionar e selecione **Alterar Propriedades**.

1. Aceda ao separador **Controlos** e selecione **Adicionar Controlo**. Escolha um dos controlos personalizados disponíveis e selecione **Adicionar**.

1. Na caixa de diálogo **Propriedades do Campo**, desmarque a caixa de verificação **Apresentar etiqueta no formulário**.

1. Selecione a opção **Web** para o controlo. Para o controlo de Enriquecimento, selecione o tipo de enriquecimento que pretende visualizar configurando o campo **enrichmentType**. Adicione um controlo de melhoramento separado para cada tipo de melhoramento.

1. Selecione **Guardar** e **Publicar** para publicar o formulário de contacto atualizado.

1. Vá para o formulário de contacto publicado. Verá o controlo adicionado recentemente. Poderá ter de iniciar sessão quando o utiliza pela primeira vez.

1. Para personalizar o que pretende mostrar no controlo personalizado, selecione o botão de editação no canto superior direito.

## <a name="upgrade-customer-card-add-in"></a>Atualizar Versão do Suplemento Ficha de Cliente
O Suplemento da Ficha de Cliente não atualiza a versão automaticamente. Para atualizar para a versão mais recente, siga este procedimento na aplicação Dynamics 365 que tem o Suplemento instalado.

1. Na aplicação Dynamics 365, vá a **Definições** > **Personalização** e selecione **Soluções**.

1. Na tabela de suplementos, procure **CustomerInsightsCustomerCard** e selecione a linha.

1. Selecione a **Aplicar Atualização da Versão da Solução** na barra de ação.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atualize a versão da solução na área Personalização das aplicações Dynamics 365":::

1. Depois de iniciar o processo de atualização de versão, verá um indicador de carregamento até que a atualização esteja concluída. Se não houver uma versão mais recente, a atualização mostrará uma mensagem de erro.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
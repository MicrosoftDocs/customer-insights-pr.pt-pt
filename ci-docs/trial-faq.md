---
title: FAQs da Versão de Avaliação - Dynamics 365 Customer Insights
description: Soluções para perguntas comuns relacionadas com a configuração e a gestão da versão de avaliação do Customer Insights. Aprenda a resolver problemas específicos da plataforma e da aplicação.
author: m-hartmann
ms.author: mhart
ms.date: 09/30/2021
ms.topic: get-started
ms.service: customer-insights
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 2837ae13b4150310193a2d09d59aed66b4a69c69
ms.sourcegitcommit: e6020c178a61beb0ee31a031c11ded914d10d995
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/13/2021
ms.locfileid: "7642900"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>FAQs da versão de avaliação do Dynamics 365 Customer Insights

## <a name="sign-up"></a>Inscrição

### <a name="what-are-the-system-requirements-for-the-trial"></a>Quais são os requisitos do sistema para a versão de avaliação?

Esta aplicação é um serviço baseado na cloud que não necessita de software especial além de um browser atualizado, embora se apliquem algumas restrições. Para obter a melhor experiência da versão de avaliação, evite aceder ao site de avaliação em modo de navegação anónima e escolha a localização da versão de avaliação mais próxima de si. [Saiba mais sobre os requisitos da aplicação Web.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Como me inscrevo para a versão de avaliação sem um inquilino do Microsoft 365?

Pode introduzir um endereço de e-mail não profissional e criaremos uma conta e inquilino para si.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Posso inscrever-me em várias aplicações do Dynamics 365, como o Sales, Marketing e Customer Service?

Sim, pode. Para ver todas as avaliações disponíveis, [visite a página do hub da versão de avaliação](https://dynamics.microsoft.com/dynamics-365-free-trial). Pode utilizar a mesma conta de e-mail para se inscrever para diferentes versões de avaliação. No entanto, não é possível ter várias aplicações no mesmo site de avaliação. Cada versão de avaliação estará numa organização e URL diferentes. Os dados de avaliação não serão partilhados entre aplicações.

## <a name="trial-app"></a>Aplicação de avaliação

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Não recebi o e-mail de detalhes da avaliação depois de me inscrever, o que devo fazer?

Quando se inscrever para a versão de avaliação, receberá um e-mail com os detalhes da versão de avaliação. Se não vir o e-mail na sua caixa de entrada, verifique a sua pasta de spam. Em alternativa, utilize os seguintes passos para aceder à sua aplicação:

1. Vá para o site da versão de avaliação e selecione **Experimentar gratuitamente**.
1. Introduza o ID de e-mail que utilizou para se inscrever para a versão de avaliação. Será redirecionado para a sua aplicação de avaliação.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Como adiciono mais utilizadores a uma avaliação?

Para adicionar utilizadores, aceda ao [centro de administração do Microsoft 365](https://admin.microsoft.com) utilizando a conta de administração da avaliação. Siga a [orientação do centro de administração](/microsoft-365/admin/add-users/add-users) para adicionar os utilizadores até ao limite da licença de avaliação. Se o utilizador que está a adicionar já tiver uma conta Microsoft 365, atribua-lhe um direito de acesso apropriado na organização de avaliação. Para obter mais informações, consulte [Atribuir uma direito de acesso a um utilizador](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Quantos utilizadores posso adicionar ao meu ambiente de avaliação?

Pode adicionar um número ilimitado de utilizadores ao ambiente de avaliação.

### <a name="how-do-i-reset-the-trial-environment"></a>Como posso repor o ambiente de avaliação?

Não é possível repor o ambiente de avaliação. No entanto, pode esperar que o período de avaliação termine e, em seguida, inscreva-se novamente para uma nova avaliação.

## <a name="trial-expiration-and-extension"></a>Expiração e expansão da versão de avaliação

### <a name="how-do-i-extend-the-trial"></a>Como posso expandir a avaliação?

Pode prolongar a versão de avaliação diretamente na aplicação. Pode prolongar a sua avaliação uma vez.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Posso converter a versão de avaliação numa licença paga?

Geralmente, recomendamos começar de novo com os seus próprios dados ao atualizar para a versão paga do Customer Insights. 

Opcionalmente, se utilizar apenas informações de audiência, pode copiar os seus dados a partir de um ambiente de avaliação se comprar o Customer Insights. Tem de ser o administrador da avaliação do Customer Insights e o admin global do seu inquilino do Microsoft 365 ou o administrador do Dynamics 365 na sua organização para migrar as definições de um ambiente de avaliação para um ambiente pago. 

Depois de iniciar sessão na sua instância paga do Customer Insights pela primeira vez, é-lhe pedido que crie um novo ambiente. Neste processo, pode optar por copiar a configuração de um ambiente existente e migrar a maioria das definições. Se tiver as permissões acima mencionadas, o ambiente de avaliação aparecerá nesta lista. Para obter mais informações, consulte [Copiar a configuração do ambiente](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Quais são os limites e quotas da versão de avaliação?

- Não pode utilizar a sua própria conta de armazenamento do Azure Data Lake para armazenar os dados de saída durante uma versão de avaliação de informações de audiência. No entanto, pode ingerir dados a partir de uma conta de armazenamento do Data Lake.
- Pode armazenar até 3 GB de dados no ambiente do Dataverse que são aprovisionados automaticamente quando inicia uma versão de avaliação do Customer Insights.

## <a name="customer-insights-specific-questions"></a>Questões específicas do Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Como posso começar a utilizar a avaliação?

Depois de se inscrever para a avaliação, chegará ao ecrã principal da aplicação. O ecrã principal fornece ligações para guias de utilizador e tutoriais. Para saber mais, visite as ligações em [Recursos adicionais](trial-signup.md#additional-resources) na página de inscrição da versão de avaliação.

### <a name="what-features-are-available-in-the-trial"></a>Que funcionalidades estão disponíveis na avaliação?

A maioria das funcionalidades das capacidades do Customer Insights estão disponíveis na versão de avaliação.

A funcionalidade seguinte não está disponível: 
- Não pode criar novos ambientes que utilizem a sua própria conta de armazenamento do Azure Data Lake.

### <a name="how-long-does-the-trial-last"></a>Quanto tempo dura a avaliação?

A versão de avaliação do Customer Insights dura 30 dias. Pode prolongar a versão de avaliação uma vez após 23 dias quando iniciar sessão no seu ambiente de avaliação.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Como removo dados de exemplo da versão de avaliação?

Não pode remover os dados de exemplo da versão de avaliação.

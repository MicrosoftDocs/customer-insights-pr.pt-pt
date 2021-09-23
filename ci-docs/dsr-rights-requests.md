---
title: Pedidos de Direitos de Titulares de Dados (DSR) ao abrigo do RGPD | Microsoft Docs
description: Responder a Pedidos de Titulares de Dados para a capacidade de insights de audiência do Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483696"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Os pedidos de Direitos de Titulares de Dados (DSR) são pedidos sob RGPD

O Regulamento Geral de Proteção de Dados (RGPD) da União Europeia está em vigor desde 25 de maio de 2018. Confere direitos significativos aos indivíduos relativamente aos seus dados. O RGPD consiste em proteger e ativar os direitos de privacidade de indivíduos. Pode ler mais sobre o compromisso da Microsoft com a segurança e a conformidade no [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Estamos empenhados em ajudar os nossos clientes a cumprir os seus requisitos de RGPD. Inclui o direito de eliminar e exportar dados que incluam informações pessoais, tais como ID de utilizador, números de telefone e endereços de e-mail. Os administradores podem implementar pedidos de utilizador para eliminar ou exportar dados pessoais.

## <a name="audience-insights"></a>Informações de Audiência

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Responder ao titular dos dados RGPD elimina os pedidos para a capacidade de insights de audiência do Dynamics 365 Customer Insights

O "direito de eliminação" através da remoção de dados pessoais dos dados de cliente de uma organização é uma proteção-chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e registos gerados pelo sistema, exceto as informações de registo de auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Gerir pedidos de eliminação do titular de dados

Os insights de audiência oferecem as seguintes experiências no produto para eliminar dados pessoais para um cliente específico ou um utilizador:

- **Gerir pedidos de eliminação de dados de clientes**: os dados dos clientes no Customer Insights são ingeridos a partir das origens de dados originais externas ao Customer Insights. Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados na origem de dados original.
- **Gerir pedidos de eliminação de dados de utilizador do Customer Insights**: Os dados para os utilizadores são criados pela Customer Insights. Todos os pedidos de eliminação ao abrigo do RGPD têm de ser efetuados no Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gerir pedidos para eliminar dados dos clientes

Um administrador do Customer Insights pode seguir estes passos para remover os dados do cliente que foram eliminados na origem de dados:

1. Iniciar sessão no Dynamics 365 Customer Insights.
2. Nas informações de audiência, vá a **Dados** > **Origens de dados**
3. Para cada origem de dados na lista que contém dados de clientes eliminados:
   1. Seleccione (...) e, em seguida, selecione **Atualizar**.
   2. Verifique o estado da origem de dados em **Estado**. Uma marca de verificação significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo correu mal. Se for apresentado um triângulo de aviso, contacte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD.](audience-insights/media/gdpr-data-sources.png "Processar pedidos de eliminação de dados dos clientes ao abrigo do RGPD")

##### <a name="manage-delete-requests-for-user-data"></a>Gerir pedidos de eliminação de dados do utilizador

Um administrador do Customer Insights pode seguir estes passos para eliminar dados dos utilizadores do Customer Insights:

1. Iniciar sessão no Dynamics 365 Customer Insights.
2. Nos insights de audiência, vá a **Admin** > **Permissões**.
3. Selecione a caixa de verificação para o utilizador que pretende eliminar.
4. Selecione **Remover**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder aos pedidos de exportação dos titulares de dados RGPD

Como parte do nosso compromisso de parceria consigo no seu percurso para o Regulamento Geral sobre a Proteção de Dados (RGPD), desenvolvemos documentação para o ajudar a preparar-se. Esta documentação descreve as medidas que pode tomar hoje para apoiar o cumprimento do RGPD ao utilizar os insights da audiência.

#### <a name="manage-export-and-view-requests"></a>Gerir pedidos de exportação e visualização

O direito da portabilidade de dados permite aos titulares de dados solicitar uma cópia dos respetivos dados pessoais num formato eletrónico (um "formato estruturado, de utilização comum, de leitura de máquina e interoperável") que poderá ser transmitido para outro controlador de dados.

##### <a name="export-customer-data-tenant-admin"></a>Exportar dados de clientes (administração de inquilinos)

Um administrador pode seguir estes passos para exportar dados:

1. Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do cliente no pedido. A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.
2. Aceite a confirmação para exportar os dados para o cliente pedido.
3. Receba os dados exportados através do endereço de e-mail do administrador de inquilino.

##### <a name="export-user-data-tenant-admin"></a>Exportar dados do utilizador (administração de inquilinos)

1. Enviar um e-mail para D365CI@microsoft.com a especificar o endereço de e-mail do utilizador no pedido. A equipa da Customer Insights enviará um e-mail ao endereço de e-mail do inquilino registado, pedindo confirmação para exportar os dados.
2. Aceite a confirmação para exportar os dados para o utilizador pedido.
3. Receba os dados exportados através do endereço de e-mail do administrador de inquilino.

## <a name="engagement-insights"></a>Informações de cativação

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Eliminação e exportação de dados de eventos que contenham informações identificáveis pelo utilizador final

As seguintes secções descrevem como eliminar e exportar dados de eventos que possam conter dados pessoais.

Para eliminar ou exportar dados:

1. Marque propriedades de eventos que contenham dados com informações pessoais.
2. Eliminar ou exportar dados associados a valores específicos (por exemplo: um ID de utilizador especificado).

#### <a name="tag-and-update-event-properties"></a>Etiquetar e atualizar propriedades do evento

Os dados pessoais estão marcados a nível de propriedade do evento. Em primeiro lugar, marque os imóveis considerados para supressão ou exportação.

Para marcar uma propriedade do evento como contendo informações pessoais, siga estes passos:

1. Abra a área de trabalho que contém o evento.

1. Vá a **Dados** > **Eventos** para ver a lista de eventos na área de trabalho selecionada.
  
1. Selecione o evento que pretende etiquetar.

1. Selecione **Editar propriedades** para abrir o painel listando todas as propriedades do evento selecionado.
     
1. Selecione **...** e, em seguida, escolha **Editar** para chegar ao diálogo de **Atualizar propriedade**.

   ![Editar evento.](engagement-insights/media/edit-event.png "Editar evento")

1. Na janela **Atualizar propriedade** selecione **...** no canto superior direito e, em seguida, escolha a caixa **Contém EUII**. Escolha **Atualizar** para guardar as alterações.

   ![Guardar as suas alterações.](engagement-insights/media/update-property.png "Guardar as alterações")

   > [!NOTE]
   > Sempre que o esquema do evento muda ou cria um novo evento, recomenda-se que avalie as propriedades do evento associado e marque ou desmarque como contendo dados pessoais, se necessário.

#### <a name="delete-or-export-tagged-event-data"></a>Eliminar ou exportar dados de eventos identificados

Se todas as propriedades do evento tiverem sido identificadas adequadamente, tal como descrito no passo anterior, um administrador de ambiente pode emitir um pedido de eliminação contra os dados do evento identificados.

Para gerir pedidos de supressão ou exportação da UEII

1. Vá a **Administração** > **Ambiente** > **Definições**.

1. Na secção **Gerir informações identificáveis do utilizador final (EUII)** selecione **Gerir EUII**.

##### <a name="deletion"></a>Eliminação

Para eliminação, pode introduzir uma lista de ID de utilizador separados por vírgula na secção **Eliminar informação identificável de utilizador final (EUII)**. Estes ID serão então comparados com todas as propriedades de eventos marcados de todos os projetos no ambiente atual através de combinações exatas de cadeias. 

Se um valor de propriedade corresponder a um dos ID fornecidos, o evento associado será permanentemente eliminado. Devido à irreversibilidade desta ação, deve confirmar a eliminação após a seleção de **Eliminar**.

##### <a name="export"></a>Export

O processo de exportação é idêntico ao processo de eliminação quando se trata de definir os valores de propriedade do evento na secção de **Exportar informação identificável do utilizador final (EUII)**. Além disso, terá de fornecer um **URL de Armazenamento de Blobs do Azure** para especificar o destino de exportação. O URL Blob do Azure deve incluir uma [Assinatura de Acesso Partilhado (SAS)](/azure/storage/common/storage-sas-overview).

Após a seleção de **Exportar**, todos os eventos da equipa atual que contenham propriedades marcadas correspondentes serão exportados em formato CSV para o destino de exportação.

### <a name="good-practices"></a>Boas práticas

* Tente evitar o envio de quaisquer eventos que contenham dados pessoais.
* Se precisar de enviar eventos que contenham dados da EUII, limite o número de eventos e propriedades de eventos que contenham dados da EUII. Idealmente, limite-se a um desses eventos.
* Certifique-se de que o menor número de pessoas possível tenha acesso aos dados pessoais enviados.
* Para eventos que contenham dados pessoais, certifique-se de que define uma propriedade para emitir um identificador único que pode facilmente ser ligado a um utilizador específico (por exemplo, um ID do utilizador). Isto facilita a segregação de dados e a exportação ou eliminação dos dados certos.
* Marque apenas uma propriedade por evento como contendo dados pessoais. Idealmente, um que contenha apenas um identificador único.
* Não identifique propriedades que contenham valores verbosos (por exemplo, um corpo de pedido inteiro). A capacidade de informações de cativação utiliza uma correspondência exata de cadeias ao decidir quais os eventos a eliminar ou exportar.

[!INCLUDE[footer-include](includes/footer-banner.md)]
[//]: # (Módulo 7 - Criando Uma Notificação de E-mail)
[//]: # (This is a translation of Version 7, published on August 9, 2021.)

## Introdução

O Módulo 7 no curso de treinamento [Introdução ao Jitterbit Harmony
Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR) demonstra como criar uma notificação de e-mail que é
acionada pela falha de uma operação.


## Pré-requisitos

A operação criada no [Módulo 1 - Banco de Dados para Texto](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text?showLanguage=pt_BR) é usada
como exemplo. No entanto, uma notificação de e-mail pode ser configurada
em qualquer operação.


## Resumo

Neste módulo, você vai adicionar uma notificação de e-mail à operação
criada no [Módulo 1 - Banco de Dados para Texto](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text?showLanguage=pt_BR).

A operação completa ficará parecida com a imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_db-to-text.png" /></span>


## 1. Criar e Adicionar uma Notificação de E-mail a uma Operação

Neste módulo, você continuará trabalhando no mesmo workflow do Módulo 1
e vai adicionar uma notificação de e-mail à operação:

1.  Na parte superior direita da operação, clique no ícone do menu de
    ações <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> e, no
    menu que aparecer, selecione **Settings** (Configurações).

2.  Dentro da aba **Actions** (Ações), use o menu *dropdown* **Action**
    (Ação) para selecionar "Send Email Notification" (Enviar
    Notificação de E-mail), daí clique em **Create New Email
    Notification** (Criar Nova Notificação de E-mail).

3.  Configure a [notificação de e-mail](https://success.jitterbit.com/display/CS/Email+Notifications?showLanguage=pt_BR):

    -   **Email Notification Name** (Nome da Notificação de E-mail): "Falha
        na Operação"

    -   **SMTP Email Server(s)** (Servidor\[es\] de E-mail SMTP): Coloque o
        seu próprio servidor de e-mail SMTP.

        <div
        class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
        hasbody="true" macro-name="info">

        <span
        class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
        </span>
        <div class="confluence-information-macro-body">

        **NOTA:** Caso você não esteja familiarizado(a) com esta informação,
        por favor entre em contato com o(a) administrador(a) interno(a) da sua
        organização para mais detalhes.

        </div>

        </div>

    -   **To Email Address(es)** (Para o\[s\] Endereço\[s\] de E-mail):
        Coloque quaisquer endereços de e-mail, separados por vírgula, para
        onde você queira que os e-mails sejam enviados.

    -   **From Email Address** (Do Endereço de E-mail): Coloque o endereço
        de e-mail que deverá fazer o envio do e-mail.

    -   **Subject** (Assunto): Escreva "`Falha de
        [jitterbit.operation.name]`" para usar uma variável Jitterbit que
        relata dinamicamente o nome de uma operação que fracassou.

    -   **Message** (Mensagem): Digite a mensagem abaixo, de novo usando
        variáveis Jitterbit que relatam dinamicamente informações sobre o
        nome da operação e o erro específico:

        > Houve uma falha de operação em:
        >
        > \[jitterbit.operation.name\]
        >
        > O erro foi:
        >
        > \[jitterbit.operation.error\]
        >
        > Por favor verifique os registros no Cloud Studio ou no Management
        > Console para mais detalhes.

4.  Clique em **Save** (Salvar) para voltar para a aba **Actions**
    (Ações) e configure a [ação de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR):

-   Faça as seguintes seleções no menu *dropdown*:

    -   **Condition** (Condição): "On Fail" (Em Caso de Falha)

    -   **Action** (Ação): "Send Email Notification" (Enviar Notificação
        de E-mail)

    -   **Email Notification** (Notificação de E-mail): "Operation
        Failure" (Falha de Operação)

-   Clique em **Add Action** (Adicionar Ação). A notificação de e-mail
    será mostrada numa tabela na parte de baixo da configuração. Daí
    feche as configurações de operação.

A notificação de e-mail deverá ter uma configuração similar à imagem
abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/notification/email_operation-failure.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/notification/email_operation-failure.png" /></span>

A notificação da falha é retratada graficamente no design canvas:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_db-to-text.png" /></span>


## 2. Implantar a Operação

Agora, reimplante a operação para que a ação de operação configurada
comece a fazer efeito:

1.  Na parte superior direita da operação, clique no ícone do menu de
    ações <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> e, no
    menu que aparecer, clique em **Deploy** (Implantar). Caso a
    operação execute e falhe, a notificação de e-mail será enviada.


## 3. Remover ou Editar uma Notificação de E-mail

Você também pode remover a notificação de e-mail como ação de operação:

1.  No design canvas, clique na notificação de e-mail e, no menu que
    aparecer, selecione **View/Edit** (Visualizar/Editar) para reabrir
    a configuração de notificação, ou selecione **Remove** (Remover)
    para remover a notificação da operação.

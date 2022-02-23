[//]: # (Módulo 6 - Criando uma Agenda)
[//]: # (This is a translation of Version 4, published on August 9, 2021.)

## Introdução

O Módulo 6 do curso de treinamento [Introdução ao Jitterbit Harmony
Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio) demonstra como criar uma agenda customizada para
executar a operação automaticamente nos horários definidos nela.


## Pré-requisitos

A operação criada no [Módulo 5 - Serviço Web RESTful](https://success.jitterbit.com/display/DOC/Module+5+-+RESTful+Web+Service) é usada como
exemplo. No entanto, uma agenda pode ser aplicada a qualquer operação.


## Resumo

Neste módulo, você vai adicionar uma agenda à operação criada no
[Módulo 5 - Serviço Web RESTful](https://success.jitterbit.com/display/DOC/Module+5+-+RESTful+Web+Service).

A operação completa ficará parecida com a imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest_schedule.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest_schedule.png" /></span>


## 1. Criar e Atribuir uma Agenda

Neste módulo, você continua trabalhando dentro do mesmo workflow do
Módulo 5 e adiciona uma agenda à operação:

1.  Na parte superior direita da operação, clique no ícone do menu de
    ações <img src="media/image2.png" style="width:0.25in" /> e, no
    menu que aparecer, selecione **Settings** (Configurações).

2.  Dentro da aba **Schedules** (Agendas), clique em **Create New
    Schedules** (Criar Nova Agenda).

3.  Configure a [agenda de operação](https://success.jitterbit.com/display/CS/Operation+Schedules):

    -   **Name** (Nome): “Mensal”

    -   **Occurrence** (Ocorrência): Selecione **Monthly** (Mensal), daí
        selecione o segundo botão de opção e configure a agenda para o
        **4th Sunday** (quarto domingo) de cada **1** mês.

    -   **Frequency** (Frequência): Selecione **Occurs once at** (Ocorre uma
        vez às) e **01:00 AM**. Clique em **Save** (Salvar).

4.  Na aba **Schedules** (Agendas), use o primeiro menu *dropdown* para
    selecionar **On Schedule** (Na Hora). Sob **Available Schedule**
    (Agenda Disponível), selecione a agenda “Mensal” que você acabou
    de criar. Clique em **Assign** (Atribuir). Daí feche as
    configurações de operação.

A agenda deverá ficar parecida com a imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/operation/schedule_monthly.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/operation/schedule_monthly.png" /></span>

Quando uma agenda é atribuída a uma operação, um ícone de agenda aparece
na parte superior direita da operação:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest_schedule.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest_schedule.png" /></span>


## 2. Implantar a Operação

Agora, reimplante a operação para que a agenda atribuída comece a fazer
efeito:

1.  Na parte superior direita da operação, clique no ícone do menu de
    ações <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> e, no
    menu que aparecer, clique em **Deploy** (Implantar). A operação
    agora será executada de acordo com a agenda atribuída.


## 3. Remover ou Editar uma Agenda

Você também pode remover ou editar a agenda:

1.  Na parte superior direita da operação, clique no ícone de agenda
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/schedules.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/schedules.png"
    height="25" /></span>.

2.  Sob **Assigned Schedule** (Agenda Atribuída), clique no ícone de
    edição
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/edit_3.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/edit_3.png"
    height="14" /></span>
    para reabrir a configuração da agenda ou clique no ícone de
    remoção
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/delete_3.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/delete_3.png"
    height="12" /></span>
    para desfazer a atribuição da agenda à operação.

3.  Depois de fazer mudanças ou de remover uma agenda, lembre-se de
    reimplantar para que as mudanças comecem a fazer efeito.

[//]: # (Criando e Lançando uma Aplicação)
[//]: # (This is a translation of Version 1, published on April 15, 2022.)


## Introdução

Esta página descreve o processo de criar e lançar uma aplicação com o App Builder. Depois de lançá-la, veja o artigo [Configurando uma Aplicação Lançada](https://success.jitterbit.com/display/APP/Configuring+a+Released+App?showLanguage=pt_BR).


## Criando uma Aplicação

Novas aplicações podem ser criadas apenas por administradores organizacionais do Harmony (veja o artigo [Pré-requisitos](https://success.jitterbit.com/display/APP/Prerequisites?showLanguage=pt_BR)).

Quando você acessa o App Builder, a página **Apps** (Aplicações) é mostrada. Para criar uma nova aplicação, clique no botão **Create New App** (Criar Nova Aplicação) e selecione a opção **Create from Scratch** (Criar do Início). Preencha as informações na caixa de diálogo chamada **Create New App** (Criar Nova Aplicação) e clique no botão **Save** (Salvar). Para ver mais detalhes sobre cada um dos campos, veja o artigo [Criação de Aplicações](https://success.jitterbit.com/display/APP/App+Creation?showLanguage=pt_BR).


## Configurando uma Aplicação

Uma vez que a aplicação está criada, a tela de configuração de aplicação abre. A esta altura, todos os componentes técnicos da aplicação - o *back-end*, o *middleware* e a interface de usuário - já estão preparados.

Agora, configure a aplicação usando as seções no menu de navegação da aplicação:

-   Na seção [Domain Model](https://success.jitterbit.com/display/APP/Domain+Model?showLanguage=pt_BR) (Modelo do Domínio), você cria os componentes estruturais da aplicação, o que consiste dos módulos, relações, menus *dropdown* e dependências.

-   Na seção [Application Logic](https://success.jitterbit.com/display/APP/Application+Logic?showLanguage=pt_BR) (Lógica de Aplicação), você define os comportamentos da sua aplicação, implementados usando microfluxos e fluxos de interface de usuário.

-   Na seção [Configuration](https://success.jitterbit.com/display/APP/Configuration?showLanguage=pt_BR) (Configurações), você ajusta o menu, o guia de usuário, o *design* e as configurações de e-mail da sua aplicação.

A última seção, [Development](https://success.jitterbit.com/display/APP/Development?showLanguage=pt_BR) (Desenvolvimento) é abordada mais à frente aqui nesta página (consulte as seções [Definindo Colaboradores](https://success.jitterbit.com/display/APP/Creating+and+Releasing+an+App?hideelements=false#CreatingandReleasinganApp-definin), [Criando um Pacote](https://success.jitterbit.com/display/APP/Creating+and+Releasing+an+App?hideelements=false#CreatingandReleasinganApp-creating-a-package) e [Lançando uma Aplicação](https://success.jitterbit.com/display/APP/Creating+and+Releasing+an+App?hideelements=false#CreatingandReleasinganApp-releasing-an-app)).


## Pré-visualizando uma Aplicação

Durante o processo de configuração da aplicação, você pode usar o botão **Preview** (Pré-visualização) localizado acima do menu de navegação da aplicação para ver a aplicação que você está projetando ao vivo no navegador. Pré-visualizar a aplicação é uma forma conveniente de ver como ela está sem ter que lançá-la num ambiente de produção.

Ao clicar em **Preview** (Pré-visualização), a interface de usuário abre automaticamente em uma aba separada do navegador. Os elementos padrão da interface de usuário de aplicação são descritos no artigo [Interface de Usuário da Aplicação](https://success.jitterbit.com/display/APP/App+User+Interface?showLanguage=pt_BR).

<div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**CUIDADO**: Mudanças e dados inseridos no modo de pré-visualização tornam-se parte da aplicação e são publicados no ambiente de produção durante o processo de lançamento.

</div>

</div>


## Definindo Colaboradores

Na página [Development](https://success.jitterbit.com/display/APP/Development?showLanguage=pt_BR) \> **Collaborators** (Desenvolvimento \> Colaboradores), os administradores organizacionais do Harmony conseguem controlar quem pode acessar e contribuir com cada aplicação ao especificar níveis de autorização.


## Criando um Pacote

Na página [Development](https://success.jitterbit.com/display/APP/Development?showLanguage=pt_BR) \> **Packages** (Desenvolvimento \> Pacotes), os administradores organizacionais do Harmony conseguem criar um pacote de aplicações.


## Lançando uma Aplicação

Na página [Development](https://success.jitterbit.com/display/APP/Development?showLanguage=pt_BR) \> **Releases** (Desenvolvimento \> Lançamentos), os administradores organizacionais do Harmony conseguem selecionar um pacote de aplicações para ser lançado num ambiente em nuvem.

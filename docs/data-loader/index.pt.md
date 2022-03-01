# Jitterbit Data Loader

[//]: # (This is a translation of Version 52, published on January 12, 2022.)

## Visão Geral

O *Jitterbit Data Loader* (ou, simplesmente, Data Loader) é uma
ferramenta de migração de dados gratuita que permite que administradores
Salesforce automatizem de forma rápida e fácil a importação e exportação
de dados entre *flat files*, bancos de dados e a Salesforce.

O Data Loader reduz dramaticamente o tempo e o esforço necessários para
automatizar o movimento de dados de negócio críticos entrando e saindo
da Salesforce com agendamento integrado que permite que os usuários
programem uma vez e logo não precisem mais se preocupar.

Não importa se você está importando novos *marketing leads*, exportando
dados de vendas para inteligência de negócios avançada ou atualizando
informações de contas e contatos a partir de fontes de bancos de dados,
o Data Loader oferece a ferramenta gratuita mais fácil e funcional
disponível.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** As notas de lançamento estão disponíveis no artigo [Cloud
Data Loader](https://success.jitterbit.com/display/DOC/Cloud+Data+Loader?showLanguage=pt_BR) e a licença do usuário final está disponível no artigo
[Acordo de Licença do Usuário Final do Data Loader](https://success.jitterbit.com/display/DOC/Data+Loader+End+User+License+Agreement?showLanguage=pt_BR).

</div>

</div>

### Vídeos do Data Loader

Para ajudar você a usar o Data Loader e as suas capacidades, visite a
página [Primeiros Passos com o Cloud Data Loader](https://success.jitterbit.com/display/DOC/Getting+Started+with+Cloud+Data+Loader?showLanguage=pt_BR). Vídeos mais
aprofundados podem ser encontrados na nossa Biblioteca de Vídeos, em
<a
href="https://success.jitterbit.com/display/DOC/Video+Library?showLanguage=pt_BR#VideoLibrary-GettingStartedwithDataLoader"
rel="nofollow">Primeiros Passos com o Data Loader</a>. Os vídeos incluem os recursos
básicos além de dicas e sugestões para usar o Data Loader.

### Atualizando do Data Loader para o Jitterbit Harmony

Para ver informações sobre como atualizar do Data Loader para o nosso
produto principal [Jitterbit Harmony](https://success.jitterbit.com/display/DOC/Getting+Started?showLanguage=pt_BR), consulte o nosso <a
href="https://www.jitterbit.com/webinar/webinar-upgrade-your-data-loader-experience-090215/"
class="external-link" rel="nofollow">Webinar
sobre Atualizações</a> e também as Perguntas Frequentes sobre
Atualizações com o Data Loader, <a
href="https://www.jitterbit.com/blog/data-loader-upgrade-webinar-faq-part-1/"
class="external-link" rel="nofollow">Parte 1</a> e <a href="https://www.jitterbit.com/blog/data-loader-upgrade-faq-part-2/"
class="external-link" rel="nofollow">Parte 2</a>.

## Data Loader

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** As versões 8.16.13.1 e posteriores do Jitterbit Cloud Data
Loader suportam TLS 1.2. As versões 10.47 e posteriores do Data Loader
já não suportam TLS 1.0 e TLS 1.1 para conexões de *driver* JDBC com
*endpoints* de bancos de dados por padrão.

</div>

</div>

<div
class="confluence-information-macro confluence-information-macro-warning conf-macro output-block"
hasbody="true" macro-name="warning">

<span
class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**ALERTA:** O Jitterbit Cloud Data Louder, como é uma aplicação de 32
bits, é incompatível e incapaz de executar em sistemas macOS 10.15
“Catalina” ou posteriores, já que estas versões do sistema operacional
requerem que todas as aplicações sejam de 64 bits. Você pode usar uma
máquina virtual para executar uma versão pré-”Catalina” do macOS ou uma
versão do sistema operacional Windows que suporte a versão atual do Data
Loader. Veja o artigo [Requisitos de Sistema do Data Loader](https://success.jitterbit.com/display/DOC/System+Requirements+for+Data+Loader?showLanguage=pt_BR) para
obter mais informações.

</div>

</div>

**Operações de Dados Poderosas**

-   Configuração do tipo aponte-e-clique com o auxílio de assistentes.

-   Suporte para operações do tipo Insert, Update, Upsert, Query, Delete e Bulk.

-   Salvar, editar e reusar operações, conexões e mapeamentos de dados.

**Conectividade Melhorada**

-   Suporte a *flat files* com qualquer delimitador.

-   Conexão com qualquer banco de dados ODBC ou JDBC.

-   Suporte completo a serviços web, incluindo a Bulk API.

**Funcionalidade Avançada**

-   Funções semelhantes ao Microsoft Excel permitem que você transforme
    seus dados, incluindo concatenações, *substrings* e *trims*.

-   Processamento paralelo permite uma performance incomparável,
    incluindo suporte para *bulk loads*.

**Automação e Gerenciamento Fáceis**

-   Marcar operações numa agenda para automatizar *data loads*.

-   Console de gerenciamento que dispõe um histórico completo de registros e operações.

### Benefícios da Conectividade

-   Maximizar o seu investimento na nuvem.

-   Importação ou exportação rápida e fácil de configurar de dados de
    negócios críticos que precisem entrar ou sair da Salesforce.

-   Melhorar significativamente eficiências operacionais por meio da
    automatização de processos comuns.

-   Importar rapidamente novos *leads* de vendas, atualizar contas ou
    exportar dados de *marketing* para aplicações analíticas.

-   Prover uma visão consistente de informações de contas e de clientes por toda a organização.

-   Eliminar a dependência do TI para tarefas de carregamento de dados
    com ferramentas projetadas para o Administrador Salesforce.

-   ***É grátis!***

### Gerencie Seus Dados em 5 Passos

1.  **Configurar:** Configure *endpoints* incluindo *flat files*, bancos
    de dados ou Salesforce.

2.  **Selecionar:** Selecione um objeto Salesforce usando filtros e
    condições do tipo apontar-e-clicar.

3.  **Mapear e Transformar:** Campos de dados podem ser mapeados e
    transformados numa interface gráfica.

4.  **Automatizar:** Agende operações com precisão de segundos com o
    agendador integrado.

5.  **Gerenciar:** Gerencie as suas operações, monitore filas e
    visualize os registros de atividades.

### Como Conseguir o Jitterbit Cloud Data Loader Grátis

Para ter o Jitterbit Cloud Data Loader, visite
<a
href="https://www.jitterbit.com/solutions/salesforce-integration/salesforce-data-loader/"
class="external-link"
rel="nofollow">https://www.jitterbit.com/solutions/salesforce-integration/salesforce-data-loader/</a>.

Se você for um(a) usuário(a) existente do Data Loader, faça *login* no
Harmony Portal em
<a href="https://login.jitterbit.com/" class="external-link"
rel="nofollow">https://login.jitterbit.com/</a> e
acesse a página **Downloads** para conseguir a versão mais recente.

### Suporte ao Data Loader

Para conseguir suporte ao Data Loader, por favor envie todas as
perguntas para
<a href="https://dataloader.jitterbit.com" class="external-link"
rel="nofollow">https://dataloader.jitterbit.com/</a>.

### Folha de Dados em PDF

Saiba mais nesta folha de dados em PDF sobre o Jitterbit Cloud Data
Loader:

<a href="https://bit.ly/2SqPAuK" class="external-link"
rel="nofollow"><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="/download/attachments/55148784/data-loader-vs-ipaas-comparison.png?version=3&amp;modificationDate=1557520174242&amp;api=v2"
class="confluence-embedded-image"
data-image-src="/download/attachments/55148784/data-loader-vs-ipaas-comparison.png?version=3&amp;modificationDate=1557520174242&amp;api=v2"
data-unresolved-comment-count="0" data-linked-resource-id="95290095"
data-linked-resource-version="3" data-linked-resource-type="attachment"
data-linked-resource-default-alias="data-loader-vs-ipaas-comparison.png"
data-base-url="https://success.jitterbit.com"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="55148784"
data-linked-resource-container-version="52" height="250" /></span></a>

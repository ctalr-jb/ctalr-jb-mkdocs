# Jitterbit Harmony API Manager

[//]: # (This is a translation of Version 47, published on December 3, 2021.)

## Visão Geral

O *Jitterbit Harmony API Manager* (isto é, o Gerenciador de APIs do
Jitterbit Harmony, ou, simplesmente, o API Manager) é a interface web
para gerenciamento de APIs da Jitterbit onde você pode criar e publicar
APIs para desenvolvedores e realizar tarefas de gerenciamento do ciclo
de vida completo de uma API. Você pode expor qualquer sistema como uma
API segura, gerenciada e em tempo real que pode ser chamada e consumida
por qualquer outra aplicação. Você pode acessar o API Manager através do
[Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR).

## Pré-requisitos

Para acessar o API Manager, você deve ser membro de uma organização
Jitterbit Harmony com uma assinatura do API Manager e ter as permissões
organizacionais apropriadas e níveis de acesso ambientais descritos no
artigo [Permissões e Acesso no Jitterbit Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access?showLanguage=pt_BR).

Como o API Manager é acessado por meio do Harmony Portal, ele não requer
nenhuma instalação de *softwares* ou *hardwares* adicionais. Os
seguintes navegadores comuns são suportados:

-   Chrome

-   Firefox

-   Safari (apenas para macOS)

Para poder haver comunicação com a nuvem do Harmony e acesso ao Harmony
Portal, o JavaScript precisa estar habilitado e a porta de saída 443
(HTTPS) precisa estar aberta. Esta porta é normalmente permitida por
*firewalls* de servidores corporativos.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Se você estiver usando um [Private Agent](https://success.jitterbit.com/display/DOC/Private+Agents?showLanguage=pt_BR), por favor
note que os Private Agents do Linux podem aceitar uma carga de APIs mais
alta (mais solicitações por minuto) do que os Private Agents do Windows
em máquinas idênticas.

</div>

</div>

## Referência

A documentação de referência do API Manager está incluída nesta seção da
seguinte forma:

-   **[Guia de Início Rápido com o API Manager](https://success.jitterbit.com/display/DOC/API+Manager+Quick+Start+Guide?showLanguage=pt_BR):**
    Um guia para os novos usuários que estão começando com o API Manager.

-   **[Segurança de APIs do Harmony](https://success.jitterbit.com/display/DOC/Harmony+API+Security?showLanguage=pt_BR):** Informações sobre como
    tornar seguras as APIs criadas por meio do API Manager.

-   **API Manager:** Documentação para cada uma das páginas do API
    Manager:

    -   **[My APIs (Minhas APIs)](https://success.jitterbit.com/display/DOC/My+APIs?showLanguage=pt_BR):** A página inicial, onde você
        cria, edita, clona, deleta, publica e gerencia APIs.

    -   **[Portal Manager (Gerenciador do Portal)](https://success.jitterbit.com/display/DOC/Portal+Manager?showLanguage=pt_BR):**
        Esta página é onde você gera documentação OpenAPI interativa para as APIs,
        para serem exibidas na página do Portal.

    -   **[Portal](https://success.jitterbit.com/display/DOC/Portal?showLanguage=pt_BR):** Esta página exibe a documentação OpenAPI
        interativa gerada para as APIs.

    -   **[API Logs (Registros de APIs)](https://success.jitterbit.com/display/DOC/API+Logs?showLanguage=pt_BR):** Esta página exibe os
        registros para todas as APIs.

    -   **[Analytics (Análises)](https://success.jitterbit.com/display/DOC/Analytics?showLanguage=pt_BR):** Esta página exibe as métricas
        de consumo e de performance de todas as APIs.

    -   **[Security Profiles (Perfis de Segurança)](https://success.jitterbit.com/display/DOC/Security+Profiles?showLanguage=pt_BR):** Esta página
        é onde você configura perfis de segurança para atribuir às
        APIs com o objetivo de controlar e tornar seguro o uso delas.

-   **[Jitterbit Private API Gateway (Porta de APIs Privada da
    Jitterbit)](https://success.jitterbit.com/display/DOC/Jitterbit+Private+API+Gateway?showLanguage=pt_BR):**
    Instruções para a instalação de uma porta privada
    local para executar APIs com segurança e controle adicionais além
    das funções de segurança padrão.

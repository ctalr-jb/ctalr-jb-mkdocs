# Jitterbit Harmony Cloud Studio

[//]: # (This is a translation of Version 34, published on October 14, 2021.)

## Visão Geral

O *Jitterbit Harmony Cloud Studio* (ou, apenas Cloud Studio) é a versão
baseada na web da aplicação de *design* de projetos da Jitterbit.

Acessível diretamente pelo [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR), o Cloud
Studio oferece uma experiência de *design* moderna otimizada para a
máxima facilidade de uso e de acesso por parte de *designers* de
integração.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/overview_workflows-tab.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/overview_workflows-tab.png" /></span>

## Pré-requisitos

O Cloud Studio é acessado pelo Harmony Portal e não exige nenhum
*hardware* adicional nem *instalação* de software. Os únicos requisitos
referem-se ao navegador e à versão do Jitterbit Harmony Agent.

### Requisitos de Navegador

Os navegadores abaixo são suportados:

-   Chrome

-   Firefox

-   Safari (apenas para macOS)

Para haver comunicação com a nuvem do Harmony e acessar o Harmony
Portal, o JavaScript precisa estar habilitado e a porta de saída 443
(HTTPS) precisa estar aberta. Esta porta normalmente é permitida por
*firewalls* de servidores corporativos.

### Requisitos de Agente

A versão mínima do Jitterbit Harmony Agent que é suportada com o Cloud
Studio no geral é a versão 9.4.2.

Alguns recursos do Cloud Studio requerem versões de agente posteriores,
incluindo as seguintes:

-   Conectores customizados construídos com o [Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder?showLanguage=pt_BR)
    requerem um agente versão 10.0 ou superior.

-   Conectores customizados construídos com o <a href="https://developer.jitterbit.com/pt/connector-sdk/"
    class="external-link" rel="nofollow">Connector SDK</a>
    requerem um agente versão 10.0 ou superior.

-   [Conectores de aplicação](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-application) &mdash; exceto para os conectores
    customizados indicados acima &mdash; requerem um agente versão 10.1 ou
    superior.

-   O conector NetSuite tem [pré-requisitos de versões de agente](https://success.jitterbit.com/display/CS/NetSuite+Prerequisites?showLanguage=pt_BR)
    diferentes para versões específicas do NetSuite WSDL.

-   O [botão **Try Again** (Tentar de Novo)](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR#OperationLogs-operation-retry), disponível nos
    registros de operação, requer um agente versão 10.1 ou superior.

-   A [função `SendEmail`](https://success.jitterbit.com/display/CS/Email+Functions?showLanguage=pt_BR#EmailFunctions-SendEmail) requer um agente versão 10.1 ou superior
    para usar caracteres *multi-bytes*.

-   A [configuração **Retry** (Nova Tentativa)](https://success.jitterbit.com/display/CS/HTTP+Connection?showLanguage=pt_BR#HTTPConnection-retry) disponível na
    configuração de uma conexão HTTP exige um Private Agent versão
    10.22 ou superior.

-   A [configuração **Retry on Recoverable Exception** (Nova Tentativa
    em Caso de Exceção Recuperável)](https://success.jitterbit.com/display/CS/NetSuite+Connection?showLanguage=pt_BR#NetSuiteConnection-retry) disponível na configuração de
    uma conexão NetSuite requer um Private Agent versão 10.24 ou
    superior.

-   A [configuração **Retry** (Nova Tentativa)](https://success.jitterbit.com/display/CS/SOAP+Connection?showLanguage=pt_BR#SOAPConnection-retry) disponível na
    configuração de uma conexão SOAP requer um Private Agent versão
    10.29 ou superior.

A lista acima não está completa; recursos que requerem versões de agente
posteriores estão descritos na documentação de cada recurso.

## Referência

A documentação de referência do Cloud Studio está organizada em seções
por tópico:

-   **[Introdução](https://success.jitterbit.com/display/CS/Introduction?showLanguage=pt_BR):** Esta seção inclui um guia de início rápido e
    tutoriais, bem como descrição da interface do usuário,
    terminologia e definições.

-   **[Projetos](https://success.jitterbit.com/display/CS/Projects?showLanguage=pt_BR):** Um projeto é uma coleção de um ou mais
    workflows que compõem e executam um caso de uso de integração.

-   **[Componentes de Projeto](https://success.jitterbit.com/display/CS/Project+Components?showLanguage=pt_BR):** Componentes de projeto são as
    partes individuais de um projeto.

-   **[Workflows](https://success.jitterbit.com/display/CS/Workflows?showLanguage=pt_BR):** Um workflow é uma coleção de operações usadas
    como ferramenta para sua conveniência para ajudar a segregar
    diferentes partes de um projeto.

-   **[Operações](https://success.jitterbit.com/display/CS/Operations?showLanguage=pt_BR):** Uma operação é a menor unidade que é executada
    independentemente num agente e registrada pelo Harmony. As
    operações são usadas para definir o que uma integração deve fazer
    e quando isso deve ser feito.

-   **[Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR):** Os conectores fornecem a interface para a
    inserção de informações vindas do usuário, tais como credenciais,
    para criar uma conexão autorizada. Atividades associadas a estas
    conexões podem então ser adicionadas às operações no design canvas
    e configuradas como fontes ou alvos. Um *endpoint* refere-se a uma
    conexão específica e às suas atividades.

-   ***[Schemas](https://success.jitterbit.com/display/CS/Schemas?showLanguage=pt_BR)*:** *Schemas* fonte e alvo representam as
    estruturas de solicitação e resposta para a interação com um
    recurso de dados em uma operação. Estes *schemas* podem ser
    definidos dentro do *transformation* ou fornecidos por uma
    atividade adjacente.

-   ***[Transformations](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR)*:** Os *transformations* são usados como
    etapas numa operação para mapear ou *transformar* entradas em
    saídas, através da movimentação ou limpeza de dados, ou aplicação
    de lógica de negócio. Um *transformation* consiste dos *schemas*
    fonte e alvo que foram definidos no *transformation* e do
    mapeamento de *transformation* que gera a saída.

-   ***[Scripts](https://success.jitterbit.com/display/CS/Scripts?showLanguage=pt_BR)*:** Os *scripts* trazem flexibilidade e capacidade
    para transformar dados, realizar cálculos ou executar validação de
    lógica além de um simples mapeamento de campos. Os *scripts* podem
    ser usados como etapas de uma operação ou dentro de
    *transformations* para aplicar uma lógica ou algumas condições
    específicas aos dados.

-   **[Funções](https://success.jitterbit.com/display/CS/Functions?showLanguage=pt_BR):** Funções são usadas dentro de *scripts* em
    operações e *transformations* para melhorar e refinar processos de
    dados.

-   **[Variáveis](https://success.jitterbit.com/display/CS/Variables?showLanguage=pt_BR):** Variáveis são usadas para permitir a
    configuração dinâmica de *endpoints*, para dar suporte à passagem
    de dados entre operações, e para conduzir lógica de integração
    detalhada dentro de *scripts* de *transformation*.

-   **[Notificações](https://success.jitterbit.com/display/CS/Notifications?showLanguage=pt_BR):** Notificações que enviam um e-mail
    customizado podem ser acionadas mediante o sucesso ou a falha de
    uma operação, ou então chamadas de um *script*.

-   ***[Plugins](https://success.jitterbit.com/display/CS/Plugins?showLanguage=pt_BR)*:** *Plugins* são aplicações supridas pela
    Jitterbit ou por usuários que estendem as capacidades nativas do
    Harmony. A Jitterbit oferece uma ampla gama de *plugins*, ou você
    pode criar os seus próprios usando o Plugin SDK da Jitterbit.

-   **[Protótipos e *Templates*](https://success.jitterbit.com/display/CS/Recipes+and+Templates?showLanguage=pt_BR):** Um protótipo de integração do
    Cloud Studio é um projeto de integração simples e pré-construído
    que move dados em uma direção entre objetos através de duas
    aplicações ou sistemas. Um *template* de processo do Cloud Studio
    é um grupo de casos de uso de integração pré-construído que
    acelera a execução de um processo de negócio específico usando
    vários objetos através de várias aplicações ou sistemas. Os
    protótipos de integração e os *templates* de processo podem ser
    acessados via [Jitterbit Marketplace](https://success.jitterbit.com/display/DOC/Marketplace?showLanguage=pt_BR).

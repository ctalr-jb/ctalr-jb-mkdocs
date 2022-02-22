[//]: # (Perguntas Frequentes sobre o Cloud Studio)
[//]: # (This is a translation of Version 9, published on September 27, 2021.)

## Introdução

Esta página abrange perguntas frequentes sobre o [Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR), a versão baseada na Web da aplicação de *design* de projetos
da Jitterbit.


## Quem pode usar o Cloud Studio?

Todos os assinantes do Jitterbit Harmony têm acesso ao Cloud Studio.

Quando você fizer login no [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR),
clique no cartão do aplicativo Cloud Studio à esquerda para começar a fazer o *design* de projetos diretamente no
seu navegador:

![](https://docs-source.jitterbit.com/hp/landing/cards_cloud-studio_with-header.png)


## Sendo um novo usuário do Cloud Studio, por onde eu começo?

Matricule-se no [curso introdutório](https://success.jitterbit.com/display/DOC/Getting+Training?showLanguage=pt_BR#GettingTraining-cloud-studio)
oferecido na Jitterbit University, nossa plataforma online de gerenciamento de aprendizagem. Mais informações sobre
como se matricular estão disponíveis em [Como Receber
Treinamento](https://success.jitterbit.com/display/DOC/Getting+Training?showLanguage=pt_BR).

Nós também temos um [Guia de Início Rápido com o Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Quick+Start+Guide?showLanguage=pt_BR) para você poder começar em pouco tempo, e uma
seção dedicada de documentação do [Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR) para consultas
detalhadas.

Além disso, o [Jitterbit Marketplace](https://success.jitterbit.com/display/DOC/Marketplace?showLanguage=pt_BR) oferece centenas de projetos
pré-construídos através dos [Protótipos de Integração do Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Integration+Recipes?showLanguage=pt_BR) e dos [*Templates* de Processo do Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Process+Templates?showLanguage=pt_BR), e sempre há novos sendo adicionados. Para
começar com um protótipo ou um *template* já existente, veja [Começando um Projeto com um Protótipo ou um
*Template*](https://success.jitterbit.com/display/DOC/Starting+a+Recipe+or+Template+Project?showLanguage=pt_BR).


## Onde eu posso encontrar ajuda?

Nós oferecemos o mesmo nível de suporte para o Cloud Studio que oferecemos para os nossos outros produtos Harmony.
Saiba mais em [Como Receber Ajuda](https://success.jitterbit.com/display/DOC/Getting+Support?showLanguage=pt_BR).


## Como eu posso construir o meu próprio conector?

O Cloud Studio oferece duas formas de construir conectores customizados:

-   O [Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder?showLanguage=pt_BR) (literalmente "construtor de
    conectores") é uma ferramenta baseada em interface de usuário e que não envolve código, que serve para construir
    conectores a partir de REST APIs. Conectores feitos com o Connector Builder podem ser usados imediatamente após
    serem criados mediante o uso de Cloud Agents ou Private Agents.

-   O [Connector SDK](https://developer.jitterbit.com/pt/connector-sdk/) é um Kit de Desenvolvimento de Software
    Java que serve para construir conectores escrevendo código em Java. Conectores feitos com o Connector SDK devem
    ser compilados e construídos e só podem ser usados com Private Agents.


## Qual versão do Cloud Studio eu estou usando?

Como o Cloud Studio é uma aplicação Harmony localizada na nuvem, você sempre estará usando a versão mais recente
dele. Se você quiser correlacionar a versão com as notas de lançamento, veja [Descobrindo a Minha Versão
Jitterbit](https://success.jitterbit.com/display/DOC/Finding+My+Jitterbit+Version?showLanguage=pt_BR).

Assim como a nossa aplicação para *desktops* Design Studio, o Cloud Studio requer o uso de [Harmony
Agents](https://success.jitterbit.com/display/DOC/Agent?showLanguage=pt_BR) para executar os seus projetos. A versão de agente mínima suportada
com o Cloud Studio é a [versão 9.4.2](https://success.jitterbit.com/display/DOC/9.4?showLanguage=pt_BR).

Certos recursos do Cloud Studio podem requerer uma versão de agente posterior, incluindo a construção de conectores
customizados com o [Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder?showLanguage=pt_BR) ou o [Connector
SDK](https://developer.jitterbit.com/pt/connector-sdk/) ([versão 10.0](https://success.jitterbit.com/display/DOC/10.0?showLanguage=pt_BR)) e o
uso de certos conectores específicos a certas aplicações ([versão 10.0](https://success.jitterbit.com/display/DOC/10.0?showLanguage=pt_BR) ou
[10.1](https://success.jitterbit.com/display/DOC/10.1?showLanguage=pt_BR)), conforme documentado em
[Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

<strong>NOTA:</strong> Para usar certos recursos, você pode precisar usar um <a
href="https://success.jitterbit.com/display/DOC/Private+Agents?showLanguage=pt_BR">Private Agent</a> ou o Cloud Agent Group do Jitterbit
Sandbox, já que o Cloud Agent Group do Jitterbit Production está num ciclo de lançamento posterior e pode não
incluir os recursos disponibilizados há menos tempo (veja <a
href="https://success.jitterbit.com/display/DOC/Cloud+Agent+Groups?showLanguage=pt_BR">Cloud Agent Groups</a>).

</div>

</div>


## O Cloud Studio e o Design Studio são muito diferentes?

Ao fazer a transição do [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR) para o Cloud Studio, você
pode repassar as principais diferenças entre os dois no nosso artigo [Visão Geral do Cloud Studio para Usuários do
Design Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Overview+for+Design+Studio+Users?showLanguage=pt_BR).


## Posso migrar projetos do Design Studio para o Cloud Studio?

Nós oferecemos uma avaliação grátis para serviços de migração. O custo da migração pode variar dependendo da
complexidade do projeto. A Readiness Team (equipe responsável pela avaliação da maturidade dos projetos) do
Jitterbit Cloud Studio pode revisar o seu projeto e oferecer uma estimativa. O seu ou a sua
[CSM](mailto:success@jitterbit.com) pode marcar uma reunião com esta equipe.

Você também pode reconstruir os projetos do início no Cloud Studio.


## Qual é o futuro do Design Studio?

Atualmente, nós não temos planos para encerrar o ciclo de vida ou desabilitar o suporte do [Design
Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR), nossa aplicação de *design* de projetos para *desktops*
existente.


## Posso usar o Cloud Studio mesmo que eu pretenda continuar usando o Design Studio para os meus projetos atuais?

Claro! Você pode inclusive usar o Cloud Studio e o Design Studio ao mesmo tempo, desde que seja para projetos
***diferentes***. Usar as duas aplicações de *design* para o mesmo projeto não é possível.

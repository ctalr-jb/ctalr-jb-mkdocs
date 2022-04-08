# Metodologia de Projetos de Integração

[//]: # (This is a translation of Version 6, published on June 29, 2021.)

## Introdução

Sejamos sinceros: projetos de integração podem ser difíceis, com muitas armadilhas em potencial. Se uma integração é feita de “dados em movimento”, existem horas em que os dados não estão interessados em se mover. Projetos de integração são altamente dependentes de *endpoints* e portanto existem riscos que estão fora do controle do integrador.

Em um mundo ideal, os *endpoints* são estáveis, têm APIs bem documentadas e têm respostas de erro claras. Existem SMEs (especialistas no assunto, sigla em inglês) prontamente disponíveis, e há ambientes de não-produção disponíveis tanto para desenvolvimento quanto para teste. Também, o projeto é bem financiado, é visto como prioridade absoluta pela administração, e há uma quantidade de tempo adequada para os testes. Se o seu projeto é assim, parabéns! O restante, continue lendo.

### Abordagem

Quando você sabe que há um terreno cheio de minas terrestres, você tem duas opções:

1.  Avançar de forma muito cuidadosa e deliberada, analisar a paisagem inteira até o mais mínimo detalhe, e construir somente quando tudo for conhecido.

2.  Iniciar o mais rápido possível, identificar quaisquer minas o quanto antes e celebrar as explosões porque descobrir problemas logo é muito superior a descobri-los depois.

Certo, então vamos com a opção *número 2*. Aperte os cintos, vamos acelerar.

### Audiência

O público alvo são gerentes de projeto (PMs, sigla em inglês) ou líderes técnicos que tenham experiência geral em TI e agora estejam liderando um projeto de integração usando a Plataforma de Integração de APIs Jitterbit Harmony.

Isto inclui as pessoas com papéis tais como parceiro Jitterbit fazendo trabalho de integração geral, um vendedor de aplicações que também aceitou a tarefa de construir as integrações do seu produto até os *endpoints* do cliente, ou um PM cliente, que está implementando o Jitterbit Harmony sozinho ou com ajuda da Jitterbit Professional Services (Serviços Profissionais Jitterbit).

### Foco

O foco deste documento não é mostrar como usar a Jitterbit tecnicamente (consulte o restante da documentação contida na [Success Central](https://success.jitterbit.com/display/DOC/Jitterbit+SuccessCentral) para encontrar as minúcias técnicas). Em vez disso, este documento aborda os itens chave que o(a) PM de um projeto do Jitterbit Harmony precisa saber. Este guia mostra como organizar a sua equipe, como reunir e validar os requisitos de forma clara e concisa, e como utilizar os pontos fortes do Jitterbit Harmony para entregar um projeto bem-sucedido.

## Scoping

*Scoping* (ou seja, determinar o escopo do projeto) é um processo de duas partes que envolve reunir informações, definir as fronteiras do projeto e obter as informações básicas necessárias para implementar o projeto:

1.  **[Ordem de Grandeza](https://success.jitterbit.com/display/DOC/Integration+Project+Methodology#IntegrationProjectMethodology-rough-order-of-magnitude)**: Faça uma estimativa da Ordem de Grandeza (ROM, sigla em inglês) de alto nível do trabalho (esta etapa pode ser saltada para certos *endpoints*).

2.  **[Escopo do Trabalho](https://success.jitterbit.com/display/DOC/Integration+Project+Methodology#IntegrationProjectMethodology-scope-of-work)**: Refine a estimativa detalhando um Escopo do Trabalho (SOW, sigla em inglês) para a entrega do projeto.

Este processo é sensível ao conceito de GIGO — *Garbage In, Garbage Out* (em tradução livre, Lixo Entra, Lixo Sai — então não o negligencie. A planilha abaixo é usada como ponto de partida para o processo de determinação do escopo. A terminologia específica usada nesta planilha será definida mais abaixo nas subseções [Ordem de Grandeza](https://success.jitterbit.com/display/DOC/Integration+Project+Methodology#IntegrationProjectMethodology-rough-order-of-magnitude) e [Escopo do Trabalho](https://success.jitterbit.com/display/DOC/Integration+Project+Methodology#IntegrationProjectMethodology-scope-of-work).

<span class="confluence-embedded-file-wrapper"><img
src="https://success.jitterbit.com/download/attachments/87528965/image%2001.png?version=1&modificationDate=1546542931135&api=v2"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2001.png?version=1&modificationDate=1546542931135&api=v2" /></span>

### Ordem de Grandeza (ROM)

Ao entrar nesta etapa, existe a suposição de que já houve análise o suficiente por parte do cliente para determinar quais interfaces precisam ser construídas. Em alto nível, interfaces são necessárias quando um processo de negócio atravessa as fronteiras entre aplicações. Se os processos de negócio não forem firmes, então a integração também não será, e pode ser que seja cedo demais para fazer uma estimativa.

A Ordem de Grandeza (ROM, sigla em inglês) é projetada para permanecer no alto nível e facilitar um *turnaround* rápido para suportar o planejamento dos clientes e as tomadas de decisões. Estimativas de Ordem de Grandeza dependem dos seguintes elementos:

-   ***Endpoints***: Eles são a “coisa” com que o Jitterbit Harmony vai interagir e onde ele vai escrever ou ler dados. Podem ser uma aplicação com um grupo de métodos remotos, um sistema baseado em arquivos tal como FTP ou sistemas de arquivo internos, um banco de dados ou uma aplicação web expondo APIs.

-   **Cenário de Integração**: Esta é a descrição do movimento dos dados necessário para atingir o objetivo da integração. “Sincronizar Contas”, “Criar Pedidos de Compra” ou “Recolher Informações do Envio” são exemplos.

    -   **Objeto**: Pode ser um objeto SFDC (Salesforce) (tal como uma conta ou um produto), uma tabela de banco de dados ou um objeto de negócio virtual, como por exemplo pedidos de compra em um documento EDI.

    -   **Método**: Isto é o que está sendo feito com os dados, tais como as ações CRUD (criar, ler, atualizar e deletar, sigla em inglês).

    -   **Nível de Complexidade da Transformação**: Pode ser um dos seguintes níveis:

        -   **Baixo**: Usa conectores de *endpoint*, um baixo número de *transformations* e uma ou duas operações para conseguir o cenário.

        -   **Médio**: Pode ou não usar conectores de *endpoint*, usa várias *transformations* e consultas externas e usa várias operações por cenário.

        -   **Alto**: Não usa conectores de *endpoint*, possui várias etapas por cenário, e o *endpoint* é desafiador.

A heurística é usada para gerar horas. Fórmulas são usadas com base na quantidade de cenários e na complexidade para se chegar a uma estimativa, que pode facilmente estar de 15 a 20% fora do alvo. Pense nisso como um número orçamentário a ser usado no início do processo.

As estimativas de ROM partem do pressuposto de que um especialista do Jitterbit Harmony está fazendo o trabalho com certa medida de gerenciamento de projeto. Elas também são *end-to-end* (ponta-a-ponta): desde a iniciação até a implantação. O tempo para construir uma integração não corresponde exatamente com o tempo decorrido. O tempo necessário de fato vai depender da quantidade de pessoas envolvidas, da estabilidade dos *endpoints* do cliente, da disponibilidade de SMEs, etc. Para ser cautelosos, vamos supor uma razão de 3:1 entre a duração no calendário e as horas estimadas.

### Escopo de Trabalho (SOW)

O Escopo de Trabalho (SOW) é projetado para fornecer mais detalhes com o objetivo de se ter uma imagem mais clara do projeto e para que se tenha uma melhora ou um recálculo da estimativa da ROM. Para certos *endpoints* (como SAP) ou tipos de projeto (como acordos Hub), você pode saltar o processo da ROM e ir direto para o passo SOW.

Durante este passo, você deve programar uma sessão de definição de escopo para finalizar detalhes e responder perguntas em aberto. O ideal é que estejam presentes neste encontro os usuários do negócio (e todos os donos do processo) e os SMEs do *endpoint*. Incluir estes últimos é essencial, já que do contrário pode ser difícil mergulhar nos detalhes.

Esta é a melhor chance de esclarecer o perfil de risco do projeto, então ouça com cuidado e faça perguntas. Cubra os seguintes tópicos:

-   ***Endpoints***

    -   **Versões**: Versões a serem usadas ou encontradas.

    -   **Local ou não**: Se forem locais (*on-premises*), não se esqueça de discutir o uso de Cloud Agents ou Private Agents. Uma preocupação comum é a segurança de rede, por exemplo, a abertura do *firewall* para os Private Agents, então garanta aos clientes e aos investidores que isto não é uma preocupação de segurança. Forneça um *link* para os artigos [Whitepaper da Segurança e Arquitetura Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper) e [Requisitos de Sistema para Private Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents).

    -   **Suporte**: Como o(s) *endpoint(s)* é/são suportado(s) (externa ou internamente).

    -   **Estágios do ciclo de vida**: Em desenvolvimento/pré-produção, manutenção, passando por atualizações, final de ciclo.

-   **Conhecimento sobre o _Endpoint_**

    -   **Conhecimento de fonte interna vs. externa**: Caso seja um *endpoint* complexo, como um ERP ou CRM, geralmente há pessoas com conhecimento relevante no departamento de TI, ou um parceiro de implementação e/ou *help desk*. Claro, se você tiver isso, muito melhor.

    -   **Fronteiras/papéis**: Às vezes os clientes não entendem bem o papel do integrador e supõem que a customização do *endpoint* é feita pela Jitterbit; se este tópico surgir, esclareça quais são as fronteiras.

    -   **Disponibilidade e qualidade da documentação**: Com a proliferação de serviços em nuvem e APIs, alguns vendedores estão simplesmente listando suas APIs mas a documentação pode às vezes deixar a desejar. Se esta for a sua situação, você deve construir com tempo para processos de descobrimento, viabilidade e teste.

-   **Cenários de Integração**

    -   **Método e objetos _endpoint_**: Defina quais são para cada cenário. Exemplos:

        -   *“Fazer* queries *periódicas para novos clientes no* Endpoint *X e incluí-los na conta do* Endpoint *Y em grupos e atualizar o novo número de conta em Cliente”.*

        -   *“Receber uma solicitação em tempo real do* Endpoint *X que contenha informação de pedidos para mandar para o método criar pedido do* Endpoint *Y e responder com o novo número de pedido”.*

        -   *“Fazer* query *na Tabela X do Banco de Dados e atualizar 200.000 valores de balanço de estoque para a API de Inventário do* Endpoint *Y”.*

    -   **Bloqueadores em potencial**: Os cenários são usados para a estimativa de tempo. Espere que o desenvolvimento de cada cenário (a menos que seja extremamente simples) encontre bloqueadores. Eles podem ser técnicos (credenciais ruins, *endpoint* inacessível, API opaca) ou procedurais (o negócio precisa definir um novo processo, customização é necessária, SMEs não estão disponíveis).

-   **Prazos**

    -   **Datas importantes**: Normalmente um cliente sabe a data em que quer a integração pronta, mas existem outras datas importantes.

    -   **Datas de Teste de Aceitação do Usuário (UAT, sigla em inglês)**: Quando começam os UATs? (Pode ser que este conceito precise ser explicado caso o cliente não esteja habituado ao desenvolvimento em fases.)

    -   **Prontidão do *endpoint***: Ao usar novos *endpoints*, quando os ambientes vão estar prontos para desenvolvimento de integração e testes?

    -   **Disponibilidade de SMEs**: Há restrições à disponibilidade dos SMEs?

        <div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-warninf confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **CUIDADO**: Tenha cuidado ao tentar acelerar um projeto de integração. Adicionar mais desenvolvedores não faz o desenvolvimento acontecer mais rápido a menos que haja cenários muito claros e separados.

        </div>

        </div>

-   **Recursos**

    -   **Abordagens**: Os clientes têm abordagens variadas para recursos de projeto:

        -   **Mais terceirizado**: O cliente fornece um ponto de contato de negócio ou SME, e toma conta dos requisitos, da escalação, do UAT, e da coordenação de recursos externos. Todos os outros recursos (principalmente o desenvolvimento) são fornecidos pela Jitterbit Professional Services e/ou o Parceiro Jitterbit.

        -   **Mais interno**: O cliente vai aprender a usar o Jitterbit Harmony e só quer acesso a um Jitterbit SME para obter orientações e melhores práticas.

        -   **Mesclado**: O cliente quer que a Jitterbit Professional Services ou o Parceiro Jitterbit construa várias integrações e gradualmente as entregue para os recursos de clientes. Esta parte é difícil de estimar. A abordagem recomendada é estimar todo o trabalho, daí subtrair uma porcentagem de horas.

            <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

            <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

            <div class="confluence-information-macro-body">

            **NOTA**: O cliente pode não entender que gastará muito tempo no projeto de qualquer forma, e que mudar o desenvolvimento de externo para interno não terá um grande impacto (já que a maioria dele é limitado a uma única fase), e pode até desacelerar o progresso por causa da transferência de conhecimento.

            </div>

            </div>

-   **Nível de envolvimento**: Este diagrama ilustra o nível de envolvimento relativo do gerente do projeto (PM), recursos de clientes e recursos de desenvolvimento. Note que os recursos de desenvolvimento são mais envolvidos durante a fase de desenvolvimento, e o envolvimento deles cai logo após. Os recursos de clientes (geralmente usuários de negócio) são muito envolvidos durante a fase dos UATs (Testes de Aceitação do Usuário), um fato que é muitas vezes ignorado.

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/87528965/image%2002.png?version=1&modificationDate=1546542931582&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2002.png?version=1&modificationDate=1546542931582&api=v2" /></span>


## Equipe

Estas diretrizes gerais são para a escolha de equipes com habilidades técnicas Jitterbit e de gerenciamento de projetos. Elas não incluem recursos tais como SMEs dos processos de negócio de clientes nem donos de *endpoints*. Baseado no tamanho do projeto, os seguintes níveis de tamanho de equipe são recomendados:

-   **Projetos pequenos**: Projetos com 2 *endpoints* e menos de 12 cenários podem ser desenvolvidos por um único recurso com habilidades técnicas Jitterbit trabalhando em tempo parcial com um gerente de projeto também trabalhando em tempo parcial.

-   **Projetos médios**: Projetos com 2 a 4 *endpoints* e 12 a 20 cenários podem ter o mesmo tamanho de equipe que os projetos pequenos, porém com a equipe mais envolvida.

-   **Projetos grandes**: Projetos com mais de 5 *endpoints* e mais de 20 cenários têm muitas dependências na hora de determinar o tamanho da equipe.

O papel de gerente do projeto pode ter próximo de 100% de envolvimento ao longo do projeto caso qualquer uma das afirmações a seguir seja verdadeira:

-   O cliente requer relatórios de *status* detalhados (tais como relatórios para um escritório de gerenciamento de projetos).

-   Vários SMEs externos têm que configurar os *endpoints* do cliente para possibilitar a integração.

-   É provável que o cliente tenha dificuldade para conseguir os requisitos de integração detalhados.

-   O gerente do projeto é inexperiente ou ausente, e o cliente espera que você gerencie o projeto inteiro.

Exerça um gerenciamento de escopo e de mudanças bastante estrito nessas situações! Deixe claro para o cliente que o sucesso do projeto depende de que o cliente ajude a remover quaisquer bloqueadores e que todos os recursos do projeto cumpram seus prazos.

Ao usar vários recursos de desenvolvimento, faça as seguintes considerações:

-   Ter mais de um desenvolvedor em um único projeto Jitterbit requer um alto nível de coordenação (mais trabalho para o gerente) já que é fácil implantar mudanças e sobrescrever o trabalho de outra pessoa.

-   Esforce-se para dar diferentes cenários de integração aos desenvolvedores, ou dilua o trabalho em diferentes projetos Jitterbit.

-   Use o mesmo *design* para todos os desenvolvedores e faça revisões de código.

-   Se possível, aumente os recursos durante a fase de desenvolvimento, daí diminua durante as fases de UAT e de implantação final.


## Reunião de *Kickoff*

O propósito da reunião de *kickoff* é reunir os participantes principais do projeto, geralmente o(s) usuário(s) de negócio chave, os SMEs, os donos do *endpoint* e os arquitetos de integração. Este tempo é usado para que todos alinhem suas expectativas e para que os papéis e responsabilidades sejam esclarecidos. Durante a reunião de *kickoff*, as seguintes tarefas devem ser completadas:

-   **Datas chave**: Revise todas as datas chave (não apenas a data de implantação final).

-   **Compartilhamento de informações**: Compartilhe informações de contato e documentos.

-   **Revisão do cenário de integração**: Reveja os cenários de integração da determinação de escopo.

    -   Esta é uma boa hora para confirmar se algo mudou desde a última sessão de determinação de escopo.

    -   Se for necessário, marque uma reunião de revisão de escopo detalhada.

-   **Papéis e responsabilidades**: Construir integrações com a Jitterbit é muito rápido, mas tenha em mente que o fator mais determinante que atrasa projetos de integração são as dependências não-técnicas. Este é um bom momento para enfatizar esse ponto. Esclareça as responsabilidades de cada papel:

    -   **Gerente do Projeto**

        -   Trabalha com o cliente e com a equipe técnica para conseguir e organizar requisitos de integração detalhados, incluindo mapeamentos a nível de campo. Mapeamentos a nível de campo são necessários tanto pelo(s) recurso(s) de desenvolvimento Jitterbit quanto pelos SMEs do *endpoint*.

        -   Organiza a disponibilidade dos SMEs de negócio e do *endpoint* para o projeto e resolve prontamente itens em aberto para a integração, tais como quem é quem, seus níveis de comprometimento com o projeto, calendários, etc.

        -   Comunica ao cliente e à equipe técnica o progresso do desenvolvimento da integração e os itens em aberto a serem resolvidos.

    -   **Desenvolvedor Jitterbit**

        -   Tem entendimento dos requisitos para fazer o *design* da arquitetura de integração, e trabalha com o cliente nas considerações de *design* (entrega em *batches* ou em tempo real, APIs, gerenciamento de dados, requisitos de segurança, etc.). O desenvolvedor precisa estar familiarizado com a documentação da [Biblioteca de Padrões de *Design*](https://success.jitterbit.com/display/DOC/Design+Pattern+Library) do Jitterbit Harmony.

        -   Pega os requisitos detalhados e usa a ferramenta para desenvolver os cenários de operação, de acordo com as [Melhores Práticas Jitterbit](https://success.jitterbit.com/display/DOC/Best+Practices+with+Jitterbit).

        -   Rapidamente identifica quaisquer bloqueadores, e toma a iniciativa para resolvê-los.

        -   Idealmente, o desenvolvedor Jitterbit está em comunicação direta com o cliente. Isolar o desenvolvedor Jitterbit dos SMEs e dos clientes é uma prática ruim e leva a falhas de comunicação e atrasos. Os recursos do projeto precisam ser uma equipe e devem se comunicar fluidamente.

    -   **SME do *Endpoint***

        -   Provê profundo conhecimento sobre as interfaces expostas.

        -   Entende os requisitos de integração, e se houver problemas em potencial — tais como precisar de uma mudança em um *endpoint* ou se um requisito for inviável — alerta o resto da equipe de forma proativa.

        -   Está altamente disponível para ajudar com o teste de unidades. Isto pode incluir o fornecimento de dados de teste, dar *feedback* rápido sobre os resultados dos testes de integração e interpretar as respostas de erros.

-   **Licenciamento e prerrogativas**: Revise o licenciamento e as prerrogativas Jitterbit e o processo para solicitar prerrogativas.

-   **Arquitetura do Jitterbit Harmony**: Considere os seguintes pontos com relação à arquitetura do Jitterbit Harmony:

    -   Se forem usados Private Agents, dê prioridade à instalação da arquitetura técnica e a conectividade com os *endpoints*, primariamente para o desenvolvimento.

    -   Se estiver trabalhando com sistemas locais (*on-premises*), há muitos passos que podem demorar para acabar, tais como aquisição de *hardware*, instalação de Private Agents, conectividade de rede, credenciais de usuários de integração e o ciclo de teste. Já que isto pode envolver vários grupos, comece este processo assim que possível para o ambiente de desenvolvimento.

    -   Espere que as lições aprendidas durante o preparo do ambiente de desenvolvimento acelerem o preparo do ambiente de não-desenvolvimento, então cumpra este passo o quanto antes dentro do que for razoável.

    -   Para mais informações, consulte os artigos [Agents e Agent Groups](https://success.jitterbit.com/display/DOC/Agents+%3E+Agent+Groups), [Requisitos de Sistema para Private Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents), [Ambientes](https://success.jitterbit.com/display/DOC/Environments) do Harmony e o [Whitepaper da Segurança e Arquitetura Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper).

-   **Membros do Jitterbit Harmony**: Tenha certeza de que os recursos de desenvolvimento sejam adicionados à organização Harmony com permissão do tipo *Admin* (veja o artigo [Organizações Jitterbit](https://success.jitterbit.com/display/DOC/Organizations)).

-   **APIs do Jitterbit Harmony**: Se APIs forem usadas, reveja as dependências. Verifique a URL padrão da API do Jitterbit Harmony. Se o cliente começou usando uma amostra, é possível que a URL padrão ainda inclua a palavra “trial” (“amostra” em inglês). Escale para o licenciamento Jitterbit para que isso seja removido antes de você começar a construir APIs (veja o artigo [Jitterbit API Manager](https://success.jitterbit.com/display/DOC/API+Manager)).

-   **Reuniões futuras**: Estabeleça a cadência das reuniões futuras.

    -   Se a integração for parte de uma implementação de *endpoints*, então entre nessas reuniões.

    -   Caso contrário, reuniões curtas mas frequentes (não é incomum elas serem diárias) são preferidas. Uma plataforma de mensagens instantâneas como o Slack também pode ser preparada.

### Plano do Projeto de Integração

Como mencionado antes, a integração tem muitas dependências. Os planos do projeto tendem a vir em dois tipos:

-   Parte da implementação de um novo *endpoint*, como um ERP.

-   Individualmente, onde os *endpoints* são relativamente estáveis.

No primeiro caso, as tarefas do projeto de integração podem (e terão que) ser intercaladas com o projeto geral. Por exemplo, o desenvolvimento da integração terá que esperar até que os objetos *endpoint* sejam configurados.

No segundo caso, um plano de projeto apenas para a construção da integração pode ser preparado.

Independentemente de as tarefas de integração serem ou não parte de outro plano, as tarefas são iguais. Aqui está um exemplo de um plano de projeto individual:

<span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/87528965/image%2003.png?version=1&modificationDate=1546542931211&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2003.png?version=1&modificationDate=1546542931211&api=v2" /></span>

Note que o plano do projeto começa com os blocos de construção básicos, daí itera por cada cenário. A seção com os UATs (Testes de Aceitação do Usuário, sigla em inglês) pode ser adiada até depois de todos os cenários terem chegado a seu estado de prontidão.


## Reunião de Requisitos e Desenvolvimento

Esta seção começa cobrindo a abordagem geral para reunião de requisitos e desenvolvimento, daí vai a fundo nos detalhes do mapeamento, desenvolvimento, gerenciamento do processo de desenvolvimento, reuso, e tratamento de registros e de erros.

### Abordagem Geral

O *front-end* para desenvolvimento gráfico de baixo código do Jitterbit Harmony (o Harmony Studio) é muito útil para um modelo iterativo. Esta abordagem ***não*** é do tipo “waterfall” (cascata), em que todos os requisitos são documentados antes do início do desenvolvimento. Os seguintes passos chave descrevem o modelo iterativo geral:

-   Comece com os cenários de dados mestre. Já que a abordagem envolve iterar rapidamente por um ciclo definir-construir-testar, precisamos ter os *endpoints* populados com dados mestre antes de trabalhar com dados transacionais.

-   Entenda quais sistemas são tipo SOR (Systems of Record, isto é, Sistemas de Registro) e quais são tipo SOE (Systems of Engagement, isto é, Sistemas de Engajamento):

    -   **SOR (Systems of Record)**: A fonte autoritativa para dados mestre, geralmente um ERP.

    -   **SOE (Systems of Engagement)**: O sistema que fica de frente para o cliente ou vendedor, como um sistema para comprar um produto.

-   Entenda os campos de dados chave e quais são compartilhados (chaves externas ou estrangeiras).

    -   Tipicamente as chaves de dados mestre de um SOR são armazenadas no SOE para facilitar o envio de atualizações para o SOR. Por exemplo, se SAP for o SOR e SFDC for o SOE, então os números de clientes SAP são armazenados como IDs externos no SFDC.

    -   Já que chaves compartilhadas podem exigir customização (que pode se tornar um bloqueador de tempo), é importante lidar com esta área o quanto antes.

O diagrama abaixo mostra um exemplo usando a Salesforce como SOE e SAP como SOR, em um fluxo de dados mestre unidirecional com *write-back*.

<span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/87528965/image%2005.png?version=1&modificationDate=1546542931286&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2005.png?version=1&modificationDate=1546542931286&api=v2" /></span>

Se estiver lidando com atualizações de dados mestre bidirecionais, reconheça que isto pode ser uma integração complicada:

-   Você pode se deparar com condições de corrida, lógica para excluir atualizações do usuário de integração separada dos usuários de negócio e chaves compartilhadas mútuas.

-   Frequentemente, as regras de negócio para os dados mestre não são as mesmas nos *endpoints*, e ou a camada de integração tem que acomodá-las ou os *endpoints* precisam ser customizados. Isto pode ser um bloqueador, então percorra os cenários em detalhes para estes tipos de integração.

### Mapeamento

O PM deve pedir que o cliente comece a trabalhar nos mapeamentos a nível de campo detalhados. Eles são necessários tanto pelos recursos de desenvolvimento Jitterbit quanto pelos SMEs dos *endpoints*.

O cliente pode estar acostumado a olhar para os sistemas do ponto de vista da interface do usuário e pode não conseguir produzir mapeamentos baseados no ponto de vista dos *schemas*. Neste caso, inclua os *schemas* na planilha do mapeamento, se possível. Isto pode exigir ajuda do SME, documentação *online* ou o uso do Jitterbit Harmony para se conectar com o *endpoint* e puxar os *schemas*.

Se o mapeamento for direto, você pode fazê-lo “ao vivo” usando o Jitterbit Harmony para puxar os *schemas* dos *endpoints* em um *transformation* durante uma reunião de clientes.

A planilha abaixo demonstra um exemplo de mapeamentos a nível de campo:

<span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/87528965/image%2006.png?version=1&modificationDate=1546542931339&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2006.png?version=1&modificationDate=1546542931339&api=v2" /></span>

Quando há definição de cenário suficiente para começar, tente construir a integração no Jitterbit Harmony e teste o quanto antes para identificar quaisquer bloqueadores.

À medida que o cliente percorre a planilha de mapeamento, preste bastante atenção a quais mapeamentos serão mais difíceis. O *transformation* é onde os pneus tocam o asfalto, o que significa que é onde nós mapeamos os métodos de integração expostos entre os sistemas. É importante descobrir quais cenários serão mais difíceis do que os outros, já que há um multiplicador de tempo alto nesses casos. Mapeamentos fáceis podem demorar apenas alguns minutos, enquanto mapeamentos mais complexos podem demorar dias, então procure localizar essas situações e priorize:

-   **Consultas a sistemas externos**: Para alguns sistemas, você pode precisar consultar valores executando *queries*. O perigo aqui é o impacto na performance: esteja ciente de que o *transformation* do Jitterbit Harmony executa com base em registros. Se você estiver processando 200 registros, e o *transformation* faz uma consulta em cada registro, serão 200 *queries*. Isto não é um grande problema se o alvo for um banco de dados, mas se o dado for uma API, isso pode significar também 200 *logins* e *logouts*. Considere usar um dicionário para fazer *query* dos dados em um *script* pré-operação, assim terá que fazer uma única *query*.

-   **_Schemas_ complexos**: O *transformation* do Jitterbit Harmony é “baseado em iterações”. Por exemplo, se os *schemas* alvo e fonte forem de tipo *flat* (tais como um nome de cliente e endereço domiciliar), então o *transformation* vai iterar uma vez por registro, assim:

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/87528965/image%2007.png?version=1&modificationDate=1546542931405&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2007.png?version=1&modificationDate=1546542931405&api=v2" /></span>

    No exemplo seguinte (abaixo), tanto o *schema* fonte quanto o alvo são complexos, e o *transformation* precisa processar as seções filha repetidas vezes. Para complicar ainda mais as coisas, ele pode ter que processar as seções filha condicionalmente:

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/87528965/image%2008.png?version=1&modificationDate=1546542931492&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2008.png?version=1&modificationDate=1546542931492&api=v2" /></span>

Frequentemente, para fazer progresso rápido em mapeamentos complexos, os SMEs dos *endpoints* precisam ser reunidos para definir os requisitos, o que pode até exigir *input* do negócio e pode levar à customização dos *endpoints*, todas coisas que podem atrasar o projeto em geral. É de importância vital identificar requisitos de integração complexos o quanto antes e cobrir as dependências de forma rápida para manter o projeto avançando.

### Desenvolvimento

Como mencionado antes, o trabalho de desenvolvimento pode começar logo após o *kickoff*:

-   Conecte os *endpoints*.

-   Identifique e implemente cenários fáceis, particularmente em caso de dados mestre.

-   Para integrações complexas, mesmo que não estejam completamente mapeadas, dê os passos para levar os métodos de integração expostos a um *transformation*.

    -   Os *schemas* (normalmente) se aplicam somente ao lidar com bancos de dados e serviços *web*.

    -   Ao lidar com arquivos, será mais eficiente construir visualizações do que fazer o Jitterbit Harmony unir tabelas. Um procedimento armazenado pode ser uma abordagem melhor do que fazer o Harmony fazer atualizações complexas.

    -   Ao trabalhar com conectores de *endpoints*, use os assistentes do Jitterbit Harmony e tenha cuidado para que todos os objetos no escopo estejam disponíveis. Esta é uma boa forma de validar que o usuário de integração tem todas as permissões que precisa para trabalhar.

-   O desenvolvedor deve analisar os *schemas* fonte e alvo para poder fazer perguntas de mapeamento “inteligentes”, tais como as seguintes:

    -   *“Nós temos todos os campos obrigatórios?”*

    -   *“Se passarmos um ID de registro, o* endpoint *vai atualizar um registro automaticamente ou vai tentar criá-lo?”*

    -   *“Quantos registros podem ser passados em uma chamada?”*

    -   *“Este* schema *SAP IDoc usa abreviações em alemão. Alguém aqui Sprechen Sie Deutsch?”*

-   Não negligencie rever o *schema* de resposta (se for um serviço *web*), principalmente a parte de como os erros são lidados. Alguns *schemas* indicam sucesso ou falha geral, enquanto outros fornecem códigos que precisam ser avaliados.

### Gerenciando o Processo de Desenvolvimento

Uma boa abordagem para gerenciar o processo de desenvolvimento é pegar os cenários capturados durante o escopo e monitorar marcos relacionados a cada cenário. Esta é uma planilha exemplo usada para monitorar marcos chave em um desenvolvimento de integração:

<span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/87528965/image%2009.png?version=1&modificationDate=1546542931549&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2009.png?version=1&modificationDate=1546542931549&api=v2" /></span>

Trate cada cenário como uma iteração de mini-desenvolvimento, começando com as dependências de dados (tais como dados mestre). Daí construa operações, construa *transformations*, busque dados teste, empurre para um *endpoint*, lide com a resposta. Não espere perfeição. Busque apenas mover dados de teste simples do ponto A para o ponto B e daí prossiga para o próximo cenário. Daí, itere o desenvolvimento do cenário de integração, revelando bloqueadores até que tanto o principal cenário de sucesso quanto cenários de erros variados tenham sido desenvolvidos e testados unitariamente.

O primeiro conjunto de integrações serão as que terão o maior número de problemas, tais como conectividade, permissões, campos faltantes, etc. Então quanto antes chegarmos a este ponto e nos livrarmos dos bloqueadores, melhor. Não estamos buscando perfeição imediatamente.

Comece com um pequeno grupo de dados de teste. Isto pode ser incluído nos *scripts* de forma *hard-coded* ou você pode usar uma *query* limitada a apenas alguns registros.

Se houver um pequeno bloqueador, documente-o, atribua a resolução dele à pessoa certa, e prossiga para outro cenário. De novo, o objetivo é encontrar rapidamente as armadilhas para que elas possam ser removidas, e esta responsabilidade é normalmente do cliente e/ou dos SMEs.

Aqui está um exemplo de uma planilha que registra erros:

<span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/87528965/image%2010b.png?version=1&modificationDate=1546542931568&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/87528965/image%2010b.png?version=1&modificationDate=1546542931568&api=v2" /></span>

### Reuse!

Como qualquer outra plataforma de desenvolvimento de *software*, o desenvolvimento pode ser acelerado se você não tentar reinventar a roda. O Jitterbit Harmony tem várias formas de permitir isso:

-   ***Scripts***

    -   Funções customizadas inteiras podem ser construídas e chamadas a partir de muitas operações. A regra geral é que se você tem que escrever o mesmo *script* duas vezes, faça dele um *script* que pode ser chamado.

-   **Fonte e Alvos**

    -   Passe variáveis globais e/ou de projeto em vez de incluir de forma *hard-coded* coisas tais como caminhos de arquivos ou anfitriões FTP.

    -   Use uma variável global como um espaço de trabalho intermediário em vez de fontes e alvos específicos a operações.

-   **Operações**

    -   Operações de tarefa única podem ser construídas uma vez e usadas muitas vezes, principalmente aquelas que lidam com tratamento de erros e registros.

    -   As operações em um projeto podem ser chamadas por outro. Esteja ciente que os registros vão aparecer nos projetos nativos (os que foram chamados). Mas já que o escopo de variáveis globais é a corrente de operação (que pode ser chamada de mais de um projeto), é possível conseguir os resultados da operação remota e registrá-los no projeto que fez o chamado.

### Registros e Tratamento de Erros

Um grupo de requisitos frequentemente ignorado tem a ver com os registros e com o tratamento de erros. O cliente pode não ter requisitos específicos, principalmente se for a primeira vez dele com um projeto de integração, então o cliente precisará de ajuda com as melhores práticas nesta área. Os pontos chave são os seguintes:

-   O Jitterbit faz registro de operações por padrão.

-   É fácil registrar dados adicionais, o que é muito útil para diagnóstico e resolução de erros.

    -   É neste momento que o cliente pode se dar conta de que os seus cenários de integração vão exigir suporte interno.

    -   Quando um problema é identificado em um *endpoint*, se uma causa raiz possível for a integração, então um recurso terá que inspecionar os registros do Jitterbit Harmony. Quanto mais claros e informativos forem os registros, mais rápido será o processo de diagnóstico e resolução.

-   Há duas classes gerais de alertas: alertas relacionados a dados e alertas de falhas técnicas, que podem ou não precisar ir ao mesmo grupo. As falhas técnicas são fáceis de configurar, mas os registros relacionados a dados são todos customizados, e é mais fácil incluí-los durante o desenvolvimento da integração do que adicioná-los depois.

-   O Jitterbit Harmony Studio pode usar e-mail facilmente, onde o serviço de e-mail é tratado como um *endpoint* para o serviço de e-mail do cliente, usando ou as notificações de e-mail do Cloud Studio ou um alvo de e-mail do Design Studio. Embora isso seja geralmente fácil de programar, este passo não deve ser deixado por último.

-   O Jitterbit Harmony Management Console pode ser usado para configurar notificações adicionais relacionadas à organização.

Para informações mais detalhadas, consulte o artigo [Programando Alertas, Registros e Tratamento de Erros](https://success.jitterbit.com/display/DOC/Setting+Up+Alerting%2C+Logging%2C+and+Error+Handling) e a página de [Notificações](https://success.jitterbit.com/display/DOC/Notifications) do Harmony.


## Tratamento de Regras de Negócio

O grande debate: incluir — ou não incluir — regras de negócio.

Muitos clientes começam pensando “Eu não quero incluir regras de negócio no meio, quero deixar as coisas simples”, mas aí fazem requisitos que são exatamente o contrário!

A arquitetura de *middleware* ideal dita que a camada de integração deve ser o mais enxuta possível, focada em seus pontos fortes: transformação de dados, processamento e orquestragem de cenários, conexão de *endpoints*, registros e alertas. Adicionar regras de negócio pesadas vai só estragar a perfeição dessa arquitetura por trazer o suporte da regra de negócio para o outro lado da fronteira do *endpoint*. Ou seja, se uma regra de negócio mudar, ela não muda só na aplicação; ela muda no *middleware* também. Além disso, como o *middleware* é confuso, indistinto e místico, a manutenção das regras é uma chatice.

A realidade infelizmente vai se meter no meio, já que o Jitterbit Harmony precisa trabalhar com o que as aplicações expõem:

-   Os dados são mal apresentados, e a única forma de processá-los é aplicar regras de negócio (*“se valor = a, departamento = vendas, se b, departamento = operações, se c, departamento = suporte”*)

-   Os dados fonte são incompletos (*“se país = EUA, ano fiscal é igual ao do calendário, se país = Reino Unido, ano fiscal vai de abril a março”*)

-   O cenário de integração é puxado por dados (*“se o pedido de trabalho contiver linhas que usam terceiros, processe esta linha como uma entrada AP, caso contrário atualize-a, como pedido de serviço”*)

Sim, todos os casos acima poderiam ser lidados pelo *endpoint*. Mas isto parte do pressuposto de que o cliente tem os recursos e o tempo para customizar o *endpoint* ou mudar uma API. Se tudo isso estiver disponível, então fique à vontade para fazer dessa forma. No entanto, é mais comum que os *endpoints* sejam mais difíceis de mudar e manter do que o projeto de integração do Jitterbit Harmony.

Quando as regras de negócio devem ser tratadas, as melhores práticas são as seguintes:

-   Externalize sempre que possível. Por exemplo, mantenha os dados numa tabela onde possam ser mantidos por um usuário.

-   Use variáveis de projeto. Elas são expostas no Jitterbit Harmony Management Console juntos com a documentação específica. O caso de uso principal é para credenciais de *endpoints* específicas a certos ambientes, mas elas também podem ser usadas para conduzir lógica de orquestração e condições de *query*.

-   Adicione registros customizados detalhados e tratamento de erros de dados, para que se e quando as regras de negócio mudarem, o efeito na integração seja óbvio.


## Agentes e Ambientes

O Jitterbit Harmony Agent é o burro de carga da integração. O Harmony Studio não executa nenhum processo de operação. Tudo ocorre num Harmony Agent. Uma decisão chave que precisa ser tomada bem cedo é qual tipo de agente usar: um Private Agent ou um Cloud Agent (veja o artigo [Jitterbit Agents](https://success.jitterbit.com/display/DOC/Agents)).

Se qualquer uma das condições abaixo for verdadeira, o projeto deve ser executado num Private Agent:

-   Um *endpoint* está atrás do *firewall* do cliente. Isto pode ser uma aplicação ou um compartilhamento de rede.

-   Um *plugin* ou *driver* é exigido que não está disponível nos Cloud Agents. Por exemplo, o *driver* Excel só está disponível nos Private Agents.

-   Os requisitos de segurança do cliente são tais que não permitem que nenhum dado saia do *firewall* dele.

Caso contrário, os Cloud Agents são uma opção viável. De uma perspectiva de tempo de projeto, isto é ideal, já que evita todos os passos relacionados a um cliente ter que providenciar *hardware* de servidor e instalar o *software* do Jitterbit Harmony Agent. No entanto, independentemente de você usar Cloud Agents ou Private Agents, você ainda tem que definir membros e ambientes.

Dependendo do nível de licença, um cliente terá duas ou mais licenças de Private Agent. Também, o cliente terá direito a vários ambientes, que são tipicamente preparados seguindo as categorias padrão do ciclo de vida do desenvolvimento de um *software* (desenvolvimento, qualidade, *staging*, produção, suporte, etc.). A ferramenta de migração da Jitterbit funciona com os ambientes para possibilitar a promoção dos projetos de integração.

Com respeito a agentes e ambientes, note os seguintes pontos importantes:

-   Identificar um ambiente como “produção” não confere nada de especial. Ele não executa mais rápido nem é mais resiliente. Um ambiente é basicamente como qualquer outro.

-   Um ambiente do Jitterbit Harmony pode ser usado de muitas formas. Se o cliente estiver fornecendo integração para um terceiro, um ambiente pode ser usado como um *container* para projetos de empresa dedicados.

-   Um único Private Agent pode executar mais de um ambiente.

-   Uma pergunta frequente é se alguma regra de *firewall* de rede precisa ser mudada. Normalmente a resposta é “não”, a menos que o cliente esteja restringindo o tráfego HTTP que sai de seus servidores e/ou portas. A comunicação entre o Jitterbit Harmony e o Agent é toda de saída no sentido do Agent para o Harmony.

Um Agent Group é uma parte obrigatória da arquitetura do agente. Além de ser o *container* virtual que abriga os Private Agents, ele desempenha outro papel importante. Ao contrário de ferramentas de gerenciamento de servidor tradicionais que exigem aplicações adicionais tais como balanceadores de carga, o Jitterbit Harmony torna fácil conseguir resiliência de servidor por meio do balanceamento de cargas e *failover*. Simplesmente por adicionar um agente a um grupo, o agente automaticamente se torna parte de um agrupamento de servidores.

Para sermos claros, ao executar uma operação em um Agent Group com vários agentes, apenas um agente está executando aquela operação. A operação não é dividida e executada por todos os agentes no grupo. Adicionar agentes a um grupo não vai (normalmente) fazer as operações executarem mais rápido. A única exceção é um *design* que pede que um grupo de agentes sirva APIs com alto tráfego de entrada, e neste caso dividir a carga em vários agentes é uma boa ideia.

Para começar o desenvolvimento, tudo que é necessário é um único Private Agent e um único ambiente. Agentes adicionais podem ser adicionados a grupos, e novos ambientes podem ser adicionados à medida que o projeto avança (tudo dentro dos limites da licença, é claro),

Se providenciar até mesmo um único agente for problemático, um Jitterbit Private Agent pode ser executado numa estação de trabalho. A melhor forma de fazer isso é usar o Docker Agent para evitar conflitos de *desktop*.


## Processamento em Lotes ou Orientado a Eventos (Tempo Real)

Para cada cenário de integração, existe uma grande decisão: como a integração será inicializada?

Existem basicamente duas formas: uma abordagem em lotes (em inglês, *batch processing*), como por agenda, ou acionada por um evento (em inglês, *event-driven processing*), como por exemplo uma API.

De uma perspectiva de projeto de integração, implementar o processamento orientado a eventos requer muito menos esforço do que em lotes. Por quê?

-   Embora a Jitterbit ofereça suporte a uma função de agendamento, a maioria dos processos em lote exigem um processo de recolhimento de dados baseado em uma “data da última modificação”, o que requer um *script* customizado para obter a última data em que a operação foi executada, decidir se a execução ocorreu com sucesso, e daí atualizar o repositório de datas e horas. No meio do caminho, você lida com fusos horários de *endpoints* potencialmente diferentes, horário de verão e formatos de data. Não se esqueça: faça *query* apenas de dados mudados por todos os usuários *exceto* o usuário de integração. E, ao migrar para outros ambientes, você precisa pensar em ligar e desligar as agendas de acordo com o plano do projeto. Nenhuma dessas coisas é um enorme desafio, mas é claramente um fardo de desenvolvimento e a responsabilidade do gerenciamento é colocada sobre a camada de integração.

-   Compare o processamento em lotes ao orientado a eventos: a operação executa somente quando é chamada pelo *endpoint*. Sem agendas, sem registros de data e hora, sem fusos horários. A responsabilidade recai claramente sobre o *endpoint*.

-   O principal mecanismo de processamento orientado a eventos do Jitterbit Harmony é a Plataforma de APIs do Harmony. Embora haja um custo de licenciamento mais alto, vale muito a pena.

-   Obviamente, se o *endpoint* não suporta chamar uma API, então o processamento em lote é a sua única opção. Também, o cliente pode relutar em usar uma API se o processamento em lote for uma opção.

Porém também existe a estranha exceção da opção do “lote rápido”, onde o requisito de negócio é mandar os dados para o alvo o mais rápido possível, mas o cliente não quer implementar uma API. A conversa é mais ou menos assim:

> *Jitterbit:* Para o cenário dos pedidos, quando você quer que os pedidos apareçam no ERP?
>
> **Cliente:** O mais rápido possível.
>
> *Jitterbit:* Então a melhor opção são APIs de uso em tempo real.
>
> **Cliente:** Não, eu não quero fazer isso. Não dá para fazer um lote bem rápido?
>
> *Jitterbit*: Quer dizer, verificar a cada 10 minutos se há pedidos novos?
>
> **Cliente:** Não; mais rápido. Qual é o tempo mínimo de uma agenda?
>
> *Jitterbit:* É….. um minuto.
>
> **Cliente:** Ótimo! Então vamos fazer *queries* no sistema de pedidos a cada minuto! Pronto!
>
> *Jitterbit:* Um minuto. Percebe que dessa forma você estará martelando o sistema de pedidos, sendo que na maioria das vezes não haverá dados para processar? Você terá muitos ciclos perdidos, e depois verificar os registros do Jitterbit Harmony vai ser bem chato. Se o seu requisito de negócio realmente é mover dados o mais rápido possível, então você precisa usar uma API. Além disso, existem vários outros benefícios…

E agora o cliente, motivado por essa nova informação, toma a decisão correta e autoriza o uso de uma API. Mas se você não for convincente o suficiente, entre em contato com a nossa equipe de *marketing*; eles saberão o que fazer.

Tome nota das seguintes considerações para usar uma API:

-   Entenda bem os requisitos de processamento máximos da API.

    -   Entenda que a API é chamada quando um usuário muda um registro. Fácil! O *design* é para que a operação seja chamada diretamente e daí atualize o alvo imediatamente.

    -   Mas o que o cliente esqueceu de mencionar para você (e você esqueceu de perguntar) é que quando há uma atualização em massa dos registros, em vez de receber um registro a cada 10 minutos, você recebe 10 mil. A Jitterbit vai fazer a parte dela e iniciar quantas *threads* o servidor conseguir aguentar e enfileirar o restante do tráfego de entrada, para daí começar a atualizar o alvo. Mas isso pode sobrecarregar o sistema alvo.

-   Verifique a saída máxima, e considere a possibilidade de adicionar uma fila JMS, um banco de dados, ou mesmo um arquivo temporário para armazenar os dados da API que entram antes de processá-los no alvo.

-   As APIs são licenciadas independentemente do ambiente. Então se uma API for usada para o desenvolvimento, outra para os testes de qualidade e outra para os ambientes de produção, serão necessárias três licenças de API, não apenas uma.


## Migração

Dependendo do processo do cliente, o projeto terá que ser migrado para um ambiente de teste de qualidade antes dos UATs, ou o teste é feito num ambiente de desenvolvimento e o projeto é depois migrado para um ambiente de produção.

-   Se possível, não migre para o próximo ambiente mais alto até que o projeto esteja quase completo. Uma vez que uma migração acontece, você precisa se lembrar de migrá-los para outros ambientes.

-   Evite fazer mudanças num ambiente “mais alto” para resolver rapidamente um problema, achando que vai sincronizar os ambientes depois. Em vez disso, faça o conserto no ambiente “mais baixo” e depois migre-o. Não há forma infalível de identificar diferenças granulares entre projetos, então é fácil se perder entre as mudanças.


## Testes de Aceitação do Usuário (UATs)

Todos os cenários foram construídos, todos os testes de unidade foram bem-sucedidos e os usuários estão prontos para testar a integração. Hora de soltar os usuários no meio da integração, e agora é que você vai descobrir quais são *realmente* os requisitos!

Essa fase pode ser um processo bastante suave, ou muito intenso. Realmente depende da qualidade dos passos anteriores. Mantenha essas dicas em mente durante a fase dos UATs:

-   Esteja preparado para reagir rápido à medida que os problemas aparecerem. Se você tiver feito bem o seu trabalho, a maioria dos problemas serão relacionados aos dados, não a aspectos técnicos. Então tenha certeza que os SMEs dos *endpoints* estejam de prontidão para fazer a triagem dos problemas.

-   Quando possível, deixe o usuário tomar a frente do processo de diagnóstico e resolução de problemas: reagindo aos alertas, lendo os registros, traçando a lógica da integração. Idealmente, a pessoa que fará este trabalho na produção o fará também durante esta fase.

-   Permaneça atento aos problemas que aparecerem durante os UATs e como são resolvidos. Uma situação frequente é os problemas afetarem os dados dos *endpoints*, e embora o problema da integração seja consertado, os dados não são e aí se tornam um problema recorrente durante os testes.

-   Planeje ter reuniões frequentes com todas as partes interessadas para resolver quaisquer bloqueadores.

-   À medida que o tempo permitir, comece a documentação.

-   Desenvolva seu plano de entrada em produção.

-   No ambiente de produção, faça testes de conexão além de quaisquer outros testes que você possa ou tenha permissão de fazer.


## Pós-Produção e Monitoramento

UATs concluídos! Autorização dos usuários recebida! Hora de acionar esse foguete!

Nesse estágio, a migração final para a produção deverá estar completa. Se você estiver usando agendas, esteja ciente de que você pode migrá-las para a produção e desligá-las no Jitterbit Harmony Management Console. Daí, pode ficar a cargo do cliente ligá-las de volta.

Espere se encontrar com o cliente periodicamente para ter certeza de que as coisas estão correndo bem, e procure se preparar para possíveis perguntas.

Planeje uma reunião de “encerramento” para entregar a documentação do projeto e fazer qualquer transferência final de conhecimento que for necessária.

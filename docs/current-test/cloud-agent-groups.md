[//]: # (Cloud Agent Groups)
[//]: # (This is a translation of Version 39, published on April 26, 2022.)


## Visão Geral

Um Jitterbit Cloud Agent Group consiste de um conjunto de [Jitterbit Harmony Agents](https://success.jitterbit.com/display/DOC/Private+Agents) mantidos e gerenciados pela Jitterbit. Esta opção permite que você execute todas as suas integrações na nuvem com um Agent Group escalável, *multi-tenant* e tolerante a erros.

Dois Cloud Agent Groups estão disponíveis:

-   **Production Cloud Agent Group**: Este grupo está disponível com uma versão do Jitterbit Harmony Agent que está plenamente testada e pronta para produção.

-   **Sandbox Cloud Agent Group**: Este grupo é sempre a próxima versão do Jitterbit Harmony Agent, para a qual o Production Cloud Agent Group será atualizado no futuro. (Normalmente, é a versão do Private Agent incluída no lançamento mais recente da Plataforma Harmony na hora da atualização do Sandbox Cloud Agent Group).

O Sandbox Cloud Agent Group está disponível para testar os seus projetos com uma nova versão do Jitterbit Harmony para garantir que você esteja pronto(a) para a próxima atualização do Production Cloud Agent Group. ***A intenção não é que ele seja um ambiente de teste para os seus projetos antes do "go-live"***—para isso use um [ambiente do Harmony](https://success.jitterbit.com/display/DOC/Environments) - como projetos no Sandbox Cloud Agent, caso eles usem um novo recurso introduzido naquela versão específica, eles não podem ser movidos para o Production Agent Group até que o Production Cloud Agent seja atualizado para a mesma versão.


## Configuração dos Cloud Agent Groups

Os Cloud Agents são configurados usando as [configurações padrão](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf) para um Harmony Private Agent com as seguintes diferenças:

-   A autenticação em sistemas operacionais Windows para bancos de dados não é permitida.

-   O *login* SSH com uso de chaves não é permitido.

-   Apenas *drivers* JDBC são suportados. O acesso para *drivers* ODBC não é permitido.

-   TLS 1.2 é exigido para todas as conexões, tanto com a plataforma Jitterbit Harmony quanto entre o Harmony, os Agents e os *endpoints*. TLS 1.0 e 1.1 não são suportados.

-   Os registros (*logs*) de depuração de operações não são permitidos.

-   Os registros de operações de agentes em um Cloud Agent Group são retidos por 30 dias pelo Jitterbit Harmony. Os registros de atividades podem ser visualizados apenas dentro do Studio ou interface de usuário do Management Console e não podem ser baixados.

-   O limite de tamanho do armazenamento temporário é de 50 GB por arquivo para as versões 10.10 ou superiores dos Cloud Agents.

-   Todos os arquivos temporários são limpos muito rápido; você não pode contar com a presença deles depois que uma operação for executada.

-   Por padrão, o uso de arquivos locais como fontes ou alvos está desabilitado e eles não podem ser usados nos Cloud Agents.

-   Um projeto é limitado a 8 operações em execução por agente em qualquer dado momento.

-   O período de tempo mais longo que uma operação pode ficar em execução (`MaxOperationRuntimeSeconds`) está programado para 21600 segundos (6 horas).

-   O fuso horário usado para as agendas nos Cloud Agents é UTC, a menos que a configuração **Override Schedule Agent Time Zone** esteja habilitada nas [políticas da sua organização](https://success.jitterbit.com/display/DOC/Organizations#Organizations-organization-policies).

-   Um grupo limitado de [plugins Jitterbit](https://success.jitterbit.com/display/DOC/Plugins+Available+in+Jitterbit+Harmony) está disponível para uso com Cloud Agents.

-   Conforme documentado individualmente, certos recursos ou conectores, como o [Conector QuickBooks OAuth 2.0](https://success.jitterbit.com/display/DOC/QuickBooks+Connector) do Design Studio, não estão disponíveis para Cloud Agent Groups.

Caso esta configuração não satisfaça os requisitos do seu projeto, use um [Private Agent](https://success.jitterbit.com/display/DOC/Private+Agents).

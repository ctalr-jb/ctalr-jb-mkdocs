# Segurança Jitterbit

[//]: # (This is a translation of Version 24, published on June 17th, 2022.)


## Visão Geral

O Jitterbit Harmony entrega ferramentas e serviços de integração poderosos por meio da plataforma de integração em nuvem *multi-tenant* da Jitterbit, chamada Jitterbit Harmony. Versões anteriores da Jitterbit exigiam que as organizações fizessem os *deploys* e gerenciassem os *softwares* Jitterbit e projetos de integração em infraestruturas de rede internas ou em nuvens privadas dedicadas. Com o Harmony, a Jitterbit agora pode assumir qualquer uma dessas responsabilidades, ou todas elas.

As seguintes páginas estão incluídas neste tópico:

-   **[*Whitepaper* da Segurança e Arquitetura Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR)**<br/>
    Reveja os detalhes da segurança lógica, física e organizacional da Jitterbit.

-   **[Recursos de Segurança Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Security+Features?showLanguage=pt_BR)**<br/>
    Veja um resumo dos recursos de segurança da nuvem, dos *datacenters* e da rede do Jitterbit Harmony.

-   **[Controles de Senha Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Password+Controls?showLanguage=pt_BR)**<br/>
    Descubra como a Jitterbit controla o acesso à sua organização via administração por meio do Management Console.

-   **[Permissões e Acesso do Jitterbit Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access?showLanguage=pt_BR)**<br/>
    Use uma matriz de permissões de funções organizacionais e níveis de acesso ambientais para determinar quais áreas do Jitterbit Harmony um membro pode acessar.

-   **[Jitterbit Harmony Single Sign-On](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Single+Sign-On?showLanguage=pt_BR)**<br/>
    Como alternativa ao uso de credenciais Harmony, os administradores das organizações podem configurar SAML 2.0 ou OAuth 2.0 para autenticar com vários provedores de identidade.

-   **[Informações sobre *Whitelists*](https://success.jitterbit.com/display/DOC/Whitelist+Information?showLanguage=pt_BR)**<br/>
    Descubra como utilizar uma *whitelist* (lista de permissões) com os [Agents](https://success.jitterbit.com/display/DOC/Agents?showLanguage=pt_BR) e com o [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR).

-   **[Certificação ISO 27001 e ISO 27017](https://success.jitterbit.com/display/DOC/ISO+27001+and+ISO+27017+Certification?showLanguage=pt_BR)**<br/>
    Leia mais sobre as certificações ISO do Information Security Management System (Sistema de Gerenciamento de Segurança da Informação) da Jitterbit.

-   **[Melhores Práticas para Administradores, Construtores de Projeto e Especialistas de Integração](https://success.jitterbit.com/display/DOC/Security+Best+Practices+for+Administrators%2C+Project+Builders%2C+and+Integration+Specialists?showLanguage=pt_BR)**<br/>
    Veja as recomendações e as melhores práticas para segurança.

Os seguintes recursos adicionais relacionados à segurança também estão disponíveis:

-   **[Política de Privacidade da Jitterbit](https://www.jitterbit.com/privacy-policy/)**<br/>
    Informe-se sobre quais dados pessoais a Jitterbit coleta e como eles são usados.

-   **[Trust Site da Jitterbit](https://trust.jitterbit.com/)**<br/>
    Verifique informações em tempo real sobre a performance dos sistemas da Jitterbit por meio do nosso [Trust site](https://trust.jitterbit.com/). Você também pode se [inscrever para receber notificações](https://success.jitterbit.com/display/DOC/System+Status+Notifications?showLanguage=pt_BR) por e-mail, mensagem de texto, pelo Slack ou por *webhook* para ser avisado(a) de quaisquer mudanças no *status* do sistema, manutenções ou quedas.

-   **[Segurança de APIs da Jitterbit](https://success.jitterbit.com/display/DOC/Harmony+API+Security?showLanguage=pt_BR)**<br/>
    Aprenda a aplicar vários níveis de segurança para usar com a plataforma de APIs do Jitterbit Harmony.


## Perguntas Frequentes

**Pergunta:** *Quais auditorias acontecem no Jitterbit Harmony Portal?*

**Resposta:** A auditoria de *deploys* (implantações) está disponível. A Jitterbit possui um mecanismo de registros extremamente robusto que expõe tudo que ocorre no caminho da integração. Estes registros podem ser inspecionados livremente por usuários autorizados ou usados por uma operação Jitterbit para salientar o que for de interesse.
<br/>
<br/>

**Pergunta:** *Vocês oferecem criptografia de mensagens?*

**Resposta:** Sim, a Jitterbit oferece suporte à two-way SSL. A Jitterbit também suporta AES (Padrão de Criptografia Avançada). Além disso, a Jitterbit tem um *plugin* de criptografia PGP que pode ser usado para criptografar mensagens.
<br/>
<br/>

**Pergunta:** *É oferecida segurança em nível de transporte com validação de certificados?*

**Resposta:** Sim. Isto pode ser realizado via SSL.
<br/>
<br/>

**Pergunta:** *A autenticação de usuários pode ser feita usando autorização de domínios, ou ela deve ser feita por meio do banco de dados de usuários interno?*

**Resposta:** A Jitterbit oferece autorização de domínios privados para arquivo fonte/alvo e para acesso a bancos de dados. A autenticação de usuários pode ser feita via autorização de domínios para acessar *endpoints* de bancos de dados. A autorização de domínios não pode ser usada para acessar Jitterbit Private Agents. É possível fazer uma transformação LDAP para desabilitar usuários, mas a senha não pode ser determinada a partir da operação se ela for "create" (nós usamos nossa senha privada).
<br/>
<br/>

**Pergunta:** *Quais controles de senha estão em efeito?*

**Resposta**: As senhas do Jitterbit Harmony são controladas dentro da página **Organizations** (Organizações) do Management Console. Os recursos de controle de senha são configurados para cada organização separadamente. Apenas um(a) Administrador(a) da organização tem acesso para revisar os controles de senha. Consulte a página [Organizações](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR) para ver detalhes específicos sobre os controles de senha.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**NOTA:** Controles de senha para organizações usando [*single sign-on (SSO)*](https://success.jitterbit.com/display/DOC/Single+Sign-On?showLanguage=pt_BR) são controlados por meio do Identity Provider.

</div>

</div>

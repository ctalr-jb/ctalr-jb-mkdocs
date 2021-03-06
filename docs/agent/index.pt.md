# Jitterbit Harmony Agent

[//]: # (This is a translation of Version 14, published on January 26, 2022.)

## Visão Geral

Quando você executa uma integração, a conectividade com os seus dados é
possibilitada por meio dos *Jitterbit Harmony Agents* (ou seja, Agentes
do Jitterbit Harmony) que você configurou. Os Agents (mesmo que só haja
um) são agrupados em um Agent Group (Grupo de Agentes). Você escolhe o
Agent Group que quer usar no <a href="https://login.jitterbit.com/" class="external-link"
rel="nofollow">Management Console</a>, conforme
descrito na página [Agents \> Agent Groups](https://success.jitterbit.com/display/DOC/Agents+%3E+Agent+Groups?showLanguage=pt_BR).

Existem dois tipos de Jitterbit Harmony Agent Groups: *Cloud* (Nuvem) e
*Private* (Privado).

## Cloud Agent Groups

Um Jitterbit Cloud Agent Group consiste de um grupo de agentes mantidos
e gerenciados pela Jitterbit. Esta opção permite que você execute todas
as suas integrações na nuvem com um Agent Group que é escalável,
*multi-tenant* e tolerante a falhas. O caso de uso mais comum é uma
integração nuvem-para-nuvem.

Para mais detalhes, veja o artigo [Cloud Agent Groups](https://success.jitterbit.com/display/DOC/Cloud+Agent+Groups?showLanguage=pt_BR).

## Private Agent Groups

Você também pode fornecer e gerenciar os seus próprios Private Agent(s)
e Agent Groups. Eles podem usar os seus próprios servidores, estar
dentro de um *firewall* corporativo ou estar localizados em nuvens
privadas virtuais. Esta opção permite que você escolha onde o seu
ambiente de tempo de execução de integração opera e também que você
controle em qual rede seus dados transitam e residem. Os Private Agents
permitem que você use arquivos locais como fontes ou alvos, adicione
*plugins* customizados ou use *drivers* ODBC. Estas opções não estão
disponíveis com os Cloud Agents.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Os Private Agents eram antes chamados de Local Agents.

</div>

</div>

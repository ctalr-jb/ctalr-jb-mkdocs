# Componentes de Projeto

[//]: # (This is a translation of Version 7, published on November 19, 2020.)

## Visão Geral

Componentes de projeto são as peças individuais de um projeto. Alguns componentes, incluindo atividades, *scripts* e *transformations*, podem ser adicionados a operações que são executadas como uma sequência de passos. Outros componentes podem ser usados em apoio a tais operações, tais como variáveis, agendas, *schemas*, notificações e *plugins*. As operações em si também são componentes de projeto.

Para mais informações sobre como configurar cada componente, consulte estas páginas:

-   **Workflows**: [Criação e Design de Workflows](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design?showLanguage=pt_BR)

-   **Operações**: [Criação e Configuração de Operações](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR) e [Configurações de Operações](https://success.jitterbit.com/display/CS/Operation+Settings?showLanguage=pt_BR)

-   **Conexões e Atividades**: [Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR), para a criação e configuração de conexões e atividades por tipo de *endpoint*

-   ***Transformations***: [Criação e Configuração de *Transformations*](https://success.jitterbit.com/display/CS/Transformation+Creation+and+Configuration?showLanguage=pt_BR)

-   ***Scripts***: [Tipos e Criação de *Scripts*](https://success.jitterbit.com/display/CS/Script+Types+and+Creation?showLanguage=pt_BR)

-   ***Schemas***: [*Schemas*](https://success.jitterbit.com/display/CS/Schemas?showLanguage=pt_BR), para *schemas* criados em um *transformation* vs. *schemas* criados numa atividade

-   **Variáveis**: [Variáveis](https://success.jitterbit.com/display/CS/Variables?showLanguage=pt_BR), para informações sobre a criação (se necessário) e busca de variáveis Jitterbit locais, globais e de projeto

-   **Notificações**: [Notificações](https://success.jitterbit.com/display/CS/Notifications?showLanguage=pt_BR), para informações sobre a criação e configuração de mensagens de e-mail

-   **Agendas**: [Agendas de Operação](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR), para informações sobre a criação e aplicação de agendas a operações

-   ***Plugins***: [*Plugins*](https://success.jitterbit.com/display/CS/Plugins?showLanguage=pt_BR), para informações sobre o uso de *plugins* em *scripts* e a aplicação de *plugins* a atividades

Dentro da documentação do Cloud Studio, detalhes sobre cada componente de projeto são cobertos separadamente por tópico. No entanto, muitas das ações que você pode tomar com componentes de projeto têm muito em comum. Este tópico abrange os pontos em comum entre componentes e direciona você para documentações mais específicas quando isso for aplicável. As seguintes páginas estão inclusas neste tópico:

-   [**Implantação de Componentes**](https://success.jitterbit.com/display/CS/Component+Deployment?showLanguage=pt_BR)<br/>
    Componentes e seus componentes dependentes podem ser implantados independentemente do resto do projeto. Com uma implantação configurável, você também pode escolher a dedo quais componentes de projeto implantar.

-   [**Dependências, Exclusão e Remoção de Componentes**](https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR)<br/>
    Ver dependências é uma forma de ver todos os componentes em um projeto que são dependentes uns dos outros. Componentes que são dependentes de outro componente devem ter suas dependências removidas antes de poderem ser deletados. Em vez de deletar componentes usados como etapas de operação de um projeto, você também pode removê-los de ser usados numa operação sem deletá-los.

-   [**Reuso de Componentes**](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR)<br/>
    Componentes podem ser reusados através de várias referências ao mesmo componente ou mediante a criação de uma cópia das configurações de um componente existente para criar um componente novo e independente.

-   [**Validade de Componentes**](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR)<br/>
    Componentes devem ser válidos para serem implantados. Esta página explica como identificar componentes inválidos e ver os erros de validação associados a eles, e também como resolver erros de validação.

-   [**Grupos de Componentes**](https://success.jitterbit.com/display/CS/Component+Groups?showLanguage=pt_BR)<br/>
    Componentes de projeto podem ser agrupados em categorias customizadas, conhecidas como grupos, para ajudar a organizar um projeto. Componentes de projeto podem pertencer a vários grupos.

# Workflows

[//]: # (This is a translation of Version 3, published on November 17, 2020.)

## Visão Geral

Um workflow é uma coleção de operações que é usado como ferramenta para ajudar a segregar diferentes partes de um projeto. Agrupando operações num workflow, você pode achar mais conveniente organizar os fluxos de processo de forma lógica.

Os workflows não podem ser executados; apenas as operações dentro deles podem ser executadas. Se um workflow estiver configurado de tal forma que uma operação cause a execução em cascata de todas as outras operações num workflow, você pode efetivamente executar todas as operações de um workflow.

Você também pode executar operações individuais dentro dos workflows, o que pode levar à execução de outras operações no mesmo ou em outros workflows. Isto é, se alguma operação estiver acima de outra(s) numa cadeia de operações, dentro ou fora do workflow, as operações abaixo na cadeia serão executadas como consequência. Dessa forma, você pode efetivamente executar todas as operações dentro de um projeto.

As seguintes páginas estão inclusas neste tópico:

-   [**Criação e** ***Design*** **de Workflows**](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design)<br/>
    Esta página mostra como criar, renomear, reordenar e fazer o *design* de workflows.

-   [**Implantação de Workflows**](https://success.jitterbit.com/display/CS/Workflow+Deployment)<br/>
    Esta página descreve como implantar workflows ou componentes de projeto selecionados na nuvem do Jitterbit Harmony. Uma vez que todos os componentes dos quais uma operação é dependente estão implantados, tal operação pode ser executada.

-   [**Dependências e Exclusão de Workflows**](https://success.jitterbit.com/display/CS/Workflow+Dependencies+and+Deletion)<br/>
    Visualizar as dependências de um workflow exibe os outros componentes de projeto dos quais o workflow depende. Visto que componentes de projeto não podem ser dependentes de workflows, workflows podem ser deletados sem que haja preocupação com dependências.

-   [**Validade de Workflows**](https://success.jitterbit.com/display/CS/Workflow+Validity)<br/>
    Workflows devem ser válidos para poderem ser implantados. Esta página descreve como identificar workflows inválidos e visualizar os erros de validação associados a eles, assim como a maneira de resolver erros de validação.

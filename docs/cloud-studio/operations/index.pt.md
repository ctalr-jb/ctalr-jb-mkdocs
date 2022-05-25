# Operações
[//]: # (This is a translation of Version 3, published on November 16, 2020.)


## Visão Geral

Uma operação é a menor unidade dentro de um workflow que é executada independentemente em um agente e registrada pelo Harmony (hora de início e fim, sucesso, falha, erros, arquivos de registro de depuração, etc.). Operações são usadas para definir o que uma integração deve fazer e quando isso deve ser feito.

Uma operação consiste de pelo menos uma etapa de operação, e muitas vezes contém várias etapas de operações. As etapas de operação são os componentes individuais que compõem uma operação e são representadas visualmente por blocos no design canvas, criados através da adição de atividades, *scripts* ou *transformations* na operação.

As operações devem seguir um padrão de operação válido para serem consideradas válidas. Combinações que não são permitidas em uma única operação podem ser funcionalmente possíveis através do encadeamento de várias operações usando ações de operação.

As seguintes páginas estão inclusas neste tópico:

- [**Criação e Configuração de Operações**](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR)<br/>
  Depois de criar um workflow, você cria operações adicionando etapas de operação. Esta página explica as partes de uma operação, daí aborda como adicionar etapas às operações, acessar as opções do menu, renomear operações, expandir/reduzir operações, reordenar operações, bem como remover, reusar ou mover etapas de operação.

- [**Configurações de Operação**](https://success.jitterbit.com/display/CS/Operation+Settings?showLanguage=pt_BR)<br/>
  Depois que uma operação é criada, você pode configurá-la. A tela de configurações de operação inclui três abas, descritas separadamente em [Agendas de Operação](https://success.jitterbit.com/display/CS/Operation+Schedules), [Ações de Operação](https://success.jitterbit.com/display/CS/Operation+Actions) e [Opções de Operação](https://success.jitterbit.com/display/CS/Operation+Options).

- [**Implantação e Execução de Operações**](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR)<br/>
  Esta página descreve como implantar operações ou componentes de projeto selecionados para a nuvem do Jitterbit Harmony. Uma vez que todos os componentes dos quais uma operação depende estejam implantados, ela pode ser executada. Para a sua conveniência, componentes dependentes são automaticamente implantados quando se executa manualmente uma operação.

- [**Registros de Operação**](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR)<br/>
  Depois de você ter implantado e executado operações dentro de um projeto, você pode visualizar os registros de operação diretamente dentro do Cloud Studio. Os registros também podem ser vistos por meio da página [Atividades](https://success.jitterbit.com/display/DOC/Activities) do [Management Console](https://success.jitterbit.com/display/DOC/Management+Console) (Console de Gerenciamento).

- [**Dependências, Exclusão e Remoção de Operações**](https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR)<br/>
  Ver as dependências de uma operação lista os outros componentes de projeto dos quais a operação depende. Se outros componentes forem dependentes da operação, tais dependências devem ser removidas antes de a operação poder ser deletada. Além disso, operações que são contidas dentro de um workflow podem ser removidas do workflow.

- [**Reuso de Operações**](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR)<br/>
  Operações podem ser reusadas através de várias referências à mesma operação ou mediante a criação de uma cópia de uma configuração de operação existente para criar um componente novo e independente.

- [**Validade de Operações**](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR)<br/>
  Operações devem ser válidas para poderem ser implantadas. Esta página abrange como identificar operações inválidas e como ver os erros de validação associados a elas, bem como a forma de resolver erros de validação. Exemplos de arranjos de operação comuns também são fornecidos.

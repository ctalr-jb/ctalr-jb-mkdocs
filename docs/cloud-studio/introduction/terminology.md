[//]: # (Cloud Studio Terminology)

## Introduction

This page defines important technical terms and concepts used in [Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio).


## <span id="CloudStudioTerminology-project" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Project

A [project](https://success.jitterbit.com/display/CS/Projects) is a collection of one or more [workflows](#CloudStudioTerminology-workflow) that
comprise and execute an integration use case. A project contains [operations](#CloudStudioTerminology-operation) as
well as other [project components](#CloudStudioTerminology-project-component) that may be part of an operation or
used to support operations. A project can be shared, archived, or redistributed by exporting and importing the
project as a JSON file.


## <span id="CloudStudioTerminology-project-component" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Project Component

[Project components](https://success.jitterbit.com/display/CS/Project+Components) are the discrete building blocks of a project. Some components,
including [activities](#CloudStudioTerminology-activities),
[transformations](#CloudStudioTerminology-transformation), and [scripts](#CloudStudioTerminology-scripts), can be
added to [operations](#CloudStudioTerminology-operation) and executed as a sequence of steps. Other components can
be used in support of those operations, such as [variables](https://success.jitterbit.com/display/CS/Variables),
[schedules](https://success.jitterbit.com/display/CS/Operation+Schedules), [file schemas](https://success.jitterbit.com/display/CS/Schemas),
[notifications](https://success.jitterbit.com/display/CS/Notifications), and [plugins](https://success.jitterbit.com/display/CS/Plugins). Operations themselves are also
project components.


## <span id="CloudStudioTerminology-dependencies" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Dependencies

Some project components may depend on other components to function properly. Two distinct phrases are used to
discuss dependencies: *dependent on* and *dependency of*. In the following examples, Component A is ***dependent on***
Component B. Component B is ***a dependency of*** Component A:

-   **Dependent on:** If a component is dependent on another component,
    it needs that component in order to function properly. A component
    that is dependent on another component cannot stand alone without
    that component. When Component A needs Component B in order to
    execute successfully, Component A is dependent on Component B.
    Another way to say this is that Component A depends on Component B.

-   **Dependency of:** If a component is a dependency of another
    component, it is needed by the first component in order for the
    first component to function properly. A component that is a
    dependency of another component is the component that is needed by
    another. When Component A needs Component B in order to execute
    successfully, Component B is a dependency of Component A.


## <span id="CloudStudioTerminology-workflow" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Workflow

A workflow is a collection of [operations](#CloudStudioTerminology-operation) used as tool to help segregate
different parts of the project for the convenience of the user.

Workflows are created from along the top of the [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas):

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/workflow-tab_new.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/workflow-tab_new.png" /></span>

When you create a new workflow, a blank canvas opens, ready for you to design the workflow by creating operations.

Workflows cannot be executed; only the operations within them can be executed. If the workflow is configured such
that one operation leads to the chain execution of all the other operations in a workflow, you can effectively run
all operations in the workflow.

You can also execute individual operations within workflows, which may lead to execution of operations in the same
or other workflows. That is, if any operations are upstream of other operations in an operation chain, within or
outside the workflow, the downstream operations will be kicked off accordingly. In this way, you can effectively run
all operations within a project.


## <span id="CloudStudioTerminology-operation" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operation

An operation is the smallest unit within a [workflow](#CloudStudioTerminology-workflow) that is independently
executed on an agent and recorded by Harmony (start and run time, success, failure, errors, debug log files, etc.).
Operations are used to define what an integration should do and when it should be done.

An operation consists of at least one operation step, and often contains multiple operation steps consisting of
[activities](#CloudStudioTerminology-activities), [transformations](#CloudStudioTerminology-transformation), or
[scripts](#CloudStudioTerminology-scripts). Operation steps are the discrete components that make up an operation
and are visually represented within an operation on the design canvas:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation.png" /></span>

Operations must follow a [valid operation pattern](https://success.jitterbit.com/display/CS/Operation+Validity). Combinations that are not
allowed in a single operation may be functionally possible by chaining together multiple operations using operation
actions. Once they are created, operations can be executed manually, triggered by an API, or scheduled.


## <span id="CloudStudioTerminology-connectivity" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="CloudStudioTerminology-connectors" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="CloudStudioTerminology-connections" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="CloudStudioTerminology-activities" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="CloudStudioTerminology-endpoints" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Connectivity

Connectivity resources are accessed within the **Connectivity** tab of the [design component
palette](https://success.jitterbit.com/display/CS/Design+Component+Palette). Within this tab, [connectors](https://success.jitterbit.com/display/CS/Connectors) are first
configured to create connections. Activities associated with those connections can then be instantiated using the
activity types and configured as sources or targets in a project. An endpoint refers to a specific connection and
its activities.

-   **Connectors:** A connector provides the interface for entering
    user-provided input such as credentials to create a connection. The

    **Connectors** filter shows the available connectors. You can also
    create [custom connectors](https://success.jitterbit.com/display/CS/Custom+Connector).

-   **Connections:** A connection is a component that is created from a
    connector and provides access to a data resource.
    The **Endpoints** filter shows the available connections.

-   **Activities:** An activity is a component that is created from a
    connection and configured to interact with an endpoint. The
    **Endpoints** filter shows the connections, which can be clicked to
    reveal the activity types. The activity types are used to create an
    instance of an activity in a project. Activity instances can act as
    sources (providing data) or targets (receiving data).

-   **Endpoints:** An endpoint refers to a specific connection and its
    activities.

<span class="confluence-embedded-file-wrapper conf-macro output-inline"
hasbody="true" macro-name="multiexcerpt"><img
src="https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png" /></span>


## <span id="CloudStudioTerminology-scripts" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Scripts

[Scripts](https://success.jitterbit.com/display/CS/Scripts), written in either Jitterbit Script or JavaScript, provide the flexibility and
power to transform data, perform calculations, or perform logic validation beyond simple field mapping.

Scripts can be used in multiple places, both within the [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas) as steps of an
[operation](#CloudStudioTerminology-operation), as well as within transformations to apply specified logic or
conditions to the data.


## <span id="CloudStudioTerminology-variables" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Variables

[Variables](https://success.jitterbit.com/display/CS/Variables) are used throughout a project to make integrations more flexible and dynamic.
They allow for the dynamic configuration of endpoints, support passing of data between
[operations](#CloudStudioTerminology-operation), and are used in transformation scripts to drive detailed
integration logic.

Jitterbit Harmony supports multiple types of variables with varying scope:

-   **Local Variables:** Limited to the current script.

-   **Global Variables:** Available to current and downstream scripts.

-   **Project Variables:** Available across all project workflows, and
    accessible outside of Cloud Studio through the Management Console
    and Citizen Integrator.

-   **Jitterbit Variables:** Predefined by Harmony and available to
    current and downstream scripts.

In addition, filename keywords can be used to generate unique filenames for configurable fields that take filenames
as input.

Integration best practice suggests that you use the variable that is most limited in scope, in order to minimize the
risk of changing variable values across multiple components in the project.


## <span id="CloudStudioTerminology-transformation" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Transformation

A [transformation](https://success.jitterbit.com/display/CS/Transformations) is a project component that is used as a step in an operation to map
or *transform* inputs to a resulting output by moving data, cleaning data, or applying business logic.

A transformation consists of source and target schemas that have been defined in the transformation and the
transformation mapping that generates the output. A source schema is required only when an adjacent source activity
provides input data that needs to be transformed. A target schema is always required.

Source and target schemas can be either defined within the transformation or provided by an adjacent activity, with
schemas defined within the transformation taking precedence. Schemas provided by adjacent activities are not part of
the transformation. In addition, a transformation does not include the input or output data itself.

The configuration of a transformation can take place in either mapping mode or script mode.

In addition, while configuring a transformation, you should also be familiar with these terms:

-   **Mapping:** A transformation mapping consists of target fields or
    nodes and their corresponding scripts. These scripts may contain
    references to source fields or nodes or to project components, use
    functions, or contain other valid script logic. A mapping does not
    include target fields that are not mapped.

-   **Condition:** A condition, as used in a transformation, is a script
    applied on the target to determine if the source record being
    processed should be output to the target. If the script evaluates to
    true, then the record is output. If the script result evaluates to
    false, then the record is skipped.

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/transformation/script-mode/condition_if.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/transformation/script-mode/condition_if.png" /></span>

-   **Loop Node:** A loop node is a source or target node with repeating
    data values, such as line items in an invoice or a set of customer
    records. When loop node fields are mapped, a solid
    black iterator line automatically appears, indicating that the
    transformation process will loop through the source data set. A
    transformation can have zero or more iterator lines.

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/loop-node.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/loop-node.png" /></span>


## <span id="CloudStudioTerminology-recipes" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Integration Recipe

A [Cloud Studio integration recipe](https://success.jitterbit.com/display/CS/Cloud+Studio+Integration+Recipes), available through [Jitterbit
Marketplace](https://success.jitterbit.com/display/DOC/Marketplace), is a single, pre-built integration project that moves data in one direction
between objects across two applications or systems. Integration recipes are available to all Jitterbit Harmony
subscribers.


## <span id="CloudStudioTerminology-templates" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Process Template

A [Cloud Studio process template](https://success.jitterbit.com/display/CS/Cloud+Studio+Process+Templates), available through [Jitterbit
Marketplace](https://success.jitterbit.com/display/DOC/Marketplace), is a group of pre-built integration use cases that accelerates the execution
of a specific business process using numerous objects across multiple applications or systems.

Process templates are designed to reduce the time to deployment by 50 to 80 percent and can be either
self-implemented, delivered by Jitterbit Professional Services, or delivered by an implementation partner.

A process template consists of one or more projects using multiple endpoints, may include customization files, and
has its own documentation in PDF format. After the projects are created, you must enter appropriate values in the
project variables that set credentials and other information for the project in each project individually.

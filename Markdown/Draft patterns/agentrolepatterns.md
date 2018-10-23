::: {#skip-link}
[Skip to main content](#main-content){.element-invisible
.element-focusable}
:::

::: {#page-wrapper}
::: {#page}
::: {#header .with-secondary-menu}
::: {.section .clearfix}
[![Home](https://patterns.promsns.org/sites/all/themes/bartik_rda/rda_square.png)](/ "Home"){#logo}

::: {#name-and-slogan}
::: {#site-name}
**[Patterns DB](/ "Home")**
:::
:::

::: {#main-menu .navigation}
Main menu {#main-menu .element-invisible}
---------

-   [Home](/)
-   [Use Cases](/usecases)
-   [Patterns](/patterns)
-   [Implementations](/implementations)
-   [Actors](/actors)
-   [Initiatives](/initiatives)
-   [About](/about)
-   [Contact](/contact)
:::

::: {#secondary-menu .navigation}
Secondary menu {#secondary-menu .element-invisible}
--------------

-   [My account](/user)
-   [Log out](/user/logout)
:::
:::
:::

::: {#main-wrapper .clearfix}
::: {#main .clearfix}
::: {#breadcrumb}
You are here {#you-are-here .element-invisible}
------------

::: {.breadcrumb}
[Home](/)
:::
:::

::: {#sidebar-first .column .sidebar}
::: {.section}
::: {.region .region-sidebar-first}
::: {#block-system-navigation .block .block-system .block-menu}
Navigation
----------

::: {.content}
-   [Add content](/node/add)
:::
:::
:::
:::
:::

::: {#content .column}
::: {.section}
[]{#main-content}

::: {.tabs}
:::

::: {.region .region-content}
::: {#block-system-main .block .block-system}
::: {.content}
::: {#node-96 .node .node-patterns .node-promoted .node-full .clearfix about="/content/agent-role-patterns" typeof="sioc:Item foaf:Document"}
[]{.rdf-meta .element-hidden property="dc:title"
content="Agent Role Patterns"}[]{.rdf-meta .element-hidden
property="sioc:num_replies" content="0" datatype="xsd:integer"}

::: {.meta .submitted}
[Submitted by [admin]{.username lang="" about="/user/1"
typeof="sioc:UserAccount" property="foaf:name" datatype=""} on Mon,
04/30/2018 - 07:41]{property="dc:date dc:created"
content="2018-04-30T07:41:38-05:00" datatype="xsd:dateTime"
rel="sioc:has_creator"}
:::

::: {.content .clearfix}
::: {.field .field-name-field-contributor .field-type-text .field-label-above}
::: {.field-label}
Contributor: 
:::

::: {.field-items}
::: {.field-item .even}
Dave Dubin
:::
:::
:::

::: {.field .field-name-body .field-type-text-with-summary .field-label-hidden}
::: {.field-items}
::: {.field-item .even property="content:encoded"}
Introduction
------------

There are several ways to document the roles agents play in a
transaction. The most important factor to consider in choosing from
among these approaches is the stakeholder communities with which you
plan to share the provenance, and the ontological commitments that
govern the vocabularies used by those communities.

The running example illustrating the patterns described below will be a
specimen loan scenario, in which an organization loans a physical
specimen to a researcher for use in a study. We wish to document the
lending organization\'s role as a lender in this transaction. In all
three of the patterns the loan itself is understood to be an event, and
we will identify the
[\"Resources\"](http://dictionary.casrai.org/Contributor_Roles/Resources)
taxon from the [CRediT Contributor Roles
Taxonomy](http://docs.casrai.org/CRediT).

Patterns
--------

### Pattern 1: roles as shared social object instances

![](http://patterns.promsns.org/sites/default/files/Platonistic_0.svg#overlay-context=pattern/63){width="500px"}

The first approach for documenting agent roles is to understand the role
as one instance of a class of social objects. This pattern is consistent
with the treatment of roles in the PROV data model and vocabulary.

![](http://patterns.promsns.org/sites/default/files/AgentRolePROV.svg){width="500px"}

Roles in the PROV data model are attributes of the *association* between
an agent and an event, but since RDF admits only binary relationships,
we reify the association as a vertex (the assignment of responsibility)
as well as an edge (\"was associated with\"). The important thing to
note about this pattern is that the agent\'s role is a *particular,*
i.e., an instance of a Role class. A different agent participating in a
different transaction might play exactly the same role, using the same
identifier for the resources role. For example, some other lening agency
could play the very same resources role in the context of other loan
events.

### Pattern 2: roles as a common class identity

Many communities use vocabularies based in BFO, the Basic Formal
Ontology, which has an Aristotelian characterization of roles. On this
view, roles inhere within the agents that assume them.

![](http://patterns.promsns.org/sites/default/files/Aristotelian.svg#overlay-context=pattern/63){width="500px"}

We illustrate this pattern using properties from the VIVO-ISF
vocabulary, which takes BFO as a basis. The **Resources Role** in this
example is not an instance or particular, but a *class.* That is because
no role instance can inhere within two different agents. Two agent roles
may have the same *class identity,* but not the same *individual
identity.*

![](http://patterns.promsns.org/sites/default/files/AgentRoleVIVO.svg){width="500px"}

### Pattern 3: contingent subclasses

The last example illustrates a third way we can represent contributor
roles: as contingent agent subclasses. With this approach, an agent\'s
participation in an event of a particular type licenses the deduction
that it has played a particular role. But rather than reifying the role
itself, we represent the agent as an instance of a role-specific
subclass.

![](http://patterns.promsns.org/sites/default/files/AgentClass.svg){width="500px"}

In the running example, being a **Resource Provider** is understood as a
class identity for agents that loan. This class identity is deduced
(dashed edge) from the agent\'s participation in a **Resources
Provision** event. With this pattern, the participation that licenses
this inference is not directly associated with the triggering event (as
it was in the realization of the BFO role).

![](http://patterns.promsns.org/sites/default/files/AgentRoleContingent2.svg){width="500px"}

Summary
-------

As stated earlier, one\'s choice from among these patterns should be
justified based on which stakeholder communities one wishes to cooperate
with. But it\'s not always a matter of chosing one pattern over another:
note that in the running example the bare facts are the same, only the
interpretations differ. The same database record documenting these facts
could be serialized and published according to any or all three of these
patterns, as needed.
:::
:::
:::

::: {.field .field-name-field-svg-image .field-type-file .field-label-above}
::: {.field-label}
SVG Image: 
:::

::: {.field-items}
::: {.field-item .even}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[AgentClass.svg](https://patterns.promsns.org/sites/default/files/AgentClass.svg)]{.file}
:::

::: {.field-item .odd}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[Aristotelian.svg](https://patterns.promsns.org/sites/default/files/Aristotelian.svg)]{.file}
:::

::: {.field-item .even}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[Platonistic.svg](https://patterns.promsns.org/sites/default/files/Platonistic.svg)]{.file}
:::
:::
:::
:::
:::
:::
:::
:::
:::
:::
:::
:::

::: {#footer-wrapper}
::: {.section}
::: {#footer .clearfix}
::: {.region .region-footer}
::: {#block-system-powered-by .block .block-system}
::: {.content}
Powered by [Drupal](https://www.drupal.org)
:::
:::
:::
:::
:::
:::
:::
:::

::: {.region .region-page-bottom}
:::

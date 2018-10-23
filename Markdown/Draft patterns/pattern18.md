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
::: {#node-94 .node .node-patterns .node-promoted .node-full .clearfix about="/pattern/18" typeof="sioc:Item foaf:Document"}
[]{.rdf-meta .element-hidden property="dc:title"
content="A basic data processing model"}[]{.rdf-meta .element-hidden
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
Nicholas Car
:::
:::
:::

::: {.field .field-name-body .field-type-text-with-summary .field-label-hidden}
::: {.field-items}
::: {.field-item .even property="content:encoded"}
Introduction
------------

Many organisations want a template for how to describe, in PROV-O terms,
data processing event. They understand the benefits of using a
graph-based modelling system like PROV-O but need something simpler than
the open-world assumption of OWL to implement, perhaps on top of legacy
metadata systems such as catalogues.

Here is a simple PROV-O template that relates the fundamental aspects of
a processing event such as its timing, inputs, outputs and causative
agents. Use of the template will indicate what items about a data
processing event should be recorded and how they should be related,
according to PROV-O.

A basic template
----------------

Data and other things are *used* within a processing event (*used* by an
*Activity*) to produce more data (an *Entity*). The output *Entity*
*wasGeneratedBy* the processing *Activity* and the *Activity* was
conducted by (*wasAssociatedWith*) an *Agent*: a person or a system. The
figure below shows this basic template.

![](https://patterns.promsns.org/sites/default/files/Pattern_18_a.svg){width="500px"}

The process may be something manual (\'columnate data in Excel\') or
something automatic (\'extract a geographic subset using a subsetting
query\') but, regardless, the particulars of it can be described in a
*Plan* input to the *Activity*, see [Pattern
12](http://patterns.promsns.org/pattern/12). It may be important to
record additional configuration required to usefully describe the
situation in which the processing event operated. Such config should be
recorded in additional *Entities* *used* by the *Activity*.

Often data processing is conducted by a machine, perhaps a
supercomputer, as directed by a person. This is indicated by the *Agent*
running the process (*wasAssocicatedWith* it) having *acetedOnBehalfOf*
another *Agent*.
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
[Pattern\_18\_a.svg](https://patterns.promsns.org/sites/default/files/Pattern_18_a.svg)]{.file}
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

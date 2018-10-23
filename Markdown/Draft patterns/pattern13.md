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
::: {#node-110 .node .node-patterns .node-promoted .node-full .clearfix about="/pattern/13" typeof="sioc:Item foaf:Document"}
[]{.rdf-meta .element-hidden property="dc:title"
content="Describing activities' actions"}[]{.rdf-meta .element-hidden
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

Often it is important to describe what happened within an activity, such
as a processing event.

### Pattern 13.1: Use of specialised *Activity*

We can make a special kind of PROV-O\'s *Activity* class and publish
information about it.

Entity B was derived from Entity A via a specialised type of *Activity*
which, within the context of this domain, some information is known.
Example in the figure below: Entity A is an uncompressed sound file,
Entity B is a frequency spectrum of that sound. The Specialised Activity
X is a Fourier Transform. The particulars of the Fourier Transform must
be published by the recorded of this provenance. Regular *Activity*
information about the Fourier Transform, such as start and stop times,
are indicated, as per a normal *Activity*.

![](https://patterns.promsns.org/sites/default/files/Pattern_13_a.svg){width="500px"}

#### Pros

The positive aspect of this pattern is that, if details of the
Specialised Activity class are published, then this pattern is a quick
way of associating information with an event.

#### Cons

A problem with this pattern is that in order to reuse the Specialised
Activity definition, it must be published as a definitional resource (an
ontology specialising PROV-O). This then requires technical know-how and
additional resource maintenance on behalf of the provenance publisher.
If, to avoid this additional effort, all the information about the
Specialised Activity, i.e. its class definition, is published directly
in the provenance information, then reusing it will be difficult since
provenance documents are inherently associated with a particular event -
the provenance they are recording - and are thus best suited to
containing instances of classes, not class definitions.

### Antipattern: Annotation properties

There is a temptation to record simple descriptions of an *Activity*
using annotation properties. Example: Entity A is an uncompressed sound
file, Entity B is a frequency spectrum of that sound and the *Activity*
used to generate B from A is shown as a regular *Activity* with an
rdfs:comment property of text stating \"Fourier Transform\".

![](https://patterns.promsns.org/sites/default/files/Pattern_13_b.svg){width="500px"}

#### Cons

This is not machine readable as it does not allow for sophisticated
descriptions of the activity other than with lots of text. Reuse of the
*Activity* (as a class) is not possible. Interpreting the annotation (is
refs:comment or act:abstract or other used?) requires knowledge of OWL
outside PROV-O.

### Pattern 13.2: Use of *Plan*, as per PROV-O

PROV-O contains a *Plan* which is \"an entity that represents a set of
actions or steps intended by one or more agents to achieve some goals\".

The figure below (top part) gives the general pattern for associating
*Plans* with *Activities*, as per PROV-O, and below that the figure
shows an example of this pattern for the Fourier Transform scenario
given above. If textual information is usefully associated with this
*Plan* then a PROV-O *value* property should be used.

![](https://patterns.promsns.org/sites/default/files/Pattern_13_c.svg){height="450px"}

#### Pro

Compared with the Antipattern described above, organisations are much
more easily able to publish *Entities* (including *Plans*) given the
widespread use of catalogues, software repositories and so on. It\'s
therefore easier to publish a *Plan* which describes actions in an
*Activity* independently from any provenance bundle that includes a
reference to that *Plan*.

#### Con

This is a slightly complex graph to relate simple information. See the
Pattern below for a simplification.

### Pattern 13.3: Simplified use of *Plan*

This pattern is a simplified version of Pattern 13.2 above where the
*Plan* is *used* by the *Activity*. This is easier to represent (no
*Association* object is required) and the role that the *Plan* plays -
informing the *Activity*\'s actions - is still understandable by the
very definition of the *Plan* class in PROV-O.

![](https://patterns.promsns.org/sites/default/files/Pattern_13_d.svg){height="150px"}

Summary
-------

Use endurance objects such as *Plan*s to describe how an *Activity*
proceeds. They can be published more easily than specialised *Activity*
subclasses and can be reused.
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
[Pattern\_13\_a.svg](https://patterns.promsns.org/sites/default/files/Pattern_13_a.svg)]{.file}
:::

::: {.field-item .odd}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[Pattern\_13\_b.svg](https://patterns.promsns.org/sites/default/files/Pattern_13_b_0.svg)]{.file}
:::

::: {.field-item .even}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[Pattern\_13\_c.svg](https://patterns.promsns.org/sites/default/files/Pattern_13_c.svg)]{.file}
:::

::: {.field-item .odd}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[Pattern\_13\_d.svg](https://patterns.promsns.org/sites/default/files/Pattern_13_d_0.svg)]{.file}
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

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
::: {#node-101 .node .node-patterns .node-promoted .node-full .clearfix about="/pattern/12" typeof="sioc:Item foaf:Document"}
[]{.rdf-meta .element-hidden property="dc:title"
content="Associating metadata in documents with graph provenance"}[]{.rdf-meta
.element-hidden property="sioc:num_replies" content="0"
datatype="xsd:integer"}

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

Many organisations already contains systems that deliver metadata about
objects for which they now want to deliver standardised, graph-based
provenance information, perhaps using PROV. These metadata systems, such
as catalogues, sometimes have legacy methods for delivering provenance
or lineage, such as free text fields perhaps linked to the items as a
dc:source property. Sometimes, as per ISO19115-2 documents, structured
machine-readable provenance is given but it is not able to be directly
mapped to PROV.

Patterns
--------

### Antipattern: current document practice

The figure below shows the sort of arrangement people are familiar with
regarding document metadata and provenance. In the first part of the
figure, a generic metadata document is shown with a \"provenance field\"
in which structured or un-structored provenance (sometimes called
lineage) may be recorded. In the second part of the figure, a DCAT
metadata document with a free text dc:source an an ISO19115 metadata
document with a structured LI\_Lineage field are shown as examples.

This is now considered an antipattern for provenance or, at least, not
best practice. The reasons for this are that provenance, when recorded
within a document like this, cannot easily be machine read and elements
of it cannot be reused by other items without simply copying the
provenance completely. This will be both inefficient when large volumes
of provenance are recorded and unable to create a network of provenance
that can be used to traverse relationships between things.

![](https://patterns.promsns.org/sites/default/files/Pattern_12_a.svg){width="500px"}

There may well be good reasons to use document-based provenance but the
recommendation here is to, where possible, move to machine-readable,
standardised provenance using one of the three patterns described below.

### Pattern 12.1: PROV-AQ linking

The [PROV-AQ](https://www.w3.org/TR/prov-aq/) part of the PROV family of
documents (\"Access & Query\") specifies the use of a *has\_provenance*
property to indicate a relationship to a PROV-O compliant provenance
document. Additionally there is a *has\_query\_service* that can be used
to relate something to an undefined type of query service used to
deliver provenance. Pattern 12.1, shown in the figure below, recommends
using either of these two relationships to link a metadata document to
either a provenance document or a query service about the item the
metadata is for.

![](https://patterns.promsns.org/sites/default/files/Pattern_12_b.svg){width="500px"}

When *has\_provenance* is used, the target of the relationship can be
inferred to be a *prov:Bundle* object, which is a collection of
provenance information.

When *has\_query\_service* is used, the target may be a SPARQL service
or some other sort of service (perhaps a RESTful API) but it must return
PROV-O compliant information about the document metadata's object. The
service's own metadata, not the object's document metadata, should
describe what it is and how it functions.

### Pattern 12.2: linking directly with PROV-O relations

For Pattern 12.2, we treat the object which the document metadata is
about as a PROV-O object and use normal PROV-O relationships to link it
to other things, perhaps themselves described with document metadata but
not necessarily: either way, we then also treat as PROV-O objects. OWL
inferencing can then be used to understand what the PROV-O classes of
the objects are.

![](https://patterns.promsns.org/sites/default/files/Pattern_12_c.svg){height="700px"}

In the example shown in the figure above, *wasGeneratedBy* relationship
is used to indicate that the Dataset \"Gravity Map for the Bowen Basin\"
was generated by \"Survey 801\". Given that *wasGeneratedBy* has a
domain of an *Entity* and the range of an *Activity*, we can infer that
the Dataset is an Entity and the Survey is an Activity.

This pattern has the effect of encoding single subject predicate object
relationships or \"triples\" in legacy catalogues which when they are
all extracted from the legacy system can be interpreted as a graph.

It may not always be possible to deliver PROV-O properties in legacy
metadata systems. One solutions to this is given in Pattern 12.3.

### Pattern 12.3: linking with other properties interpretable as PROV-O

It\'s not always possible to link objects using PROV-O relationships.
Sometimes, legacy systems don\'t allow for relationships according to
models other than their own. In these circumstances we use Pattern 12.3
where objects with document metadata are conceptually mapped to PROV-O
class types and then relationships between them or other objects are
described using domain-specific semantics that are then mapped to PROV-O
properties.

A combination of this approach and Pattern 12.3 can be used whereby only
domain-specific properties are mapped. If this is done, only properties
with single-class domain & range values can be used to ensure there is
no abiguity regarding the object's representations in PROV-O (e.g.
Object X *wasAttributedTo* Object Y is understandable only with Object X
as an Entity and Object Y as an Agent due to *wasAttributedTo*'s domains
and ranges. For Object X *wasInfluencedBy* Object Y, no specific
indication of PROV-O classes for Object & or Y is given since
*wasInfluencedBy* has multiple PROV-O class domain & range values.

It is not recommended to map classes only as there are multiple possible
PROV-O relationships between objects of particular classes.

In the figure below, the generic case for this pattern is shown at the
top. Below it is shown an example of a mapping whereby an
ISO19115-compliant catalogue is used to record a relationship between a
\"Dataset X\" & \"Dataset Y\". The relationship is one of
\"derivedFrom\" which is an association type code [published by
Geoscience Australia](http://pid.geoscience.gov.au/def/schema/ga/)
specifically to indicate a *wasDerivedFrom* relationship.

![](https://patterns.promsns.org/sites/default/files/Pattern_12_d.svg){height="700px"}

Summary
-------

Do not use document-based metadata fields, such as Dublin Core\'s
dc:source or ISO19115\'s LI\_Lineage.

Use a method to link objects or documents that is recommended in PROV-AQ
or that can be interpreted as PROV-O.
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
[Pattern\_12\_a.svg](https://patterns.promsns.org/sites/default/files/Pattern_12_a_0.svg)]{.file}
:::

::: {.field-item .odd}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[Pattern\_12\_b.svg](https://patterns.promsns.org/sites/default/files/Pattern_12_b_0.svg)]{.file}
:::

::: {.field-item .even}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[Pattern\_12\_c.svg](https://patterns.promsns.org/sites/default/files/Pattern_12_c_0.svg)]{.file}
:::

::: {.field-item .odd}
[![File](/modules/file/icons/image-x-generic.png "image/svg+xml"){.file-icon}
[Pattern\_12\_d.svg](https://patterns.promsns.org/sites/default/files/Pattern_12_d_0.svg)]{.file}
:::
:::
:::

::: {.field .field-name-field-related-use-case .field-type-node-reference .field-label-above}
::: {.field-label}
Related Use Case: 
:::

::: {.field-items}
::: {.field-item .even}
[Click through the provenance of a registered item and
back](/usecase/22)
:::

::: {.field-item .odd}
[Record standards-compliant provenance for datasets in a legacy data
catalogue](/usecase/39)
:::
:::
:::

::: {.field .field-name-field-implementations .field-type-node-reference .field-label-above}
::: {.field-label}
Implementations: 
:::

::: {.field-items}
::: {.field-item .even}
[Geoscience Australia\'s metadata catalogue](/implementation/38)
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

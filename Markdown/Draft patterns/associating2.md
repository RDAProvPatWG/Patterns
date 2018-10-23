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
::: {#node-100 .node .node-patterns .node-promoted .node-full .clearfix about="/content/associating-iso19115-1-items-provenance-query-service-2" typeof="sioc:Item foaf:Document"}
[]{.rdf-meta .element-hidden property="dc:title"
content="Associating ISO19115-1 items with a provenance query service #2"}[]{.rdf-meta
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

This pattern is a sibling of [Pattern
25](http://patterns.promsns.org/pattern/25) and is another way to link
datasets described with ISO19115-1 records to provenance query services.

Unlike Pattern 25 in which a provenance query service is described, this
pattern requires that a catalogue record for the provenance query
service is created and then the record for the dataset is associated
with that. This allows for very detailed service information to be
related in the record for the service, rather than endpoints and
examples needing to be given in the dataset\'s record, as per Pattern
25.

This pattern is similar to the regular method used by publishers of
datasets and web services via ISO19115-1 catalogues where the Service is
indicated as *operatesOn* one or more Dataset records.

Implementation
--------------

![image of the
pattern](http://patterns.promsns.org/sites/default/files/Pattern_26.svg)

### In PROV terms

What we are doing is treating the metadata record of the Dataset as a
PROV-O object (an *Entity* if a dataset but could be another class of
object, depending on the object\'s type and role) and the metadata
record for the Service as an *Entity* record as it describes the Service
as a *thing*.

### Service record

Whatever form of provenance query service is implemented, it should be
listed in the ISO19115-1 catalogue by having a metadata record created
for it. This record should indicate that it is for a (web) service with
its *ScopeCode* set to `Service`.

### Datasets/Service linking

The Dataset which the provenance query service is for should then have
the following linkage made to indicate the provenance query service:


    <mdb:identificationInfo>
      <mri:MD_DataIdentification>
        <mri:associatedResource>
          <mri:MD_AssociatedResource xlink:title="Provenance Query Service" uuidref="{SERVICE_RECORD_UUID}">
            <mri:associationType>
              <mri:DS_AssociationTypeCode codeList="http://pid.geoscience.gov.au/def/schema/ga/ISO19115-3/codelists.xml#DS_AssociationTypeCode" codeListValue="provenanceQueryService">
                provenanceQueryService
              </DS_AssociationTypeCode>
            </mri:associationType>
          </mri:MD_AssociatedResource>
        </mri:associatedResource>
      </mri:MD_DataIdentification>
    </mdb:identificationInfo>

The logic here is that the Associated Resource is indicated by an Xlink
reference to its UUID only, with a title \"Provenance Query Service\"
just for readability and that the semantic association of the Dataset to
the service is indicated via the `AssociationTypeCode` which uses the
code list value of `provenanceQueryService`. This term is an extension
to the ISO19115-1\'s `DS_AssociationTypeCode` codelist published by
Geoscience Australia at
<http://pid.geoscience.gov.au/def/schema/ga/ISO19115-3/codelists.xml>.
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
[Pattern\_26.svg](https://patterns.promsns.org/sites/default/files/Pattern_26_0.svg)]{.file}
:::
:::
:::

::: {.field .field-name-field-broader-pattern .field-type-node-reference .field-label-above}
::: {.field-label}
Broader Pattern: 
:::

::: {.field-items}
::: {.field-item .even}
[Associating metadata in documents with graph provenance](/pattern/12)
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

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
::: {#node-99 .node .node-patterns .node-promoted .node-full .clearfix about="/content/associating-iso19115-1-items-provenance-query-service" typeof="sioc:Item foaf:Document"}
[]{.rdf-meta .element-hidden property="dc:title"
content="Associating ISO19115-1 items with a provenance query service"}[]{.rdf-meta
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
Every Bleys
:::
:::
:::

::: {.field .field-name-body .field-type-text-with-summary .field-label-hidden}
::: {.field-items}
::: {.field-item .even property="content:encoded"}
Introduction
------------

Organisations wishing to associate items in an ISO19115-1-conformant
catalogue with graph-based provenance delivered by a provenance query
service (likely a SPARQL service) may wish to make the link to that
service as visible as possible to people used to the ISO19115-1 norms.
Since ISO19115-1 typically uses the *Lineage* field for structured or
un-structured lineage information (provenance), this pattern suggests
making that link to the provenance query service in that field.

Prerequisite
------------

PROV DM in OWL ontology form ([PROV-O](https://www.w3.org/TR/prov-o/))
and SPARQL services require the identification of provenance objects
using [HTTP
URIs](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier). For
this reason, any object catalogued according to ISO19115-1 wanting to
link to a provenance query service as described here must be able to be
referred to by URI. Some ISO19115-1-compliant catalogues use URIs but
some only use UUIDs and do not provide persistent URIs base on those
UUIDs. An effort must be made to establish persistent URIs using those
UUIDs before integration with a provenance query service.

Implementation
--------------

This pattern is a specialisation of [Pattern
12.1](http://patterns.promsns.org/pattern/12). It suggests placing a
*has\_query\_service* link, as [PROV-AQ](https://www.w3.org/TR/prov-aq/)
calls it, in the *LI\_Lineage* field in a manner conformant with
ISO19115-1.

![Pattern 25
diagram](http://patterns.promsns.org/sites/default/files/Pattern_25.svg#overlay-context=pattern/25)

### In PROV terms

Using this method, we can work out that the query service itself is a
PROV Entity (when described) and an Agent (when performing actions like
causing Entities to be generated) but we can\'t say anything, in PROV
terms, about the item linking to the query service. It could be any
class of PROV object since any object may have provenance about it made
available by a query service. Having said that, it is likely to be an
Entity as ISO19115-1 catalogues tend to store information about sorts of
Entities such as Datasets or Images.

### ISO19115-1 Structure

The suggested structure is for the *resourceLineage* field of a metadata
document to contain a *LI\_Lineage* element containing a *LI\_Source*
which, in turn, cites an *CI\_OnlineResource* which is described by a
*name*, *function*, *linkage*, *protocol* & *protocolRequest*. Note that
ISO191151 documents may contain multiple *LI\_Lineage* objects within a
*resourceLineage* field so that a reference to a provenance query
service may be made alongside written statements of provenance, which
are the current usage norm, or other structured lineage.

The specific elements that should be used to communicate that the
metadata document is linking to a query service are described here:

-   **CI\_Citation.title** - compulsory for any CI\_Citation use. Should
    indicate a well-known name for the thing cited - the query service.
    Could be a phrase similar to \"Organisation Z\'s Provenance Query
    Service\".
-   **CI\_OnlineResource.name** - optional. Likely a something similar
    to the citation title above.
-   **CI\_OnlineResource.function** - required. The code term
    provenanceQueryService should be used.\
    This term is available in the Geoscience Australia codelist
    extension to ISO19115-1\'s *CI\_OnlineFunctionTypeCode* code list.
-   **CI\_OnlineResource.linkage** - the URI to the endpoint of the
    query service
-   **CI\_OnlineResource.protocol** - required. While ISO19115-1 treats
    this field as free text, the widely-used IDO19115-1 catalogue tool
    GeoNetwork implements a code list for it in its [ISO19115-1
    protocols vocabulary](https://vocabs.ands.org.au/protocol-type).
    Geosciecne Australia includes a term to indicate SPARQL services
    \"HTTP-SPARQL\" and this should be used in the case of a SPARQL
    service.
-   **CI\_OnlineResource.protocolRequest** - optional. An example
    request. The most basic SPARQL query that could be used to find
    information about a resource is a *DESCRIBE* query which can be
    lodged over HTTP via a GET request. This field should give an
    example of that, or another query service\'s most basic query. For a
    SPARQL service, it would also need to indicate how to identify the
    resource being queried for which is the resource the ISO metadata is
    describing. In the SPARQL case, the query would be
    `DESCRIBE <resource>;` and if the resource was identifiable via a
    URI, perhaps <http://example.com/dataset/x>, then it would be
    `DESCRIBE <http://example.com/dataset/x>;`. The full information for
    this filed then would be that query as a provenance service request
    action and would just be an HTTP GET link. See the example below.

<!-- -->


    <mdb:resourceLineage>
      <mrl:LI_Lineage>
        <mrl:LI_Source>
          <mrl:sourceCitation>
            <cit:CI_Citation>
              <cit:title>
                <gco:CharacterString>{SERVICE_NAME}</gco:CharacterString>
              </cit:title>
              <cit:onlineResource>
                <mcc:CI_OnlineResource>
                <cit:name>
                  <gco:CharacterString>{SERVICE_NAME}</CharacterString>
                </cit:name>
                <cit:function>
                  <cit:CI_OnLineFunctionCode codeList="codeListLocation#CI_OnLineFunctionCode" codeListValue="provenanceQueryService"/>
                </cit:function>
                <cit:linkage>
                  <gco:CharacterString>{ENDPOINT_URI}</gco:CharacterString>
                </cit:linkage>
                <cit:protocol>
                  <gco:CharacterString>{PROTOCOL}</gco:CharacterString>
                </cit:protocol>
                <cit:protocolRequest>
                  <gco:CharacterString>{REQUEST_EXAMPLE}</gco:CharacterString>
                </cit:protocolRequest>
                </mcc:CI_OnlineResource>
              </cit:onlineResource>
            </cit:CI_Citation>
          <mrl:sourceCitation>
        </mrl:LI_Source>
      <mrl:LI_Lineage>
    </mdb:resourceLineage>

Example
-------

For a Dataset X with a SPARQL query service at
<http://location.com/sparql>, the following XML might be used:


    <mdb:resourceLineage>
      <mrl:LI_Lineage>
        <mrl:LI_Source>
          <mrl:sourceCitation>
            <cit:CI_Citation>
              <cit:title>
                <gco:CharacterString>Provenance Query Service</gco:CharacterString>
              </cit:title>
              <cit:onlineResource>
                <mcc:CI_OnlineResource>
                <cit:name>
                  <gco:CharacterString>Corporation A's Provenance Finder</CharacterString>
                </cit:name>
                <cit:function>
                  <cit:CI_OnLineFunctionCode codeList="codeListLocation#CI_OnLineFunctionCode" codeListValue="provenanceQueryService"/>
                </cit:function>
                <cit:linkage>
                  <gco:CharacterString>http://location.com/sparql</gco:CharacterString>
                </cit:linkage>
                <cit:protocol>
                  <gco:CharacterString>HTTP-SPARQL</gco:CharacterString>
                </cit:protocol>
                <cit:protocolRequest>
                  <gco:CharacterString>
                    http://location.com/sparql?query=DESCRIBE%20%3Chttp%3A%2F%2Fexample.com%2Fdataset%2Fx%3E
                  </gco:CharacterString>
                </cit:protocolRequest>
                </mcc:CI_OnlineResource>
              </cit:onlineResource>
            </cit:CI_Citation>
          <mrl:sourceCitation>
        </mrl:LI_Source>
      <mrl:LI_Lineage>
    </mdb:resourceLineage>

The **CI\_OnlineResource.protocolRequest** value used in this example is
the basic SPARQL `DESCRIBE` query for the resource applied to the SPARQL
service in a GET request which is then a single link consisting of;

-   the base URI of the SPARQL service (as per the
    **CI\_OnlineResource.linkage** field): `http://location.com/sparql`
-   The SPARQL service standardised query parameter: `?query=`
-   The URL-encoded version of the query:
    `DESCRIBE%20%3Chttp%3A%2F%2Fexample.com%2Fdataset%2Fx%3E` for the
    query `DESCRIBE <http://example.com/dataset/x>;`
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
[Pattern\_25.svg](https://patterns.promsns.org/sites/default/files/Pattern_25_0.svg)]{.file}
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

::: {#comments .comment-wrapper}
Add new comment {#add-new-comment .title .comment-form}
---------------

<div>

::: {#edit-author--2 .form-item .form-type-item}
Your name [ddubin]{.username lang="" about="/user/ddubin"
typeof="sioc:UserAccount" property="foaf:name" datatype=""}
:::

::: {.form-item .form-type-textfield .form-item-subject}
Subject
:::

::: {#edit-comment-body .field-type-text-long .field-name-comment-body .field-widget-text-textarea .form-wrapper}
::: {#comment-body-add-more-wrapper}
::: {.text-format-wrapper}
::: {.form-item .form-type-textarea .form-item-comment-body-und-0-value}
Comment [\*]{.form-required title="This field is required."}

::: {.form-textarea-wrapper .resizable}
:::
:::

::: {.fieldset-wrapper}
::: {#edit-comment-body-und-0-format-help .filter-help .form-wrapper}
[More information about text formats](/filter/tips)
:::

::: {.form-item .form-type-select .form-item-comment-body-und-0-format}
Text format MarkdownFiltered HTMLPlain text
:::

::: {#edit-comment-body-und-0-format-guidelines .filter-guidelines .form-wrapper}
::: {.filter-guidelines-item .filter-guidelines-markdown}
### Markdown

-   Quick Tips:
    -   Two or more spaces at a line\'s end = Line break
    -   Double returns = Paragraph
    -   \*Single asterisks\* or \_single underscores\_ = *Emphasis*
    -   \*\*Double\*\* or \_\_double\_\_ = **Strong**
    -   This is \[a link\](http://the.link.example.com \"The optional
        title text\")

    For complete details on the Markdown syntax, see the [Markdown
    documentation](http://daringfireball.net/projects/markdown/syntax)
    and [Markdown Extra
    documentation](http://michelf.com/projects/php-markdown/extra/) for
    tables, footnotes, and more.
:::

::: {.filter-guidelines-item .filter-guidelines-filtered_html}
### Filtered HTML

-   Web page addresses and e-mail addresses turn into links
    automatically.
-   Allowed HTML tags: \<a\> \<em\> \<strong\> \<cite\> \<blockquote\>
    \<code\> \<ul\> \<ol\> \<li\> \<dl\> \<dt\> \<dd\>
-   Lines and paragraphs break automatically.
:::

::: {.filter-guidelines-item .filter-guidelines-plain_text}
### Plain text

-   No HTML tags allowed.
-   Web page addresses and e-mail addresses turn into links
    automatically.
-   Lines and paragraphs break automatically.
:::
:::
:::
:::
:::
:::

[CAPTCHA]{.fieldset-legend}

::: {.fieldset-wrapper}
::: {.fieldset-description}
This question is for testing whether or not you are a human visitor and
to prevent automated spam submissions.
:::

![Image
CAPTCHA](/image_captcha?sid=56880&ts=1540337365 "Image CAPTCHA"){width="180"
height="60"}

::: {.form-item .form-type-textfield .form-item-captcha-response}
What code is in the image? [\*]{.form-required
title="This field is required."}

::: {.description}
Enter the characters shown in the image.
:::
:::
:::

::: {#edit-actions .form-actions .form-wrapper}
:::

</div>
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

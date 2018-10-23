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
::: {#node-122 .node .node-patterns .node-promoted .node-full .clearfix about="/pattern/generating-citations-provenance-incomplete" typeof="sioc:Item foaf:Document"}
[]{.rdf-meta .element-hidden property="dc:title"
content="Generating citations from provenance - INCOMPLETE"}[]{.rdf-meta
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

Citing documents, datasets or other things is an inherently
provenance-related task given that information in a reference, such as
an item\'s creator or date of publication, are often provenance facts
about it. Additionally, provenance graphs may contain information
valuable for citation that are not associated directly with the object
cited but with objects related to it or perhaps its use.

This pattern relates a methodology for determining how to cite objects
and then a methodology for generating reference text from provenance
information.

Class-based determination of citation requirements
--------------------------------------------------

The first step to generating a sensible citation for an object is to
determine the object\'s class. This is because the class of the object
will determine what elements of a citation are necessary in order to be
useful. For example, a static object such as a book or a dataset can be
cited as is commonly done so, but objects that are subject to change,
such as an internet articles, will need an access date related in order
to provide information about the state of the object at the time cited.
Consider a more specialised object, a software code repository. This
will need both a citation time indicator (or a software \"commit\"
reference which provides information about a particular repository
state) and also a reference to the \"branch\" of the repository used.
Branches are an element unique to software version control systems used
in repositories.

If information about the use of an object is recorded in a provenance
graph, then, regardless of type, the URI of the Named Individual (the
object) in question can be used to refer to it. Details from the
provenance graph can then supply the particular citation elements.

Citation/reference format background
------------------------------------

Academic literature-style citations usually have a link within text to a
formatted reference, e.g.:

"... according to Car (2016)."

Car, N.J., Leveraging provenance in citation. In J.Something, 18 (2)
152-167, DOI:10.123/abcdef987

There are many reference data models (and resulting templates and
formatting) for references but, for the purposes of this patterning, we
will just use a simplified AAAS citation template, used by the example
above, which, for a journal article citation, we give as:

{AUTHOR}\[, {AUTHOR}\], {TITLE}. {JOURNAL} {JOURNAL\_NUMBER}\[,
({JOURNAL\_VOLUME})\]\[, {PAGE\_RANGE}\] ({YEAR}).

For a book, we give the following simplified AAAS template:

{AUTHOR}\[, {AUTHOR}\], {TITLE} ({PUBLISHER\_NAME},
{PUBLISHER\_LOCATION}\[, ed. {EDITION\_NUMBER},\] {YEAR})\[, pp.
{PAGE\_RANGE}\].

This renderes examples such as:

M. Lister, Fundamentals of Operating Systems (Springer-Verlag, New York,
ed. 3, 1984), pp. 7-11.

All of the elements in a formatted reference, regardless of the cited
object type, are elements that can be described in the provenace of the
cited object and, specifically, in PROV-O. Therefore, we can generate
formatted reference text from provenance.

In order to effectively use provenance in citations, coginsance of both
the (PROV-O) class of object cited and the purpose of the citation must
be taken.

Provenance citation: see Samples API generation template Reverese case:
citation provenance: what can we infer?

ISOz39.29 -- bibliographic reference standard
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
CAPTCHA](/image_captcha?sid=56881&ts=1540337594 "Image CAPTCHA"){width="180"
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

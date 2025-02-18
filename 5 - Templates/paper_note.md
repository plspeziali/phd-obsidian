---
%% cssclass: research-note %%

{% if title %}
title: "{{title}}"{% endif %}
{% if publicationTitle %}
publication: "{{publicationTitle}}"
{% endif %}

type: "paper-note"

{% if date %}
year: {{date | format("YYYY")}}
{% endif %}

paper type: "{{itemType}}"

{% for type, creators in creators | groupby("creatorType") -%}{% if loop.first %}{% endif %}{{type | replace("interviewee", "author") | replace("director", "author") | replace("presenter", "author") | replace("podcaster", "author") | replace("programmer", "author") | replace("cartographer", "author") | replace("inventor", "author") | replace("sponsor", "author")  | replace("performer", "author") | replace("artist", "author")}}: "{%- for creator in creators -%}{%- if creator.name %}{{creator.name}}{%- else %}{{creator.lastName}}, {{creator.firstName}}{%- endif %}{% if not loop.last %}; {% endif %}{% endfor %}"{% if not loop.last %}
{% endif %}{%- endfor %}

{% if abstractNote %}
abstract: "{{abstractNote}}"
{% endif %}

{% if archive %}
archive: "{{archive}}"{% endif %}{% if archiveLocation %}
archive-location: "{{archiveLocation}}"{% endif %}
citekey: {{citekey}}

{% if uri %}
URI: {{desktopURI}}
{% endif %}

{% if collections.length > 0 %}
Projects: {% for c in collections -%}
{{c.name}}; {% endfor %}
{% endif %}

{% if tags.length > 0 %}
Tags: {% for t in tags -%}
{{t.tag}} {% endfor %}
{% endif %}
---
# {% if title %}{{title}}{% endif %}

> [!Cite]
> {{bibliography}}

---
## Summary
{% persist "summary" %}
{% endpersist %}

## Key Contributions
{% persist "key contributions" %}
{% endpersist %}

## Relevance to Projects
{% if collections.length > 0 -%}
{% for c in collections -%}
- [{{c.name}}]({{c.name}}.md)  
{% endfor %}{% endif %}

## Annotations
These are automatically sourced from Zotero.{% macro calloutHeader(a) -%}{%- if a.color == "#ffd400" -%}
>[!quote] Quote
>{{a.annotatedText}} [(p. {{a.pageLabel}})](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}}&annotation={{a.id}})
>{%- endif -%}

{%- if a.color == "#ff6666" -%}
>[!error] Important/Limitation
>{{a.annotatedText}} [(p. {{a.pageLabel}})](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}}&annotation={{a.id}})
{%- endif -%}

{%- if a.color == "#5fb236" -%}
>[!check] Contribution/Claim
>{{a.annotatedText}} [(p. {{a.pageLabel}})](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}}&annotation={{a.id}}){%- endif -%}

{%- if a.color == "#2ea8e5" -%}
>[!seealso] Related Work
>{{a.annotatedText}} [(p. {{a.pageLabel}})](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}}&annotation={{a.id}})
{%- endif -%}

{%- if a.color == "#a28ae5" -%}
Undefined - Purple
{%- endif -%}

{%- if a.color == "#e56eee" -%}
>[!example] Example
>{{a.annotatedText}} [(p. {{a.pageLabel}})](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}}&annotation={{a.id}})
>{%- endif -%}
{%- endmacro -%}

{% if annotations.length > 0 %}
{% set annotations = annotations | sort %}

{%- for annotation in annotations %}

{{calloutHeader(annotation)}}
{%- endfor %}
{% endif %}
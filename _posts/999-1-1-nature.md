---
layout: post
title: "TERMÉSZET / NATURE"
published: true
---

* TOC
{:toc}

{% assign kingdom = "" %}
{% assign type = "" %}

{% for row in site.data.nature %}

<!-- kingdom -->
{% if row["_kingdom] != kingdom %}
{% assign kingdom = row["_kingdom"] %}

## {{ kingdom }}

{% if kingdom == "Plantae" %}
🇺🇸 plant kingdom / 🇭🇺 növények országa
{% endif %}
{% endif %}

<!-- type -->
{% if row["type] != type %}
{% assign type = row["type"] %}

### {{ type }}

{% if type == "Lignosae" %}
🇺🇸 woody plants / 🇭🇺 fás szárúak
{% else if type == "Herbaceae" %}
🇺🇸 herbaceous plants / 🇭🇺 lágyszárúak
{% endif %}
{% endif %}

<!-- details -->
#### {{ row["lat"] }}

🇺🇸 {{ row["eng"] }} / 🇭🇺 {{ row["hun"] }}

([Source]({{ row["source"] }}){:target="_blank" rel="noopener noreferrer"}) {{ row["notes"] }}

{% assign urls = row["urls"] | split: "|" %}

{% for url in urls %}
<!-- ![{{ row["lat"] }}]({{ url }}) -->
{{ url }}
{% endfor %}

{% endfor %}

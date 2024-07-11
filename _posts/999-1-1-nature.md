---
layout: post
title: "TERMÉSZET / NATURE"
published: true
---

* TOC
{:toc}

{% assign kingdom = "" %}
{% assign type = "" %}
{% assign sortedRows = site.data.nature | sort: 'eng' | sort: 'lat' | sort: 'type' | sort: '_kingdom' %}

{% for row in sortedRows %}
{% assign type = "" %}

<!-- kingdom -->
{% if row["_kingdom"] != kingdom %}
{% assign kingdom = row["_kingdom"] %}
{% assign type = "" %}

## {{ kingdom }}

{% if kingdom == "Plantae" %}
🇺🇸 plant kingdom / 🇭🇺 növények országa
{% endif %}
{% if kingdom == "Animalia" %}
🇺🇸 animal kingdom / 🇭🇺 állatok országa
{% endif %}
{% if kingdom == "Ceterus" %}
🇺🇸 other / 🇭🇺 egyéb
{% endif %}
{% endif %}

<!-- type -->
{% if row["type"] != type %}
{% assign type = row["type"] %}

### {{ type }}

{% if type == "Lignosae" %}
🇺🇸 woody plants / 🇭🇺 fás szárúak
{% endif %}
{% if type == "Herbaceaes" %}
🇺🇸 herbaceous plants / 🇭🇺 lágyszárúak
{% endif %}
{% if type == "Insecta" %}
🇺🇸 insects / 🇭🇺 rovarok
{% endif %}
{% if type == "Mineralia" %}
🇺🇸 minerals / 🇭🇺 ásványok
{% endif %}
{% endif %}

<!-- name -->
{% if row["lat"] != null and row["lat"] != "" %}
{% assign name = row["lat"] %}
{% else %}
{% assign name = row["eng"] | capitalize %}
{% endif %}

#### {{ name }}

🇺🇸 {{ row["eng"] }} / 🇭🇺 {{ row["hun"] }}

([Source]({{ row["source"] }}){:target="_blank" rel="noopener noreferrer"}) {{ row["notes"] }}

{% assign urls = row["urls"] | split: "|" %}

{% for url in urls %}
![{{ row["lat"] }}]({{ url }})
<!-- {{ url }} -->
{% endfor %}

{% endfor %}

---
layout: post
title: "TERMÉSZET / NATURE"
published: true
---

- TOC
  {:toc}

{% assign kingdoms = 'Animalia,Plantae,Ceterus' | split: ',' %}
{% for kingdom in kingdoms %}
{% assign type = "" %}

{% if kingdom == "Plantae" %}
{% assign kingdom_name = "Plants / Növények %}

<!-- 🇺🇸 plant kingdom / 🇭🇺 növények országa -->

{% endif %}
{% if kingdom == "Animalia" %}
{% assign kingdom_name = "Animals / Állatok %}

<!-- 🇺🇸 animal kingdom / 🇭🇺 állatok országa -->

{% endif %}
{% if kingdom == "Ceterus" %}
{% assign kingdom_name = "Other / Egyéb %}

<!-- 🇺🇸 other / 🇭🇺 egyéb -->

{% endif %}

## {{ kingdom_name }}

{% assign sortedRows = site.data.nature | sort: 'eng' | sort: 'lat' | sort: 'type' | sort: '_kingdom' %}

{% for row in sortedRows %}
{% if row["_kingdom"] != kingdom %}
{% continue %}
{% endif %}

<!-- type -->

{% if row["type"] != type %}
{% if row["type"] == "Lignosae" %}
{% assign type = "Woody plants / Fás szárúak %}

<!-- 🇺🇸 woody plants / 🇭🇺 fás szárúak -->

{% endif %}
{% if row["type"] == "Herbaceaes" %}
{% assign type = "Herbaceous plants / Lágyszárúak %}

<!-- 🇺🇸 herbaceous plants / 🇭🇺 lágyszárúak -->

{% endif %}
{% if row["type"] == "Insecta" %}
{% assign type = "Insects / Rovarok %}

<!-- 🇺🇸 insects / 🇭🇺 rovarok -->

{% endif %}
{% if row["type"] == "Mineralia" %}
{% assign type = "Minerals / Ásványok %}

<!-- 🇺🇸 minerals / 🇭🇺 ásványok -->

{% endif %}
{% endif %}

### {{ type }}

<!-- name -->

{% if row["lat"] != null and row["lat"] != "" %}
{% assign name = row["lat"] %}

#### {{ row["eng"] }} / {{ row["hun"] }} ({{ row["lat"] }})

{% else %}

#### {{ row["eng"] }} / {{ row["hun"] }}

{% endif %}

<!-- 🇺🇸 {{ row["eng"] }} / 🇭🇺 {{ row["hun"] }} -->

[[Wikipedia]({{ row["source"] }}){:target="\_blank" rel="noopener noreferrer"}] {{ row["notes"] }}

{% assign urls = row["urls"] | split: "|" %}

{% for url in urls %}
![{{ row["lat"] }}]({{ url }}){:height="100px"}

<!-- {{ url }} -->

{% endfor %}
{% endfor %}
{% endfor %}

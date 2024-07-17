---
layout: post
title: "TERMÉSZET / NATURE"
published: true
---

* TOC
{:toc}

{% assign kingdoms = 'Animalia,Plantae,Ceterus' | split: ',' %}
{% for kingdom in kingdoms %}
{% assign type = "" %}

{% if kingdom == "Plantae" %}

## Plants | Növények

{% endif %}
{% if kingdom == "Animalia" %}

## Animals | Állatok

{% endif %}
{% if kingdom == "Ceterus" %}

## Other | Egyéb

{% endif %}

{% assign sortedRows = site.data.nature | sort: 'eng' | sort: 'type' | sort: '_kingdom' %}

{% for row in sortedRows %}
{% if row["_kingdom"] != kingdom %}
{% continue %}
{% endif %}

<!-- type -->

{% if row["type"] != type %}
{% assign type = row["type"] %}
{% if type == "Lignosae" %}

### Woody plants | Fás szárúak

{% endif %}
{% if type == "Herbaceaes" %}

### Herbaceous plants | Lágyszárúak

{% endif %}
{% if type == "Insecta" %}

### Insects | Rovarok

{% endif %}
{% if type == "Mineralia" %}

### Minerals | Ásványok

{% endif %}
{% endif %}

<!-- name -->

{% if row["lat"] != null and row["lat"] != "" %}
{% assign name = row["lat"] %}

#### {{ row["eng"] }} | {{ row["hun"] }} ({{ row["lat"] }})

{% else %}

#### {{ row["eng"] }} | {{ row["hun"] }}

{% endif %}

[[Wikipedia]({{ row["source"] }}){:target="\_blank" rel="noopener noreferrer"}] {{ row["notes"] }}

{% assign urls = row["urls"] | split: "|" %}

{% for url in urls %}
![{{ row["lat"] }}]({{ url }}){:height="100px"}

<!-- {{ url }} -->

{% endfor %}
{% endfor %}
{% endfor %}

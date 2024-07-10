---
layout: post
title: "TERMÉSZET / NATURE"
published: true
---

* TOC
{:toc}

{% for row in site.data.nature %}

## {{ row["lat"] }}

🇺🇸: {{ row["eng"] }} / 🇭🇺: {{ row["hun"] }}

([Source]({{ row["source"] }}){:target="_blank" rel="noopener noreferrer"}) {{ row["notes"] }}

{% assign urls  = row["urls"] | split: "|" %}

{% for url in urls %}
![{{ row["lat"] }}]({{ url }})
{% endfor %}

Test

{% endfor %}

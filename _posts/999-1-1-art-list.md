---
layout: post
title: "FESTMÉNYEK / LIST OF ARTS"
published: true
---

* TOC
{:toc}

{% for row in site.data.arts %}

## {{ row["artist"] }}: {{ row["title"] }}, {{ row["year"] }}

([Source]({{ row["source"] }}){:target="_blank" rel="noopener noreferrer"}) {{ row["notes"] }}

![{{ row["title"] }} by {{ row["artist"] }}]({{ row["url"] }})

{% endfor %}

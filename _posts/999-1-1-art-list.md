---
layout: post
title: "FESTMÉNYEK / LIST OF ARTS"
published: true
---

* TOC
{:toc}

{% for row in site.data.arts %}

## {{ row["_artist"] }}: {{ row["title"] }}, {{ row["year"] }}

([Source]({{ row["source"] }}){:target="_blank" rel="noopener noreferrer"}) {{ row["notes"] }}

![{{ row["title"] }} by {{ row["_artist"] }}]({{ row["url"] }})

{% endfor %}

---
layout: post
title: "FESTMÉNYEK / LIST OF ARTS"
published: true
---

{% for row in site.data.arts %}

## {{ row["artist"] }}: {{ row["title"] }}, {{ row["year"] }}

{{ row["notes"] }}

[Source]({{ row["source"] }}){:target="_blank"}

![{{ row["title"] }} by {{ row["artist"] }}]({{ row["url"] }})

{% endfor %}
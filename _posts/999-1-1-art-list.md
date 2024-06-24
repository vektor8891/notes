---
layout: post
title: "FESTMÉNYEK / LIST OF ARTS"
published: true
---

{% for row in site.data.arts %}
<h2>{{ row["artist"] }}: {{ row["title"] }}, {{ row["year"] }}</h2>
<a href="{{ row["source"] }}" target="_blank">Source</a>
<img href="{{ row["url"] }}" target="_blank">
{% endfor %}
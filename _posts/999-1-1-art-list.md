---
layout: post
title: "FESTMÉNYEK / LIST OF ARTS"
published: true
---

{% for row in site.data.arts %}
<h2>{{ row["artist"] }}: {{ row["title"] }}, {{ row["year"] }}</h2>
<p><a href="{{ row["source"] }}" target="_blank">Source</a></p>
<p><img href="{{ row["url"] }}" alt="{{ row["title"] }} by {{ row["artist"] }}"></p>
{% endfor %}
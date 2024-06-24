---
layout: post
title: "FESTMÉNYEK / LIST OF ARTS"
published: true
---

{% for row in site.data.books %}
<p>{{ row[1]}}</p>
{% tablerow pair in row %}
    <p>{{ pair[1] }}</p>
{% endtablerow %}
{% endfor %}
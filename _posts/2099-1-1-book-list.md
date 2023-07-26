---
layout: post
title: "KÖNYVLISTA / LIST OF BOOKS"
published: true
---

<table>
  {% for row in site.data.books %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>
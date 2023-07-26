---
title: KÖNYVLISTA / LIST OF BOOKS
layout: post
---

&nbsp;

<table>
  {% for row in site.data.books %}
  {% if forloop.first %}
  <tr>
    <th><b>Szerző</b></th>
    <th><b>Cím</b></th>
  </tr>
  {% endif %}
  <tr>
    <td>{{ row["author"]}}</td>
    <td><a href="{{ row["url"]}}" target="_blank">{{ row["title"]}}</a> ({{ row["year"]}})</td>
  </tr>
  {% endfor %}
</table>

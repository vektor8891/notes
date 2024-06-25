---
layout: post
title: "FILMEK / MOVIES"
published: true
---

* TOC
{:toc}

{% for row in site.data.movies %}

## {{ row["title"] }} ({{ row["year"] }})

([Source]({{ row["source"] }}){:target="_blank" rel="noopener noreferrer"}) {{ row["notes"] }}

[![Watch the trailer](https://img.youtube.com/vi/{{ row["youtube-id"] }}/hqdefault.jpg)](https://youtu.be/{{ row["youtube-id"] }}){:target="_blank" rel="noopener noreferrer"}

{% endfor %}
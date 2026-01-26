---
title: "bab"
layout: default
---
<pre>---
title: "bab"
subtitle: "Diario <a href="/links/">QE</a>." 
---
{% assign meses = "Ene|Feb|Mar|Abr|May|Jun|Jul|Ago|Sep|Oct|Nov|Dic" | split: "|" %}
{% assign current_year = "" %}
{% for post in site.posts %}{% assign post_year = post.date | date: "%Y" %}{% if post_year != current_year %}{% if current_year != "" %}
{% endif %}{% assign current_year = post_year %}
# {{ post_year }}
{% endif %}{% assign mes_num = post.date | date: "%-m" | minus: 1 %}{{ post.date | date: "%d" }} {{ meses[mes_num] }}   <a href="{{ post.url }}">{{ post.title }}</a> <small style="color:#888">[<a href="/categories/{{ post.categories | first }}/" style="color:#888">{{ post.categories | first }}</a>]</small>
{% endfor %}

</pre>             
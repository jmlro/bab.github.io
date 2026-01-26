---
title: "bab"
layout: default
---
<pre>---
title: "bab"
subtitle: "Diario <a href="/links/">QE</a>." 
---

{% assign meses = "Ene|Feb|Mar|Abr|May|Jun|Jul|Ago|Sep|Oct|Nov|Dic" | split: "|" -%}
{% assign estaciones = "Invierno|Primavera|Verano|Otoño" | split: "|" -%}
{% assign current_year = "" -%}
{% assign current_season = "" -%}
{% assign first_post = true -%}
{% for post in site.posts -%}
{% assign post_year = post.date | date: "%Y" -%}
{% assign post_month = post.date | date: "%-m" | plus: 0 -%}
{% assign post_day = post.date | date: "%-d" | plus: 0 -%}
{% if post_month == 12 or post_month == 1 or post_month == 2 -%}
{% assign post_season = 0 -%}
{% elsif post_month == 3 and post_day < 21 -%}
{% assign post_season = 0 -%}
{% elsif post_month == 3 or post_month == 4 or post_month == 5 -%}
{% assign post_season = 1 -%}
{% elsif post_month == 6 and post_day < 21 -%}
{% assign post_season = 1 -%}
{% elsif post_month == 6 or post_month == 7 or post_month == 8 -%}
{% assign post_season = 2 -%}
{% elsif post_month == 9 and post_day < 23 -%}
{% assign post_season = 2 -%}
{% elsif post_month == 9 or post_month == 10 or post_month == 11 -%}
{% assign post_season = 3 -%}
{% elsif post_month == 12 and post_day < 21 -%}
{% assign post_season = 3 -%}
{% endif -%}
{% if post_year != current_year -%}
{% if current_year != "" -%}
---
{% endif -%}
{% if first_post -%}

{% assign first_post = false -%}
{% endif -%}
{% assign current_year = post_year -%}
{% assign current_season = "" -%}
# {{ post_year }}
{% endif -%}
{% if post_season != current_season -%}
{% assign current_season = post_season -%}
## {{ estaciones[post_season] }}
{% endif -%}
{% assign mes_num = post.date | date: "%-m" | minus: 1 -%}
{{ post.date | date: "%d" }} {{ meses[mes_num] }}   <a href="{{ post.url }}">{{ post.title }}</a> <small style="color:#888">[<a href="/categories/{{ post.categories | first }}/" style="color:#888">{{ post.categories | first }}</a>]</small>
{% endfor %}

</pre>             
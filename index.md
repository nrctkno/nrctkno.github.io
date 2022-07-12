---
title: {{ site.title }} - {{ site.description }}
---

<ul>
{% for cat in site.categories %}
    <li><a href="{{ cat.url }}">{{ cat|first }}</a></li>
{% endfor %}
</ul>

_________________________________________

{% for page in site.pages %}
    <a href="{{ page.url }}">{{ page.title }}</a>
{% endfor %}


---
title: {{ site.title }} - {{ site.description }}
---

<ul>
{% for cat in site.categories %}
  <li>
    <a href="{{ cat.url }}">{{ cat|first }}</a>
  </li>
{% endfor %}
</ul>

<articles>
  {% for post in site.posts %}
    <article>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p>{{ post.excerpt }}</p>
      <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%d/%m/%Y" }}</time>
    </article>
  {% endfor %}
</articles>

<hr/>

<footer>
{% for page in site.pages %}
  <a href="{{ page.url }}">{{ page.title }}</a>
{% endfor %}
</footer>
